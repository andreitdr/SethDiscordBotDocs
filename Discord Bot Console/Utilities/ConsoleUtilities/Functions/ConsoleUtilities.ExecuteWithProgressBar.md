
### Definition
Namespace: DiscordBot.ConsoleUtilities
Assembly: DiscordBot
Source: ConsoleUtilities.cs


Executes a Task with built in progress bar control.

```cs
public static async Task<T> ExecuteWithProgressBar<T>(Task<T> function, string message)
```
### Remarks

Parameter `T` is the return type of the base function.
Message is the default message to be displayed. Please set it to `string.Empty` for an empty message

### Example

```cs
List<PluginOnlineInfo> data = await ConsoleUtilities.ExecuteWithProgressBar(Application.CurrentApplication.PluginManager.GetPluginsList(), "Reading remote database");
```

