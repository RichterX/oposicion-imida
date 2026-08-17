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
## Parte 4 (Preguntas 26-55)

---

# Pregunta 26

## Enunciado

¿Cuál de los siguientes comandos permite cambiar el propietario de un archivo en GNU/Linux?

a) chmod

✅ b) chown

c) chgrp

d) passwd

### ✔ Respuesta correcta

**b) chown**

### 📖 Explicación

El comando **chown** (*change owner*) modifica el propietario de un archivo o directorio. Opcionalmente también permite cambiar el grupo propietario.

Ejemplo:

```bash
chown pedro informe.pdf
```

También:

```bash
chown pedro:ventas informe.pdf
```

En este caso cambia tanto el propietario como el grupo.

Es un comando muy utilizado tras copiar archivos entre usuarios o al configurar servicios como Apache o Nginx, que necesitan que determinados archivos pertenezcan al usuario adecuado.

### ❌ ¿Por qué no las demás?

**chmod**

Modifica permisos.

**chgrp**

Solo cambia el grupo propietario.

**passwd**

Modifica contraseñas.

### 💡 Recuerda

> chmod → Permisos

> chown → Propietario

> chgrp → Grupo

---

# Pregunta 27

## Enunciado

En Active Directory, una Unidad Organizativa (OU) puede contener:

a) Únicamente usuarios.

b) Únicamente equipos.

✅ c) Usuarios, equipos, grupos y otras OU.

d) Exclusivamente grupos de seguridad.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Una OU es un contenedor lógico.

Puede contener prácticamente cualquier objeto del dominio:

- Usuarios
- Equipos
- Grupos
- Impresoras
- Contactos
- Otras OU

Gracias a esta jerarquía es posible organizar el dominio de forma muy flexible.

Ejemplo:

```
Empresa
│
├── Administración
│   ├── Usuarios
│   └── Equipos
│
└── Informática
```

### ❌ ¿Por qué no las demás?

Las opciones a), b) y d) limitan incorrectamente el tipo de objetos que puede contener una OU.

### 💡 Pregunta típica

Una OU **no concede permisos**.

---

# Pregunta 28

## Enunciado

¿Qué comando muestra el tiempo que lleva encendido un sistema GNU/Linux?

a) top

b) hostname

✅ c) uptime

d) who

### ✔ Respuesta correcta

**c) uptime**

### 📖 Explicación

El comando **uptime** muestra:

- Hora actual.
- Tiempo que lleva funcionando el sistema.
- Número de usuarios conectados.
- Carga media del sistema (Load Average).

Ejemplo:

```bash
uptime
```

Salida:

```
13:25 up 15 days, 4:16, 3 users,
load average: 0.24, 0.18, 0.15
```

Es muy útil para comprobar la estabilidad de un servidor.

### ❌ ¿Por qué no las demás?

**top**

Procesos.

**hostname**

Nombre del equipo.

**who**

Usuarios conectados.

### 💡 Muy preguntable

No confundas:

- uptime → tiempo funcionando
- top → procesos

---

# Pregunta 29

## Enunciado

¿Qué servicio de Windows Server asigna automáticamente direcciones IP?

a) DNS

✅ b) DHCP

c) IIS

d) LDAP

### ✔ Respuesta correcta

**b) DHCP**

### 📖 Explicación

DHCP (*Dynamic Host Configuration Protocol*) asigna automáticamente:

- Dirección IP
- Máscara
- Puerta de enlace
- DNS
- Otros parámetros de red

Sin DHCP habría que configurar manualmente cada equipo.

### ❌ ¿Por qué no las demás?

DNS resuelve nombres.

IIS publica páginas web.

LDAP es un protocolo de acceso a directorios.

### 💡 Asociación rápida

DHCP → Configuración IP

DNS → Resolución de nombres

---

# Pregunta 30

## Enunciado

Respecto a las Directivas de Grupo (GPO), indique la respuesta CORRECTA.

a) Solo pueden aplicarse a usuarios.

