### Definition

Namespace: DiscordBotCore.Bot
Assembly: DiscordBotCore
Source: CommandHandler.cs

This is the method that is executed whenever a slash command was called.

```cs
private Task Client_SlashCommandExecuted(SocketSlashCommand arg)  
{  
    try  
    {  
        var plugin = PluginLoader.SlashCommands.FirstOrDefault(p => p.Name == arg.Data.Name);  
  
        if (plugin is null)  
            throw new Exception("Failed to run command !");  
  
        if (arg.Channel is SocketDMChannel)  
            plugin.ExecuteDm(arg);  
        else plugin.ExecuteServer(arg);  
    }
    catch (Exception ex)  
    {
	    Application.Logger.LogException(ex, this);  
    }  
    return Task.CompletedTask;  
}
```


#Remarks-Missing