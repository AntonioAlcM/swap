#Pasos para realizar la pr�ctica 2
**1)** Primero he tenido que configurar /etc/ssh/sshd_config y cambiar PermitRootLogin a yes, despu�s lo he reiniciado con el comando service ssh restart.
**2)** He ejecutado el comando rsync -avz -e ssh IPmaquina1:/var/www/ /var/www/ en la m�quina 2
**3)** Luego para que no me pidiera constantemente la clave, he generado una clave con ssh-keygen -t dsa, esto lo he hecho en la m�quina 2.
**4)** Luego en la m�quina 2 he ejecutado este comando ssh-copy-id -i .ssh/id_dsa.pub IPmaquina1, para copiar la clave en la m�quina 1.
**5)**Ahora hemos configurado el crontab para automatizar la clonaci�n de los servidores, para ello debemos editar /etc/crontab en la m�quina 2. Al final del archivo a�adiremos  la siguiente l�nea *****  rsync -avz --delete -e ssh IPmaquina1:/var/www/ /var/www/ . Importante a�adir el delete porque sino no borrar� los archivos.

Con esto est� la pr�ctica terminada.