b) Solo pueden aplicarse a equipos.

✅ c) Permiten aplicar configuraciones de forma centralizada a usuarios y equipos.

d) Sustituyen a los grupos de seguridad.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Una GPO puede contener:

- Configuración de usuario.
- Configuración de equipo.

Dentro de una misma política pueden existir ambos tipos de configuración.

Ejemplos:

Usuarios:

- Fondo de pantalla.
- Panel de control.
- Escritorio.

Equipos:

- Firewall.
- Windows Update.
- Auditoría.
- Servicios.

### ❌ ¿Por qué no las demás?

a) Incorrecta.

b) Incorrecta.

Las GPO permiten ambas configuraciones.

d) Incorrecta.

Los grupos gestionan permisos, las GPO gestionan configuración.

### 💡 Error clásico

Grupo ≠ GPO

---

# Pregunta 31

## Enunciado

¿Qué comando permite buscar procesos cuyo nombre contiene la palabra "apache"?

a) ls | apache

✅ b) ps aux | grep apache

c) top apache

d) find apache

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Una combinación muy utilizada en administración:

```bash
ps aux | grep apache
```

Primero:

```bash
ps aux
```

Muestra todos los procesos.

Después:

```bash
grep apache
```

Filtra únicamente aquellos cuyo nombre contiene "apache".

### ❌ ¿Por qué no las demás?

Las demás opciones no son comandos válidos para este propósito.

### 💡 Muy útil

Este patrón se utiliza constantemente para localizar procesos.

---

# Pregunta 32

## Enunciado

¿Cuál de las siguientes afirmaciones sobre NTFS es CORRECTA?

a) No admite permisos sobre archivos.

b) Solo puede utilizarse en Windows XP.

✅ c) Permite establecer permisos sobre archivos y carpetas.

d) No admite cuotas de disco.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

NTFS incorpora numerosas características avanzadas:

- ACL
- Compresión
- Cifrado (EFS)
- Cuotas
- Journaling
- Permisos

Es el sistema de archivos recomendado para Windows Server.

### ❌ ¿Por qué no las demás?

Todas contradicen funcionalidades reales de NTFS.

### 💡 Regla

Windows Server → NTFS

---

# Pregunta 33

## Enunciado

Un usuario cambia del departamento de Administración al de Investigación. ¿Cuál de las siguientes acciones sería la más adecuada?

a) Crear un usuario nuevo.

b) Cambiar únicamente la contraseña.

✅ c) Mover el usuario a la OU correspondiente y revisar su pertenencia a grupos.

d) Eliminar la cuenta y volver a crearla.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

La buena práctica consiste en mantener la misma cuenta.

Solo es necesario:

- moverla a la nueva OU;
- revisar los grupos de seguridad;
- comprobar las GPO que se aplicarán.

Así se conserva el historial, SID, permisos y recursos asociados.

### ❌ ¿Por qué no las demás?

Crear una cuenta nueva implica perder referencias y aumentar el trabajo administrativo.

### 💡 Esta pregunta es muy de oposición

Busca la solución administrativa más eficiente, no simplemente una que funcione.

---

# Pregunta 34

## Enunciado

¿Cuál de los siguientes directorios virtuales proporciona información sobre procesos y el kernel?

a) /tmp

✅ b) /proc

c) /srv

d) /boot

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

/proc es un sistema de archivos virtual.

No almacena archivos reales.

Genera información dinámicamente sobre:

- procesos
- memoria
- CPU
- kernel
- dispositivos

Ejemplo:

```
/proc/cpuinfo

/proc/meminfo

/proc/version
```

### ❌ ¿Por qué no las demás?

/tmp → temporales.

/srv → servicios.

/boot → arranque.

### 💡 Muy preguntable

/proc no ocupa espacio en disco como un directorio normal.

---

# Pregunta 35

## Enunciado

¿Cuál de las siguientes afirmaciones sobre los grupos de seguridad es CORRECTA?

