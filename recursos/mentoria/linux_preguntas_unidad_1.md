# Instrucciones del cuestionario

*Las siguientes 40 preguntas poseen diferentes modalidades:*

- **Opción múltiple:** permite seleccionar varias respuestas correctas.
- **Opción única:** permite seleccionar una sola respuesta correcta.
- **Completar:** permite escribir la respuesta en un campo de texto.

---

# Preguntas del cuestionario

## Parte 1: Sistemas operativos y conceptos fundamentales

### Pregunta 1 — OPCIÓN MÚLTIPLE

¿Cuáles son funciones habituales de un sistema operativo?

A) Garantizar que todos los programas estén libres de errores  
B) Gestionar la ejecución de los procesos  
C) Proporcionar mecanismos para que las aplicaciones interactúen con el sistema  
D) Administrar los recursos de hardware del equipo

**Respuestas correctas:** B, C y D

### Pregunta 2 — OPCIÓN MÚLTIPLE

¿Cuáles de las siguientes afirmaciones describen correctamente la relación entre el kernel y el shell en Linux?

A) El kernel administra los recursos del sistema y proporciona servicios fundamentales.  
B) El shell permite al usuario interactuar con el sistema mediante comandos.  
C) El shell reemplaza al kernel cuando el usuario inicia sesión.  
D) El shell puede solicitar al sistema operativo que ejecute comandos.

**Respuestas correctas:** A, B y D

### Pregunta 3 — OPCIÓN MÚLTIPLE

¿Cuáles de las siguientes afirmaciones sobre Linux y GNU son correctas?

A) Linux es, estrictamente hablando, el kernel del sistema.  
B) Todas las distribuciones Linux incluyen exactamente el mismo conjunto de programas.  
C) GNU proporciona herramientas y programas que pueden utilizarse junto con el kernel Linux.  
D) Linux y el proyecto GNU trabajaron en conjunto para el desarrollo del primer kernel.

**Respuestas correctas:** A y C

### Pregunta 4 — OPCIÓN MÚLTIPLE

¿Cuáles son características habituales de Linux?

A) Es multiusuario.  
B) Permite ejecutar múltiples procesos de manera concurrente.  
C) Es un sistema operativo de escritorio.  
D) Existen distribuciones adaptadas para servidores, computadoras personales y sistemas embebidos.

**Respuestas correctas:** A, B y D

### Pregunta 5 — OPCIÓN MÚLTIPLE

¿Cuáles de las siguientes afirmaciones describen correctamente el proyecto GNU?

A) Busca desarrollar un sistema operativo compuesto por software libre.  
B) Proporciona herramientas y utilidades que pueden utilizarse en sistemas con kernel Linux.  
C) Es el nombre oficial del kernel Linux.  
D) Incluye proyectos de software como el compilador GCC y muchas utilidades del sistema.

**Respuestas correctas:** A, B y D

### Pregunta 6 — COMPLETAR

En la jerarquía tradicional de directorios de Linux, ¿cuál es la ruta del directorio destinado a muchos de los binarios esenciales del sistema? *Escribe su ruta absoluta.*

**Respuesta correcta:** `/bin`

### Pregunta 7 — COMPLETAR

¿Qué directorio de Linux almacena habitualmente los archivos de configuración del sistema? *Escribe su ruta absoluta.*

**Respuesta correcta:** `/etc`

### Pregunta 8 — OPCIÓN MÚLTIPLE

¿Qué rutas absolutas representan mi directorio `home` siendo mi nombre de usuario `bob`?

A) `/bob`  
B) `/home/bob`  
C) `~`  
D) `~/bob`

**Respuestas correctas:** B y C

### Pregunta 9 — OPCIÓN ÚNICA

¿Cuál es una de las shells más utilizadas y la shell predeterminada habitual en muchas distribuciones Linux?

A) Bash  
B) PowerShell  
C) Zsh  
D) Fish

**Respuesta correcta:** A) Bash

### Pregunta 10 — OPCIÓN MÚLTIPLE

¿Qué opciones permiten solicitar ayuda directamente a la mayoría de comandos de Linux? _Nota: la disponibilidad de estas opciones depende del comando._

A) `--help`  
B) `-h`  
C) `-t`  
D) `--h`

**Respuestas correctas:** A y B

---

## Parte 2: Comandos y navegación por el sistema de archivos

### Pregunta 11 — COMPLETAR

¿Qué comando permite consultar las páginas del manual de otros comandos de Linux?

**Respuesta correcta:** `man`

### Pregunta 12 — COMPLETAR

¿Qué comando debes ejecutar para desplazarte al directorio padre del directorio actual?

**Respuesta correcta:** `cd ..`

### Pregunta 13 — OPCIÓN MÚLTIPLE

Tu nombre de usuario es `alice`. Estás ubicado en `/home` y quieres listar los archivos y directorios de tu carpeta `Downloads`. ¿Qué comandos logral el objetivo?

A) `ls ./Downloads`  
B) `ls alice/Downloads`  
C) `ls /home/alice/Downloads`  
D) `ls ~/Downloads`

**Respuestas correctas:** B, C y D

