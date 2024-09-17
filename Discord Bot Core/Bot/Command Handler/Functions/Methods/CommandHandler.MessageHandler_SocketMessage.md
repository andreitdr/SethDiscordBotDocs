### Definition

Namespace: DiscordBotCore.Bot
Assembly: DiscordBotCore
Source: CommandHandler.cs

This method is called whenever a message is written in any server where the bot is present and also when a DM is being written to the bot.

```cs
    private async Task MessageHandler(SocketMessage Message)
    {
        try
        {
            if (Message.Author.IsBot)
                return;

            if (Message as SocketUserMessage == null)
                return;

            var message = Message as SocketUserMessage;

            if (message is null)
                return;

            var argPos = 0;

            if (!message.Content.StartsWith(_BotPrefix) && !message.HasMentionPrefix(_Client.CurrentUser, ref argPos))
                return;

            var context = new SocketCommandContext(_Client, message);

            await _CommandService.ExecuteAsync(context, argPos, null);

            IDbCommand? plugin;
            var        cleanMessage = "";

            if (message.HasMentionPrefix(_Client.CurrentUser, ref argPos))
            {
                var mentionPrefix = "<@" + _Client.CurrentUser.Id + ">";

                plugin = PluginLoader.Commands!
                                     .FirstOrDefault(plug => plug.Command ==
                                                             message.Content.Substring(mentionPrefix.Length + 1)
                                                                    .Split(' ')[0] ||
                                                             plug.Aliases is not null &&
                                                             plug.Aliases.Contains(message.CleanContent
                                                                                          .Substring(mentionPrefix.Length + 1)
                                                                                          .Split(' ')[0]
                                                             )
                                     );

                cleanMessage = message.Content.Substring(mentionPrefix.Length + 1);
            }

            else
            {
                plugin = PluginLoader.Commands!
                                     .FirstOrDefault(p => p.Command ==
                                                          message.Content.Split(' ')[0].Substring(_BotPrefix.Length) ||
                                                          p.Aliases is not null &&
                                                          p.Aliases.Contains(
                                                              message.Content.Split(' ')[0]
                                                                     .Substring(_BotPrefix.Length)
                                                          )
                                     );
                cleanMessage = message.Content.Substring(_BotPrefix.Length);
            }

            if (plugin is null)
                return;

            if (plugin.RequireAdmin && !context.Message.Author.IsAdmin())
                return;

            var split = cleanMessage.Split(' ');

            string[]? argsClean = null;
            if (split.Length > 1)
                argsClean = string.Join(' ', split, 1, split.Length - 1).Split(' ');

            DbCommandExecutingArguments cmd = new(context, cleanMessage, split[0], argsClean);

            Application.Logger.Log(
                $"User ({context.User.Username}) from Guild \"{context.Guild.Name}\" executed command \"{cmd.CleanContent}\"",
                this,
                LogType.Info
            );

            if (context.Channel is SocketDMChannel)
                plugin.ExecuteDm(cmd);
            else plugin.ExecuteServer(cmd);
        }
        catch (Exception ex)
        {
            Application.Logger.LogException(ex, this);
        }
    }
```

### Remarks

#Remarks-Missing 