<!-- encabezado-homogeneizado -->
# Bloque 01 - CORRECCION RAZONADA
> **Bloque:** Bloque 01  
> **Documento:** Correccion razonada  
> **Preguntas de referencia:** N/D  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# SIMULACRO 01
# Corrección
## Parte 1 (Preguntas 1-25)

---

# Pregunta 1

## Enunciado

¿Cuál de los siguientes directorios de GNU/Linux contiene habitualmente los archivos de configuración del sistema?

a) /usr

✅ b) /etc

c) /var

d) /opt

### ✔ Respuesta correcta

**b) /etc**

### 📖 Explicación

El directorio **/etc** almacena la mayoría de los archivos de configuración del sistema operativo y de los servicios instalados.

Aquí encontramos, entre otros:

- /etc/passwd
- /etc/shadow
- /etc/group
- /etc/hosts
- /etc/fstab
- /etc/hostname

Cuando un administrador necesita modificar la configuración de Apache, SSH, Samba o MySQL, normalmente acudirá a este directorio.

### ❌ ¿Por qué no las demás?

**a) /usr**

Contiene programas, bibliotecas y documentación, pero no la configuración principal.

**c) /var**

Guarda información variable como registros, correo, caché o colas de impresión.

**d) /opt**

Se utiliza habitualmente para instalar software de terceros.

### 💡 Recuerda

**/etc = configuración**

---

# Pregunta 2

## Enunciado

¿Cuál de los siguientes comandos muestra el usuario actualmente autenticado en un sistema GNU/Linux?

a) users

b) id

✅ c) whoami

d) who

### ✔ Respuesta correcta

**c) whoami**

### 📖 Explicación

El comando **whoami** devuelve únicamente el nombre del usuario efectivo que está ejecutando la sesión actual.

Ejemplo:

```bash
pedro
```

Es uno de los comandos más utilizados para comprobar rápidamente con qué identidad se está trabajando.

### ❌ ¿Por qué no las demás?

**a) users**

Muestra los usuarios conectados.

**b) id**

Muestra el usuario, el UID, el GID y todos los grupos a los que pertenece.

**d) who**

Lista las sesiones abiertas en el sistema.

### 💡 Truco

- whoami → "¿Quién soy?"
- who → "¿Quién está conectado?"
- id → "¿Qué identidad tengo?"

---

# Pregunta 3

## Enunciado

Respecto a Active Directory, señale la respuesta correcta.

a) Cada equipo administra sus propios usuarios.

✅ b) Active Directory permite la administración centralizada de usuarios y recursos.

c) Solo puede administrar impresoras.

d) Sustituye completamente al sistema operativo Windows.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

La finalidad de Active Directory es centralizar la administración de:

- usuarios
- grupos
- equipos
- impresoras
- recursos compartidos
- políticas de seguridad

Gracias a ello un usuario puede iniciar sesión en cualquier equipo del dominio utilizando la misma cuenta.

### ❌ ¿Por qué no las demás?

**a)** Describe un grupo de trabajo, no un dominio.

**c)** Administra muchos más recursos que impresoras.

**d)** Active Directory es un servicio del sistema operativo, no un sustituto de Windows Server.

### 💡 Recuerda

Dominio = administración centralizada.

---

# Pregunta 4

## Enunciado

¿Qué comando permite visualizar el espacio ocupado por los sistemas de archivos montados?

a) free -h

b) du

✅ c) df -h

d) mount

### ✔ Respuesta correcta

**c) df -h**

### 📖 Explicación

El comando **df** informa del espacio total, utilizado y disponible de los sistemas de archivos montados.

La opción **-h** muestra la información en un formato legible (MB, GB, TB).

Ejemplo:

```bash
df -h
```

### ❌ ¿Por qué no las demás?

**a) free -h**

Muestra memoria RAM.

**b) du**

Calcula el espacio ocupado por archivos o directorios concretos.

**d) mount**

Muestra o monta sistemas de archivos, pero no resume el espacio libre.

### 💡 Truco

**df → Disk Free**

---

# Pregunta 5

## Enunciado

En Windows Server, una Unidad Organizativa (OU) se utiliza principalmente para:

a) Compartir carpetas.