a) Se utilizan principalmente para enviar correo electrónico.

✅ b) Permiten asignar permisos a varios usuarios simultáneamente.

c) Sustituyen a las OU.

d) No pueden contener usuarios.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Los grupos permiten aplicar permisos de forma colectiva.

Ejemplo:

Grupo:

```
Ventas_RW
```

Usuarios:

- Ana
- Pedro
- María

Se concede el permiso al grupo.

Los usuarios lo heredan automáticamente.

Es una de las principales buenas prácticas en administración de Active Directory.

### ❌ ¿Por qué no las demás?

Los grupos de distribución son los utilizados para correo electrónico.

Las OU organizan objetos.

Los grupos precisamente están diseñados para contener usuarios.

### 💡 Regla de oro

Nunca concedas permisos usuario por usuario.

Concede permisos a grupos y añade los usuarios a esos grupos.

---

# Pregunta 36

## Enunciado

¿Qué comando muestra el nombre del equipo en GNU/Linux?

a) uname

✅ b) hostname

c) whoami

d) machine

### ✔ Respuesta correcta

**b) hostname**

### 📖 Explicación

El comando **hostname** muestra el nombre asignado al equipo dentro de la red.

Ejemplo:

```bash
hostname
```

Salida:

```
srv-web-01
```

También puede utilizarse para modificar temporalmente el nombre del equipo (aunque actualmente suele gestionarse mediante `hostnamectl` en sistemas con systemd).

### ❌ ¿Por qué no las demás?

**a) uname**

Muestra información del sistema operativo y del kernel.

**c) whoami**

Muestra el usuario actual.

**d) machine**

No es un comando estándar de GNU/Linux.

### 🎯 Lo que busca realmente el tribunal

Distinguir entre información del **equipo** (`hostname`) y del **usuario** (`whoami`).

---

# Pregunta 37

## Enunciado

¿Cuál de las siguientes ventajas ofrece una GPO frente a la configuración manual de cada equipo?

a) Reduce la memoria utilizada por Windows.

✅ b) Permite administrar configuraciones de forma centralizada.

c) Sustituye la autenticación del dominio.

d) Elimina la necesidad de Active Directory.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Las Directivas de Grupo (GPO) permiten definir configuraciones que se aplicarán automáticamente a múltiples usuarios o equipos.

Por ejemplo:

- Deshabilitar el Panel de control.
- Configurar Windows Update.
- Instalar software.
- Definir el fondo de pantalla.
- Configurar el Firewall.

Sin GPO, estas tareas tendrían que realizarse equipo por equipo.

### ❌ ¿Por qué no las demás?

Las GPO no reducen el consumo de memoria, no sustituyen la autenticación y dependen precisamente de Active Directory.

### 🎯 Lo que busca realmente el tribunal

Comprobar si el opositor entiende el concepto de **administración centralizada**, una de las ventajas fundamentales de un dominio.

---

# Pregunta 38

## Enunciado

¿Qué comando permite crear un archivo comprimido en formato tar?

a) zip

✅ b) tar

c) cpio

d) gzip

### ✔ Respuesta correcta

**b) tar**

### 📖 Explicación

El comando **tar** agrupa varios archivos en un único archivo (tarball) y, opcionalmente, puede comprimirlos utilizando gzip, bzip2 o xz.

Ejemplos:

```bash
tar -cvf copia.tar documentos/
```

Crear un archivo TAR.

```bash
tar -czvf copia.tar.gz documentos/
```

Crear un archivo TAR comprimido con gzip.

### ❌ ¿Por qué no las demás?

**zip**

Utiliza otro formato distinto.

**cpio**

Es otra utilidad de archivado, mucho menos habitual.

**gzip**

Comprime un único archivo, pero no crea por sí mismo un archivo TAR.

### 💡 Truco

**tar** agrupa.

**gzip** comprime.

Normalmente se utilizan juntos.

---

# Pregunta 39

## Enunciado

