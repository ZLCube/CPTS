
Para crear una clave privada que nos puede servir para cifrar archivos, conexiones, etc. Podemos usar la herramienta openssl con los siguientes parámetros, esto nos generará una clave privada:

```
openssl genrsa -out keyprivada.pem 2048
```

Así mismo podemos usar la clave privada para generar una clave pública con el siguiente comando de la herramienta openssl:

```
openssl rsa -pubout -in keyprivada.pem -out publica.pem
```

Podemos generar ambas claves con un solo comando:

```
openssl genrsa -aes128 -out privkey.pem 4096
```

Ejercicio: utiliza la llave privada o publica y cifra un documento con ella. (No el texto del documento, se tiene que cifrar el documento completo.)

Primero crearemos el archivo, yo lo haré de la siguiente forma: ```echo "prueba" > archivo.txt```

Crearemos nuestras llaves con los comandos que vimos en la explicación y posteriormente cifraremos el archivo con openssl, la clave privada y el parámetro rsautl -inkey

```
openssl rsautl -inkey keyprivada.pem -in archivo.txt -sign > cifrado.enc
```

Para descifrarlo usaremos la llave pública:  

```
openssl rsautl -inkey publica.pem -pubin -in cifrado.enc -out archivodescifrado.dec
```