✅ b) Organizar objetos dentro del dominio.

c) Crear nuevas particiones NTFS.

d) Almacenar perfiles móviles.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Las OU permiten organizar lógicamente los objetos del dominio.

Una estructura típica sería:

Empresa

├── Dirección

├── Administración

├── Informática

└── Recursos Humanos

Posteriormente pueden vincularse GPO a cada OU.

### ❌ ¿Por qué no las demás?

Las OU no sirven para compartir archivos, crear particiones ni almacenar perfiles.

### 💡 Error típico

Muchos opositores confunden una OU con un grupo de seguridad.

Una OU **organiza**.

Un grupo **concede permisos**.

---

# Pregunta 6

## Enunciado

¿Cuál de los siguientes comandos crea un nuevo usuario en GNU/Linux?

a) addgroup

b) usermod

✅ c) useradd

d) passwd

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

El comando **useradd** crea una nueva cuenta de usuario.

Ejemplo:

```bash
sudo useradd pedro
```

Posteriormente suele asignarse una contraseña:

```bash
sudo passwd pedro
```

### ❌ ¿Por qué no las demás?

**addgroup**

Crea grupos.

**usermod**

Modifica usuarios existentes.

**passwd**

Cambia la contraseña.

### 💡 Regla

- useradd → crear
- usermod → modificar
- userdel → eliminar

---

# Pregunta 7

## Enunciado

¿Qué componente almacena la información del directorio en un Controlador de Dominio?

a) SYSVOL

b) Registry

✅ c) NTDS.DIT

d) SAM

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

NTDS.DIT es la base de datos de Active Directory.

Contiene:

- usuarios
- grupos
- equipos
- OU
- atributos
- relaciones

Es uno de los archivos más importantes del dominio.

### ❌ ¿Por qué no las demás?

**SYSVOL**

Almacena las GPO y scripts.

**Registry**

Configuración del sistema operativo.

**SAM**

Base de datos de usuarios locales.

### 💡 Muy preguntable

**SAM = Local**

**NTDS.DIT = Dominio**

---

# Pregunta 8

## Enunciado

¿Cuál de los siguientes sistemas de archivos admite permisos avanzados, compresión, cifrado y cuotas de disco?

a) FAT16

b) FAT32

c) exFAT

✅ d) NTFS

### ✔ Respuesta correcta

**d)**

### 📖 Explicación

NTFS es el sistema de archivos recomendado para Windows Server porque incorpora funciones avanzadas como:

- ACL
- permisos
- compresión
- EFS
- cuotas
- journaling

### ❌ ¿Por qué no las demás?

Los sistemas FAT y exFAT carecen de buena parte de estas funcionalidades.

### 💡 Recuerda

Servidor Windows = NTFS.

---

# Pregunta 9

## Enunciado

¿Qué comando permite cambiar la contraseña de un usuario en GNU/Linux?

a) useradd

✅ b) passwd

c) chmod

d) chown

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

El comando **passwd** cambia la contraseña de un usuario.

Ejemplo:

```bash
passwd pedro
```

### ❌ ¿Por qué no las demás?

useradd crea usuarios.

chmod modifica permisos.

chown modifica propietario.

### 💡 Error muy habitual

No confundir:

- chmod → permisos
- chown → propietario
- passwd → contraseña

---

# Pregunta 10

## Enunciado

Respecto a un grupo de trabajo (Workgroup), indique la afirmación correcta.

a) Dispone de autenticación centralizada.

b) Requiere un Controlador de Dominio.

✅ c) Cada equipo administra sus propios usuarios.

d) Permite aplicar GPO.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

En un grupo de trabajo no existe un servidor que centralice la autenticación.

Cada equipo mantiene su propia base de datos de usuarios locales.

Por ello, un mismo usuario debe existir en cada ordenador si se desea acceder con las mismas credenciales.

### ❌ ¿Por qué no las demás?

**a)** La autenticación centralizada es propia de un dominio.

**b)** Un Workgroup no utiliza Controladores de Dominio.

**d)** Las GPO requieren Active Directory.

### 💡 Comparativa rápida

**Workgroup**

- Usuarios locales
- Administración individual
- Sin GPO

**Dominio**

