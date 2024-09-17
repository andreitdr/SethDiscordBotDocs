### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

Defines a new table based on a list of string that are the headers of the columns.
Given the `List<string>` for the headers, we can know also the number of columns in the table.

```cs
public TableData(List<string> columns)  
{  
    Columns = columns;  
    Rows = new List<OneOf<string, IRenderable>[]>();  
}
```

### Remarks

`IRenderable` is an interface defined in the [Spectre.Console](www.nuget.org/packages/Spectre.Console)