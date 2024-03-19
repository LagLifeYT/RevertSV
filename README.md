# RevertSV
*tested on Windows 11 build 22000.2538*

Please make a backup of your data before proceeding. It is not unlikely that something will break and you have to reinstall.

## Windows 10 settings app
Grab ImmersiveControlPanel, Windows.UI.SettingsAppThreshold (SystemResources), and SettingsEnvironment.Desktop.dll (System32) from build 22000.1 and replace the corresponding files in 22000.2538 / whatever build you are using.

Method originally discovered by Valinet (creator of [ExplorerPatcher](https://github.com/valinet/ExplorerPatcher))

## Windows 10 login screen
**Only tested on 22000.194 and 22000.2538, broken on latest Windows 11 23H2!**

Grab Windows.UI.Logon.dll (System32) and Windows.UI.Logon (SystemResources) from build 22000.1 and drop them into 22000.194. Locking will be Win11 styled until you replace the UWP lock screen in SystemApps.

## Windows 10 shell

Create a DWORD named "UndockingDisabled" under `HKLM\Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages` and set it to 1. Reboot.

The control panel for editing tray icons has been hidden, use `shell:::{05d7b0f4-2121-4eff-bf6b-ed3f69b894d9}\SystemIcons` in the run dialog to get to it again. From there you can fix the tray.

Note that the start menu and various other functionality is broken.