- Usuarios centralizados
- Active Directory
- GPO
- Administración centralizada

---

# Pregunta 11

## Enunciado

¿Qué comando permite visualizar la memoria RAM utilizada y disponible en GNU/Linux?

a) df -h

✅ b) free -h

c) du -h

d) lsmem

### ✔ Respuesta correcta

**b) free -h**

### 📖 Explicación

El comando **free** muestra el uso de la memoria principal (RAM) y de la memoria de intercambio (Swap).

La opción **-h** presenta los valores en un formato legible (MB, GB...).

Ejemplo:

```bash
free -h
```

Salida típica:

```
              total   used   free   shared  buff/cache
Mem:           15Gi   5Gi    7Gi      ...
Swap:           2Gi   0Gi    2Gi
```

Es uno de los primeros comandos que utiliza un administrador cuando sospecha que un servidor está consumiendo demasiada memoria.

### ❌ ¿Por qué no las demás?

**a) df -h**

Muestra espacio en disco.

**c) du -h**

Calcula el tamaño de archivos y directorios.

**d) lsmem**

Muestra la configuración física de la memoria instalada, pero no el uso actual.

### 💡 Recuerda

**free = memoria**

**df = disco**

---

# Pregunta 12

## Enunciado

¿Cuál de los siguientes es un objeto de Active Directory?

a) FAT32

b) DHCP

c) NTFS

✅ d) Usuario

### ✔ Respuesta correcta

**d) Usuario**

### 📖 Explicación

Active Directory almacena objetos que representan recursos de la red.

Entre ellos:

- Usuarios
- Equipos
- Grupos
- Unidades Organizativas
- Impresoras
- Contactos

Todos estos objetos se almacenan en la base de datos NTDS.DIT.

### ❌ ¿Por qué no las demás?

**FAT32** y **NTFS** son sistemas de archivos.

**DHCP** es un servicio de red.

Ninguno constituye un objeto del directorio.

### 💡 Lo importante

No confundas **servicios** con **objetos**.

---

# Pregunta 13

## Enunciado

¿Qué permiso permite ejecutar un archivo en GNU/Linux?

a) Lectura (r)

✅ b) Ejecución (x)

c) Escritura (w)

d) Propietario (o)

### ✔ Respuesta correcta

**b) Ejecución (x)**

### 📖 Explicación

Los permisos básicos son:

- **r** → lectura
- **w** → escritura
- **x** → ejecución

En un archivo, el permiso **x** permite ejecutarlo como programa o script.

En un directorio, el significado cambia ligeramente: permite acceder a él.

### ❌ ¿Por qué no las demás?

**r**

Solo permite leer.

**w**

Permite modificar.

**o**

No es un permiso; representa "otros usuarios".

### 💡 Truco

**rwx**

Read

Write

eXecute

---

# Pregunta 14

## Enunciado

¿Qué servicio resulta imprescindible para localizar un Controlador de Dominio?

a) FTP

✅ b) DNS

c) SMTP

d) Telnet

### ✔ Respuesta correcta

**b) DNS**

### 📖 Explicación

Active Directory depende completamente de DNS.

Cuando un equipo intenta iniciar sesión en el dominio, utiliza registros DNS (especialmente registros SRV) para localizar el Controlador de Dominio adecuado.

Si DNS falla, el inicio de sesión en el dominio también puede fallar.

### ❌ ¿Por qué no las demás?

FTP sirve para transferencia de archivos.

SMTP para correo electrónico.

Telnet para acceso remoto (actualmente en desuso).

### 💡 Error típico

Muchos alumnos piensan que DNS solo sirve para navegar por Internet.

En un dominio Windows, **DNS es una pieza esencial de Active Directory**.

---

# Pregunta 15

## Enunciado

¿Qué comando modifica los permisos de un archivo en GNU/Linux?

✅ a) chmod

b) chown

c) passwd

d) usermod

### ✔ Respuesta correcta

**a) chmod**

### 📖 Explicación

El comando **chmod** modifica los permisos de acceso de un archivo o directorio.

Ejemplo:

```bash
chmod 755 script.sh
```

o

```bash
chmod +x script.sh
```

### ❌ ¿Por qué no las demás?

**chown**

Cambia el propietario.

