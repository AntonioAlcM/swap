# T6.1
## Aplicar con iptables una política de denegar todo el tráfico en una de las máquinas de prácticas. Comprobar el funcionamiento.
Para bloquear todo el tráfico tanto de entrada como de salida de bemos introducir estas tres instrucciones.
1. iptables -P INPUT DROP
2. iptables -P OUTPUT DROP
3. iptables -P FORWARD DROP

![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Ejercicio6.1.1.png)

La parte marcada en rojo corresponde a la máquina servidora donde he configurado el iptables. La parte de arriba es otra máquina desde donde hago un ping antes de configurar el iptables y debajo otro ping ya con el iptables configurado

## Aplicar con iptables una política de permitir todo el tráfico en una de las máquinas de prácticas. Comprobar el funcionamiento.

Para aceptar todo el tráfico tanto de entrada como de salida de bemos introducir estas tres instrucciones.
1. iptables -P INPUT ACCEPT
2. iptables -P OUTPUT ACCEPT
3. iptables -P FORWARD ACCEPT

![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Ejercicio6.1.2.png)

La parte marcada en rojo corresponde a la máquina servidora donde he configurado el iptables. La parte de arriba es otra máquina desde donde hago un ping antes de configurar el iptables y debajo otro ping ya con el iptables configurado

# T6.2 Comprobar qué puertos tienen abiertos nuestras máquinas, su estado, y qué programa o demonio lo ocupa.
 Yo para ello voy a usar el comando netstat -ap, el -a sirve para ver todos los puertos y con el -p podemos ver el pid de los programas que están usando los distintos puertos.

 ![imagen](https://github.com/AntonioAlcM/swap/blob/master/trabajos_clase/Ejercicio6.2.png)

# T6.3 Buscar información acerca de los tipos de ataques más comunes en servidores web, en qué consisten, y cómo se pueden evitar.

## 1. Inyección SQL (SQLi)
 Es una técnica para modificar una cadena de consulta de base de datos mediante la inyección de código en la consulta. El SQLI explota una posible vulnerabilidad donde las consultas se pueden ejecutar con los datos validados.

 La solución que he encontrado es evitar que el usuario interaccione directamente con la base de datos

## 2. DDoS
Son los intentos de inundar un sitio con solicitudes externas, por lo que ese sitio no podría estar disponible para los usuarios reales. Los ataques de denegación de servicio por lo general se dirigen a puertos específicos, rangos de IP o redes completas, pero se pueden dirigir a cualquier dispositivo o servicio conectado.

Una posible solución es implementar un Honeypot

## 3. Fuerza Bruta
Estos son básicamente intenta “romper” todas las combinaciones posibles de nombre de usuario + contraseña en una página web.

La mejor solución es hacer contraseñas cada vez masfuertes.

## 4.Cross Site Scripting
Consiste en inyectar scripts maliciosos en lo que serían sitios web inofensivos.

En algunos sitios proponen un grupo de medidas como solución, a continuación expondré las medidas

1. Análisis y filtrado de la información intercambiada
2. Aplicación de medidas de seguridad en el navegador en
tiempo de ejecución
