
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

Primero indicamos una nueva partición (n), después que es del tipo primaria (p), el número de partición y por último el tamaño para esta partición. (si se quisiera todo el disco en una sola partición, bastaría con presionar enter).Hay que indicar el tipo de sistema de archivos que tendrá la partición, esto con el comando t, seguido del número de partición, y de un número hexadecimal que define el sistema de archivos. Si en vez del número hexadecimal, introducimos "L", nos mostrará el listado de estos números hexadecimales junto a su sistema de archivos correspondiente. Por último pulsamos "w" para guardar los cambios. Si no quisieramos guardar los cambios pulsaríamos "q" En este caso se dividirá el disco en más de una partición asi que repetiriamos lo anterior pero empezando en el siguiente cilindro disponible y sería la partición 2. 

Creamos los directorios donde posteriormente, montaremos los discos:
~~~
root@rafiki:/home/rafiki# mkdir /DiscoAlinux
root@rafiki:/home/rafiki# mkdir /DiscoAfat
root@rafiki:/home/rafiki# mkdir /DiscoBlinux
root@rafiki:/home/rafiki# mkdir /DiscoBntfs
root@rafiki:/home/rafiki# mkdir /DiscoBfat
~~~

~~~
root@rafiki:/home/rafiki# blkid /dev/sdb1 >> /etc/fstab
root@rafiki:/home/rafiki# blkid /dev/sdb2 >> /etc/fstab
root@rafiki:/home/rafiki# blkid /dev/sdc1 >> /etc/fstab
root@rafiki:/home/rafiki# blkid /dev/sdc2 >> /etc/fstab
root@rafiki:/home/rafiki# blkid /dev/sdc3 >> /etc/fstab
~~~
