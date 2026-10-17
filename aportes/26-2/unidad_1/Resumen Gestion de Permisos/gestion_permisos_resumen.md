- Autor: **eduargalg**
- Tipo de documento: **resumen/apuntes**

---

# Tipos de cuentas y grupos

Los archivos en Linux no son accesibles para cualquier usuario. El sistema gestiona los permisos de cada usuario mediante un sistema de cuentas.

- **Hay 4 tipos de cuentas:** usuario, sistema, serivicio y `root`
- `root` es el superusurio del sistema, tiene **UID 0** y **control total**.

|          | Propósito                 | Características                                                       | Ejemplo          |
| -------- | ------------------------- | --------------------------------------------------------------------- | ---------------- |
| Usuario  | persona que inicia sesión | UID mayor a 1000, entorno propio (carpeta en `/home`)                 | Usuario personal |
| Sistema  | procesos internos         | UID bajo, sin login interactivo                                       | *daemon*         |
| Servicio | ejecutar *daemons*        | privilegios limitados, sin shell (`/usr/sbin/nologin` o `/bin/false`) | www-data         |
| `root`   | superusuario              | UID 0, acceso irrestricto                                             | `root`           |

> **UID** (Identificador de Usuario): Es un número único que el S.O. asigna a cada cuenta pra reconocerla.

# Permisos fundamentales

| Permiso   | Símbolo | Efecto sobre el archivo                        |
| --------- | ------- | ---------------------------------------------- |
| *read*    | `r`     | permite leer el contenido                      |
| *write*   | `w`     | permite modificar el contenido                 |
| *execute* | `x`     | permite ejecutar el archivo (binario o script) |

## Ejemplo

### Instrucción

```bash
ls -ld Documents
```

### Resultado

|     | user  | group | others |              |
| --- | ----- | ----- | ------ | ------------ |
| `d` | `rwx` | `rw-` | `rw-`  | `Documents/` |

# Comando `chmod`

## Modo simbólico

| Modo | Diseño                 |
| ---- | ---------------------- |
| u    | dueño                  |
| g    | grupo                  |
| o    | otros                  |
| a    | todos                  |
| +    | añadir permiso         |
| -    | quitar permiso         |
| =    | asignar permiso exacto |

## Modo numérico

| Permiso | Valor numérico |
| ------- | -------------- |
| r       | 4              |
| w       | 2              |
| x       | 1              |

## Ejemplo

### Instrucción

```bash
chmod 651 file.txt
ls -l file.txt
```

### Resultado

|     | user  | group | other |            |
| --- | ----- | ----- | ----- | ---------- |
| `-` | `rw-` | `r-x` | `--x` | `file.txt` |
|     | 110   | 101   | 001   |            |
|     | **6** | **5** | **1** |            |

# Comando `umask`

Modifica los permisos predeterminados

## Ejemplo

- Archivo base: **666**
- Directorio base: **777**
- `umask` típica: **022**

Con `umask` igual a **022**, los archivos se crean como **644** y los directorios como **755**.

# Comandos `chown` y `chgrp`

- `chown`: cambia el dueño y/o grupo
- `chgrp`: cambia el grupo

# Comandos `su` y `sudo`

- `su`: cambia de usuario, solicita la contraseña del destino
- `sudo`: ejecuta un comndo como otro usuario

# Registros especiales

Los siguientes archivos disponen información acerca de cuentas, sus contraseñas y grupos.

| Ruta           | Estructura                                                               |
| -------------- | ------------------------------------------------------------------------ |
| `/etc/passwd`  | `usuario:contraseña:UID:GID:comentario:home:shell`                       |
| `/etc/shadow`  | `usuario:hash:último_cambio:mín:máx:aviso:inactivo:expiración:reservado` |
| `/etc/group`   | `grupo:contraseña:GID:miembros`                                          |
| `/etc/gshadow` | `grupo:contraseña:adminitradores:miembros`                               |

# Gestión de usuarios y grupos

- `useradd`: crea un usuario
- `usermod`: modifica atributos de un usuario
- `userdel`: borra un usuario
- `groupadd`: crea un grupo
- `groupmod`: modifica atributos de un grupo
- `groupdel`: borra un grupo
- `passwd`: cambia la contraseña de una cuenta
- `gpasswd`: administra contraseñas y miembros de un grupo
- `who`: muestra usuarios conectados
- `w`: muestra usuarios conectados y su actividad

# Permisos especiales

## Conceptos

| Permiso        | Número | Símbolo         | Descripción                                                                                                    |
| -------------- | ------ | --------------- | -------------------------------------------------------------------------------------------------------------- |
| **SUID**       | 4      | `s` en *user*   | Se ejecuta con permisos del dueño.                                                                             |
| **SGID**       | 2      | `s` en *group*  | Se ejecuta con permisos del grupo.                                                                             |
| **Sticky bit** | 1      | `t` en *others* | Solo el dueño o `root` pueden renombrar o borrar archivos dentro del directorio (el permiso se asigna a este). |

## Comandos

| Permiso        | Número           | Símbolo           |
| -------------- | ---------------- | ----------------- |
| **SUID**       | `chmod u+s file` | `chmod 4755 file` |
| **SGID**       | `chmod g+s file` | `chmod 2755 file` |
| **Sticky bit** | `chmod o+t dir`  | `chmod 1755 dir`  |
