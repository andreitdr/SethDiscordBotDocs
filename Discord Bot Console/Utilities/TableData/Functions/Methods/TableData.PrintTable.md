### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

Prints the table to the console.

```cs
public void PrintTable()  
{  
    if (IsEmpty) return;  
    AnsiConsole.Write(this.AsTable());  
}
```

### Remarks
`AnsiConsole` is a class defined in the [Spectre.Console](https://www.nuget.org/packages/Spectre.Console)