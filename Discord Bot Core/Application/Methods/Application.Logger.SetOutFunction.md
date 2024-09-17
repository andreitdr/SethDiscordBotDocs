
### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs


This is a method that sets the output function to the extern logger.
After this method is called, the external logger will use the method that is sent as parameter to this function to log messages.

```cs
public static async void SetOutFunction(Action<string, LogType> outFunction)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["SetPrintFunction"], [outFunction]);  
}
```

#Items-missing 