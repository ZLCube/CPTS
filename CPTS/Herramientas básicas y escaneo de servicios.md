------------------------------------------------------------------------------------
Conexiones SSH
--------------------------------------------------------------------------------------------------------------------
Una conexión SSH se refiere a secure shell, más adelante en el escaneo de puertos con nmap entenderemos a que se refiere un puerto abierto, sin embargo hablando de SSH lo que nos permite es conectarnos en remoto a la terminal de un servidor o máquina linux ya sea con una clave pública conocida como ID_RSA o con una contraseña. Para establecer la conexión utilizaremos el siguiente comando: 

*__ssh usuario@ip__* a esta conexión se le pueden añadir parámetros como -i que nos permite pasarle un archivo id_rsa el cual debe tener el permiso 600, esto se lo podemos agregar con el comando 
*__chmod 600 id_rsa___*
Por el contrario con el parámetro -p le podemos proporcionar una contraseña, de cualquier forma en caso de no proporcionar parámetros la misma conexión nos lo va a solicitar. 

La conexión nos regresaría una shell que se ve algo así:

![[Pasted image 20230619185747.png]]

------------------------------------------------------------------------------------
Conexiones con NETCAT
--------------------------------------------------------------------------------------------------------------------

Así mismo también podemos establecer conexiones con netcat, estas las podemos hacer con el comando *__netcat, ncat o nc__* y en caso de no tener la herramienta instalada podemos descargarla con el comando *__sudo apt install netcat__*, esta herramienta nos permitirá poner puertos en escucha, establecer conexiones, enviar y jalar archivos, entre otras funciones sin embargo es algo que veremos más adelante. En este ejemplo podemos utilizar netcat para establecer una conexión o mandar una traza por protocolos TCP y UDP en busca de el servicio corriendo en el puesto especificado.

![[Pasted image 20230619190621.png]]

------------------------------------------------------------------------------------
Conexiones FTP 
--------------------------------------------------------------------------------------------------------------------

También tenemos conexiones por protocolo FTP o como sus siglas lo describen (File Transfer Protocol)
Este protocolo normalmente se aloja en el puerto 21 y podemos ver archivos  públicos.

El comando sería  *__ftp -p IP__* lo cual nos establecerá una consola interactiva donde prodremos listar archivos, subir o descargar los mismos. Para establecer una conexión segura normalmente se utiliza el comando SFTP en lugar de FTP aun que al estar vulnerando un sistema no hace falta.

![[Pasted image 20230619192946.png]]


------------------------------------------------------------------------------------
Conexiones SMB 
--------------------------------------------------------------------------------------------------------------------

Las conexiones por SMB se pueden realizar de la misma manera que FTP o SSH, esto va a depender de que servicio esté corriendo dentro del sistema a vulnerar, con el comando *__smbclient__* podemos establecer un cliente que nos permita ver el contenido de los archivos estableciendo una conexión por SMB, así mismo con parámetros como -L podemos listar los directorios y con -N podemos bypassear el prompt de contraseña, es decir saltarnos el paso de ingresar una contraseña para establecer la conexión.

De igual forma podemos usar el comando get para jalar archivos a nuestro sistema local.

![[Pasted image 20230619193706.png]]

También podemos proporcionar tanto usuario como contraseña para establecer una conexión. 

![[Pasted image 20230619193827.png]]

------------------------------------------------------------------------------------
Conexión SNMP 
--------------------------------------------------------------------------------------------------------------------

Para el servicio SNMP la autenticación y encriptación como modo de seguridad solo se agregaron hasta la versión 3, por lo que es un servicio  bastante explotable al menos en la versión 1 y 2c

Podemos utilizar el comando *__snmpwalk__* seguido de diferentes parámetros, como -v para definir la versión del servicio. Sin embargo no siempre se consigue establecer una conexión como en el siguiente ejemplo:

![[Pasted image 20230619222149.png]]

En estos casos tenemos una herramienta llamada *__onesixtyone__* la cual podemos encontrar en el siguiente link de GitHub con la finalidad de realizar ataques de fuerza bruta y crackear la credencial de acceso con un diccionario.  (https://github.com/trailofbits/onesixtyone)

![[Pasted image 20230619222323.png]]

[[Uso de NMAP]]
