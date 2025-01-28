---
title: All About Permissions
---

To begin with file permissions in linux are way to controll we can access what? generally this comprises of following file permissions

read(r)    &rarr; who can view
write(w)   &rarr; who can modify
execute(c) &rarr; who can execute

now each file has a set of three pople accessing it owner-group-others ex. `.rw-r--r--` this means owner has read and write while group and others has read permissions.
you can check file permissions using `ls -l` or `getfacl filepath` for more details

we can modify the files using octal code and chmod command
| Permission | Octal bit |
| -------------- | --------------- |
| r | 4 |
| w | 2 |
| x | 1 |

looking at above table the addition or removal of those will determine permisson example 755 =>
7 &rarr; 4+2+1 &rarr; owner &rarr; read-write-execute
5 &rarr; 4+0+1 &rarr; group &rarr; read-execute
5 &rarr; 4+0+1 &rarr; others &rarr; read-execute
this means all have execute and read permissions. only owner has write permission.
0 -> no permissions
1 -> execute
2 -> write
3 -> write-execute
4 -> read
5 -> read-execute
6 -> read-write
7 -> read-write-execute

644 => .rw-r--r-- => read-write to owner. read group and others
655 => .rw-r-xr-x => read-write to owner. read-execute to group and other
777 => .rwxrwxrwx => every permission to everyone
766 => .rwxrw-rw- => all for owner and read-write for group-others
