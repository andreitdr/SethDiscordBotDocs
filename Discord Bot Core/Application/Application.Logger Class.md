
### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs

This is the logger class.
It is responsible to link all other plugins, as well as the main application, with the external logger (module).

```cs
public static class Logger
```

This class is inside [[Application Class]]

### Members

| Member        | Member Type    | Member Access Specifier | Default Value |
| ------------- | -------------- | ----------------------- | ------------- |
| _LoggerModule | `LoadedModule` | `internal static`       | `null`        |

### Methods

| Method                                                                                         | Description                                                  |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [[Application.Logger.LogException_Exception_object_bool\|LogException(Exception,object,bool)]] | This method is used to log exceptions.                       |
| [[Application.Logger.Log\|Log(string)]]                                                        | Log strings with the default `LogType`                       |
| [[Application.Logger.Log\|Log(string, LogType, string)]]                                       | Log strings by specifying the `LogType` and a custom format. |
| [[Application.Logger.Log\|Log(string, LogType)]]                                               | Log string by specifying the `LogType`                       |
| [[Application.Logger.Log\|Log(string, object)]]                                                | Log string by specifying the sender object                   |
| [[Application.Logger.Log\|Log(string,object,LogType)]]                                         | Log string by specifying the sender and the `LogType`        |
| [[Application.Logger.SetOutFunction\|SetOutFunction(Action<string,LogType>)]]                  | Set the output function for the external logger              |
