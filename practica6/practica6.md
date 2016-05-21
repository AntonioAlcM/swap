## Práctica 6

1. Creamos el raid con la siguiente instrucción sudo mdadm -C /dev/md0 --level=raid1 --raid-devices=2 /dev/sdb /dev/sdc

2. Luego le damos formato, para ello ejecutaremos: sudo mkfs /dev/md0
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.1.png?raw=true)
3. Para comprobar que se han montado bien ejecutaremos: sudo mount
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.2.png?raw=true)
4. Para comprobar el estado del RAID, ejecutaremos:
sudo mdadm --detail /dev/md0
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.3.png?raw=true)
5. Obtenemos los UUID de todos los dispositivos de almacenamiento que tenemos, para ello debemos
ejecutar la orden: ls -l /dev/disk/by-uuid/
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.4.png?raw=true)
6. Añadimos al final del archivo /etc/fstab la línea para que monte automáticamente
el dispositivo RAID, que será similar a:
UUID=ccbbbbcc-dddd-eeee-ffff-aaabbbcccddd /dat ext2 defaults 0 0
7. Ahora probamos a simular un fallo en un disco y a reenganchar uno nuevo.
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.5.png?raw=true)
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica6/practica6.6.png?raw=true)
