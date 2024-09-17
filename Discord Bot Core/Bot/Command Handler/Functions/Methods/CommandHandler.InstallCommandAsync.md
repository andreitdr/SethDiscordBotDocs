
### Definition

Namespace: DiscordBotCore.Bot
Assembly: DiscordBotCore
Source: CommandHandler.cs

Initialize Command Handlers.

```cs
public async Task InstallCommandsAsync()  
{  
    _Client.MessageReceived      += MessageHandler;  
    _Client.SlashCommandExecuted += Client_SlashCommandExecuted;  
    await _CommandService.AddModulesAsync(Assembly.GetEntryAssembly(), null);  
}
```


### Remarks

This method is intended to be execute `asynchronous`.