### Definition

Namespace: DiscordBot
Assembly: DiscordBot
Source: StartupAction.cs

A common StartupAction with nothing more then the bare bones.

```cs
internal class StartupAction : IStartupAction  
{  
    public string Command { get; init; }  
    public Action<string[]> RunAction { get; init; }  
  
    public StartupAction(string command, Action<string[]> runAction)  
    {
	    this.Command = command;  
        this.RunAction = runAction;  
    }  
    public StartupAction(string command, Action runAction)  
    {        
	    this.Command = command;  
        this.RunAction = (args) => runAction();  
    }
}
```

### Inheritance

This class inherits [[IStartupAction Interface]].
### Constructors

| Constructor                                                                                           | Description                                                                                                      |
| ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| [[StartupAction.StartupAction_string_Action(string_vector)\|StartupAction(string, Action<String[]>)]] | Defines a StartupAction with two parameters: the command and an `Action` that accepts an array of type `string`. |
| [[StartupAction.StartupAction_string_Action\|StartupAction(string, Action)]]                          | Defines a StartupAction object with two parameters: the command name and its `Action`.                           |

### Properties

| Property Name | Property Type | Property Accessor Specifier | GET Type |   SET Type    |
| :-----------: | :-----------: | :-------------------------: | :------: | :-----------: |
|    Command    |   `public`    |          `string`           | `public` | `public init` |
|   RunAction   |   `public`    |     `Action<string[]>`      | `public` | `public init` |

### Remarks

This class is used to define custom Startup Actions.
The `Command` parameter is used to separate action form one another.
Starting an action is done by simply searching for the specified action using its `Command` and calling the `RunAction` method.