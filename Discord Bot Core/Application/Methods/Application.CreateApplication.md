
### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs

This method is used to create and initialize an Application.
An application is responsible with everything a Discord Bot would ever need and its the bridge between plugins, modules and the internal Discord Bot.

```cs
public static async Task CreateApplication(Func<ModuleRequirement, Task>? moduleRequirementsSolver)
```

### Remarks
`moduleRequirementsSolver` is a Task that accepts a parameter type of `ModuleRequirement`.