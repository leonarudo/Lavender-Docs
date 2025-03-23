# IConsoleCommand Interface
<br>

## Definition
Namespace: Lavender.CommandLib <br>
Source: [IConsoleCommand.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/CommandLib/IConsoleCommand.cs)

<br>

## Examples

Creating a custom command:
```cs
using Lavender.CommandLib;

public class EchoCommand : IConsoleCommand
{
    public string Name => "echo";

    public string Description => "echoes whatever you tell it to";

    public string Usage => "echo <string>";

    public void Execute(params string[] args)
    {
        if (args.Length < 2)
        {
            CommandManager.PrintToDevConsole(Usage);
            return;
        }

        //Specifically call string.Trim(char[]) instead of 
        //string.Trim(char) to avoid a netstandard 2.0 -> 2.1
        //issue
        CommandManager.PrintToDevConsole(args[1].Trim(['"']));
    }
}
```

Register the command:
```cs
CommandManager.RegisterCommand(new EchoCommand());
```
*Put this in ur plugin innit code; e.g., In your BaseUnityPlugin class in Awake()*

<br>

## Properties

<table>
<tr>
    <td>Name</td>
    <td>The name of the console command, (e.g., "give").</td>
</tr>
<tr>
    <td>Description</td>
    <td>The description of the console command (e.g., "Gives the player an item").</td>
</tr>
<tr>
    <td>Usage</td>
    <td>A short explanation on how to use the console command (e.g., "give [item_name]").</td>
</tr>
</table>

<br>

## Methods

<table>
<tr>
    <td>Execute(params string[])</td>
    <td>A function to be executed when the console command is run.</td>
</tr>
</table>

<br>