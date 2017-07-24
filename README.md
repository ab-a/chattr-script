# chattr-script
Script that help you to use chattr 

## DESCRIPTION
This script restrict the writing access to your folders.

You can pass a file that contain exclusions.

More info : man chattr

## Installation

```
cd /opt
git clone https://github.com/ab-a/chattr-script.git
chmod +x chattr-script/attr_manage && ln -s /opt/chattr-script/attr_manage /usr/local/bin
```
Reload the shell : 
```
. ~/.bashrc
```
Check :
```
attr_manage
```
## USAGE

```
attr_manage [-f []] [-s [lock][unlock]] [-e []]
```
```
attr_manage -f $PATH -s lock -e $EXCLUSIONS
attr_manage -f $PATH -s unlock
```
## OPTIONS
```
-f [folder]                                mandatory
-s [status of install folder]              mandatory
-e [exclude file]                          optionnal
-h help
```
## EXCLUSION FILE
One path by line

## EXAMPLES
Lock and add exception :
```
attr_manage -f /var/www/lock -s lock -e /home/user/exception
```
Unlock :
```
attr_manage -f /var/www/lock -s unlock
```
Exclusion file example :
```
$ cat /home/user/exclusion
  /var/www/lock/static-folder
  /var/www/lock/static-folder2
```
