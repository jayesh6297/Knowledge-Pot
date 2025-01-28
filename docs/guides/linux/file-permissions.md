---
title: All About Permissions
---

To begin with file permissions in linux are way to controll who can access what? generally this comprises of following file permissions

`read(r)`    &rarr; who can view<br>
`write(w)`   &rarr; who can modify<br>
`execute(c)` &rarr; who can execute<br>

Now each file has a set of three pople accessing it owner-group-others ex. `.rw-r--r--` this means owner has read and write while group and others has read permissions.
you can check file permissions using `ls -l` or `getfacl filepath` for more details. we can modify the files using octal code and chmod command.

| Permission | Octal bit |
| -------------- | --------------- |
| r | 4 |
| w | 2 |
| x | 1 |

looking at above table the addition or removal of those will determine permisson example 755. This means all have execute and read permissions. only owner has write permission.<br>
7 &rarr; 4+2+1 &rarr; owner &rarr; read-write-execute<br>
5 &rarr; 4+0+1 &rarr; group &rarr; read-execute<br>
5 &rarr; 4+0+1 &rarr; others &rarr; read-execute<br>

**information of representation**

0 &rarr; no permissions<br>
1 &rarr; execute<br>
2 &rarr; write<br>
3 &rarr; write-execute<br>
4 &rarr; read<br>
5 &rarr; read-execute<br>
6 &rarr; read-write<br>
7 &rarr; read-write-execute<br>

**Take look at below example**
>644 => .rw-r--r-- => read-write to owner. read group and others
>655 => .rw-r-xr-x => read-write to owner. read-execute to group and other
>777 => .rwxrwxrwx => every permission to everyone
>766 => .rwxrw-rw- => all for owner and read-write for group-others
>600 => .rw------- => only owner can read and write
>700 => .rw------- => only owner can read-write-execute
