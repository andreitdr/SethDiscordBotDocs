
### Definition

Namespace: DiscordBot
Assembly: DiscordBot
Source: StartupAction.cs

Defines a StartupAction with two parameters: the command and an `Action` that accepts an array of type `string`.

```cs
public StartupAction(string command, Action<string[]> runAction)  
{   
	this.Command = command;  
    this.RunAction = runAction;  
}
```

