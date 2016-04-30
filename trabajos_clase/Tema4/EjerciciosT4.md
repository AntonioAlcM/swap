#**Ejercicio T4.1:**
**Buscar informaci�n sobre cu�nto costar�a en la actualidad un mainframe.
Comparar precio y potencia entre esa m�quina y una granja web de unas
prestaciones similares.**

  > El �nico mainframe que he encontrado es uno de IBM el z13, el precio no
esta
claro en algunas p�ginas apuntan que dependiendo de las configuraciones puede
estar entre 75000 dolares y 2 millones de dolares. Las especificaciones que he
encontrado son:

  > > *la ram va desde 64GB hasta 10TB.

  > > *En cuanto al procesador lo poco que he encontrado indica que es de 5Ghz
y
tiene 8 n�cleos de 22 nan�metros, esto lo que indica es que funciona como si
fuera 166 nucleos de 5GHZ.

 > Este mainframe puede albergar hasta 141 unidades de procesamiento en un solo
sistema y ejecute hasta 8.000 servidores virtuales, seg�n la compa��a.

  > Voy a intentar hacer la comparaci�n con este servidor ya preparado, el HP
ProLiant
ML310e G8 XE E3-1220/8GB/2TB:

 > Especificaciones:

 > > *Procesador

   > > > Velocidad de reloj* 3.1 GHz

   > > > Modelo del procesador* Intel Xeon (4 n�cleos, 3,1 GHz, 8 MB, 69 W)

   > > > N�mero de n�cleos de procesador* 4

   > > > N�mero de procesadores instalados* 1

   > > > L2 cache 8 MB


 > > *Medios de almacenaje

   > > > Dos unidades de 1TB (2x1TB)

   > > >  Reguladores del almacenaje

   > > > Controlador de disco duro (1) Dynamic Smart Array B120i / ZM;

 > > *Memoria

   > > > Memoria interna* UDIMM de 8 GB

   > > > Memoria interna m�xima* 32 GB

   > > > Tipo de memoria interna* 2R x8 PC3L-10600E-9

   > > > Ranuras de memoria* 4 ranuras DIMM; M�ximo

  > Solo para igualar la ram de 10TB necesitas 320 ordenadores, cada ordenador
cuesta 735 euros lo que nos da un total de 235.000 euros.
Para igualar la capacidad de procesamiento necesitamos 67 ordenadores. En
conclusi�n es mas factible una granja web que un mainframe, es verdad que en
n�meros piensas que un mainframe merece mas la pena, pero siempre es mas barato
un ordenador que un mainframe, ojo lo estamos comparando con el mainframe de
mayor capacidad que ronda los 2 millones de dolares.



#**Ejercicio T4.2:**
**Buscar informaci�n sobre precio y caracter�sticas de balanceadores hardware
espec�ficos. Compara las prestaciones que ofrecen unos y otros.**

 > **La familia LoadMaster de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.png)

 > **La familia loadbalancer.org de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.1.png)

 > **La familia F5 de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.2.png)

#**Ejercicio T4.3:**
**Buscar informaci�n sobre los m�todos de balanceo que implementan los
dispositivos recogidos en el ejercicio 4.2**

 > Los balanceadores de LoadMaster implementan:

  > > Round Robin

  > > Weighted Round Robin

  > > Least Connection

  > > Weighted Least Connection

  > > Agent-based Adaptive

  > > Chained Failover (Fixed Weighting)

  > > Source-IP Hash

  > > Layer 7 Content Switching

  > > Global Server Load Balancing (GSLB)

  > > SDN Adaptive(Este solo se implementa en algunos balanceadores)

 > Los balanceadores de loadbalancer.org implementan:

  > > Round Robin

  > > Weighted Round Robin

  > > Least Connection

  > > Weighted Least Connection

  > > Agent-based Adaptive (Windows and Linux Agents)

  > > Layer 7 Content Switching

  > > Destination Hash for transparent proxy

 > De los balanceadores F5 no he conseguido informaci�n sobre el algoritmo que
implementa

#**Ejercicio T4.4:**
**Instala y configura en una m�quina virtual el balanceador ZenLoadBalancer.**

 > Una vez instalado el ZenLoadBalancer entramos a la m�quina desde el
navegador
introduciendo https://ip:444, una vez en la p�gina principal accedemos a manage
y pinchamos en Farms, all� aparecer� un recuadro que pone Configure a new Farm
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.1.png)
 > Una vez que le damos a save&continue aparecer� la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.2.png)
introducimos la direcci�n virtual de nuestro servidor y el puerto que queramos
que use, le damos a save y aparecer� la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.3.png)
seleccionamos el bot�n edit de nuestra granja y pasaremos a la siguiente p�gina
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.4.png)
en el apartado edit real IP servers configurate a�adimos las ips de nuestros
servidores.

Ya por �ltimo solo poner en marcha nuestro servidor.

#**Ejercicio T4.5:**
**Probar las diferentes maneras de redirecci�n HTTP.**
**�Cu�l es adecuada y cu�l no lo es para hacer balanceo de carga global? �Por
qu�?**

 > En HTML el principal problema es que te redirecciona este o no el servidor
funcionando

 > Java es el propio navegador el que te direcciona, problema no sabes si esta o
no la p�gina

 > PHP te redirecciona desde el servidor, en caso de que el servidor este ca�do
no realiza la petici�n, mientras que en lo otros hacen la petici�n este o no
ca�do el servidor.

  > Para mi php es la mejor opci�n por lo anteriormente comentado y tambi�n por
la potencia que tienen el propio lenguaje. Pero personalmente el c�digo de
javascript me resulta mas intuitivo, tambi�n es debido a que javascript si lo he
estudiado y php no.

#**Ejercicio T4.6:**
**Buscar informaci�n sobre los bloques de IP para los distintos pa�ses o
continentes.**

 > En este [enlace](http://www.nirsoft.net/countryip/) podemos ver los bloques
de ip seg�n cada pa�s del mundo.  

#**Ejercicio T4.7:**
**Buscar informaci�n sobre m�todos y herramientas para implementar GSLB.**

 > En la mayor�a de los balanceadores hardware, el software tiene una opci�n
para implementar GSLB. En este
[enlace](http://www.clm.com.pe/productos/a10/ax-global-server-load-balancing.htm
)
podemos ver un ejemplo. Los balanceadores de LoadMaster tambi�n permite
implementar el GSLB

 > La familia LoadMaster de balanceadores de carga virtual tambi�n permite
implementar el GSLB, esta es una opci�n software

 > F5 tambi�n dispone de software y hardware, donde se puede implementar GSLB.

 > En cuanto m�todos de balanceo est�n los vistos en clase de teor�a, que son
los siguientes:
   1. Uso de DNS
   2. Redirecci�n HTTP
   3. GSLB basado en DNS
   4. GSLB usando protocolos de enrutamiento
