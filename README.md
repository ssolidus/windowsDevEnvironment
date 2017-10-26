# Developing on Windows
This is a guide on setting up an optimal development environment on Windows.

## Shell and console emulator
The best environment setup is Babun, which is built on-top of [Cygwin](https://www.cygwin.com/), but includes an easy-to-use package-manager, out-of-thebox Zsh support, and better compatibility.

Cmder is the best console emulator. 

### Babun
  - Get [Babun](https://babun.github.io/)
  - Run `install.bat`
  - To install packages, use `pact <packagename>`
### Cmder
#### Installation
 - Get [Cmder](http://cmder.net/)

#### Configuration
##### Babun integration
 - Go to Settings>Startup>Tasks
 - Create a new task
 - Task parameters:

`/icon "%userprofile%\.babun\cygwin\bin\mintty.exe" /dir "%userprofile%"`
 - Commands:
  
`%userprofile%\.babun\cygwin\bin\mintty.exe /bin/env CHERE_INVOKING=1 /bin/zsh.exe`

##### Set font
Go to  **Settings** > **Main** and select desired font. Consolas is my preferred monospace font on Windows.

##### Style
- Set a preferred style under **Settings** > **Features** > **Colors** 

My configuration:

 Monokai
 
 `0.` (background) set to `0 0 0`

 `7.` set to `202 202 202`

## Font rendering
### Mactype
Mactype hooks provides [freetype](https://www.freetype.org/developer.html) on Windows. Freetype is currently the best font-rasteriser, and is used on Linux, Android, iOS and macOS. Microsoft still uses [ClearType](https://www.microsoft.com/en-us/Typography/ClearTypeInfo.aspx), which is considerably worse, especially for alphabets other than Latin.
#### Installation
 - Get [Mactype](https://github.com/snowie2000/mactype)
 - Choose your desire loading mode. I prefer **Load with MacTray** with **Standalone loading mode**, as it allows you to toggle exclusions for incompatible programs.

## Code editing
### Installation
Install [VSCode](https://code.visualstudio.com/)
### Configuration
#### MacType integration
(Taken from [VSCode Mactype Hack](https://github.com/thomasklash/vscode-mactype-hack))

VSCode requires the following flags to be passed for MacType to work correctly:
- Right-click the shortcut to **VSCode** > **Properties**
- In the **Target** field, append the following string:

`` --disable-lcd-text --disable-gpu --disable-directwrite-for-ui --disable-font-antialiasing``

#### Babun integration
- Open **VSCode**
- Open **File** > **Preferences** > **Settings**
- Add the following to the **USER SETTINGS** section
```JSON
"terminal.integrated.shell.windows": "C:\\Users\\tom\\.babun\\cygwin\\bin\\zsh.exe",
```