#backup2tc
Backup all your personnal files, easily, using TrueCrypt

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

