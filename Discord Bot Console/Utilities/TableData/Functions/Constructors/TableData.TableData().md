
### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

The base constructor for the class. 
Initialize a table with empty list of Rows and Column headers are unknown.

```cs
public TableData()  
{  
    Columns = new List<string>();  
    Rows = new List<OneOf<string, IRenderable>[]>();  
}
```

### Remarks
`IRenderable` is an interface defined in the [Spectre.Console](https://www.nuget.org/packages/Spectre.Console)

