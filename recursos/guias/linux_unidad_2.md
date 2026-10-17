# Contenido de la unidad

**Objetivo:** Dominar la redirección de entrada/salida y el procesamiento de texto en la CLI para encadenar comandos y filtrar o transformar información específica

## Redireccionamiento I/O

- Operadores de redirección de salida (`>`, `>>`)
- Operador de redirección de entrada (`<`)
- Duplicación de salida (`tee`)
- *File descriptors*: `stdin`, `stdout`, `stderr`
- Redirección de errores (`2>`, `2>>`)
- Fusión de flujos (`2>&1`, `&>`)
- Descarte de salida (`/dev/null`)
- *Here-doc* (`<<`) y *here-string* (`<<<`)

## Encadenamiento y control de flujo

- Operador _pipe_ (`|`)
- Ejecución secuencial (`;`)
- Ejecución condicional por éxito (`&&`)
- Ejecución condicional por fallo (`||`)
- Pipe con `stderr` (`|&`)

## Procesamiento y filtrado de texto

- Expresiones regulares
- Búsqueda de patrones (`grep`)
- Transformación del flujo de texto (`sed`)
- Procesamiento por campos/registros (`awk`)

# Metodología de aprendizaje

## Sesiones de aprendizaje

Las clases tendrán un papel fundamental en el desarrollo de esta unidad, debido a la disponibilidad limitada de recursos didácticos que integren todos los conceptos.

*Por ello, las clases se centrarán en explicar los dos primeros bloques:*

