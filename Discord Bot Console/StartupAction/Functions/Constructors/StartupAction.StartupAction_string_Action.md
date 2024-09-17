
### Definition

Namespace: DiscordBot
Assembly: DiscordBot
Source: StartupAction.cs


Defines a StartupAction object with two parameters: the command name and its `Action`.
This `Action` does not have any parameters.

```cs
public StartupAction(string command, Action runAction)  
{  
    this.Command = command;  
    this.RunAction = (args) => runAction();  
}
```

