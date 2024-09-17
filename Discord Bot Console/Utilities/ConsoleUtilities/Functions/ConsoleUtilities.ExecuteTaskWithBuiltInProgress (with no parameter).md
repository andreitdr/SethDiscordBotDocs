
### Definition
Namespace: DiscordBot.ConsoleUtilities
Assembly: DiscordBot
Source: ConsoleUtilities.cs



Executes a Task with built in progress bar control.

```cs
public static async Task ExecuteTaskWithBuiltInProgress(Func<IProgress<float>, Task> method, string taskMessage)
```
### Remarks

TaskMessage is a string that represents the custom message to be printed in front of the progress bar.
