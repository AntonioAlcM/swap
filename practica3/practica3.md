#**Resoluci�n practica 3**

 > Para poder comprobar que funciona el balanceador correctamente, en la
m�quina 2 de nuestra granja web debemos deshabilitar la orden del crontab que
actualizaba la m�quina 2 al estado de la m�quina 1. Despu�s en la carpeta
/var/www debemos modificar el archivo index.html y poner en cada uno de ellas,
soy la m�quina 1 o soy la m�quina 2, seg�n corresponda

##**Configuraci�n del servidor nginx**

  > Instalamos nginx, una vez instalado debemos modificar el archivo
/etc/nginx/conf.d/default.conf.
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/nginx.png)

 > Como vemos en la imagen, en la parte de upstream es donde yo voy a ir
a�adiendo las m�quinas de mi granja web. Adem�s he a�adido la linea keepalive,
esto me permite hacer una conexi�n con  una persistencia de m�ltiples
peticiones HTTP en lugar de abrir una conexi�n nueva cada vez.

 > En la parte server, la configuramos de esta forma especifica, para que
funcione como balanceador.

 > Una vez instalado arrancamos el servicio con esta orden **service nginx
restart** (este si esta ya arrancado) o **service nginx start**

##**Configuraci�n del servidor haproxy**

  > Instalamos haproxy, una vez instalado debemos modificar el archivo
/etc/haproxy/haproxy.cfg
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/haproxy.png)

 > Como vemos en la imagen, en la parte de backend servers es donde yo voy a ir
a�adiendo las m�quinas de mi granja web

 > El resto es la configuraci�n dada por el profesor, para poder iniciar el
servidor debes usar este comando, **/usr/sbin/haproxy -f
/etc/haproxy/haproxy.cfg**

##**Configuraci�n del servidor lighttpd**

 > Instalamos lighttpd, una vez instalado debemos modificar el archivo
/etc/lighttpd/lighttpd.conf

![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/lighttpd.png
)

 > Voy a describir las distintas partes de que se compone el archivo:

 > > 1. server.modules es el comando que carga los m�dulos que deseas usar para
el servidor
 > > 2. La parte intermedia  viene por defecto, importante comentar
server.username, server.groupname y server.port, esto atributos son para
configurar el servidor.
 > > 3. La parte mas importante es $SERVER["socket"] == ":80", esto quiere
decir
que se va a crear un servidor que va a usar el puerto 80, el proxy.balance
sirve para establecer el algoritmo de balanceo, el proxy.server sirve para
a�adir las m�quinas a nuestro balanceador.

 > Para arrancarlo basta con escribir **service lighttpd start o restart**,
seg�n
lo tengas en ejecuci�n o no.

##**Configuraci�n del servidor Zenload Balancer**

 > Una vez instalado el ZenLoadBalancer entramos a la m�quina desde el
navegador
introduciendo https://ip:444, una vez en la p�gina principal accedemos a manage
y pinchamos en Farms, all� aparecer� un recuadro que pone Configure a new Farm
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.4.1.png)
 > Una vez que le damos a save&continue aparecer� la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.4.2.png)
introducimos la direcci�n virtual de nuestro servidor y el puerto que queramos
que use, le damos a save y aparecer� la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.4.3.png),
seleccionamos el bot�n edit de nuestra granja y pasaremos a la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica3/Ejercicio4.4.4.png)
en el apartado edit real IP servers configurate a�adimos las ips de nuestros
servidores.

Ya por �ltimo solo poner en marcha nuestro servidor.

#**Consideraciones**

 > Importante en caso de tener instalado Apache hay que pararlo, para eso usar
el comando service apache2 stop, en caso contrario nos dar� error al intentar
lanzar nuestros balanceadores, ya que Apache usa el mismo puerto que nuestros
balanceadores

 > Se recomienda no instalar el apache