### Pregunta 14 — COMPLETAR

¿Qué comando permite renombrar un archivo llamado `informe.txt` a `resumen.txt` dentro del mismo directorio?

**Respuesta correcta:** `mv informe.txt resumen.txt`

### Pregunta 15 — OPCIÓN ÚNICA

¿Qué comando permite listar los archivos ocultos de un directorio, incluidos los nombres que comienzan con un punto?

A) `ls -a`  
B) `ls -l`  
C) `pwd -h`    
D) `mkdir -a`

**Respuesta correcta:** A) `ls -a`

### Pregunta 16 — OPCIÓN MÚLTIPLE

¿Cuáles de los siguientes nombres corresponden al de un archivo oculto en Linux?

A) `.documento.txt`  
B) `...`  
C) `.git`  
D) `_bashrc`

**Respuestas correctas:** A, B y C

### Pregunta 17 — OPCIÓN MÚLTIPLE

¿Cuáles de los siguientes comandos permiten eliminar un directorio (llamado `my_docs`) que contiene archivos y subdirectorios?

A) `rm -r my_docs`  
B) `rmdir my_docs`  
C) `touch my_docs`  
D) `rm -R my_docs`

**Respuestas correctas:** A y D

### Pregunta 18 — OPCIÓN ÚNICA

¿Qué comando permite copiar un archivo llamado `origen.txt` a otro archivo llamado `copia.txt`?

A) `mv origen.txt copia.txt`  
B) `cp origen.txt copia.txt`  
C) `cp copia.txt origen.txt`  
D) `mv copia.txt origen.txt`

**Respuesta correcta:** B) `cp origen.txt copia.txt`

### Pregunta 19 — COMPLETAR

¿Qué comando permite mostrar las últimas 10 líneas de un archivo llamado `registros.log` utilizando su comportamiento predeterminado?

**Respuesta correcta:** `tail registros.log`

### Pregunta 20 — OPCIÓN ÚNICA

Quieres encontrar archivos regulares cuyo tamaño sea superior a 50 MiB en todo el sistema. ¿Qué comando debes utilizar para realizar la búsqueda ?

A) `find / -type f -size +50M`  
B) `find / -size 50M`  
C) `fi / -type f -size +50M`  
D) `fi / -name * -type f -size +50M`

**Respuesta correcta:** A) `find / -type f -size +50M`

### Pregunta 21 — OPCIÓN MÚLTIPLE

En tu directorio actual existe un archivo cuyo nombre es exactamente `- -` (dos guiones separados por un espacio). ¿Cuáles de los siguientes comandos permiten mostrar su contenido de forma segura?

A) `cat ./- -`  
B) `cat './- -'`  
C) `cat - -`  
D) `cat -- '- -'`

**Respuestas correctas:** B y D

### Pregunta 22 — COMPLETAR

¿Qué comando permite leer todo el contenido de un archivo llamado `file.txt` utilizando su comportamiento predeterminado?

**Respuesta correcta:** `cat file.txt`

---

## Parte 3: Usuarios y grupos

### Pregunta 23 — OPCIÓN MÚLTIPLE

¿Qué comandos permiten consultar los grupos a los que pertenece el usuario actual?

A) `groups`  
B) `id`  
C) `chmod`  
D) `mkdir`

**Respuestas correctas:** A y B

### Pregunta 24 — COMPLETAR

¿Qué comando muestra el nombre del usuario efectivo con el que estás trabajando en la terminal?

**Respuesta correcta:** `whoami`

### Pregunta 25 — OPCIÓN ÚNICA

¿Qué comando permite consultar los permisos, el propietario y el grupo propietario de un archivo?

A) `ls -l archivo.txt`  
B) `ls -a archivo.txt`  
C) `id archivo.txt`  
D) `groups archivo.txt`

**Respuesta correcta:** A) `ls -l archivo.txt`

### Pregunta 26 — OPCIÓN ÚNICA

¿Qué comando permite cambiar el propietario de `informe.txt` al usuario `john`?

A) `chmod john informe.txt`  
B) `umask john informe.txt`  
C) `groups john informe.txt`  
D) `chown john informe.txt`

**Respuesta correcta:** D) `chown john informe.txt`

---

## Parte 4: Permisos en Linux

### Pregunta 27 — OPCIÓN ÚNICA

¿Qué permisos establece el comando `chmod 644 informe.txt` para el propietario, el grupo y los demás usuarios?

A) **Propietario:** lectura y escritura; **grupo:** lectura; **otros:** lectura  
B) **Propietario:** lectura, escritura y ejecución; **grupo:** lectura y ejecución; **otros:** lectura y ejecución  
C) **Propietario:** lectura; **grupo:** lectura y escritura; **otros:** escritura  
D) Todos los usuarios tienen lectura y escritura

**Respuesta correcta:** A

### Pregunta 28 — OPCIÓN ÚNICA

¿Qué permisos establece el comando `chmod 755 script.sh`?

