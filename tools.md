# Other Tools

## Cmder Context Menu

```c#
// ContextCmder-Disable.reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder]
[-HKEY_CLASSES_ROOT\Directory\shell\Cmder]
```

```c#
// ContextCmder-Enable.reg
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder]
@="Open Cmder Here"
"Icon"="C:\\tools\\cmder\\Cmder.exe,0"

[HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder\command]
@="\"C:\\tools\\cmder\\Cmder.exe\" \"%V\""

[HKEY_CLASSES_ROOT\Directory\shell\Cmder]
@="Open Cmder Here"
"Icon"="C:\\tools\\cmder\\Cmder.exe,0"

[HKEY_CLASSES_ROOT\Directory\shell\Cmder\command]
@="\"C:\\tools\\cmder\\Cmder.exe\" \"%1\""
```