**passwd**

Modifica contraseñas.

**usermod**

Modifica cuentas de usuario.

### 💡 Regla de oro

chmod → permisos

chown → propietario

chgrp → grupo

---

# Pregunta 16

## Enunciado

¿Qué ocurre cuando un equipo se une correctamente a un dominio?

a) Elimina todos los usuarios locales.

✅ b) Se crea una cuenta de equipo en Active Directory.

c) Cambia automáticamente el sistema de archivos.

d) Desaparece el grupo de trabajo.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Cuando un equipo entra en un dominio:

- se crea una cuenta de equipo en Active Directory (si no existía),
- establece una relación de confianza con el dominio,
- puede autenticarse utilizando el Controlador de Dominio.

Los usuarios locales siguen existiendo.

### ❌ ¿Por qué no las demás?

No elimina cuentas locales.

No modifica NTFS.

El grupo de trabajo deja de utilizarse, pero no "desaparece".

### 💡 Muy preguntable

Usuarios → cuentas de usuario.

Ordenadores → cuentas de equipo.

---

# Pregunta 17

## Enunciado

¿En qué directorio se almacenan habitualmente los archivos de registro del sistema?

a) /etc

b) /usr

✅ c) /var/log

d) /proc

### ✔ Respuesta correcta

**c) /var/log**

### 📖 Explicación

Los archivos de registro (logs) permiten conocer qué ha ocurrido en el sistema.

Ejemplos:

- syslog
- auth.log
- kern.log
- apache2/
- mysql/

Son fundamentales para la resolución de incidencias.

### ❌ ¿Por qué no las demás?

**/etc**

Configuración.

**/usr**

Programas.

**/proc**

Información del kernel.

### 💡 Recuerda

**/var/log = registros**

---

# Pregunta 18

## Enunciado

¿Cuál es la principal finalidad de un grupo de seguridad?

a) Organizar usuarios por departamentos.

✅ b) Facilitar la asignación de permisos.

c) Crear nuevas OU.

d) Aplicar GPO.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

La mejor práctica consiste en conceder permisos a grupos y añadir usuarios a dichos grupos.

Así se evita administrar permisos usuario por usuario.

Ejemplo:

Grupo:

Finanzas_RW

Usuarios:

Ana

Pedro

Laura

El permiso se concede al grupo, no a cada usuario.

### ❌ ¿Por qué no las demás?

Organizar departamentos corresponde normalmente a las OU.

Las GPO se vinculan a OU, dominios o sitios.

### 💡 Error clásico

OU organiza.

Grupo concede permisos.

---

# Pregunta 19

## Enunciado

¿Qué comando muestra los procesos en ejecución en GNU/Linux?

✅ a) ps

b) passwd

c) cd

d) touch

### ✔ Respuesta correcta

**a) ps**

### 📖 Explicación

El comando **ps** muestra información sobre los procesos en ejecución.

Una de las formas más utilizadas es:

```bash
ps aux
```

Combinado con **grep** permite localizar procesos concretos.

Ejemplo:

```bash
ps aux | grep apache
```

### ❌ ¿Por qué no las demás?

passwd cambia contraseñas.

cd cambia de directorio.

touch crea archivos o actualiza su fecha de modificación.

### 💡 Diferencia importante

**ps**

Fotografía del estado actual.

**top**

Información en tiempo real.

---

# Pregunta 20

## Enunciado

¿Qué permiten aplicar las Directivas de Grupo (GPO)?

a) Permisos NTFS.

✅ b) Configuraciones centralizadas para usuarios y equipos.

c) Direcciones IP automáticas.

d) Usuarios locales.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Las GPO permiten distribuir de forma centralizada cientos de configuraciones.

Algunos ejemplos:

- Fondo de pantalla.
- Restricciones del Panel de control.
- Configuración del Firewall.
- Instalación automática de software.
- Scripts de inicio y cierre.
- Políticas de contraseñas.
- Configuración de Windows Update.

Son una de las principales ventajas de Active Directory frente a un grupo de trabajo.

### ❌ ¿Por qué no las demás?

Los permisos NTFS se administran desde el sistema de archivos.

Las direcciones IP automáticas las proporciona DHCP.

