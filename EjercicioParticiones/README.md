
~~~
Welcome to fdisk (util-linux 2.27.1).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

El dispositivo no contiene una tabla de particiones reconocible.
Created a new DOS disklabel with disk identifier 0xfc6e9827.

Orden (m para obtener ayuda): n
Partition type
   p   primary (0 primary, 0 extended, 4 free)
   e   extended (container for logical partitions)
Select (default p): p
Número de partición (1-4, default 1): 1
First sector (2048-10485759, default 2048): 
Last sector, +sectors or +size{K,M,G,T,P} (2048-10485759, default 10485759): +2,5G

Created a new partition 1 of type 'Linux' and of size 2,5 GiB.

Orden (m para obtener ayuda): t
Selected partition 1
Partition type (type L to list all types): 83
Changed type of partition 'Linux' to 'Linux'.

Orden (m para obtener ayuda): w
The partition table has been altered.
Calling ioctl() to re-read partition table.
Syncing disks.
~~~


 mkfs -t
