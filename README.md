#backup2tc
Backup all your personnal files, easily, using TrueCrypt

#Details
This script aims to help users making simple, secure and efficient backups using TrueCrypt and rsync. Using rsync, it will synchronise a source folder to a destination folder (inside a TrueCrypt container) coping/moving/deleting only the files that changed on the source since the last run. That means that the first time you run the script, it will copy all the source folder to the destination folder. Depending on the amount of files, it can take time, but then, depending on the changes of the source's folder, it will only copy the files that changed.

#Disclaimer
The script aims to help people doing their backups. I'm not responsable in case of lost data, faulty backups, files corruption and so on. You are responsable of your data, this script only tries to help you doing it, but without any warranty.

#Requirements
##Linux
* bash
* rsync
* TrueCrypt (https://truecrypt.ch/)

##Windows
* Cygwin with rsync (https://cygwin.com/)
* TrueCrypt (https://truecrypt.ch/)

#Setting up
##Linux
* Install TrueCrypt
* Move the files 'include_to_backup.conf' and 'exclude_from_backup.conf' to /usr/local/etc
* Move the file backup2tc to /usr/local/bin and make it executable (chmod +x /usr/local/bin/backup2tc)

##Windows
* Install TrueCrypt
* Install Cygwin with rsync
* Move the files 'include_to_backup.conf' and 'exclude_from_backup.conf' to C:\cygwin\usr\local\etc
* Move the file backup2tc to C:\cygwin\usr\local\bin
* (optional) Put the file Backup.bat on a simple and reachable place (on the Desktop for example) to backup fast and simply

#Usage
##Edition
The first thing to do is to edit the 'include_to_backup.conf', 'exclude_from_backup.conf' and 'backup2tc' for your need.
On Linux, the path is standard, from the root folder:
```bash
/media/ludovic/the_partition_name/one\ folder/the_truecrypt_file.tc
```
On Windows, using Cygwin, the path should always be like this:
```bash
/cygdrive/letter_of_a_parition/one\ folder/the_truecrypt_file.tc
```
###'include_to_backup.conf' and 'exclude_from_backup.conf'
These two files are used to know what folders you would like to backup and which folders inside the folders included to the backup you want to ignore.

####Example
Let's say that you want to backup your personnal home folder (Linux example).
In the file 'include_to_backup.conf', you should put the path to your home folder (and/or all the folders you want to backup):
```bash
/media/ludovic
```
But imagine that you don't want the 'Downloads' folder *inside* the /media/ludovic's folder. Just exclude it in the file 'exclude_from_backup.conf':
```bash
/media/ludovic/Downloads
```
Easy no ?

###'backup2tc'
This file defines where is the TrueCrypt's file, where should the TrueCrypt's container should be mounted and other few parameters. Just open it and change it for your needs. The most importants lines are these:
```bash
TRUECRYPT_FILE_PATH="/cygdrive/f/Backup.tc" # File path to the TrueCrypt container

MOUNT_POINT="/media/TrueCrypt" # TrueCrypt container's mount destination (Unix only)
WINDOWS_MOUNT_POINT="Z:" # Windows's mount point's letter
```
You may also change the programs' path. As I've tested on my computer, with my configuration, some path to programs may need to be changed (32bit systems VS 64bit for example) in 'backup2tc' and in Backup.bat (Windows' users).

##Execution
Just open a terminal, and type 'backup2tc' or use the Backup.bat (for Windows' users only) to run the backup.

The script will ask you the password of the TrueCrypt's container and mount it. When this is done, the user have to press 'Enter' to continue. The backup begins and when it's done, the script will lock the TrueCrypt's container and notify the user of the end.
