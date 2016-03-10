#*Ejercicio Tema 1*

***Apache*** puede mostrar contenido dinámico. Trabaja con gran cantidad de Perl, PHP y otros lenguajes de script, Java y páginas JSP, teniendo todo el soporte que se necesita para tener páginas dinámicas.

***Nginx*** puede mostrar contenido estático, pero necesita herramientas externas para contenido dinámico, el consumo de ram es bajo. El resultado final es que Nginx puede servir a más clientes simultáneos con un mayor rendimiento que Apache con el mismo hardware. Puede ser implementado como balanceador de carga para otros servidores web.

***Lighttpd*** es apropiado para cualquier servidor que tenga problemas de carga. Lighttpd permite comunicarse con programas externos mediante FastCGI o SCGI, que son mejoras al CGI original (también soportado). De esta forma, se pueden usar programas en prácticamente cualquier lenguaje de programación.
Tiene una importancia especial en PHP, para el que se han hecho mejoras específicas.

***Cherokee*** es un servidor web multiplataforma. Su objetivo es ser rápido y completamente funcional, sin dejar de ser liviano comparado con otros servidores web. La velocidad de carga de los sitios web es uno de los puntos fuertes de Cherokee Web Server. Puede ser implementado como balanceador de carga para otros servidores web.

***Node.js*** es un entorno JavaScript de lado de servidor que utiliza un modelo asíncrono y dirigido por eventos. Básicamente Node es adecuado cuando necesitas hacer muchas cosas al mismo tiempo, sobre todo muchas operaciones I/O (acceso a ficheros, bases de datos,…) a la vez. Y es especialmente bueno para aplicaciones realtime, que necesitan mantener una conexión persistente entre el buscador y el servidor (juegos online, chats, herramientas de colaboración, etc ).

***Tomcat*** es sólo un contenedor de servlets(son objetos que corren dentro y fuera del contexto de un contenedor de servlets y extienden su funcionalidad), es decir, que implementa sólo la especificación servletsy jsp