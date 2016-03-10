#*Ejercicio Tema 1*

***Apache*** puede mostrar contenido din�mico. Trabaja con gran cantidad de Perl, PHP y otros lenguajes de script, Java y p�ginas JSP, teniendo todo el soporte que se necesita para tener p�ginas din�micas.

***Nginx*** puede mostrar contenido est�tico, pero necesita herramientas externas para contenido din�mico, el consumo de ram es bajo. El resultado final es que Nginx puede servir a m�s clientes simult�neos con un mayor rendimiento que Apache con el mismo hardware. Puede ser implementado como balanceador de carga para otros servidores web.

***Lighttpd*** es apropiado para cualquier servidor que tenga problemas de carga. Lighttpd permite comunicarse con programas externos mediante FastCGI o SCGI, que son mejoras al CGI original (tambi�n soportado). De esta forma, se pueden usar programas en pr�cticamente cualquier lenguaje de programaci�n.
Tiene una importancia especial en PHP, para el que se han hecho mejoras espec�ficas.

***Cherokee*** es un servidor web multiplataforma. Su objetivo es ser r�pido y completamente funcional, sin dejar de ser liviano comparado con otros servidores web. La velocidad de carga de los sitios web es uno de los puntos fuertes de Cherokee Web Server. Puede ser implementado como balanceador de carga para otros servidores web.

***Node.js*** es un entorno JavaScript de lado de servidor que utiliza un modelo as�ncrono y dirigido por eventos. B�sicamente Node es adecuado cuando necesitas hacer muchas cosas al mismo tiempo, sobre todo muchas operaciones I/O (acceso a ficheros, bases de datos,�) a la vez. Y es especialmente bueno para aplicaciones realtime, que necesitan mantener una conexi�n persistente entre el buscador y el servidor (juegos online, chats, herramientas de colaboraci�n, etc ).

***Tomcat*** es s�lo un contenedor de servlets(son objetos que corren dentro y fuera del contexto de un contenedor de servlets y extienden su funcionalidad), es decir, que implementa s�lo la especificaci�n servletsy jsp