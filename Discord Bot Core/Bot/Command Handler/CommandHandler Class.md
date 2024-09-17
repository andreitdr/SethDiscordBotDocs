### Definition

Namespace: DiscordBotCore.Bot
Assembly: DiscordBotCore
Source: CommandHandler.cs

This is an internal class that handles all type of commands.
This is the bridge between the Discord bot and the Discord client.

```cs
internal class CommandHandler
```

### Constructors

| Constructor                                                                                                                               | Description                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| [[CommandHandler.CommandHandler_DiscordSocketClient_commandService_string\|CommandHandler(DiscordSocketCommand, CommandService, string)]] | Creates a Command Handler based on the logged in user bot. |

### Members

| Member          | Member Type           | Member Access Specifier |
| --------------- | --------------------- | ----------------------- |
| _BotPrefix      | `string`              | `private readonly`      |
| _CommandService | `CommandService`      | `private readonly`      |
| _Client         | `DiscordSocketClient` | `private readonly`      |

### Methods

| Method                                                                                                             | Description                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| [[CommandHandler.InstallCommandAsync\|InstallCommandsAsync()]]                                                     | Initialize Command Handlers.                                                                                                               |
| [[CommandHandler.Client_SlashCommandExecuted_SocketSlashCommand\|Client_SlashCommandExecuted(SocketSlashCommand)]] | This is the method that is executed whenever a slash command was called.                                                                   |
| [[CommandHandler.MessageHandler_SocketMessage\|MessageHandler(SocketMessage)]]                                     | This method is called whenever a message is written in any server where the bot is present and also when a DM is being written to the bot. |