Los usuarios locales no son gestionados mediante GPO.

### 💡 Lo que más pregunta un tribunal

No confundas:

- **Grupo de seguridad → permisos.**
- **GPO → configuración.**

Son dos conceptos diferentes que suelen aparecer juntos en los exámenes.

---

# Pregunta 21

## Enunciado

¿Qué comando permite cambiar el propietario de un archivo en GNU/Linux?

a) chmod

✅ b) chown

c) chgrp

d) passwd

### ✔ Respuesta correcta

**b) chown**

### 📖 Explicación

El comando **chown** (*change owner*) permite modificar el propietario de un archivo o directorio. También puede cambiar simultáneamente el grupo propietario.

Ejemplos:

```bash
chown pedro informe.txt
```

Cambia el propietario a **pedro**.

```bash
chown pedro:ventas informe.txt
```

Cambia el propietario a **pedro** y el grupo a **ventas**.

Es una operación muy habitual cuando se administran directorios compartidos o servicios que necesitan acceder a determinados archivos.

---

### ❌ ¿Por qué no las demás?

**a) chmod**

Modifica los permisos, pero no el propietario.

**c) chgrp**

Solo modifica el grupo propietario.

**d) passwd**

Cambia la contraseña de un usuario.

---

### 💡 Regla fácil de recordar

- **chmod** → permisos.
- **chown** → propietario.
- **chgrp** → grupo.

Muchísimas preguntas de oposición juegan precisamente con estos tres comandos.

---

# Pregunta 22

## Enunciado

En Active Directory, una Unidad Organizativa (OU) permite:

a) Asignar permisos sobre carpetas.

✅ b) Organizar los objetos del dominio.

c) Sustituir a los grupos de seguridad.

d) Crear automáticamente usuarios.

### ✔ Respuesta correcta

**b) Organizar los objetos del dominio.**

### 📖 Explicación

Las **OU (Organizational Units)** sirven para organizar de forma lógica los objetos del dominio.

Dentro de una OU podemos almacenar:

- Usuarios
- Equipos
- Grupos
- Impresoras
- Otras OU

Esta organización facilita enormemente la administración y permite aplicar políticas específicas mediante GPO.

Por ejemplo:

```
Empresa
│
├── Dirección
├── Administración
├── Informática
└── Comercial
```

Cada departamento puede recibir configuraciones distintas sin afectar al resto.

---

### ❌ ¿Por qué no las demás?

**a)**

Los permisos sobre recursos se asignan mediante grupos de seguridad o ACL de NTFS.

**c)**

Las OU y los grupos tienen finalidades completamente distintas.

**d)**

Una OU únicamente organiza objetos existentes.

---

### 💡 Truco de oposición

Cuando aparezca una pregunta con:

- OU
- Grupo
- GPO

piensa inmediatamente:

| Elemento | Función |
|----------|----------|
| OU | Organizar |
| Grupo | Permisos |
| GPO | Configuración |

---

# Pregunta 23

## Enunciado

¿Qué comando muestra el directorio de trabajo actual?

a) cd

✅ b) pwd

c) ls

d) dir

### ✔ Respuesta correcta

**b) pwd**

### 📖 Explicación

El comando **pwd** (*Print Working Directory*) muestra la ruta completa del directorio en el que se encuentra actualmente el usuario.

Ejemplo:

```bash
pwd
```

Salida:

```
/home/pedro/proyectos
```

Es especialmente útil cuando se trabaja en estructuras de directorios profundas o tras ejecutar varios cambios de directorio consecutivos.

---

### ❌ ¿Por qué no las demás?

**a) cd**

Permite cambiar de directorio.

**c) ls**

Lista el contenido del directorio.

**d) dir**

Existe en algunos sistemas, pero no es el comando estándar utilizado en GNU/Linux.

---

### 💡 Asociación rápida

- **pwd** → ¿Dónde estoy?
- **cd** → Quiero moverme.
- **ls** → ¿Qué hay aquí?

---

# Pregunta 24

## Enunciado

¿Qué ocurre cuando se deshabilita una cuenta de usuario en Active Directory?

a) Se elimina permanentemente.

b) Se convierte en una cuenta local.

