Bak.Bat - Backup your project
=====================

A script for creating and doubling of backup copies of a project.

I've created it before I started using SVN, to create backup copies
of my projects on daily basis and also to automatically copy project
files to and from my memory stick, while moving from university
to work and from work to home (Dropbox didn't exist back then :-)

I keep this script for historical reasons - it did a good job for me.

There are plenty of other tools like Git, Sync, Dropbox etc 
to help you track and backup project files.


## Usage

In a default setup you would have a folder named `Bak_Projects` on
your memory stick (eg. `F:\Bak_Projects\`) and a folder with the same
name on your HDD (eg. `D:\Bak_Projects\`).

Copy `Bak.Bat` under `\Bak_Projects\` on each disk.
Copy `Bak.Bat` to each project's folder under `\Bak_Projects\`.

Run `Bak.Bat` in project's folder to see the list of actions.

For `Double` command to work properly you have to create
`.\Bak\bak_lng.bat` file for each project with the contents

```bat
set bak_lng=%bak_lng%\<ProjectName>
```

where `<ProjectName>` is the folder name of the current project.


You can overwrite detaults defined in `Bak.Bat` by creating 
corresponding `.bat` file in `.\Bak` folder of each project.
Overwritable variables are: 
`%bak_ext%`, `%bak_upx`, `%bak_dir`, `%bak_dsk`, `%bak_dbl_dir`, `%bak_dbl`, `%bak_net`, `%bak_clean%`.

Sample `.\Bak\bak_ext.bat` file: 
```bat
REM Add bpl and dcu file extension to the default list of backup extensions.
set bak_ext=%bak_ext%, bpl, dcu
```

### Command line

- `Bak.Bat`
Display list of actions (with choice)

- `Bak.Bat /dbl`
Double prject to other disks

- `Bak.Bat /bak`
Backup project files to `.\Bak\<date & time>`

- `Bak.Bat /pak`
Backup and pack project files to `.\Bak\<date & time>.rar` (requires RAR.exe to be in %PATH%)

- `Bak.Bat /upx`
Pack `.exe` files of the project

- `Bak.Bat /meup`
Update `Bak.Bat` in all subfolders of curent folder.


## Example of usage

- [A small collection of Delphi projects](http://dcms.duzun.me/filebrowser.html?file=programming/pascal/delphi/Tools)
- [A collection of Delphi Units](http://dcms.duzun.me/filebrowser.html?file=programming/pascal/delphi/_Units)