A) Todos los usuarios tienen lectura, escritura y ejecución  
B) **Propietario:** lectura, escritura y ejecución; **grupo y demás:** lectura y ejecución  
C) **Propietario:** lectura y escritura; **grupo y demás:** lectura y escritura  
D) **Propietario:** solo ejecución; **grupo y demás:** lectura y escritura

**Respuesta correcta:** B

### Pregunta 29 — OPCIÓN ÚNICA

¿Qué comando añade el permiso de ejecución al propietario de `script.sh` sin modificar los demás permisos?

A) `chmod g+x script.sh`  
B) `chmod o+x script.sh`  
C) `chmod u+x script.sh`  
D) `chown u+x script.sh`

**Respuesta correcta:** C) `chmod u+x script.sh`

### Pregunta 30 — OPCIÓN ÚNICA

En el comando `chmod g+w archivo.txt`, ¿qué representa la letra `g`?

A) El propietario del archivo  
B) El grupo propietario del archivo  
C) Todos los usuarios del sistema  
D) El usuario root exclusivamente

**Respuesta correcta:** B) El grupo propietario del archivo

### Pregunta 31 — OPCIÓN ÚNICA

¿Qué permisos necesita normalmente un usuario para crear archivos dentro de un directorio?

A) Lectura y ejecución (`r-x`)  
B) Escritura y ejecución (`-wx`)  
C) Solo lectura (`r--`)  
D) Solo ejecución (`--x`)

**Respuesta correcta:** B) Escritura y ejecución (`-wx`)

### Pregunta 32 — OPCIÓN ÚNICA

Un usuario intenta modificar un archivo sobre el que no tiene permiso de escritura. No dispone de privilegios adicionales ni existe otro mecanismo que le conceda acceso. ¿Qué ocurre normalmente?

A) Linux concede temporalmente el permiso de escritura.  
B) El archivo cambia de propietario.  
C) La operación es denegada.  
D) Se crea una copia del archivo para su escritura.

**Respuesta correcta:** C) La operación es denegada.

### Pregunta 33 — OPCIÓN ÚNICA

¿Qué función cumple el comando `sudo` en Linux?

A) Cambia los permisos de archivos.  
B) Permite ejecutar comandos con privilegios elevados.  
C) Concede acceso de administrador a todos los usuarios.  
D) Permite sustituir temporalmente a un usuario del sistema.

**Respuesta correcta:** B

### Pregunta 34 — OPCIÓN ÚNICA

¿Qué función cumple la máscara `umask` en Linux?

A) Permite ejecutar programas como `root`.  
B) Cambia el propietario por defecto de los archivos del usuario.  
C) Permite cambiar los permisos de archivos personales.  
D) Define los permisos que se excluyen de los permisos iniciales al crear archivos y directorios.

**Respuesta correcta:** D

### Pregunta 35 — OPCIÓN MÚLTIPLE

Señala diferencias importantes entre el permiso de ejecución de un archivo regular y el de un directorio.

A) En un archivo, regular permite ejecutar el archivo cuando corresponde.  
B) En un directorio, permite acceder a sus archivos con `cd`.  
C) En un directorio permite cambiar automáticamente su propietario.  
D) El permiso de ejecución en directorios no tiene efecto.

**Respuestas correctas:** A y B

### Pregunta 36 — OPCIÓN ÚNICA

¿Qué efecto tiene el permiso especial SUID cuando está configurado en un ejecutable y el sistema lo admite?

A) El programa se ejecuta con el identificador efectivo del propietario del archivo.  
B) Todos los usuarios obtienen permisos de lectura sobre el archivo.  
C) El programa se ejecuta siempre con el identificador efectivo del grupo propietario.  
D) El archivo se vuelve imposible de renombrar.

**Respuesta correcta:** A

---

# Parte 5: Gestión de cuentas

### Pregunta 37 — OPCIÓN ÚNICA

¿Qué sucede normalmente cuando un usuario ejecuta `su` sin especificar otro nombre de usuario?

A) Concede privilegios de `root` temporalmente.  
B) El comando falla en su ejecución porque requiere privilegios.  
C) Cambia la contraseña del usuario actual.  
D) Intenta cambiar al usuario `root` y solicita su contraseña.

**Respuesta correcta:** D

### Pregunta 38 — COMPLETAR

¿Cuál es la ruta absoluta del directorio personal del superusuario `root` en una instalación Linux convencional?

**Respuesta correcta:** `/root`

### Pregunta 39 — COMPLETAR

¿En qué archivo se almacenan normalmente los hashes de las contraseñas de las cuentas locales de Linux?

**Respuesta correcta:** `/etc/shadow`

### Pregunta 40 — OPCIÓN MÚLTIPLE

¿Cuáles son diferencias habituales entre una cuenta de usuario regular y una cuenta de sistema?

A) Una cuenta de usuario regular suele utilizarse para iniciar sesiones.  
B) Una cuenta de sistema puede utilizarse para ejecutar servicios o procesos específicos.  
C) Las cuentas de sistema suelen estar configuradas para impedir el inicio de sesiones interactivas.  
D) Las cuentas de sistema frecuentemente tienen una shell configurada como `/usr/sbin/nologin` o `/bin/false`.

**Respuestas correctas:** A, B, C y D