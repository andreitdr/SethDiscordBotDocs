### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

Converts the [[TableData Class|Table Data]] into a `Table` class from [Spectre.Console](www.nuget.org/packages/Spectre.Console) NuGet package.

```cs
public Table AsTable()  
{  
  
   var table = new Table();  
    table.Border(this.HasRoundBorders ? TableBorder.Rounded : TableBorder.Square);  
    table.AddColumns(this.Columns.ToArray());  
    table.ShowRowSeparators = DisplayLinesBetweenRows;  
    foreach (var row in this.Rows)  
    {        table.AddRow(row.Select(element => element.Match(  
            (string data) => new Markup(data),  
            (IRenderable data) => data  
        )));    }  
    table.Alignment(Justify.Center);  
  
    return table;  
}
```

### Remarks
`IRenderable` is an interface defined in the [Spectre.Console](https://www.nuget.org/packages/Spectre.Console)
