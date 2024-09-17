
### Definition
Namespace: DiscordBot.ConsoleUtilities
Assembly: DiscordBot
Source: ConsoleUtilities.cs



Executes a task with its built in progress bar control.

```cs
public static async Task ExecuteTaskWithBuiltInProgress<T>(Func<T, IProgress<float>, Task> method, T parameter, string taskMessage)
```
### Remarks

The base function must use a `IProgress<float>` to set the progress up.
Parameter `T` is Parameter type for the function. This will be used when the base function is called.
Message is the default message to be displayed. Please set it to `string.Empty` for an empty message


### Example

```cs
public async Task SelfUpdate(Update update, IProgress<float> progress)  
{  
    Directory.CreateDirectory(_TempUpdateFolder);  
  
    string tempFile = $"./{_TempUpdateFolder}/update.zip";  
    string tempFolder = $"./{_TempUpdateFolder}/";  
  
    Directory.CreateDirectory(tempFolder);  
    await ServerCom.DownloadFileAsync(update.UpdateUrl, tempFile, progress);  
  
    await ArchiveManager.ExtractArchive(tempFile, tempFolder, progress, UnzipProgressType.PERCENTAGE_FROM_TOTAL_SIZE);  
    PrepareCurrentFolderForOverwrite();  
  
    if (OperatingSystem.IsWindows())  
        tempFolder += _WindowsUpdateFile;  
    else if (OperatingSystem.IsLinux())  
        tempFolder += _LinuxUpdateFile;  
    else if (OperatingSystem.IsMacOS())  
        tempFolder += _MacOSUpdateFile;  
    else throw new PlatformNotSupportedException();  
    await CopyFolderContentOverCurrentFolder("./", tempFolder.Substring(0, tempFolder.Length-4)); // Remove the .zip from the folder name  
  
    Process.Start("DiscordBot", "--update-cleanup");  
    Environment.Exit(0);  
    }

await ConsoleUtilities.ExecuteTaskWithBuiltInProgress(updater.SelfUpdate, update, "Discord Bot Update");
```