¿Cuál de las siguientes afirmaciones sobre un Controlador de Dominio es CORRECTA?

a) Cada dominio puede tener únicamente uno.

✅ b) Almacena la base de datos de Active Directory y autentica usuarios.

c) Solo almacena perfiles móviles.

d) Sustituye completamente al servidor DNS.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

El Controlador de Dominio (Domain Controller) es el servidor que ejecuta Active Directory Domain Services.

Entre sus funciones destacan:

- Autenticar usuarios.
- Autorizar accesos.
- Replicar la información del dominio.
- Almacenar la base de datos NTDS.DIT.

Un dominio puede disponer de varios Controladores de Dominio para mejorar la disponibilidad y la tolerancia a fallos.

### ❌ ¿Por qué no las demás?

**a)**

Es habitual disponer de varios Controladores de Dominio.

**c)**

Los perfiles móviles son solo una funcionalidad adicional.

**d)**

Active Directory depende de DNS; no lo sustituye.

### 🎯 Lo que busca realmente el tribunal

Evitar la confusión entre **Dominio**, **Controlador de Dominio** y **Servidor DNS**.

---

# Pregunta 40

## Enunciado

Respecto al directorio **/tmp**, señale la respuesta correcta.

✅ a) Contiene archivos temporales.

b) Almacena los perfiles de usuario.

c) Contiene los binarios esenciales del sistema.

d) Guarda los registros del sistema.

### ✔ Respuesta correcta

**a)**

### 📖 Explicación

El directorio **/tmp** se utiliza para almacenar archivos temporales creados por aplicaciones o por el propio sistema operativo.

Su contenido puede eliminarse automáticamente durante el reinicio o mediante tareas de limpieza programadas.

### ❌ ¿Por qué no las demás?

**b)**

Los perfiles de usuario se almacenan normalmente en `/home`.

**c)**

Los binarios esenciales se encuentran en directorios como `/bin` o `/usr/bin`.

**d)**

Los registros se almacenan en `/var/log`.

### 💡 Asociación rápida

- `/tmp` → Temporales.
- `/var/log` → Registros.
- `/home` → Usuarios.

---

# Pregunta 41

## Enunciado

¿Cuál de las siguientes operaciones es recomendable realizar antes de eliminar definitivamente un objeto de Active Directory?

a) Cambiar el nombre del objeto.

b) Reiniciar el servidor.

✅ c) Deshabilitar el objeto y comprobar que ya no es necesario.

d) Convertirlo en administrador.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Eliminar un objeto es una acción irreversible (salvo que exista Papelera de reciclaje de Active Directory o una copia de seguridad).

Por ello, la buena práctica consiste en:

1. Deshabilitar la cuenta.
2. Esperar un tiempo prudencial.
3. Confirmar que ya no es necesaria.
4. Eliminarla definitivamente.

Este procedimiento reduce considerablemente el riesgo de pérdidas accidentales.

### 🎯 Lo que busca realmente el tribunal

No memorizar comandos, sino evaluar si el candidato conoce las **buenas prácticas de administración**.

---

# Pregunta 42

## Enunciado

¿Qué utilidad gráfica permite administrar usuarios, grupos y equipos en Active Directory?

a) Administración de discos.

b) Visor de eventos.

✅ c) Usuarios y equipos de Active Directory.

d) Monitor de rendimiento.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

La consola **Usuarios y equipos de Active Directory** (Active Directory Users and Computers, ADUC) es la herramienta administrativa más utilizada para gestionar:

- Usuarios.
- Equipos.
- Grupos.
- OU.
- Contactos.

Desde ella pueden realizarse la mayoría de las tareas diarias de administración.

### ❌ ¿Por qué no las demás?

Cada una corresponde a otra herramienta de Windows Server con funciones completamente distintas.

### 💡 Muy preguntable

Aprende también otras consolas habituales:

- DNS Manager.
- DHCP Manager.
- Group Policy Management.
- Active Directory Sites and Services.

---

# Pregunta 43

