#Pasos para realizar la práctica 2
**1)** Primero he tenido que configurar /etc/ssh/sshd_config y cambiar PermitRootLogin a yes, después lo he reiniciado con el comando service ssh restart.
**2)** He ejecutado el comando rsync -avz -e ssh IPmaquina1:/var/www/ /var/www/ en la máquina 2
**3)** Luego para que no me pidiera constantemente la clave, he generado una clave con ssh-keygen -t dsa, esto lo he hecho en la máquina 2.
**4)** Luego en la máquina 2 he ejecutado este comando ssh-copy-id -i .ssh/id_dsa.pub IPmaquina1, para copiar la clave en la máquina 1.
**5)**Ahora hemos configurado el crontab para automatizar la clonación de los servidores, para ello debemos editar /etc/crontab en la máquina 2. Al final del archivo añadiremos  la siguiente línea *****  rsync -avz --delete -e ssh IPmaquina1:/var/www/ /var/www/ . Importante añadir el delete porque sino no borrará los archivos.

Con esto está la práctica terminada.