- Autor: **Marquixs Ω (marquixs14122)**
- Tipo de documento: **write-up**

---

# Write-up: OverTheWire

Este documento detalla de manera estructurada la resolución y análisis metodológico de los niveles **2 al 3**, **3 al 4** y **4 al 5** del **Bandit** de OverTheWire. Se prioriza la explicación de la lógica interna de los comandos, el comportamiento del intérprete de comandos (Bash) y los conceptos de administración de sistemas Linux involucrados.


Nota 1: Preferí hacerlo en OverTheWire porque se me hizo más fácil o me pareció mejor, ya que trabajé directamente con la terminal. Las otras páginas que tenían una terminal integrada en el navegador no me parecieron una mala idea, pero pensé que si al final de cuentas iba a usar la terminal, era mejor ir utilizándola desde el comienzo.

También quise hacer los tres entregables (si se que eran 2 xd) en uno solo archivo, más que todo por los que escogí, ya que se complementan unos a otros a través de las contraseñas y algunos códigos. Normalmente tenía pensado hacer solo del 3 al 4 y del 4 al 5,(por la parte de la ocultación hacia el comando `ls` ) pero quise agregar del 2 al 3 porque me confundí con las notaciones del comando `cat` en esa parte en específico. Sentí que era bueno explicarlo e incluirlo en el entregable, ya que me ayudó a profundizar en ese aspecto.

---