## Enunciado

¿Qué comando permite cambiar el directorio de trabajo actual en GNU/Linux?

a) pwd

✅ b) cd

c) ls

d) mv

### ✔ Respuesta correcta

**b) cd**

### 📖 Explicación

El comando **cd** (*Change Directory*) permite desplazarse entre directorios.

Ejemplos:

```bash
cd /etc
```

```bash
cd ..
```

```bash
cd ~
```

Es uno de los comandos más utilizados en cualquier sistema GNU/Linux.

### ❌ ¿Por qué no las demás?

- **pwd** muestra el directorio actual.
- **ls** lista su contenido.
- **mv** mueve o renombra archivos.

### 🎯 Lo que busca realmente el tribunal

Comprobar que el opositor distingue claramente entre los comandos básicos de navegación.

---

# Pregunta 44

## Enunciado

¿Cuál de las siguientes afirmaciones sobre las cuentas de equipo es CORRECTA?

a) Solo existen mientras el equipo está encendido.

✅ b) Se crean automáticamente al unir el equipo al dominio.

c) Deben crearse manualmente cada vez que el equipo inicia Windows.

d) No pueden recibir GPO.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Cuando un equipo se incorpora a un dominio, Active Directory crea una **cuenta de equipo**.

Esta cuenta:

- Tiene un SID propio.
- Posee una contraseña que cambia automáticamente.
- Puede pertenecer a una OU.
- Puede recibir Directivas de Grupo.

No debe confundirse con una cuenta de usuario.

### ❌ ¿Por qué no las demás?

Las cuentas de equipo son permanentes mientras el objeto exista en Active Directory y sí pueden recibir GPO.

### 💡 Curiosidad

En Active Directory, los nombres de las cuentas de equipo suelen terminar con el carácter **$**.

Ejemplo:

```
PC-AULA01$
```

---

# Pregunta 45

## Enunciado

¿Qué característica diferencia principalmente un dominio de un grupo de trabajo?

a) El dominio utiliza únicamente direcciones IP estáticas.

✅ b) El dominio proporciona autenticación y administración centralizadas.

c) El dominio solo puede tener diez equipos.

d) El dominio elimina la necesidad de usuarios.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Esta es probablemente **la idea más importante de todo el bloque de Active Directory**.

En un dominio:

- Existe autenticación centralizada.
- Los usuarios pueden iniciar sesión en cualquier equipo autorizado.
- Se aplican GPO.
- Los recursos se administran de forma centralizada.

En un grupo de trabajo:

- Cada equipo mantiene sus propios usuarios.
- No existe autenticación centralizada.
- No pueden aplicarse GPO de dominio.

### ❌ ¿Por qué no las demás?

Las demás opciones son falsas y no representan diferencias reales entre ambos modelos.

### 🎯 Lo que busca realmente el tribunal

Esta pregunta no evalúa un detalle técnico, sino si el opositor comprende el **objetivo principal de Active Directory**.

---

# Pregunta 46

## Enunciado

¿Qué comando muestra información detallada sobre un usuario, incluyendo los grupos a los que pertenece?

a) groups

✅ b) id

c) whoami

d) finger

### ✔ Respuesta correcta

**b) id**

### 📖 Explicación

El comando **id** muestra la identidad completa de un usuario:

- UID (User ID).
- GID (Group ID principal).
- Grupos secundarios.
- Nombre del usuario.

Ejemplo:

```bash
id pedro
```

Salida:

```
uid=1000(pedro)
gid=1000(pedro)
groups=1000(pedro),27(sudo),100(users)
```

Es uno de los comandos más útiles para comprobar rápidamente la pertenencia a grupos y verificar permisos.

---

### ❌ ¿Por qué no las demás?

**groups**

Solo muestra los grupos del usuario.

**whoami**

Únicamente muestra el nombre del usuario actual.

**finger**

Proporciona información adicional sobre usuarios, pero actualmente apenas se utiliza y suele no estar instalado.

---

