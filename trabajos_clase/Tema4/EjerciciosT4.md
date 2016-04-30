#**Ejercicio T4.1:**
**Buscar información sobre cuánto costaría en la actualidad un mainframe.
Comparar precio y potencia entre esa máquina y una granja web de unas
prestaciones similares.**

  > El único mainframe que he encontrado es uno de IBM el z13, el precio no
esta
claro en algunas páginas apuntan que dependiendo de las configuraciones puede
estar entre 75000 dólares y 2 millones de dólares. Las especificaciones que he
encontrado son:

  > > *la ram va desde 64GB hasta 10TB.

  > > *En cuanto al procesador lo poco que he encontrado indica que es de 5Ghz
y
tiene 8 núcleos de 22 nanómetros, esto lo que indica es que funciona como si
fuera 166 núcleos de 5GHZ.

 > Este mainframe puede albergar hasta 141 unidades de procesamiento en un solo
sistema y ejecute hasta 8.000 servidores virtuales, según la compañía.

  > Voy a intentar hacer la comparación con este servidor ya preparado, el HP
ProLiant
ML310e G8 XE E3-1220/8GB/2TB:

 > Especificaciones:

 > > *Procesador

   > > > Velocidad de reloj* 3.1 GHz

   > > > Modelo del procesador* Intel Xeon (4 núcleos, 3,1 GHz, 8 MB, 69 W)

   > > > Número de núcleos de procesador* 4

   > > > Número de procesadores instalados* 1

   > > > L2 cache 8 MB


 > > *Medios de almacenaje

   > > > Dos unidades de 1TB (2x1TB)

   > > >  Reguladores del almacenaje

   > > > Controlador de disco duro (1) Dynamic Smart Array B120i / ZM;

 > > *Memoria

   > > > Memoria interna* UDIMM de 8 GB

   > > > Memoria interna máxima* 32 GB

   > > > Tipo de memoria interna* 2R x8 PC3L-10600E-9

   > > > Ranuras de memoria* 4 ranuras DIMM; Máximo

  > Solo para igualar la ram de 10TB necesitas 320 ordenadores, cada ordenador
cuesta 735 euros lo que nos da un total de 235.000 euros.
Para igualar la capacidad de procesamiento necesitamos 67 ordenadores. En
conclusión es más factible una granja web que un mainframe, es verdad que en
números piensas que un mainframe merece más la pena, pero siempre es más barato
un ordenador que un mainframe, ojo lo estamos comparando con el mainframe de
mayor capacidad que ronda los 2 millones de dólares.



#**Ejercicio T4.2:**
**Buscar información sobre precio y características de balanceadores hardware
específicos. Compara las prestaciones que ofrecen unos y otros.**

 > **La familia LoadMaster de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.png)

 > **La familia loadbalancer.org de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.1.png)

 > **La familia F5 de balanceadores de carga de hardware**
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/tablaLBEjercicio4.2.2.png)

#**Ejercicio T4.3:**
**Buscar información sobre los métodos de balanceo que implementan los
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

 > De los balanceadores F5 no he conseguido información sobre el algoritmo que
implementa

#**Ejercicio T4.4:**
**Instala y configura en una máquina virtual el balanceador ZenLoadBalancer.**

 > Una vez instalado el ZenLoadBalancer entramos a la máquina desde el
navegador
introduciendo https://ip:444, una vez en la página principal accedemos a manage
y pinchamos en Farms, allí aparecerá un recuadro que pone Configure a new Farm
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.1.png)
 > Una vez que le damos a save&continue aparecerá la siguiente página
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.2.png)
introducimos la dirección virtual de nuestro servidor y el puerto que queramos
que use, le damos a save y aparecerá la siguiente página
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.3.png)
seleccionamos el botón edit de nuestra granja y pasaremos a la siguiente página
![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Tema4/Ejercicio4.4.4.png)
en el apartado edit real IP servers configurate añadimos las ips de nuestros
servidores.

Ya por último solo poner en marcha nuestro servidor.

#**Ejercicio T4.5:**
**Probar las diferentes maneras de redirección HTTP.**
**¿Cuál es adecuada y cual no lo es para hacer balanceo de carga global? ¿Por
qué?**

 > En HTML el principal problema es que te re direcciona este o no el servidor
funcionando

 > Java es el propio navegador el que te direcciona, problema no sabes si está o
no la página

 > PHP te re direcciona desde el servidor, en caso de que el servidor este caído
no realiza la petición, mientras que en los otros hacen la petición este o no
caído el servidor.

  > Para mi php es la mejor opción por lo anteriormente comentado y también por
la potencia que tienen el propio lenguaje. Pero personalmente el código de
JavaScript me resulta más intuitivo, también es debido a que JavaScript si lo he
estudiado y php no.

#**Ejercicio T4.6:**
**Buscar información sobre los bloques de IP para los distintos países o
continentes.**

 > En este [enlace](http://www.nirsoft.net/countryip/) podemos ver los bloques
de ip según cada país del mundo.  

#**Ejercicio T4.7:**
**Buscar información sobre métodos y herramientas para implementar GSLB.**

 > En la mayoría de los balanceadores hardware, el software tiene una opción
para implementar GSLB. En este
[enlace](http://www.clm.com.pe/productos/a10/ax-global-server-load-balancing.htm
)
podemos ver un ejemplo. Los balanceadores de LoadMaster también permite
implementar el GSLB

 > La familia LoadMaster de balanceadores de carga virtual también permite
implementar el GSLB, esta es una opción software

 > F5 también dispone de software y hardware, donde se puede implementar GSLB.

 > En cuanto métodos de balanceo están los vistos en clase de teoría, que son
los siguientes:
   1. Uso de DNS
   2. Redirección HTTP
   3. GSLB basado en DNS
   4. GSLB usando protocolos de enrutamiento
