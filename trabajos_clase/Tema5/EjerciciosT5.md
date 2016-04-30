#T5.1 Buscar información sobre cómo calcular el número de conexiones por 
segundo.

He examinado la información de los link, uno habla de un módulo de Nginx 
para calcular el número de conexiones por segundo, pero al final del articulo 
te da la formula que usa para calcular el número de conexiones por segundo, 
la formula consiste en dividir handles resquests / handled connections.

El segundo articulo te comenta como usando este comando netstat | grep http | 
wc -l puedes calcular los usuarios conectados a tu servidor por http

Cisco tiene en sus gamas de productos módulos para calcular  el número 
de conexiones por segundo en 
este 
[enlace](http://www.cisco.com/c/en/us/td/docs/security/asa/asa-command- 
reference /S/cmdref3/s2.html) vemos la información de ese módulo

#T5.2 Instalar wireshark y observar cómo fluye el tráfico de red en uno de los 
servidores web mientras se le hacen peticiones HTTP.

Aquí muestro una foto del tráfico que esta teniendo el balanceador de carga 
de nginx, mientras desde el anfitrión hago peticiones con el apache 
benchmark [!imagen](swap/trabajos_clase/Ejercicio5.2.png)

#T5.3 Buscar información sobre características, disponibilidad para diversos 
SO, etc de herramientas para monitorizar las prestaciones de un servidor.

##**Linux**
	top
	htop
	nmon
	Glances
	netstat
	vmstat

##**Windows**
	monitor de recursos
	GKrellM
	netstat
	