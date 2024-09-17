
### Definition

Namespace: DiscordBot.Utilities
Assembly: DiscordBot
Source: TableData.cs

A helper class that provides basic table structure used by the GUI nuget package [Spectre.Console](https://www.nuget.org/packages/Spectre.Console)

```cs
public class TableData
```


### Constructors

| Constructor                                                    | Description                                                                        |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [[TableData.TableData()\|TableData()]]                         | The base constructor for the class.                                                |
| [[TableData.TableData(List(string))\|TableData(List<string>)]] | Defines a new table based on a list of string that are the headers of the columns. |
### Properties

|      Property Name      |            Property Type             | Property Accessor Specifier | GET Type  | SET Type  |
| :---------------------: | :----------------------------------: | :-------------------------: | :-------: | :-------: |
|         Columns         |            `List<string>`            |          `public`           | `public`  | `public`  |
|          Rows           | `List<OneOf<string, IRenderable>[]>` |          `private`          | `private` | `private` |
|         IsEmpty         |                `bool`                |          `public`           | `public`  |     -     |
|     HasRoundBorders     |                `bool`                |          `public`           | `public`  | `public`  |
| DisplayLinesBetweenRows |                `bool`                |          `public`           | `public`  | `public`  |

### Methods

| Method                                 | Description                                                                                                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[TableData.AddRow\|AddRow()]]         | Adds a new row to the table.                                                                                                                            |
| [[TableData.AsTable\|AsTable()]]       | Converts the [[TableData Class\|Table Data]] into a `Table` class from [Spectre.Console](https://www.nuget.org/packages/Spectre.Console) NuGet package. |
| [[TableData.PrintTable\|PrintTable()]] | Prints the table to the console.                                                                                                                        |

### Remarks

This class is heavily dependent on [Spectre.Console](https://www.nuget.org/packages/Spectre.Console) NuGet package.