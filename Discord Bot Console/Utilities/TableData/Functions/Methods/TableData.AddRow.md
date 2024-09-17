
### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

Adds a new row to the table. 
The new row must be of the same length as the number of columns. 

```cs
public void AddRow(OneOf<string, IRenderable>[] row)  
{  
    Rows.Add(row);  
}
```

### Remarks
`IRenderable` is an interface defined in the [Spectre.Console](https://www.nuget.org/packages/Spectre.Console)