##  Información General de Conexión
* **Plataforma:** [OverTheWire - Bandit](https://overthewire.org/wargames/bandit/)
* **Servidor SSH:** `bandit.labs.overthewire.org`
* **Puerto SSH:** `2220`

---

##  Nivel 2 → Nivel 3

### 1. Datos de Acceso
* **Usuario:** `bandit2`
* **Contraseña de Acceso:** `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB`
* **Conexión SSH:**
  ```bash
  ssh bandit2@bandit.labs.overthewire.org -p 2220
  ```

### 2. Descripción del Reto
La contraseña para avanzar al Nivel 3 está almacenada en el directorio de inicio (`~`) dentro de un archivo denominado `--spaces in this filename--`.

### 3. Fundamento Teórico y Conceptos Clave
* **Parsing de Argumentos en Bash**: Cuando se ejecuta un comando en la terminal, la shell (Bash) realiza un proceso de tokenización donde los espacios actúan como delimitadores de argumentos. Un nombre con espacios no entrecomillado se interpreta como múltiples archivos distintos.
* **Manejo de Banderas / Opciones (`-` y `--`):** Por convención en POSIX/GNU, los caracteres `-` o `--` al inicio de una palabra le indican al comando que la cadena es una opción o bandera de configuración (ej. `--help` o `-l`), no la ruta de un archivo.
* **Resolución por Ruta Relativa:** Al anteponer `./` a la ruta, se especifica explícitamente la ubicación dentro del directorio actual. De este modo, la cadena comienza con `.` en lugar de `-`, evitando que la utilidad de lectura (como `cat`) la confunda con un argumento de configuración.

### 4. Procedimiento Detallado
Para leer el archivo combinando la neutralización de opciones y la preservación de espacios:

```bash
cat ./"--spaces in this filename--"
```

### 5. Resultado Obtenido
* **Contraseña de `bandit3`:** `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`

---
Nota 2: Esta parte me pareció una buena idea ponerla por el hecho de que normalmente usamos el comando `ls` para ver las carpetas o archivos y luego `cat` para poder leerlos; pero lo que ocurre acá es que la carpeta está oculta. Al estar oculta, nos hace usar una opción como `-a` en el directorio `inhere` para mostrar todo, y recién ahí poder usar `cat` para encontrar la contraseña.
##  Nivel 3 → Nivel 4

### 1. Datos de Acceso
* **Usuario:** `bandit3`
* **Contraseña de Acceso:** `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`
* **Conexión SSH:**
  ```bash
  ssh bandit3@bandit.labs.overthewire.org -p 2220
  ```

### 2. Descripción del Reto
La contraseña para ingresar al Nivel 4 está guardada en un archivo oculto dentro del directorio denominado `inhere`.

### 3. Fundamento Teórico y Conceptos Clave
* **Convención de Archivos Ocultos en Unix:** En el sistema de archivos de Unix/Linux, cualquier archivo o directorio cuyo nombre empiece con un punto `.` es tratado como oculto. Esta convención se utiliza comúnmente para almacenar archivos de configuración del sistema o del usuario (ej. `.bashrc`, `.ssh`).
* **Comportamiento del Comando `ls`:** La herramienta de listado de directorios `ls` por defecto ignora las entradas que inician con `.`. Para forzar a `ls` a mostrar todas las entradas sin importar su visibilidad, se debe emplear el parámetro `-a` (*all*).

### 4. Procedimiento Detallado
1. Cambiar al directorio objetivo:
   ```bash
   cd inhere
   ```
2. Inspeccionar la totalidad de los archivos presentes en el directorio (incluyendo los ocultos):
   ```bash
   ls -a
   ```
3. Identificar el archivo oculto devuelto por la terminal (`...Hiding-From-You`) y desplegar su contenido:
   ```bash
   cat ...Hiding-From-You
   ```

### 5. Resultado Obtenido
* **Contraseña de `bandit4`:** `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`

---
Nota 3: Este también quise ponerlo porque no solo implica usar los comandos del ejercicio anterior, sino que ahora, cuando pones el comando `ls -a`, te muestra muchos archivos (_files_) y no sabríamos cuál leer con el comando `cat`. Aunque en este caso eran pocos y sí se podría hacer manualmente, en un caso hipotético donde sean muchos más, sería imposible revisarlos uno por uno. Es por eso que, usando el comando `file ./*` (el cual sirve para distinguir qué tipo de archivo es cada uno), podemos identificar cuál contiene la contraseña para aplicarle su respectivo `cat` y así obtenerla. 
## Nivel 4 → Nivel 5

### 1. Datos de Acceso
* **Usuario:** `bandit4`
* **Contraseña de Acceso:** `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`
* **Conexión SSH:**
  ```bash
  ssh bandit4@bandit.labs.overthewire.org -p 2220
  ```

### 2. Descripción del Reto
La contraseña para el Nivel 5 está guardada en el único archivo legible por humanos (*human-readable*) dentro de la carpeta `inhere`.

### 3. Fundamento Teórico y Conceptos Clave
* **Diferenciación de Tipos de Archivo (Texto ASCII vs Datos Binarios):** Las extensiones de archivo en Linux son meramente indicativas. El sistema determina la naturaleza de un archivo leyendo sus primeros bytes (números mágicos) o analizando la distribución de caracteres. Un archivo de texto plano (*ASCII text*) contiene únicamente caracteres imprimibles y saltos de línea, mientras que un archivo de datos (`data`) contiene secuencias de bytes binarios no interpretables directamente como texto legible.
* **Comando `file`:** Es la herramienta especializada para examinar y determinar el tipo exacto de codificación o formato de un archivo sin importar el nombre que posea.

### 4. Procedimiento Detallado
1. Navegar al directorio de trabajo:
   ```bash
   cd inhere
   ```
2. Analizar la estructura de datos interna de todos los elementos mediante comodines:
   ```bash
   file ./*
   ```
3. Observar las etiquetas arrojadas en la salida. Múltiples archivos aparecerán etiquetados como `data`, mientras que solo uno estará marcado como `ASCII text` (`-file07`).
4. Leer el archivo de texto identificado utilizando la sintaxis de ruta relativa para prevenir conflictos con el guion inicial:
   ```bash
   cat ./-file07
   ```

### 5. Resultado Obtenido
* **Contraseña de `bandit5`:** `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG`

---
Nota 4: Lamento si me falto explicar algo importante o algo esencial en los fundamentos, procedimientos o incluso en las notas ya que maso menos quería dejar las notas para que el trabajo fuera único o muy mío también he de aclarar que en el apartado de explicación del fundamento si y algunas explicaciones si lo tuve que hacer con la IA mas que todo consultándole ya que yo tenia una idea muy resumida de los comandos en general y gracias a esta pude por así decirlo perfeccionar un plan que tenia sobre el entregable.

Muchas Gracias.
