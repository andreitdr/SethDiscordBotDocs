
### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs

This is a method to log messages in various ways.

```cs
public static async void Log(string message)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["BaseLog"], [message]);  
}
```

```cs
public static async void Log(string message, LogType logType, string format)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["LogWithTypeAndFormat"], [message, logType, format]);  
}
```

```cs
public static async void Log(string message, LogType logType)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["LogWithType"], [message, logType]);  
}
```

```cs
public static async void Log(string message, object sender)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["LogWithSender"], [message, sender]);  
}
```

```cs
public static async void Log(string message, object sender, LogType type)  
{  
    await CurrentApplication.ModuleManager.InvokeMethod(_LoggerModule.Value, _LoggerModule.Value.MethodMapping["LogWithTypeAndSender"], [message, sender, type]);  
}
```

#rewrite