### 💡 Truco

Piensa en **id** como la "ficha completa" del usuario.

---

# Pregunta 47

## Enunciado

¿Cuál de las siguientes afirmaciones sobre las OU es FALSA?

a) Facilitan la organización de los objetos.

b) Permiten vincular GPO.

✅ c) Sustituyen a los grupos de seguridad para asignar permisos.

d) Pueden contener otras OU.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Las OU no tienen ninguna relación con la asignación de permisos.

Su finalidad es:

- Organizar objetos.
- Facilitar la administración.
- Permitir aplicar GPO.

Los permisos se conceden mediante:

- ACL.
- Grupos de seguridad.

---

### ❌ ¿Por qué no las demás?

Todas describen correctamente una OU.

---

### 🎯 Lo que busca realmente el tribunal

Esta es una de las confusiones más frecuentes entre opositores:

OU ≠ Grupo

---

# Pregunta 48

## Enunciado

En un entorno Windows Server, ¿qué servicio resulta imprescindible para el correcto funcionamiento de Active Directory?

a) FTP

✅ b) DNS

c) Telnet

d) SMTP

### ✔ Respuesta correcta

**b) DNS**

### 📖 Explicación

Active Directory utiliza DNS para localizar:

- Controladores de Dominio.
- Servicios LDAP.
- Servicios Kerberos.
- Catálogo Global.

Cuando un usuario inicia sesión, el primer paso suele ser consultar DNS.

Sin un DNS correctamente configurado, Active Directory no puede funcionar correctamente.

---

### ❌ ¿Por qué no las demás?

FTP → transferencia de archivos.

SMTP → correo.

Telnet → acceso remoto.

---

### 💡 Pregunta muy habitual

El tribunal suele preguntar:

> ¿Qué servicio es imprescindible para Active Directory?

La respuesta casi siempre será **DNS**.

---

# Pregunta 49

## Enunciado

Un administrador desea que todos los equipos del departamento de Investigación tengan el mismo fondo de pantalla.

¿Cuál sería la solución más adecuada?

a) Configurarlo manualmente en cada equipo.

✅ b) Crear una GPO y vincularla a la OU Investigación.

c) Cambiar el fondo del Controlador de Dominio.

d) Crear un grupo de seguridad.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Las GPO permiten distribuir configuraciones automáticamente.

En este caso bastaría con:

1. Crear la política.
2. Configurar el fondo.
3. Vincular la GPO a la OU correspondiente.

Todos los equipos recibirían automáticamente la configuración.

---

### ❌ ¿Por qué no las demás?

Configurar cada equipo manualmente no escala.

Cambiar el fondo del servidor no afecta a los clientes.

Los grupos de seguridad no modifican configuraciones.

---

### 🎯 Lo que busca realmente el tribunal

Pensar como un administrador.

No basta con que una solución funcione.

Debe ser **la más eficiente**.

---

# Pregunta 50

## Enunciado

¿Qué comando permite listar el contenido de un directorio en GNU/Linux?

a) dirlist

✅ b) ls

c) tree

d) cat

### ✔ Respuesta correcta

**b) ls**

### 📖 Explicación

El comando **ls** muestra el contenido de un directorio.

Ejemplos:

```bash
ls
```

```bash
ls -l
```

```bash
ls -la
```

Es probablemente el comando más utilizado en GNU/Linux.

---

### ❌ ¿Por qué no las demás?

**tree**

Muestra una estructura jerárquica (si está instalado).

**cat**

Muestra el contenido de archivos.

**dirlist**

No existe.

---

### 💡 Asociación

ls

↓

¿Qué hay aquí?

---

# Pregunta 51

## Enunciado

¿Cuál de los siguientes comandos permite finalizar un proceso indicando su PID?

a) stop

b) end

✅ c) kill

d) halt

### ✔ Respuesta correcta

**c) kill**

### 📖 Explicación

El comando **kill** envía señales a un proceso.

La más utilizada es:

```bash
kill PID
```

