#####Date: 29.10.2013
Explications: - Convert in Unix format
#####Date: 30.10.2013
Explications: - Begin of the modification to allow the script to run on Windows and Unix
#####Date: 31.10.2013
Explications: - Begin of the modification to allow the script to run on Windows and Unix, need to test
#####Date: 04.11.2013
Explications: - Corrections of bugs
              - Begin of tests on Windows
#####Date: 06.11.2013
Explications: - Control of the script and moved a commentary and a const
#####Date: 14.11.2013
Explications: - Test on a UNIX machine
              - Need to delete the quotes around the truecrypt commands to avoid errors
              - Huge tests and correction about rsync that doesn't really sync the two folders but just update the file list
              - Need to try on a Windows plateform again to be sure
              - Correction of a bad const name 
              - Correction of the parameters
              - Add the if at the end of the script		
#####Date: 17.11.2013
Explications: - Test on a Windows machine
              - Big changes in the script, more dynamic
              - Need to convert the Windows file path to unix file path for rsync
              - Huge tests and correction about rsync that doesn't really sync the two folders but just update the file list
              - Need to try on a Windows plateform again to be sure
              - Correction of a bad const name 
              - Correction of the parameters
              - Add the if at the end of the script		
#####Date: 18.11.2013
Explications: - Test on a UNIX machine: works perfectly
              - Add the Windows letter const for truecrypt
              - Need to retest on a Windows machine :)	
#####Date: 21.11.2013
Explications: - Change a consts in a Windows's TrueCrypt command
              - Change the if statement from *Windows* to */usr/bin*
#####Date: 16.01.2014
Explications: - Change a const in the mount commands that didn't use the right mount_dest for the right OS
#####Date: 20-21.07.2014
Explications: - Much tested on Linux many times, works perfectly.
              - Changed a bit the comments in the script for the github upload
              - Changed a const name for comprehension
              - Moved the TRUECRYPT_LOCATION outside of the if/else
              - Added the set -u
              - Correction of a bug with Windows and Truecrypt's file path (source: http://stackoverflow.com/questions/15994207/cygpath-doesnt-convert-windows-path-correctly)
#####Date: 31.07.2014
Explications: - Tested on Windows and few modifications
#####Date: 03.07.2014
Explications: - Final changes before uploading on GitHub