✅ c) El usuario deja de poder iniciar sesión, pero la cuenta permanece en el dominio.

d) Se eliminan automáticamente todos sus permisos.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Deshabilitar una cuenta impide que el usuario pueda autenticarse en el dominio, pero mantiene toda su información:

- Pertenencia a grupos.
- Descripción.
- Perfil.
- Historial.
- Permisos.

Esta práctica resulta muy útil cuando un empleado abandona temporalmente la organización o mientras se decide si la cuenta debe eliminarse definitivamente.

Es una medida mucho más segura que borrar la cuenta directamente.

---

### ❌ ¿Por qué no las demás?

**a)**

Deshabilitar no significa eliminar.

**b)**

La cuenta sigue perteneciendo al dominio.

**d)**

Los permisos permanecen asociados a la cuenta.

---

### 💡 Buena práctica

Antes de eliminar una cuenta:

1. Deshabilitarla.
2. Comprobar que ya no es necesaria.
3. Eliminarla cuando proceda.

Este procedimiento reduce el riesgo de borrar información importante por error.

---

# Pregunta 25

## Enunciado

¿Cuál es el directorio personal que se crea habitualmente para los usuarios normales en GNU/Linux?

a) /root

✅ b) /home

c) /users

d) /opt

### ✔ Respuesta correcta

**b) /home**

### 📖 Explicación

En GNU/Linux, los usuarios normales disponen de un directorio personal dentro de **/home**.

Ejemplos:

```
/home/ana

/home/pedro

/home/maria
```

En estos directorios se almacenan:

- Documentos.
- Descargas.
- Configuración personal.
- Archivos ocultos del usuario.
- Escritorio.

Por el contrario, el usuario **root** tiene normalmente su directorio personal en:

```
/root
```

---

### ❌ ¿Por qué no las demás?

**a) /root**

Corresponde exclusivamente al superusuario.

**c) /users**

No forma parte de la estructura estándar de GNU/Linux.

**d) /opt**

Se utiliza para aplicaciones adicionales.

---

### 💡 Muy preguntable

No confundas:

```
/home
```

Usuarios normales.

```
/root
```

Administrador del sistema.

---

# 📚 Resumen del bloque (Preguntas 1-25)

## Conceptos clave

### Estructura del sistema de archivos

| Directorio | Función |
|------------|----------|
| /etc | Configuración |
| /home | Usuarios |
| /root | Administrador |
| /var/log | Registros |
| /proc | Información del kernel |

---

### Comandos GNU/Linux

| Comando | Función |
|----------|----------|
| whoami | Usuario actual |
| pwd | Directorio actual |
| ls | Listar archivos |
| cd | Cambiar directorio |
| df -h | Espacio en disco |
| free -h | Memoria RAM |
| ps | Procesos |
| passwd | Contraseña |
| chmod | Permisos |
| chown | Propietario |
| useradd | Crear usuario |

---

### Active Directory

| Elemento | Función |
|----------|----------|
| OU | Organización lógica |
| Grupo de seguridad | Asignación de permisos |
| GPO | Configuración centralizada |
| NTDS.DIT | Base de datos del directorio |
| DNS | Localización de Controladores de Dominio |

---

# ⚠️ Errores típicos del opositor

❌ Confundir **chmod**, **chown** y **chgrp**.

❌ Pensar que las OU sirven para asignar permisos.

❌ Creer que una GPO concede permisos sobre recursos.

❌ Confundir **SAM** con **NTDS.DIT**.

❌ Pensar que DNS únicamente sirve para navegar por Internet.

❌ Confundir **df -h** (disco) con **free -h** (memoria).

❌ Confundir **/home** con **/root**.

❌ Creer que deshabilitar una cuenta equivale a eliminarla.

---

# 🎯 Consejo para el opositor

Si dominas estos primeros 25 conceptos, tendrás una base muy sólida para afrontar el resto del bloque de GNU/Linux, Windows Server y Active Directory. Son preguntas aparentemente sencillas, pero esconden muchas de las confusiones más habituales en los exámenes oficiales. Antes de pasar al siguiente bloque, asegúrate de poder explicar cada respuesta con tus propias palabras: si eres capaz de hacerlo, habrás dejado de memorizar y habrás empezado a comprender.