También:

```bash
kill -9 PID
```

Envía la señal SIGKILL, forzando la finalización del proceso.

---

### ❌ ¿Por qué no las demás?

**halt**

Detiene el sistema operativo completo.

Las otras opciones no son comandos válidos.

---

### 💡 Muy preguntable

Primero intenta:

```
kill PID
```

Solo utiliza:

```
kill -9
```

cuando el proceso no responde.

---

# Pregunta 52

## Enunciado

Respecto a los permisos en GNU/Linux, indique la respuesta CORRECTA.

a) Un usuario siempre puede modificar cualquier archivo del sistema.

✅ b) Los permisos determinan quién puede leer, escribir o ejecutar un archivo.

c) Los permisos únicamente afectan a los directorios.

d) Los permisos solo pueden modificarse reiniciando el sistema.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

El sistema de permisos de GNU/Linux determina qué acciones pueden realizar:

- El propietario.
- El grupo.
- El resto de usuarios.

Cada uno dispone de permisos:

- Lectura.
- Escritura.
- Ejecución.

Es uno de los pilares fundamentales del modelo de seguridad de Linux.

---

### ❌ ¿Por qué no las demás?

Todas son afirmaciones falsas.

---

### 🎯 Lo que busca realmente el tribunal

Comprobar que conoces el modelo de permisos de Linux.

---

# Pregunta 53

## Enunciado

¿Qué afirmación describe mejor la función de un bosque (Forest) en Active Directory?

a) Es un conjunto de equipos unidos mediante DHCP.

✅ b) Es el nivel superior de la estructura lógica de Active Directory.

c) Es una colección de GPO.

d) Es el directorio donde se almacenan los perfiles móviles.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

El **Bosque (Forest)** constituye el nivel más alto de la estructura lógica de Active Directory.

Un bosque puede contener:

- Uno o varios árboles.
- Uno o varios dominios.

Todos comparten:

- Esquema.
- Configuración.
- Catálogo Global.

---

### ❌ ¿Por qué no las demás?

Ninguna describe correctamente un bosque.

---

### 💡 Regla fácil

Bosque

↓

Árboles

↓

Dominios

↓

OU

↓

Objetos

---

# Pregunta 54

## Enunciado

¿Qué comando muestra los grupos a los que pertenece el usuario actual?

a) users

✅ b) groups

c) chmod

d) grep

### ✔ Respuesta correcta

**b) groups**

### 📖 Explicación

El comando **groups** muestra únicamente los grupos a los que pertenece un usuario.

Ejemplo:

```bash
groups pedro
```

Salida:

```
pedro sudo docker developers
```

Es más sencillo que **id**, ya que únicamente muestra la pertenencia a grupos.

---

### ❌ ¿Por qué no las demás?

**users**

Usuarios conectados.

**chmod**

Permisos.

**grep**

Búsqueda de texto.

---

### 💡 Diferencia importante

groups

↓

Solo grupos

id

↓

Toda la identidad

---

# Pregunta 55

## Enunciado

Un administrador necesita impedir que los usuarios accedan al Panel de control de Windows.

¿Cuál es la solución más adecuada?

a) Eliminar el Panel de control.

✅ b) Aplicar una GPO.

c) Crear una nueva OU.

d) Cambiar el sistema de archivos a FAT32.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Una Directiva de Grupo permite restringir el acceso al Panel de control de forma centralizada.

Esta configuración puede aplicarse:

- A un usuario.
- A un grupo.
- A una OU.
- A un dominio completo.

No es necesario modificar cada equipo manualmente.

---

### ❌ ¿Por qué no las demás?

Eliminar el Panel de control no es una práctica correcta.

Crear una OU no modifica configuraciones.

El sistema de archivos no tiene relación con esta funcionalidad.

---

### 🎯 Lo que busca realmente el tribunal

Cada vez que el enunciado diga:

> "Aplicar una configuración"

empieza a pensar inmediatamente en:

**GPO.**

