En linux tenemos algo llamado ruta alterna y ruta absoluta, esto quiere decir que nosotros tenemos una ubicación donde se aloja alguna aplicación, comando o script. 

Ruta relativa o ALTERNA, es la que encuentra por orden en el sistema, si tenemos por ejemplo distintas versiones de Python en distintos directorios, nuestro sistema utilizará cualquiera de las versiones que vea conveniente, esto lo considera en base a prioridad en un archivo de entorno. 

Por ejemplo con el comando *__whoami__* podemos ver que usuario somos, sin embargo si utilizamos el comando *__which whoami__* te muestra donde se aloja el comando/script/aplicación, también se puede usar el comando *__command -v whoami__* y nos arrojaría el mismo resultado.

*__echo $PATH__* para ver la ruta alterna del comando. 

La ruta ABSOLUTA es especificar cual quieres que use, por ejemplo /usr/bin/whoami donde nosotros le especificamos al sistema de dónde queremos que agarre el script, archivo o aplicación. 

El path hijacking sirve para cambiar binarios de forma relativa y así engañar a los comandos.

/etc/passwd te muestra los usuarios con id de usuario, grupo, tipo de shell y ruta al directorio al cual te redirige el cd

echo $SHELL te muestra la shell que utilizas, una zsh te permite añadir plugins, estética y es más cómoda a diferencia de una bash 

Las shells disponibles las puedes ver en la ruta /etc/shells con el comando "cat /etc/shells" y puedes editarlas para añadir o eliminar

Entender los tipos de ruta nos ayudará posterior mente cuando busquemos una escalada de privilegios utilizando técnicas como explotación binaria o path hijacking.

------------------------------------------------------------------------------------
DESCRIPTORES

Honestamente hablando de descriptores no es un tema del cual debas de preocuparte, no los vas a utilizar casi nunca, sin embargo hay un descriptor que si vas a estar utilizando y a este se le llama redirector. Un redirector prácticamente manda el resultado de un comando hacia donde nosotros le indiquemos. A continuación tienes un ejemplo.

Podemos redirigir el código de error para que no se muestre en pantalla con *__2>/dev/null__*, dev null es un archivo que funciona como bote de basura.

disown independiza un proceso de la consola, se utiliza de la sigiente forma "programa &>/dev/null & disown" 

p-id es el numero identificador de proceso, cada aplicación tiene un identificador y este no se puede compartir con otras aplicaciones 

stder es un código de error el cual podemos representar con un número 2 

stdout es el código exitoso, el cual podemos redirigir también al dev null con "comando > /dev/null", podemos combinar stder y stdout con "comando > /dev/null 2>&1"

La forma más cómoda de combinar ster y stdout es con "comando &>/dev/null"

exec 3<> file "nos crea un archivo  "el <> nos indican lectura y escritura""

Podemos enviar outputs al archivo creado con >&3 el cual es el numero que le definimos al primer descriptor

exec 3<>&- nos cierra el descriptor que creamos
exec 8>&3 nos permite clonar lo que hay en un descriptor "es como hacer una copia"
exec 8>&3- nos clona el descriptor y cierra el que copiamos

[[Permisos en Linux]]