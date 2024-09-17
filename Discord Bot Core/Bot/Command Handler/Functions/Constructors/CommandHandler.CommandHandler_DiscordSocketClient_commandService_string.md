
### Definition

Namespace: DiscordBotCore.Bot
Assembly: DiscordBotCore
Source: CommandHandler.cs

Creates a Command Handler based on the logged in user bot.

```cs
public CommandHandler(DiscordSocketClient client, CommandService commandService, string botPrefix)  
{  
    _Client         = client;  
    _CommandService = commandService;  
    _BotPrefix      = botPrefix;  
}
```


### Remarks

This constructor accepts 3 parameters:
- `DiscordSocketClient` - The Discord client after the user logged in
- `CommandService` - The command service. This is the container for all discord commands.
- `string` - The bot prefix that should be used when responding to normal (old fashioned commands)