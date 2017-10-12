# SimpleLogger
A simple logging utility ready to go out of the box.

Version: 1.17.4.1454

## Overview
SimpleLogger is a lightweight utility for logging information and errors to file and to the Windows command line written in C# for .NET applications.

You simply add SimpleLogger.dll as a reference to your project in Visual Studio and you're ready to go.

There are 4 color options and the ability to change log files on the fly to log information and other data to multiple files throughout your code. You can also edit the information and error patterns to change the format of how things are logged.

### Example
```c#
using SimpleLogger;

namespace simple
{
  class Application
  {
    static void Main(string[] args)
    {
      Log.file = @"logs/my_log.txt";
      Log.init(); // Initialize SimpleLogger
      
      Log.info("Starting application...");  // Writes to file
      Log.display_info("Starting application...", LogColor.GREEN);  // Displays in the console as green text
      
      Log.error("Looks like there's no code here");
      Log.display_error("Looks like there's no code here", LogColor.RED);
      
      Log.change_log_file(@"logs/other_log.txt");
      Log.info("Changing log file...");
      
      Log.shutdown();
    }
  }
}
```

### Color options
LogColor.RED

LogColor.GREEN

LogColor.BLUE

LogColor.YELLOW


### Methods and Accessors
```c#
public static string file { get; set; }

public static void change_log_file(string _file);

public static void display_error(string text);
public static void display_error(string text, LogColor color);

public static void display_info(string text);
public static void display_info(string text, LogColor color);

public static void display_nl();  // Writes a line break/new line to the console
public static void write_nl();  // Writes a line break/new line to file

public static void error(string text);

public static void info(string text);
public static void info(string text, bool use_new_line);  // Writes data to a file without a line break with use_new_line = false;

public static void init();
public static void shutdown();
```
