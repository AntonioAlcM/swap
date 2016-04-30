# Práctica 4
En esta práctica hemos tenido que usar un script php para darle carga al servidor. A continuación pongo una foto del script que implemente

![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/script.png)

## Tablas de datos
Ahora voy a exponer todos los datos obtenidos:

### Máquina servidor
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Servidor.png)

### Nginx
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Nginx.png)

### Haproxy
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Haproxy.png)

##Diagramas

### Apache Benchmark
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Diagrama_Apache.png)

### Siege
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Diagrama_Siege.png)

### JMeter
![imagen](https://github.com/AntonioAlcM/swap/blob/master/practica4/Tablas/Diagrama_Siege.png)

## Conclusiones
La verdad me ha resultado complicado sacar conclusiones, en algunos casos podemos ver como cuando el servidor esta ocupado no admite peticiones y entonces nos devuelve el 100% de los fallos, por lo demás no hay grandes picos los servidores suelen comportarse de forma homogénea.

En líneas generales cuando lanzas el apache benchmark, podemos observar que el haproxy se comporta mejor que el Nginx, en cambio si usamos Siege es Nginx el que mejores datos aporta.

En Jmeter según el parámetro que busques es mejor uno u otro.
