# 🔵 Nivel 5 · Automatización y copias de seguridad

---

# Pregunta 1

## Enunciado

Debes realizar una copia de seguridad del directorio:

```text
/home/investigacion
```

¿Cómo lo harías?

---

## 🧠 Cadena de diagnóstico

Antes de realizar cualquier copia debemos responder tres preguntas:

- ¿Qué información debemos proteger?
- ¿Dónde almacenaremos la copia?
- ¿Cómo verificaremos posteriormente que la copia es válida?

Una copia de seguridad solo tiene valor si puede restaurarse.

---

### ✅ Respuesta esperada

Una forma habitual consiste en utilizar:

```bash
tar -czf backup.tar.gz /home/investigacion
```

Este comando:

- agrupa todos los archivos;
- los comprime utilizando gzip;
- genera un único archivo.

---

### Explicación

Opciones utilizadas:

- `c` → crear archivo.
- `z` → comprimir con gzip.
- `f` → indicar el nombre del archivo.

---

### 💡 Otras respuestas válidas

También podrían emplearse herramientas como:

- `rsync`
- `borgbackup`
- `restic`

Sin embargo, `tar` resulta la respuesta esperada por su sencillez y disponibilidad en prácticamente cualquier distribución.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue exactamente la esperada.

Elegiste la herramienta clásica que todo administrador Linux conoce.

Muy buena elección.

---

# Pregunta 2

## Enunciado

¿Por qué no es recomendable almacenar la copia de seguridad en el mismo disco que contiene los datos originales?

---

## 🧠 Cadena de diagnóstico

El objetivo de una copia de seguridad es proteger la información frente a incidentes.

Si el disco falla físicamente, tanto los datos originales como la copia desaparecerán.

---

### ✅ Respuesta esperada

Las copias deberían almacenarse preferentemente:

- en otro disco;
- en otro servidor;
- en un NAS;
- en una ubicación externa;
- en almacenamiento en la nube.

De este modo permanecen disponibles incluso si el servidor principal deja de funcionar.

---

### ⚠️ Error habitual

Pensar que una copia realizada en el mismo disco ya constituye una copia de seguridad suficiente.

En realidad solo protege frente a determinados errores, pero no frente a fallos físicos del almacenamiento.

---

### 👨‍🏫 Comentario del preparador

Aunque esta cuestión no aparecía explícitamente en tu respuesta, considero importante incorporarla porque representa una buena práctica esencial en cualquier entorno profesional.

---

# Pregunta 3

## Enunciado

Debes copiar el archivo de respaldo a un servidor remoto.

¿Cómo lo harías?

---

## 🧠 Cadena de diagnóstico

Una vez creada la copia, el siguiente paso consiste en trasladarla a un sistema independiente.

La transferencia debe realizarse mediante un protocolo seguro.

---

### ✅ Respuesta esperada

Una opción muy habitual es:

```bash
scp backup.tar.gz backup@192.168.10.20:/home/backup/
```

Este comando copia el archivo utilizando SSH, cifrando toda la comunicación.

---

### 💡 Otras respuestas válidas

También serían correctas:

```bash
rsync -av backup.tar.gz backup@192.168.10.20:/home/backup/
```

o utilizar SFTP para realizar la transferencia de forma interactiva.

---

### ⚠️ Error habitual

En tu respuesta inicial escribiste la sintaxis de `scp` con el origen y el destino invertidos.

La forma correcta es:

```bash
scp archivo origen destino
```

En este caso:

```bash
scp backup.tar.gz backup@192.168.10.20:/home/backup/
```

---

### 👨‍🏫 Comentario del preparador

La herramienta elegida fue totalmente correcta.

Únicamente corregimos la sintaxis del comando.

Es un pequeño detalle muy frecuente incluso entre administradores con experiencia.

---

# Pregunta 4

## Enunciado

¿Cómo automatizarías la copia de seguridad para ejecutarse todos los días a las 02:00?

---

## 🧠 Cadena de diagnóstico

Las tareas repetitivas no deberían depender de la intervención manual.

Linux incorpora un sistema de planificación que permite ejecutarlas automáticamente.

---

### ✅ Respuesta esperada

Editar el cron del usuario:

```bash
crontab -e
```

Y añadir una entrada como:

```text
0 2 * * * tar -czf /home/backups/backup.tar.gz /home/investigacion
```

Con esta configuración la copia se ejecutará todos los días a las 02:00.

---

### 💡 Explicación

La expresión cron significa:

```text
Minuto Hora Día Mes DíaSemana
```

Por tanto:

```text
0 2 * * *
```

equivale a:

> Todos los días a las 02:00.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Además proporcionaste un ejemplo realista que demuestra que ya comprendes el funcionamiento básico de Cron.

---

# Pregunta 5

## Enunciado

¿Cómo consultarías las tareas programadas y cómo las modificarías?

---

## 🧠 Cadena de diagnóstico

Antes de crear nuevas tareas conviene comprobar cuáles existen ya programadas.

Esto evita duplicidades y posibles conflictos.

---

### ✅ Respuesta esperada

Consultar las tareas:

```bash
crontab -l
```

Modificar las tareas:

```bash
crontab -e
```

Eliminar todas las tareas:

```bash
crontab -r
```

(utilizar únicamente cuando sea necesario).

---

### ⚠️ Errores habituales

Editar directamente archivos internos de Cron sin necesidad.

En la mayoría de situaciones `crontab` resulta la herramienta adecuada.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Conoces tanto la consulta como la edición de tareas programadas, que constituyen dos operaciones habituales en la administración diaria.

---

# ✅ Valoración del Nivel 5

**Resultado:** Excelente.

Este nivel evalúa la capacidad para mantener un servidor a largo plazo mediante automatización y copias de seguridad.

Has demostrado que comprendes las tres fases fundamentales de cualquier estrategia de respaldo:

1. Crear la copia.
2. Almacenar la copia de forma segura.
3. Automatizar el proceso.

Además, conoces las herramientas clásicas de GNU/Linux para realizar estas tareas (`tar`, `scp` y `cron`), así como las buenas prácticas asociadas a su utilización.

Con este nivel finaliza la misión de administración Linux.

Puedes considerarte preparado para administrar un servidor GNU/Linux básico de forma autónoma y afrontar incidencias habituales siguiendo un procedimiento ordenado y profesional.

---

# 🏁 Valoración final de la misión

Has completado los cinco niveles siguiendo una evolución muy similar a la que encontrarías en un entorno de trabajo real:

- **Nivel 1:** reconocimiento del sistema.
- **Nivel 2:** administración de usuarios y grupos.
- **Nivel 3:** diagnóstico de procesos.
- **Nivel 4:** administración de servicios.
- **Nivel 5:** automatización y continuidad del servicio.

Durante la corrección se han realizado muy pocas modificaciones sobre tus respuestas originales. La mayoría de ellas han consistido en pequeños matices o mejoras de procedimiento, no en errores conceptuales.

## Competencias adquiridas

Al finalizar esta misión eres capaz de:

- Reconocer el estado general de un servidor Linux.
- Administrar usuarios y grupos.
- Gestionar permisos de forma adecuada.
- Diagnosticar procesos y servicios.
- Interpretar registros básicos del sistema.
- Crear y automatizar copias de seguridad.
- Aplicar buenas prácticas de administración.

🎉 **Enhorabuena. Has superado la Misión 01: Administrador Linux.**