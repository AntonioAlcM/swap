# Práctica 5

## Replicar una base de datos con mysqldump
1. Bloqueamos las tablas para que no se altere el contenido de las mismas, mientras estamos haciendo la copia de la base de datos. Para ello usamos el siguiente comando.

  mysql> FLUSH TABLES WITH READ LOCK;

2. Una vez bloqueadas las tablas guardamos los datos en la máquina 1. Para ello usamos el siguiente comando.

  mysqldump contactos -u root -p > /root/contactos.sql

  Ahora desbloqueamos las tablas con mysql> UNLOCK TABLES;

3. Ahora importaremos la base de datos a la máquina 2 para ello:
  1. Copias el archivo .SQL desde la máquina principal a la máquina secundaria.

    mysqldump ejemplodb -u root -p > /root/ejemplodb.sql
  2. Creamos en mysql una base de datos que se llame igual a la base de datos que queremos copiar.

    CREATE DATABASE ‘contactos’;

  3. Para finalizar restauramos los datos contenidos en la base de datos.

    mysql -u root -p ejemplodb < /root/ejemplodb.sql

![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica5/practica5.png?raw=true)
## Replicar una base de datos mediante una configuración maestro-esclavo
1. Modificar el archivo my.cnf según especifica el guion y reinicias mysql.

2. Haces lo mismo en la máquina esclava, solo que server-id en vez de un 1 tendrá un 2 como valor.

3. Entramos al mysql de la máquina maestra y en la consola introducimos las siguientes ordenes:

  mysql> CREATE USER esclavo IDENTIFIED BY 'esclavo';

  mysql> GRANT REPLICATION SLAVE ON *.* TO 'esclavo'@'%' IDENTIFIED BY 'esclavo';

  mysql> FLUSH PRIVILEGES;

  mysql> FLUSH TABLES;

  mysql> FLUSH TABLES WITH READ LOCK;

  Una vez introducida estas órdenes hacemos un mysql> SHOW MASTER STATUS; y apuntamos el contenido de file y position, los necesitaremos  a la hora de configurar la máquina esclava.

4. Entramos en la mysql de la máquina esclava he introducimos la siguiente orden:

  mysql> CHANGE MASTER TO MASTER_HOST='192.168.72.139', MASTER_USER='esclavo', MASTER_PASSWORD='esclavo', MASTER_LOG_FILE='mysql-bin.000001', MASTER_LOG_POS=501, MASTER_PORT=3306;

  En el MASTER_HOST ponemos la ip de la máquina maestra, en MASTER_LOG_FILE ponemos el contenido del file que habíamos guardado de la máquina maestra y lo mismo hacemos con MASTER_LOG_POS.

  Una vez introducido estos datos iniciamos el modo esclavo.

  mysql> START SLAVE;

  ![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica5/practica5.1.png?raw=true)
5. Desbloqueamos las tablas de la base de datos de la máquina maestra

6. Con mysql> SHOW SLAVE STATUS\G comprobamos que esté funcionando bien, para ellos buscamos Seconds_Behind_Master, si es distinto de null está funcionando correctamente.

7. Ahora vamos a añadir nuevos datos a nuestras tablas.

  ![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica5/practica5.2.png?raw=true)

## Replicar una base de datos mediante una configuración maestro-maestro.

Se hace igual que el maestro-esclavo, solo que tienes que configurar el maestro en las dos máquinas y el esclavo también en las dos máquinas.

En la primera fotografía inserto un dato en la segunda máquina y vemos como se replica en la primera.

![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica5/practica5.3.png?raw=true)

En la segunda fotografía inserto un dato en la primera máquina y vemos como se replica en la segunda.

![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica5/practica5.4.png?raw=true)
