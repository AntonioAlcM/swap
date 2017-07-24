#**Resolución practica 3**

 > Para poder comprobar que funciona el balanceador correctamente, en la 
máquina 2 de nuestra granja web debemos deshabilitar la orden del crontab que 
actualizaba la máquina 2 al estado de la máquina 1. Después en la carpeta 
/var/www debemos modificar el archivo index.html y poner en cada uno de ellas, 
soy la máquina 1 o soy la máquina 2, según corresponda

##**Configuración del servidor nginx**

  > Instalamos nginx, una vez instalado debemos modificar el archivo 
/etc/nginx/conf.d/default.conf.
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/nginx.png)

 > Como vemos en la imagen, en la parte de upstream es donde yo voy a ir 
añadiendo las máquinas de mi granja web. Además he añadido la linea keepalive, 
esto me permite hacer una conexión con  una persistencia de múltiples 
peticiones HTTP en lugar de abrir una conexión nueva cada vez.
 
 > En la parte server, la configuramos de esta forma especifica, para que 
funcione como balanceador.

 > Una vez instalado arrancamos el servicio con esta orden **service nginx 
restart** (este si esta ya arrancado) o **service nginx start**

##**Configuración del servidor haproxy**

  > Instalamos haproxy, una vez instalado debemos modificar el archivo /etc/haproxy/haproxy.cfg
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/haproxy.png)

 > Como vemos en la imagen, en la parte de backend servers es donde yo voy a ir 
añadiendo las máquinas de mi granja web

 > El resto es la configuración dada por el profesor, para poder iniciar el 
servidor debes usar este comando, **/usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg**

##**Configuración del servidor lighttpd**

 > Instalamos lighttpd, una vez instalado debemos modificar el archivo /etc/lighttpd/lighttpd.conf
 
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/lighttpd.png)
 
 > Voy a describir las distintas partes de que se compone el archivo:
 
 > > 1. server.modules es el comando que carga los módulos que deseas usar para 
el servidor
 > > 2. La parte intermedia  viene por defecto, importante comentar 
server.username, server.groupname y server.port, esto atributos son para 
configurar el servidor.
 > > 3. La parte mas importante es $SERVER["socket"] == ":80", esto quiere decir 
que se va a crear un servidor que va a usar el puerto 80, el proxy.balance 
sirve para establecer el algoritmo de balanceo, el proxy.server sirve para 
añadir las máquinas a nuestro balanceador.

 > Para arrancarlo basta con escribir **service lighttpd start o restart**, según 
lo tengas en ejecución o no.

##**Configuración del servidor Zenload Balancer**

 > Una vez instalado el ZenLoadBalancer entramos a la máquina desde el 
navegador 
introduciendo https://ip:444, una vez en la página principal accedemos a manage 
y pinchamos en Farms, allí aparecerá un recuadro que pone Configure a new Farm 
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.
4 . 1.png)
 > Una vez que le damos a save&continue aparecerá la siguiente página 
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.
4.2.png) 
introducimos la dirección virtual de nuestro servidor y el puerto que queramos 
que use, le damos a save y aparecerá la siguiente página 
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.
4.3.png),
seleccionamos el botón edit de nuestra granja y pasaremos a la siguiente página 
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.4
.4.png)
en el apartado edit real IP servers configurate añadimos las ips de nuestros 
servidores.

Ya por último solo poner en marcha nuestro servidor.

#**Consideraciones**

 > Importante en caso de tener instalado Apache hay que pararlo, para eso usar 
el comando service apache2 stop, en caso contrario nos dará error al intentar 
lanzar nuestros balanceadores, ya que Apache usa el mismo puerto que nuestros 
balanceadores
 
 > Se recomienda no instalar el apache