### Definition

Namespace: DiscordBot
Assembly: DiscordBot
Source: IStartupAction.cs

The base interface for defining a startup action.
This is used internally in Discord Bot Console.

```cs
internal interface IStartupAction  
{  
    string Command { get; init; }  
    Action<string[]> RunAction { get; init; }  
}
```
### Remarks
`Action<string[]>` is the action itself and it has an array of string as parameter.