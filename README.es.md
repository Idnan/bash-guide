<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Tabla de Contenidos
  1. [Operaciones Básicas](#1-operaciones-básicas)  
    1.1. [Operaciones con Archivos](#11-operaciones-con-archivos)  
    1.2. [Operaciones de Texto](#12-operaciones-de-texto)  
    1.3. [Operaciones de Directorio](#13-operaciones-de-directorio)  
    1.4. [SSH, Información del Sistema y Red](#14-ssh-información-del-sistema-y-red)  
    1.5. [Operaciones de Monitoreo de Procesos](#15-operaciones-de-monitoreo-de-procesos)
  2. [Programación Básica en Shell](#2-programación-básica-en-shell)  
    2.1. [Variables](#21-variables)  
    2.2. [Arreglos](#22-arreglos)  
    2.3. [Sustitución de Cadenas](#23-sustitución-de-cadenas)  
    2.4. [Otros Trucos con Cadenas](#24-otros-trucos-con-cadenas)  
    2.5. [Funciones](#25-funciones)  
    2.6. [Condicionales](#26-condicionales)  
    2.7. [Bucles](#27-bucles)  
    2.8. [Expresiones Regulares](#28-expresiones-regulares)  
    2.9. [Tuberías (Pipes)](#29-tuberías-pipes)  
  3. [Trucos](#3-trucos)  
  4. [Depuración](#4-depuración)  
  5. [Multi-threading](#5-multi-threading)

# 1. Operaciones Básicas

### a. `export`
Muestra todas las variables de entorno. Si deseas ver el detalle de una variable específica, usa `echo $NOMBRE_VARIABLE`.  
```bash
export
```
Ejemplo:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
`whatis` muestra la descripción de comandos de usuario, llamadas al sistema, funciones de biblioteca y otros elementos en las páginas del manual.
```bash
whatis algo
```
Ejemplo:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
`whereis` busca ejecutables, archivos fuente y páginas del manual usando una base de datos construida automáticamente por el sistema.
```bash
whereis nombre
```
Ejemplo:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
`which` busca ejecutables en los directorios especificados por la variable de entorno PATH. Este comando imprime la ruta completa del ejecutable encontrado.
```bash
which nombre_programa
```
Ejemplo:
```bash
$ which php
/c/xampp/php/php
```

### e. `clear`
Limpia el contenido de la ventana de la terminal.

## 1.1. Operaciones con Archivos
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-less">less</a></td>
      <td><a href="#m-lpq">lpq</a></td>
      <td><a href="#n-lpr">lpr</a></td>
      <td><a href="#o-lprm">lprm</a></td>
      <td><a href="#p-ls">ls</a></td>
      <td><a href="#q-more">more</a></td>
      <td><a href="#r-mv">mv</a></td>
      <td><a href="#s-rm">rm</a></td>
      <td><a href="#t-tail">tail</a></td>
      <td><a href="#u-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
Puede usarse para los siguientes propósitos en UNIX o Linux:
* Mostrar archivos de texto en pantalla
* Copiar archivos de texto  
* Combinar archivos de texto  
* Crear nuevos archivos de texto  
```bash
cat archivo
cat archivo1 archivo2
cat archivo1 archivo2 > nuevo_archivo_combinado
cat < archivo1 > archivo2 #copia archivo1 en archivo2
```

### b. `chmod`
El comando `chmod` significa "change mode" (cambiar modo) y permite modificar los permisos de lectura, escritura y ejecución de tus archivos y carpetas. Para más información consulta este [enlace](https://ss64.com/bash/chmod.html).
```bash
chmod -opciones archivo
```

### c. `chown`
El comando `chown` significa "change owner" (cambiar propietario) y permite cambiar el dueño de un archivo o carpeta, que puede ser un usuario y un grupo. El uso básico es sencillo: primero va el usuario (propietario) y luego el grupo, separados por dos puntos.
```bash
chown -opciones usuario:grupo archivo
```

### d. `cp`
Copia un archivo de una ubicación a otra.  
```bash
cp archivo1 archivo2
```
Donde `archivo1` es la ruta de origen y `archivo2` es la ruta de destino.

### e. `diff`
Compara archivos y lista sus diferencias.  
```bash
diff archivo1 archivo2
```

### f. `file`
Determina el tipo de un archivo.  
```bash
file archivo
```
Ejemplo:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```

### g. `find`
Busca archivos dentro de un directorio.
```bash
find directorio opciones patrón
```
Ejemplo:
```bash
$ find . -name README.md
$ find /home/usuario1 -name '*.png'
```

### h. `gunzip`
Descomprime archivos comprimidos con gzip.  
```bash
gunzip archivo
```

### i. `gzcat`
Permite ver el contenido de un archivo comprimido con gzip sin necesidad de descomprimirlo.  
```bash
gzcat archivo
```

### j. `gzip`
Comprime archivos.  
```bash
gzip archivo
```

### k. `head`
Muestra las primeras 10 líneas de un archivo.  
```bash
head archivo
```

### l. `less`
Muestra el contenido de un archivo o la salida de un comando, una página a la vez. Es similar a [more](#q-more), pero tiene funciones más avanzadas y permite navegar tanto hacia adelante como hacia atrás en el archivo.  
```bash
less archivo
```

### m. `lpq`
Consulta la cola de impresión.  
```bash
lpq
```
Ejemplo:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### n. `lpr`
Imprime un archivo.  
```bash
lpr archivo
```

### o. `lprm`
Elimina un trabajo de la cola de impresión.  
```bash
lprm número_de_trabajo
```

### p. `ls`
Lista tus archivos. `ls` tiene muchas opciones: `-l` lista los archivos en "formato largo", que incluye el tamaño exacto, el propietario, los permisos y la última fecha de modificación. `-a` lista todos los archivos, incluyendo los ocultos. Para más información consulta este [enlace](https://ss64.com/bash/ls.html).  
```bash
ls opción
```
Ejemplo:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### q. `more`
Muestra la primera parte de un archivo (avanza con la barra espaciadora y escribe `q` para salir).  
```bash
more archivo
```

### r. `mv`
Mueve un archivo de una ubicación a otra.  
```bash
mv archivo1 archivo2
```
Donde `archivo1` es la ruta de origen y `archivo2` es la ruta de destino.

También se puede usar para renombrar un archivo:
```bash
mv nombre_viejo nombre_nuevo
```

### s. `rm`
Elimina un archivo. Usar este comando en un directorio genera el error:  
`rm: directory: is a directory`  
Para eliminar un directorio debes usar `-r`, que elimina el contenido de forma recursiva. Opcionalmente puedes agregar `-f` para forzar la eliminación sin pedir confirmación.
```bash
rm archivo
```

### t. `tail`
Muestra las últimas 10 líneas de un archivo. Usa `-f` para mostrar el contenido en tiempo real mientras el archivo crece.  
```bash
tail archivo
```

### u. `touch`
Actualiza las marcas de tiempo de acceso y modificación de un archivo. Si el archivo no existe, lo crea.
```bash
touch archivo
```
Ejemplo:
```bash
$ touch truco.md
```

## 1.2. Operaciones de Texto

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
`awk` es el comando más útil para manipular archivos de texto. Opera sobre un archivo completo, línea por línea. Por defecto usa espacios en blanco para separar los campos. La sintaxis más común es:

```bash
awk '/patrón_de_búsqueda/ { acción_si_el_patrón_coincide; }' archivo_a_analizar
```

Tomemos el archivo `/etc/passwd` como ejemplo. Aquí hay una muestra de su contenido:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Ahora obtengamos solo el nombre de usuario de este archivo. `-F` especifica el delimitador de campos, en este caso `:`. `{ print $1 }` significa imprimir el primer campo coincidente.
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
Al ejecutar el comando anterior obtendrás:
```
root
daemon
bin
sys
sync
```
Para más detalles sobre `awk`, consulta este [enlace](https://www.cyberciti.biz/faq/bash-scripting-using-awk).


### b. `cut`
Elimina secciones de cada línea de un archivo.

*ejemplo.txt*
```bash
red riding hood went to the park to play
```

*mostrar las columnas 2, 7 y 9 usando espacio como separador*
```bash
cut -d " " -f2,7,9 ejemplo.txt
```
```bash
riding park play
```

### c. `echo`
Muestra una línea de texto.

*mostrar "Hola Mundo"*
```bash
echo Hola Mundo
```
```bash
Hola Mundo
```

*mostrar "Hola Mundo" con saltos de línea entre palabras*
```bash
echo -ne "Hola\nMundo\n"
```
```bash
Hola
Mundo
```

### d. `egrep`
Imprime líneas que coinciden con un patrón — Expresión Extendida (equivalente a: `grep -E`)

*ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*mostrar las líneas que contienen "Lorem" o "dolor"*
```bash
egrep '(Lorem|dolor)' ejemplo.txt
# o bien:
grep -E '(Lorem|dolor)' ejemplo.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
Imprime líneas que coinciden con un patrón — coincidencia de patrón FIJO (equivalente a: `grep -F`)

*ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*buscar la cadena literal '(Lorem|dolor)' en ejemplo.txt*
```bash
fgrep '(Lorem|dolor)' ejemplo.txt
# o bien:
grep -F '(Lorem|dolor)' ejemplo.txt
```
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Formateador de texto simple y óptimo.

*ejemplo: ejemplo.txt (1 línea)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*mostrar las líneas de ejemplo.txt con un ancho de 20 caracteres*
```bash
cat ejemplo.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
Busca texto dentro de archivos. Puedes usar `grep` para buscar líneas que coincidan con una o más expresiones regulares, y muestra solo las líneas que coinciden.  
```bash
grep patrón archivo
```
Ejemplo:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
También puedes hacer que `grep` ignore mayúsculas y minúsculas con la opción `-i`. `-r` permite buscar en todos los archivos de un directorio, por ejemplo:
```bash
$ grep -r admin /etc/
```
Y `-w` para buscar palabras completas. Para más detalles sobre `grep`, consulta este [enlace](https://www.cyberciti.biz/faq/grep-in-bash).

### h. `nl`
Numera las líneas de un archivo.

*ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*mostrar ejemplo.txt con números de línea*
```bash
nl -s". " ejemplo.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
Editor de flujo para filtrar y transformar texto.

*ejemplo.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*reemplazar todos los espacios con guiones*
```bash
sed 's/ /-/g' ejemplo.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*reemplazar todos los dígitos con "d"*
```bash
sed 's/[0-9]/d/g' ejemplo.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
Ordena líneas de archivos de texto.

*ejemplo.txt*
```bash
f
b
c
g
a
e
d
```

*ordenar ejemplo.txt*
```bash
sort ejemplo.txt
```
```bash
a
b
c
d
e
f
g
```

*ordenar ejemplo.txt de forma aleatoria*
```bash
sort ejemplo.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
Traduce o elimina caracteres.

*ejemplo.txt*
```bash
Hello World Foo Bar Baz!
```

*convertir todas las letras minúsculas a mayúsculas*
```bash
cat ejemplo.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*convertir todos los espacios en saltos de línea*
```bash
cat ejemplo.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Reporta u omite líneas repetidas.

*ejemplo.txt*
```bash
a
a
b
a
b
c
d
c
```

*mostrar solo las líneas únicas de ejemplo.txt (primero debes ordenarlo, de lo contrario no detectará los duplicados)*
```bash
sort ejemplo.txt | uniq
```
```bash
a
b
c
d
```

*mostrar los elementos únicos por línea e indicar cuántas veces aparece cada uno*
```bash
sort ejemplo.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Indica cuántas líneas, palabras y caracteres tiene un archivo.  
```bash
wc archivo
```
Ejemplo:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
Donde `7459` son líneas, `15915` son palabras y `398400` son caracteres.

## 1.3. Operaciones de Directorio

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
Te mueve de un directorio a otro. Ejecutar simplemente:
```bash
$ cd
```
te lleva al directorio de inicio (home). El comando acepta un `nombre_de_directorio` opcional al que deseas ir.
```bash
cd nombre_de_directorio
```
Volver al directorio de trabajo anterior:
```bash
cd -
```

### b. `mkdir`
Crea un nuevo directorio.  
```bash
mkdir nombre_directorio
```
Puedes crear múltiples directorios a la vez dentro del directorio actual:
```bash
mkdir primerDirectorio segundoDirectorio tercerDirectorio
```
También puedes crear directorios padre al mismo tiempo con la opción `-p` (o `--parents`). Por ejemplo, si deseas crear un directorio llamado 'proyecto1' dentro de `/ejemplos/bash/proyectos/`, puedes ejecutar:
```bash 
mkdir -p /ejemplos/bash/proyectos/proyecto1
mkdir --parents /ejemplos/bash/proyectos/proyecto1
```
Ambos comandos hacen lo mismo. Si alguno de esos directorios no existe, también se creará.

### c. `pwd`
Muestra el directorio en el que te encuentras actualmente.  
```bash
pwd
```

## 1.4. SSH, Información del Sistema y Red

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
      <td><a href="#y-rsync">rsync</a></td>
      <td><a href="#z-curl">curl</a></td>
   </tr>
</table>

### a. `bg`
Lista los trabajos detenidos o en segundo plano; reanuda un trabajo detenido en segundo plano.

### b. `cal`
Muestra el calendario del mes actual.

### c. `date`
Muestra la fecha y hora actuales.

### d. `df`
Muestra el uso del disco.

### e. `dig`
Obtiene información DNS de un dominio.  
```bash
dig dominio
```

### f. `du`
Muestra el uso de disco de archivos o directorios. Para más información consulta este [enlace](http://www.linfo.org/du.html).
```bash
du [opción] [archivo|directorio]
```
Opciones:
- `-h` (human readable — legible para humanos) Muestra el resultado en kilobytes (K), megabytes (M) y gigabytes (G).
- `-s` (summarize — resumir) Muestra el espacio total de disco de un directorio y omite los reportes de subdirectorios.

Ejemplo:
```bash
du -sh fotos
1.4M fotos
```

### g. `fg`
Trae el trabajo más reciente al primer plano.

### h. `finger`
Muestra información sobre un usuario.  
```bash
finger nombre_usuario
```

### i. `jobs`
Lista los trabajos que se ejecutan en segundo plano, indicando el número de trabajo.

### j. `last`
Lista los últimos inicios de sesión del usuario especificado.  
```bash
last tu_nombre_usuario
```

### k. `man`
Muestra el manual del comando especificado.  
```bash
man comando
```

### l. `passwd`
Permite al usuario actualmente conectado cambiar su contraseña.

### m. `ping`
Hace ping a un host y muestra los resultados.  
```bash
ping host
```

### n. `ps`
Lista tus procesos.  
```bash
ps -u tu_nombre_usuario
```
Usa las opciones `ef`: `e` para todos los procesos y `f` para listado completo.
```bash
ps -ef
```

### o. `quota`
Muestra tu cuota de disco.  
```bash
quota -v
```

### p. `scp`
Transfiere archivos entre un host local y uno remoto, o entre dos hosts remotos.

*copiar del host local al host remoto*
```bash
scp archivo_origen usuario@host:directorio/archivo_destino
```
*copiar del host remoto al host local*
```bash
scp usuario@host:directorio/archivo_origen archivo_destino
scp -r usuario@host:directorio/carpeta_origen carpeta_destino
```
Este comando también acepta la opción `-P` para conectarse a un puerto específico.  
```bash
scp -P puerto usuario@host:directorio/archivo_origen archivo_destino
```

### q. `ssh`
`ssh` (cliente SSH) es un programa para iniciar sesión y ejecutar comandos en una máquina remota.  
```bash
ssh usuario@host
```
También acepta la opción `-p` para conectarse a un puerto específico.  
```bash
ssh -p puerto usuario@host
```

### r. `top`
Muestra los procesos activos en este momento.

### s. `uname`
Muestra información del kernel.  
```bash
uname -a
```

### t. `uptime`
Muestra el tiempo que lleva encendido el sistema.

### u. `w`
Muestra quién está conectado actualmente.

### v. `wget`
Descarga un archivo.  
```bash
wget archivo
```

### w. `whoami`
Retorna el nombre del usuario actualmente conectado.

### x. `whois`
Obtiene información whois de un dominio.  
```bash
whois dominio
```

### y. `rsync`
Hace el mismo trabajo que `scp`, pero solo transfiere los archivos que han cambiado. Útil cuando se transfiere la misma carpeta hacia/desde un servidor múltiples veces.
```bash
rsync carpeta_origen usuario@host:carpeta_destino
rsync usuario@host:carpeta_destino carpeta_local
```

### z. `curl`
`curl` es una herramienta de línea de comandos para solicitar o enviar datos usando sintaxis URL. Muy útil en sistemas donde solo tienes la terminal disponible para hacer distintos tipos de solicitudes.
```bash
curl url
```
Usa `-X` o `--request` para especificar el método HTTP que deseas invocar (GET, POST, DELETE, ...).  
Usa `-d <datos>` o `--data <datos>` para enviar datos vía POST a la URL indicada.

## 1.5. Operaciones de Monitoreo de Procesos

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Termina (mata) el proceso con el ID indicado.  
```bash
kill PID
```

### b. `killall`
Termina todos los procesos con el nombre indicado.  
```bash
killall nombre_proceso
```

### c. `&`
El símbolo `&` indica al comando que se ejecute como proceso en segundo plano dentro de un subshell.
```bash
comando &
```

### d. `nohup`
`nohup` significa "No Hang Up" (no colgar). Permite ejecutar un comando, proceso o script de shell que continúa corriendo en segundo plano incluso después de cerrar sesión en el shell.
```bash
nohup comando
```
Combínalo con `&` para crear procesos en segundo plano:
```bash
nohup comando &
```

# 2. Programación Básica en Shell

La primera línea que escribirás en un script de bash se llama `shebang`. Esta línea determina la capacidad del script de ejecutarse como un programa independiente sin necesidad de escribir `sh`, `bash`, `python`, `php`, etc. antes en la terminal.

```bash
#!/usr/bin/env bash
```

## 2.1. Variables

Crear variables en bash es similar a otros lenguajes. No existen tipos de datos. Una variable en bash puede contener un número, un carácter, una cadena de caracteres, etc. No necesitas declarar una variable; simplemente asignarle un valor la crea.

Ejemplo:
```bash
str="hola mundo"
```

La línea anterior crea la variable `str` y le asigna "hola mundo". El valor de la variable se obtiene anteponiendo `$` al nombre de la variable.

Ejemplo:
```bash
echo $str   # hola mundo
```

## 2.2. Arreglos

Al igual que otros lenguajes, bash también tiene arreglos (arrays). Un arreglo es una variable que contiene múltiples valores. No hay límite máximo en el tamaño de un arreglo. Los arreglos en bash son de base cero; el primer elemento se indexa con el número 0. Hay varias formas de crear arreglos en bash:

Ejemplos:
```bash
arreglo[0]=val
arreglo[1]=val
arreglo[2]=val
arreglo=([2]=val [0]=val [1]=val)
arreglo=(val val val)
```
Para mostrar el valor en un índice específico usa la siguiente sintaxis:

```bash
${arreglo[i]}     # donde i es el índice
```

Si no se proporciona un índice, se asume el elemento 0. Para saber cuántos valores hay en el arreglo usa:

```bash
${#arreglo[@]}
```

Bash también soporta condiciones ternarias. Algunos ejemplos:

```bash
${nombre_var:-palabra}          # si nombre_var existe y no es nulo, retorna su valor; si no, retorna palabra
${nombre_var:=palabra}          # si nombre_var existe y no es nulo, retorna su valor; si no, lo define como palabra y lo retorna
${nombre_var:+palabra}          # si nombre_var existe y no es nulo, retorna palabra; si no, retorna nulo
${nombre_var:desplazamiento:longitud}  # realiza expansión de subcadena: retorna la subcadena de $nombre_var que comienza en desplazamiento y tiene longitud caracteres
```

## 2.3. Sustitución de Cadenas

Algunas sintaxis para manipular cadenas:

```bash
${variable#patrón}          # si el patrón coincide con el inicio del valor de la variable, elimina la parte más corta que coincide y retorna el resto
${variable##patrón}         # si el patrón coincide con el inicio del valor de la variable, elimina la parte más larga que coincide y retorna el resto
${variable%patrón}          # si el patrón coincide con el final del valor de la variable, elimina la parte más corta que coincide y retorna el resto
${variable%%patrón}         # si el patrón coincide con el final del valor de la variable, elimina la parte más larga que coincide y retorna el resto
${variable/patrón/cadena}   # la coincidencia más larga del patrón en la variable es reemplazada por cadena. Solo se reemplaza la primera coincidencia
${variable//patrón/cadena}  # la coincidencia más larga del patrón en la variable es reemplazada por cadena. Se reemplazan todas las coincidencias
${#nombre_var}              # retorna la longitud del valor de la variable como una cadena de caracteres
```

## 2.4. Otros Trucos con Cadenas

Bash tiene múltiples atajos para realizar distintas operaciones con cadenas.

```bash
${variable,,}    # convierte todas las letras de la variable a minúsculas
${variable^^}    # convierte todas las letras de la variable a mayúsculas

${variable:2:8}  # retorna una subcadena que comienza en el índice 2 (las cadenas comienzan en el índice 0, por lo que este es el 3er carácter)
                 # y tiene 8 caracteres de longitud, retornando así los caracteres del 3ro al 11ro
```

Algunos trucos útiles para coincidencia de patrones:
```bash
if [[ "$variable" == *subCadena* ]]  # retorna verdadero si la subcadena está en la variable
if [[ "$variable" != *subCadena* ]]  # retorna verdadero si la subcadena no está en la variable
if [[ "$variable" == subCadena* ]]   # retorna verdadero si la variable comienza con la subCadena dada
if [[ "$variable" == *subCadena ]]   # retorna verdadero si la variable termina con la subCadena dada
```

Lo anterior puede abreviarse usando una sentencia `case` con la palabra clave `IN`:
```bash
case "$var" in
	inicio*)
		# la variable comienza con "inicio"
	;;
	*subCadena*)
		# subCadena está en la variable
	;;

	*otraSubCadena*)
		# otraSubCadena está en la variable
	;;
esac
```

## 2.5. Funciones

Al igual que en casi cualquier lenguaje de programación, puedes usar funciones para agrupar fragmentos de código de forma lógica o para practicar el arte de la recursión. Declarar una función es tan simple como escribir `function mi_funcion { mi_codigo }`. Llamar a una función es igual que llamar a cualquier otro programa: solo escribe su nombre.

```bash
function nombre() {
    comandos de shell
}
```

Ejemplo:
```bash
#!/bin/bash
function hola {
   echo mundo!
}
hola

function decir {
    echo $1
}
decir "hola mundo!"
```

Al ejecutar el ejemplo anterior, la función `hola` mostrará "mundo!". Las funciones `hola` y `decir` son similares. La diferencia principal está en `decir`: esta función imprime el primer argumento que recibe. Los argumentos dentro de funciones se tratan de la misma manera que los argumentos dados al script.

## 2.6. Condicionales

Los condicionales en bash son similares a otros lenguajes de programación. La forma más básica es `if` expresión `then` sentencia, donde la sentencia solo se ejecuta si la expresión es verdadera.

```bash
if [ expresión ]; then
    se ejecuta solo si la expresión es verdadera
else
    se ejecuta si la expresión es falsa
fi
```

A veces los `if` se vuelven confusos; puedes escribir la misma condición usando `case`:

```bash
case expresión in
    patrón1 )
        sentencias ;;
    patrón2 )
        sentencias ;;
    ...
esac
```

Ejemplos de expresiones:

```bash
sentencia1 && sentencia2  # ambas sentencias son verdaderas
sentencia1 || sentencia2  # al menos una de las sentencias es verdadera

str1=str2       # str1 coincide con str2
str1!=str2      # str1 no coincide con str2
str1<str2       # str1 es menor que str2
str1>str2       # str1 es mayor que str2
-n str1         # str1 no es nulo (tiene longitud mayor que 0)
-z str1         # str1 es nulo (tiene longitud 0)

-a archivo      # el archivo existe
-d archivo      # el archivo existe y es un directorio
-e archivo      # el archivo existe; igual que -a
-f archivo      # el archivo existe y es un archivo regular (no un directorio u otro tipo especial)
-r archivo      # tienes permiso de lectura
-s archivo      # el archivo existe y no está vacío
-w archivo      # tienes permiso de escritura
-x archivo      # tienes permiso de ejecución sobre el archivo, o permiso de búsqueda si es un directorio
-N archivo      # el archivo fue modificado desde la última vez que se leyó
-O archivo      # eres el propietario del archivo
-G archivo      # el ID de grupo del archivo coincide con el tuyo (o uno de los tuyos, si perteneces a múltiples grupos)

archivo1 -nt archivo2     # archivo1 es más reciente que archivo2
archivo1 -ot archivo2     # archivo1 es más antiguo que archivo2

-lt     # menor que
-le     # menor o igual que
-eq     # igual a
-ge     # mayor o igual que
-gt     # mayor que
-ne     # no igual a
```

## 2.7. Bucles

Hay tres tipos de bucles en bash: `for`, `while` y `until`.

Sintaxis de `for`:
```bash
for nombre [in lista]
do
  sentencias que pueden usar $nombre
done

for (( inicialización ; condición_final ; actualización ))
do
  sentencias...
done
```

Sintaxis de `while`:
```bash
while condición; do
  sentencias
done
```

Sintaxis de `until`:
```bash
until condición; do
  sentencias
done
```

# 2.8. Expresiones Regulares

Son una herramienta poderosa para manipular y buscar texto. Aquí hay ejemplos de expresiones regulares que usan cada `metacarácter`:

<table>
   <tr>
      <td><a href="#a-dot">`.`(punto)</a></td>
      <td><a href="#b-asterisk">`*`(asterisco)</a></td>
      <td><a href="#c-plus">`+`(más)</a></td>
      <td><a href="#d-question_mark">`?`(signo de interrogación)</a></td>
      <td><a href="#c-plus">`|`(tubería)</a></td>
      <td><a href="#c-plus">`[]`(clase de caracteres)</a></td>
      <td><a href="#c-plus">`[^]`(clase de caracteres negada)</a></td>
      <td><a href="#c-plus">`()`(agrupación)</a></td>
      <td><a href="#c-plus">`{}`(cuantificadores)</a></td>
      <td><a href="#c-plus">`\`(escape)</a></td>
   </tr>
</table>

### a. `.` (punto)
Coincide con cualquier carácter individual excepto el salto de línea.  
```bash
grep h.t archivo.txt
```
Salida:
```bash
hat
hot
hit
```

### b. `*` (asterisco)
Coincide con cero o más ocurrencias del carácter o grupo anterior.
```bash
grep ab*c archivo.txt
```
Salida:
```bash
ac
abc
abbc
abbbc
```

### c. `+` (más)
Coincide con una o más ocurrencias del carácter o grupo anterior.
```bash
grep ab+c archivo.txt
```
Salida:
```bash
abc
abbc
abbbc
abbbbc
```

### d. `?` (signo de interrogación)
Coincide con cero o una ocurrencia del carácter o grupo anterior.
```bash
grep ab?c archivo.txt
```
Salida:
```bash
ac
abc
```

### e. `|` (tubería/pipe)
Coincide con el patrón a la izquierda o el patrón a la derecha.
```bash
egrep "cat|dog" archivo.txt
```
Salida:
```bash
cat
dog
```

### f. `[]` (clase de caracteres)
Coincide con cualquier carácter dentro de los corchetes.
```bash
[aeiou]   # coincide con cualquier vocal
[a-z]     # coincide con cualquier letra minúscula
```

### g. `[^]` (clase de caracteres negada)
Coincide con cualquier carácter que NO esté dentro de los corchetes.
```bash
[^aeiou]  # coincide con cualquier consonante
[^a-z]    # coincide con cualquier carácter que no sea minúscula
```

### h. `()` (agrupación)
Agrupa múltiples elementos y crea un grupo de captura.
```bash
egrep "(ab)+" archivo.txt
```

Salida:
```bash
ab
abab
ababab
```

### i. `{}` (cuantificadores)
Coincide con un número específico de ocurrencias del carácter o grupo anterior.
```bash
egrep "a{3}" archivo.txt
```

Salida:
```bash
aaa
aaaa
aaaaa
```

### j. `\` (escape)
Escapa el siguiente carácter para buscarlo de forma literal.
```bash
egrep "a\+" archivo.txt
```

Salida:
```bash
a+
```

## 2.9. Tuberías (Pipes)

Múltiples comandos pueden encadenarse con una tubería, `|`. El símbolo `|` envía la salida estándar del comando A hacia la entrada estándar del comando B.  
Las tuberías también pueden construirse con los símbolos `|&`. Esto envía tanto la salida estándar **como** el error estándar del comando A hacia la entrada estándar del comando B.

# 3. Trucos

## Crear un alias

Ejecuta `nano ~/.bash_profile` y agrega la siguiente línea:

```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # agrega tu alias en .bash_profile
```

## Ir rápidamente a un directorio específico

Ejecuta `nano ~/.bashrc` y agrega la siguiente línea:

```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

Ahora puedes usar la ruta guardada:

```bash
source ~/.bashrc
cd $hotellogs
```

## Repetir el último comando

Esto viene de los tiempos en que los teclados no tenían flecha hacia arriba, pero aún puede ser útil.  
Para ejecutar el último comando de tu historial:
```bash
!!
```
Un error común es olvidar usar `sudo` antes de un comando que requiere privilegios. En lugar de escribir todo el comando de nuevo, puedes hacer:
```bash
sudo !!
```
Esto convertiría un `mkdir algundirectorio` en `sudo mkdir algundirectorio`.

## Trampas de salida (Exit traps)

Haz tus scripts de bash más robustos ejecutando limpieza de forma confiable al finalizar.

```bash
function finalizar {
  # tu limpieza aquí, ej. matar procesos bifurcados
  jobs -p | xargs kill
}
trap finalizar EXIT
```

## Guardar variables de entorno

Cuando ejecutas `export FOO=BAR`, tu variable solo se exporta en el shell actual y sus procesos hijos. Para que persista en el futuro, agrega el comando de exportación en tu archivo `~/.bash_profile`:
```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Acceder a tus scripts

Puedes acceder fácilmente a tus scripts creando una carpeta `bin` en tu directorio de inicio con `mkdir ~/bin`. Todos los scripts que coloques allí estarán disponibles desde cualquier directorio.

Si no puedes acceder a ellos, agrega el siguiente código en tu `~/.bash_profile` y luego ejecuta `source ~/.bash_profile`:
```bash
# agrega el directorio bin privado del usuario al PATH si existe
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Depuración

Puedes depurar fácilmente un script de bash pasando distintas opciones al comando `bash`. Por ejemplo, `-n` no ejecuta los comandos y solo verifica errores de sintaxis. `-v` muestra los comandos antes de ejecutarlos. `-x` muestra los comandos después del procesamiento de la línea de comandos.

```bash
bash -n nombre_script
bash -v nombre_script
bash -x nombre_script
```

# 5. Multi-threading

Puedes ejecutar tareas en paralelo fácilmente usando `&`. Todos esos trabajos se ejecutarán en segundo plano simultáneamente y puedes ver los procesos en ejecución con `jobs`.

```bash
sleep 15 & sleep 5 &
```

El comando opcional `wait` esperará a que todos los trabajos terminen.

```bash
sleep 10 & sleep 5 &
wait
```

## Contribución

- Reportar problemas: [Cómo hacerlo](https://help.github.com/articles/creating-an-issue/)
- Abrir un pull request con mejoras: [Cómo hacerlo](https://help.github.com/articles/about-pull-requests/)
- Difundir el conocimiento

## Traducciones

- [Chino | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turco | Türkçe](https://github.com/omergulen/bash-guide)
- [Japonés | 日本語](https://github.com/itooww/bash-guide)
- [Ruso | Русский](https://github.com/navinweb/bash-guide)
- [Vietnamita | Tiếng Việt](https://github.com/nguyenvanhieuvn/hoc-bash)
- [Español | Spanish](https://github.com/orellanaignaciod-stack/bash-guide)

## Licencia

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
