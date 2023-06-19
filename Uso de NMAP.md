Nmap es una herramienta que nos permite escanear una dirección IP así como también una dirección web en busca de puestos abiertos y servicios corriendo dentro de este mismo.

Para instalarla en cualquier distribución de linux es tan sencillo como usar el comando: 

__*sudo apt install nmap

Para ejecutar nuestro escaneo básico de puertos podemos usar el comando *__nmap__* seguido de la dirección IP, sin embargo a pesar de ser un escaneo sencillo es un escaneo bastante ruidoso, por lo que podemos agregar diferentes parámetros para hacerlo más silencioso, rápido e incluso enfocado a lo que buscamos.
A continuación tienes unos cuantos parámetros que puedes usar con nmap con sus respectivas descripciones y un ejemplo de cómo quedaría el escaneo completo.

- *__-p-__* escanea todos los puertos, también podemos especificar los puertos con -p20,80,etc. o podemos especificar un rango de puertos con -p 20-200 que escaneará del puerto 20 al puerto 200
- *__--open__*  este comando nos ayuda a escanear únicamente los puertos abiertos
- *__-sS__*  esto significa que vamos a escanear únicamente protocolos TCP
- *__-n__*  significa que no va aplicar resolución DNS para evitar nombres de dominio
- *__-Pn__*  va a saltarnos el host Discovery 
- *__--min-rate__*  va a indicar que no lancemos paquetes menores a x cantidad, un escaneo rápido puede      utilizar un minrate de 5000, el comando quedaría como *__--min-rate 5000__*
- *__-vvv__*  la v de este comando significa verbose, esto significa que podemos reportar información más detallada del escaneo, al usar tres v nos referimos a triple verbose por lo que el escaneo será aun más detallado con el resultado
- -*__sC y sV__*  son scripts que nos ayudan a determinar la versión del servicio, aun que su uso apropiado debe ser más enfocado a puertos que sabemos que están abiertos y se pueden combinar en un solo comando por ejemplo *__-sCV__* 
- *__-sU__*  escanea protocolos UDP
- *__-oG__*  nos almacena el escaneo en un archivo de formato grepeable (extraíble), es decir un archivo del cual podemos extraer información mediante scripts
- *__-oN__*  nos almacena el escaneo en un archivo de formato NMAP, estos formatos son legibles con el comando *__cat__* dentro de la consola linux

Ejemplo: 

__*sudo nmap -p- --open -sS -n -Pn --min-rate 5000 (IP) -oG escaneo*__



