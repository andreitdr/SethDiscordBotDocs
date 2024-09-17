
### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs


This method is used to log exceptions.

```cs
public static async void LogException(Exception ex, object sender, bool fullStackTrace = false)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["BaseLogException"], [ex, sender, fullStackTrace]);  
}
```

