Como parte de la ciberseguridad, es necesario saber manejar los sistemas operativos, el más popular dentro del nicho del hacking es Kali y Parrot linux, sin embargo otras distribuciones también nos van a servir. Lo más importante es saber moverte en la consola. Es por eso que a continuación te traigo la lista de comandos más básicos y más usados, con la finalidad de que aprendas a moverte en la terminal. No es necesario que los memorices, eventualmente los usarás por instinto.

- __*cd*__  Moverte entre carpetas, puedes pasarle la ruta completa de la carpeta o usar, para regresar a la carpeta anterior puedes escribir  __*cd ..*__ o  __*cd*__ para ir al directorio principal del usuario
- __*ls*__  Muestra los archivos en el directorio en el que estás, el parámetro  __*-la*__ nos va a mostrar archivos ocultos  y el parámetro __*-l*__ te muestra los permisos de cada archivo
- __*cat*__  leer el contenido de un archivo
- __*nano*__  editor de texto para editar el contenido de un archivo, también puedes usar  __*mousepad*__ en caso de Kali para tener un editor más cómodo fuera de la terminal
- __*mkdir*__  crear una carpeta
- __*rm -r*__ eliminar carpeta independientemente de si tiene contenido o no
- __*sudo su*__ convertirse en usuario administrador (Pide contraseña)
- __*mv*__  archivo ruta_destino  nos permite mover de directorios, archivos, carpetas, etc.
- __*cp*__  copia archivos o directorios
- __*clear*__  limpia la consola
- __*pwd*__  Muestra el directorio en el que estás
- control + L Limpia la consola sin borrar lo que estás escribiendo
- flecha hacia arriba Te permite usar comando anterior sin tener que escribirlo
- flecha hacia abajo te permite limpiar lo que estas escribiendo
- flecha a la derecha --> Te permite autocompletar lo que estas escribiendo según el predictor de texto
- flecha a la izquierda <-- Te permite mover entre el texto escrito para modificarlo
- __*--version*__ te permite ver la versión del programa que quieras utilizar por ejemplo (git --version)
-  __*tecla tab*__ te permite completar nombre de archivos, directorios o comandos
- control shift c Te permite copiar lo que seleccionas
- control shift v Te permite pegar el porta papeles
- control c Termina un proceso que está en ejecución
- control o Guardar archivo
- control x Salir de archivo
- control w buscar palabra clave
- __*chmod*__ te permite cambiar los permisos, ejecución, lectura, edición. por ejemplo (chmod +x script.sh) te daría permiso de ejecutar un script sin permiso de ejecución"
- __*./*__ "te permite ejecutar un archivo, por ejemplo (./script.sh) te permite ejecutar el script que previamente le dimos permiso de ejecución"
- __*echo*__  "Te permite imprimir en pantalla texto, se le pueden pasar parámetros como echo "hola mundo" y nos muestra un hola mundo en pantalla o echo $PATH para mostrar un directorio"
- __*grep*__  "Te permite buscar una palabra clave (se conoce como "pipear"), por ejemplo cat documento.txt | grep "Palabra a buscar "
- __*git clone*__  "url" te permite clonar un repositorio de GitHub para instalar herramientas 
- __*;*__  con punto y coma puedes separar comandos, esto te permite hacer múltiples comandos en una sola línea
- __*&&*__ Te permite ejecutar más de un comando por línea pero el siguiente solo se ejecutará si el primero es exitoso y no sale error
- __*||*__ Te permite ejecutar un comando u otro, si el primero no se ejecuta entonces ejecuta el segundo
- __*touch*__  file.txt te ayuda a crear un archivo con el formato que desees, a diferencia de nano este solo crea el archivo, no permite editarlo
- __*-f *__ el parámetro -f te permite forzar, es decir que no va a preguntar y va a realizar la acción
- __*-v*__  significa verbose significa que nos dará información mas detallada del resultado de un comando
- __*| xargs*__  te permite agregar parámetros extra al resultado de un comando


![Permisos en Linux](https://github.com/ZLCube/CPTS/blob/main/CPTS/Permisos%20en%20Linux.md)

![Rutas y descriptores](https://github.com/ZLCube/CPTS/blob/main/CPTS/Rutas%20y%20descriptores.md)

![Herramientas básicas y escaneo de servicios](https://github.com/ZLCube/CPTS/blob/main/CPTS/Herramientas%20b%C3%A1sicas%20y%20escaneo%20de%20servicios.md)

