### Definition

Namespace: DiscordBotCore
Assembly: DiscordBotCore
Source: Application.cs

The startup class for the Discord Bot.
This class contains core methods and features to make the Discord bot able to run properly.

```cs
public sealed class Application
```

### Members

| Member               |   Member Type   |  Member Access Specifier  | Default Value                 |
| :------------------- | :-------------: | :-----------------------: | :---------------------------- |
| _ConfigFile          |    `string`     | `private static readonly` | ./Data/Resources/config.json  |
| _PluginsDatabaseFile |    `string`     | `private static readonly` | ./Data/Resources/plugins.json |
| _ResourcesFolder     |    `string`     | `private static readonly` | ./Data/Resources              |
| _PluginsFolder       |    `string`     | `private static readonly` | ./Data/Plugins                |
| ModuleManager        | `ModuleManager` |         `public`          | `null`                        |

### Properties

| Property Name                   | Property Type              | Property Accessor Specifier | GET Type | SET Type  |
| ------------------------------- | -------------------------- | :-------------------------: | :------: | :-------: |
| CurrentApplication              | `Application`              |       `public static`       | `public` | `private` |
| DiscordBotClient                | `DiscordBotApplication`    |          `public`           | `public` | `public`  |
| ServerIDs                       | `List<ulong>`              |          `public`           | `public` |     -     |
| PluginDatabase                  | `string`                   |          `public`           | `public` |     -     |
| ApplicationEnvironmentVariables | `CustomSettingsDictionary` |          `public`           | `public` | `private` |
| InternalActionManager           | `InternalActionManager`    |          `public`           | `public` | `private` |
| PluginManager                   | `IPluginManager`           |          `public`           | `public` | `private` |

### Sub classes

| Class                                | Description                                                                                                  |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| [[Application.Logger Class\|Logger]] | A special class that is designed to log messages. It is a wrapper around the Logger module (external module) |

### Methods


| Method                                                                               | Description                                                  |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| [[Application.CreateApplication\|CreateApplication(Func<ModuleRequirement, Task>?)]] | This method is used to create and initialize an Application. |

#Items-missing