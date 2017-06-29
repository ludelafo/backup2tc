# backup2tc
Backup all your personnal files, easily, using TrueCrypt.

This script aims to help users making simple, secure and efficient backups using TrueCrypt and rsync. Using rsync, it will synchronize a source folder to a destination folder (inside a TrueCrypt container) coping only the files that changed and delete the ones that are not present anymore on the source since the last run. That means that the first time you run the script, it will copy all the source folder to the destination folder. Depending on the amount of files, it can take time, but then, depending on the changes of the source's folder, it will only copy the files that changed.

# Disclaimer
The script aims to help people doing their backups. I'm not responsable in case of lost data, faulty backups, files corruption and so on. You are responsable of your data, this script only tries to help you doing it, but without any warranty.

# Requirements
## Linux
- bash
- rsync
- TrueCrypt (https://truecrypt.ch/)

## Windows
- Cygwin with rsync (https://cygwin.com/)
- TrueCrypt (https://truecrypt.ch/)

# Setting up
## Linux
- Install TrueCrypt
- Move the files `include_to_backup.conf` and `exclude_from_backup.conf` to `/usr/local/etc/`
- Move the file `backup2tc` to `/usr/local/bin` and make it executable: `chmod +x /usr/local/bin/backup2tc`

## Windows
- Install TrueCrypt
- Install Cygwin with `rsync`
- Move the files `include_to_backup.conf` and `exclude_from_backup.conf` to `C:\cygwin\usr\local\etc\`
- Move the file `backup2tc` to `C:\cygwin\usr\local\bin`
- Optional: You can put the file `Backup.bat` on the desktop so you do not have to go to the command line to backup your files.

# Configuration
The first thing to do is to edit the `include_to_backup.conf`, `exclude_from_backup.conf` and `backup2tc` for your need.

On Linux, the path is standard, from the root folder:
`/media/ludelafo/the_partition_name/one\ folder/the_truecrypt_file.tc`

On Windows, using Cygwin, the path should always be like this:
`/cygdrive/letter_of_the_parition/one\ folder/the_truecrypt_file.tc`

## `include_to_backup.conf` and `exclude_from_backup.conf`
These two files are used to know which folders you would like to backup and which folders inside the folders included to the backup you want to ignore.

## `backup2tc`
This file defines where is the TrueCrypt's file, where should the TrueCrypt's container should be mounted and other few parameters. Just open it and change it for your needs. The most importants lines are these:

```bash
TRUECRYPT_FILE_PATH="/cygdrive/f/Backup.tc" # File path to the TrueCrypt container

MOUNT_POINT="/media/TrueCrypt" # TrueCrypt container's mount destination (Unix only)
WINDOWS_MOUNT_POINT="Z:" # Windows's mount point's letter
```

You may also change the programs' path.

## Usage
Just open a terminal, and type `backup2tc` or use the `Backup.bat` (for Windows' users only) to run the backup.

The script will ask you the password of the TrueCrypt's container and mount it. When this is done, the user have to press 'Enter' to continue. The backup begins and when it's done, the script will lock the TrueCrypt's container and notify the user of the end.

# Sources
- http://www.manpagez.com/man/1/rsync/
- http://unix.stackexchange.com/questions/23111/what-is-the-eval-command-in-bash
- http://blog.nicolargo.com/2008/11/synchronisation-de-deux-repertoires-avec-rsync.html
- http://www.ibm.com/developerworks/aix/library/au-usingtraps/
- http://www.ss64.com/bash/set.html
- http://stackoverflow.com/questions/2053764/automating-cygwin-commands-in-windows-command-line-and-ultimately-in-msbuild
- http://cygwin.com
- http://www.truecrypt.org/docs/command-line-usage
- http://stackoverflow.com/questions/4277665/bash-how-do-i-compare-two-string-variables-in-an-if-statement
- http://stackoverflow.com/questions/5998066/bash-script-variable-content-as-a-command-to-run
- http://stackoverflow.com/questions/15994207/cygpath-doesnt-convert-windows-path-correctly
