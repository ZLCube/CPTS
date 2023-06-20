Si bien entender cómo funciona la consola en linux es importante, también debemos entender qué significan los permisos en linux, esto no solo nos ayuda a mantener nuestros archivos seguros si no que también es una pieza clave que utilizarás a la hora de escalar privilegios o vulnerar un sistema.

Las siglas a lado de un archivo cuando usamos el comando __*ls -l*__ representan los permisos, a continuación tienes una explicación de cada sigla:

- r = read
- w = write
- x = excute 

Visto de manera ejemplificada:

En caso de directorio (carpeta) los permisos nos aparecerían de la siguiente manera ---> drwx r-x r-x
En caso de archivo los permisos nos aparecerían de la siguiente manera                    --->  .rw- r-- r--
En caso de archivo ejecutable los permisos nos aparecerían de la siguiente manera  --->  .rwx rwx r-x

Los permisos se dividen en tres secciones 421 | 421 | 421 esto es una vista del permiso en octal pero lo entenderás más adelante

El primer segmento pertenece al propietario 
El segundo segmento es permiso del grupo
El tercer segmento representa los permisos de otros

Se visualiza de la siguiente forma: 
drwx r-x r-x root root "fecha" "nombre_de_la_carpeta" 
.rwx r-x r-x user group "fecha" "nombre_del_archivo" 

*__useradd + Nombre de usuario__*  te permite crear un nuevo usuario, con parámetro *__-s__* podemos asignar el tipo de shell por ejemplo "/bin/bash", con el parámetro -d podemos crearle un directorio como "/home/usuario"
*__usermod__* te permite agregar usuarios a grupos ejemplo "useradd -a -G Grupo usuario"

------------------------------------------------------------------------------------
PERMISOS EN OCTAL
--------------------------------------------------------------------------------------------------------------------

Es más sencillo viéndolo de la siguiente manera 421 421 421, si hay letra es 1, si no hay letra es 0, por ejemplo RWX sería 111 y R-X sería 101, dependiendo si tiene 1 son los números que sumaremos
Si tenemos 101 significa que vamos a sumar 4 y 1 ya que el 2 es 0 es decir que no hay valor por lo que la sumatoria de el grupo del permiso sería 5

En permisos octal se pueden referenciar como 755 al permiso RWX R-X R-X
------------------------------------------------------------------->111   101 101
------------------------------------------------------------------->421   4-1  4-1
------------------------------------------------------------------->  7       5     5

*__chmod +t carpeta__*  agrega sticky bit para que solo el propietario o root puedan modificar esos archivos/directorios

lsattr permite ver los permisos de un archivo y validar si se puede eliminar o no
chattr +i -v  hace inmutable un archivo
chattr -i -v  hace vulnerable un archivo

permiso suid se asigna con chmod u+s o chmod 4755 

------------------------------------------------------------------------------------
Escalada de privilegios
--------------------------------------------------------------------------------------------------------------------

Ahora, recuerdas que te comenté que entender los permisos nos ayuda a una escalada de privilegios?

Con el siguiente comando podemos ver que aplicaciones y archivos tienen permisos de administrador:

*__sudo find / -type f -perm -4000 2>/dev/null__* con "sudo find / -type f -perm -4000" podemos buscar quién tiene permiso SUID ROOT (admin) y con "2>/dev/null" eliminas el output ya que el texto que nos arroje el log del comando lo mandaremos a la ruta /dev/null, a esta ruta se le conoce como el bote de basura en linux.

Ser suid o sgid te permite ejecutar aplicaciones con permiso de root a fin de buscar escalar accesos de admin del sistema. 

El permiso sgid se asigna con chmod g+s o chmod 2755 

![Rutas y descriptores](https://github.com/ZLCube/CPTS/blob/main/CPTS/Rutas%20y%20descriptores.md)
