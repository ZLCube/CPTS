Cuando hablamos de enumeración, hablamos de que podemos buscar subdominios y subdirectorios. 

Pero, ¿A qué se refiere esto? 

Cuando tenemos un servicio web corriendo en los puertos 80, 8080 y 443 tenemos algo llamado dominio. Esto puede representarse como el nombre de la página el cual va apuntado a una dirección IP. Por ejemplo la dirección IP 10.10.10.10 puede apuntar al sitio hackthebox.com 

Al hablar de listar subdominios hablamos de que podemos buscar palabras que vayan antes del dominio por ejemplo subdominio.hackthebox.com

Lo mismo con los subdirectorios, sin embargo los subdirectorios como su propio nombre lo dice son directorios que derivan de un dominio por ejemplo hackthebox.com/subdominio esto con la finalidad de encontrar páginas o servicios alojados en un servidor que estén públicos y no deberían estarlo o buscar formas diferentes de vulnerar un sitio.

Existen diferentes herramientas para el listado de subdominios y subdirectorios y los más comunes son gobuster, wfuzz y ffuf.

Aparte de la herramienta que utilicemos para listar subdominios y subdirectorios vamos a necesitar la lista de donde sacar las palabras a fuzzear, a esta lista se le conoce como diccionario. A continuación te dejo un enlace a GitHub donde vas a poder encontrar la famosa [seclist](https://github.com/danielmiessler/SecLists), esta cuenta con diccionarios para ataques de fuerza bruta y listado de subdominios y subdirectorios. En sistemas base Debian como Kali o Parrot puedes usar el comando *__sudo apt install seclists__* .

![](https://github.com/ZLCube/CPTS/blob/main/CPTS/Recursos/Pasted%20image%2020230619235833.png)

Para listar subdominios con gobuster vamos a utilizar el siguiente comando:

*__gobuster dns -d dominio.com -w /usr/share/SecLists/Discovery/DNS/namelist.txt__* donde los parámetros -d representan el sitio web que vamos a utilizar para descubrir subdominios y -w nos va a especificar la lista de palabras con la que realizaremos el ataque de diccionario.

![[Pasted image 20230619235904.png]]

Para listar subdirectorios vamos a usar el siguiente comando:

*__gobuster dir -u http://pagina -w /usr/share/dirb/wordlists/common.txt__* es prácticamente el mismo comando con la diferencia de la lista que usaremos ya que es diferente en cuanto a nombres y en lugar de usar dns usaremos dir

![[Pasted image 20230620000002.png]]

Como parte del reconocimiento aparte de listado de subdominios y subdirectorios es necesario ver qué servicios y tecnologías utiliza la página que queremos vulnerar. Esto lo podemos hacer con una extensión del navegador llamada wappalyzer o por otro lado podemos usar una alternativa desde la consola linux. Esta herramienta viene preinstalada y se llama whatweb, a continuación te dejo un ejemplo: 

![[Pasted image 20230619235428.png]]

Esto nos ayuda a ver que tecnologías y versiones usa para poder explotarlas posteriormente. Así mismo podemos ver el código fuente del sitio con el comando *__curl__* y así ver si hay contraseñas hardcodeadas o vulnerabilidades en el código fácil de explotar. 

![[Pasted image 20230619235936.png]]

Una alternativa a curl puede ser apretar el atajo de teclas *__control + u__* en nuestro navegador y nos mostrará el código fuente, a continuación un ejemplo donde vemos credenciales escritas en el código del sitio web:

![[Pasted image 20230619235731.png]]

[[Uso de NMAP]]
[[Herramientas básicas y escaneo de servicios]]
