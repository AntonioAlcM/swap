#T5.1 Buscar informaci�n sobre c�mo calcular el n�mero de conexiones por
segundo.

He examinado la informaci�n de los link, uno habla de un m�dulo de Nginx
para calcular el n�mero de conexiones por segundo, pero al final del articulo
te da la formula que usa para calcular el n�mero de conexiones por segundo,
la formula consiste en dividir handles resquests / handled connections.

El segundo articulo te comenta como usando este comando netstat | grep http |
wc -l puedes calcular los usuarios conectados a tu servidor por http

Cisco tiene en sus gamas de productos m�dulos para calcular  el n�mero
de conexiones por segundo en
este
[enlace](http://www.cisco.com/c/en/us/td/docs/security/asa/asa-command-
reference /S/cmdref3/s2.html) vemos la informaci�n de ese m�dulo

#T5.2 Instalar wireshark y observar c�mo fluye el tr�fico de red en uno de los
servidores web mientras se le hacen peticiones HTTP.

Aqu� muestro una foto del tr�fico que esta teniendo el balanceador de carga
de nginx, mientras desde el anfitri�n hago peticiones con el apache
benchmark [!imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema5/Ejercicio5.2.png)

#T5.3 Buscar informaci�n sobre caracter�sticas, disponibilidad para diversos
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