- [Redireccionamiento de entrada/salida](#redireccionamiento-io)
- [Encadenamiento y control de flujo](#encadenamiento-y-control-de-flujo)

## Aprendizaje autónomo

El aprendizaje autodidacta estará orientado al [último bloque de la unidad](#procesamiento-y-filtrado-de-texto) debido a que estos temas cuentan con una amplia variedad de documentación. De igual manera, los [recursos de aprendizaje](#recursos-de-aprendizaje) cubren todos los temas de la unidad.

Los contenidos de esta unidad tienen un enfoque práctico, por ello, es fundamental reforzar los conceptos mediante su aplicación en la máquina virtual. Para este propósito, se dispone de las [guías de laboratorio](#laboratorios).

## Recursos de aprendizaje

Las fuentes de aprendizaje seleccionadas son **gratuitas**.

### GNU — Bash manual

1. [Redireccionamiento I/O](https://www.gnu.org/software/bash/manual/html_node/Redirections.html)
2. [Listas de comandos](https://www.gnu.org/software/bash/manual/html_node/Lists.html)

Los enlaces forman parte de la documentación oficial de Bash que describe la sintaxis y el funcionamiento de los operadores de redireccionamiento de entrada/salida y de encadenamiento y control de flujo de comandos.

### William Shotts — Libro "The Linux Command Line"

Este libro en inglés incluye los temas necesarios para dominar la línea de comandos de Linux; sin embargo, para esta unidad en particular, el estudio debe enfocarse en dos capítulos del libro.

- *Capítulo 6 — Redireccionamiento — pág. 49*
- *Capítulo 19 — Expresiones regulares — pág. 225*

> El libro está disponible [en el repositorio](../libros/thelinuxcommandline.pdf).

### William Shotts — LinuxCommand.org

1. [Redireccionamiento básico](https://linuxcommand.org/lc3_lts0070.php)
2. [Redireccionamiento avanzado](https://linuxcommand.org/lc3_adv_redirection.php)

Son dos tutoriales prácticos sobre los fundamentos del redireccionamiento de entrada/salida y el encadenamiento de comandos en la terminal.

Aborda desde los conceptos básicos de los flujos estándar y las tuberías hasta la manipulación avanzada de descriptores de archivo y la redirección de errores, mediante ejemplos.

### RegexOne

- **URL:** https://regexone.com/

Es un tutorial interactivo y progresivo orientado al aprendizaje de expresiones regulares mediante explicaciones breves y ejercicios prácticos.

Además, presenta problemas basados en casos frecuentes para resolver tareas concretas de procesamiento de texto.

### design.dev — RegExr

- **URL:** https://regexr.com/

Es un editor interactivo con resaltado en tiempo real, explicación del patrón y referencia de sintaxis. Es ideal para experimentar de forma libre, antes de aplicarlo en `grep`, `sed` o `awk`.

### GNU — `grep` manual

- **URL:** https://www.gnu.org/software/grep/manual/grep.html

Es la documentación oficial sobre búsqueda de patrones, expresiones regulares y opciones de filtrado para el comando `grep`.

### GNU — `sed` manual

1. [Comandos más usados de `sed`](https://www.gnu.org/software/sed/manual/html_node/Common-Commands.html)
2. [Selección de líneas con direcciones](https://www.gnu.org/software/sed/manual/html_node/sed-addresses.html)
3. [Expresiones regulares con `sed`](https://www.gnu.org/software/sed/manual/html_node/sed-regular-expressions.html)
4. [El comando `s`](https://www.gnu.org/software/sed/manual/html_node/The-_0022s_0022-Command.html)

Los enlaces forman parte del manual oficial para aprender a buscar, sustituir, eliminar y modificar texto mediante secuencias de edición con el comando `sed`.

### GNU — `awk` manual

1. [Introducción a `awk`](https://www.gnu.org/software/gawk/manual/html_node/Getting-Started.html)
2. [Expresiones regulares con `awk`](https://www.gnu.org/software/gawk/manual/html_node/Regexp.html)

Los enlaces forman parte de la guía de referencia para el procesamiento de datos estructurados en registros y campos mediante el comando `awk`.

# Desarrollo de la unidad

## Especificaciones

La unidad tendrá una duración de **tres semanas**, durante las cuales se deberán presentar al menos **dos entregables**, elaborados de acuerdo con las instrucciones establecidas en la [Guía de entregables](linux_entregables.md).

*La fecha límite exacta para completar las actividades y los retos será comunicada por los líderes a través de los canales correspondientes.*

## Desarrollo de retos

Una vez adquiridas las bases necesarias, se les **recomienda** desarrollar **al menos dos retos** relacionados con los contenidos de la unidad y utilizar la [guía de laboratorio](#laboratorios) para complementar el aprendizaje.

> **Como alternativa a la resolución de los retos**, se contemplan muchas más opciones válidas de entregables que se pueden consultar en la [Guía de entregables](linux_entregables.md#ii-formatos-de-entrega).

### Retos recomendados

- [Pwn College — Linux Luminarium: File Globbing](https://pwn.college/linux-luminarium/globbing/)
- [Pwn College — Linux Luminarium: Practicing Piping](https://pwn.college/linux-luminarium/piping/)

> También es válido utilizar retos de otras fuentes, siempre que estén relacionados con los contenidos de la presente unidad.

### Modalidades de presentación

**El canal de entrega la especifican los líderes de la categoría** en cada ciclo.

- Write-up en formado Markdown (`.md`)
- Resolución grabada o en vivo

> Estas modalidades de presentación deben seguir las indicaciones establecidas en la [Guía de entregables](linux_entregables.md#ii-formatos-de-entrega).

## Laboratorios

Se dispone de dos guías de laboratorio que abordan distintos bloques de contenido de la unidad. Su propósito es reforzar el aprendizaje práctico mediante ejercicios aplicados; por tanto, su desarrollo **no constituye un entregable adicional**.

1. [Laboratorio de redireccionamiento y encadenamiento de comandos](linux_redireccion_encadenacion.md)
2. [Laboratorio de aplicación de `awk` y `sed`](comandos_awk_sed.md)

Si surgen dudas durante el desarrollo de los laboratorios o se desea recibir retroalimentación sobre su desarrollo, estos se pueden compartirse con los líderes y mentores para su revisión.
