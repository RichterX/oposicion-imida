# 🟠 Nivel 3 · Procesos y servicios

---

# Pregunta 1

## Enunciado

El servidor responde muy lentamente.

¿Qué herramienta utilizarías para observar el sistema en tiempo real?

---

## 🧠 Cadena de diagnóstico

Cuando un servidor comienza a responder lentamente, el primer objetivo no es reiniciarlo.

Debemos obtener una visión global del sistema para identificar el recurso que está provocando el problema.

Antes de actuar conviene responder preguntas como:

- ¿La CPU está saturada?
- ¿Falta memoria RAM?
- ¿Existe un proceso consumiendo todos los recursos?
- ¿Hay un problema de entrada/salida en disco?

---

### ✅ Respuesta esperada

Las herramientas más utilizadas son:

```bash
top
```

o

```bash
htop
```

`top` está presente prácticamente en cualquier distribución Linux.

`htop` ofrece una interfaz más amigable y permite interactuar con los procesos de forma visual.

---

### 💡 Otras respuestas válidas

También podrían utilizarse:

```bash
vmstat
```

```bash
iotop
```

```bash
glances
```

Dependiendo del problema que se quiera diagnosticar.

---

### ⚠️ Errores habituales

Reiniciar el servidor sin comprobar previamente el estado de los recursos.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue muy buena.

Incluso añadiste una pequeña broma comparando `top` y `htop`, pero técnicamente acertaste por completo.

Elegiste exactamente las herramientas que utilizaría un administrador en una primera inspección.

---

# Pregunta 2

## Enunciado

Necesitas localizar el proceso de PostgreSQL.

¿Cómo lo harías?

---

## 🧠 Cadena de diagnóstico

Una vez detectado un consumo elevado de recursos, el siguiente paso consiste en identificar qué proceso lo provoca.

No debemos finalizar procesos sin conocer exactamente cuál es el responsable.

---

### ✅ Respuesta esperada

Una forma sencilla consiste en utilizar:

```bash
ps aux | grep postgres
```

o

```bash
ps aux | grep postgresql
```

Obtendremos información como:

- PID
- Usuario propietario
- Consumo de CPU
- Consumo de memoria

---

### 💡 Otras respuestas válidas

También serían correctos:

```bash
pgrep postgres
```

```bash
pidof postgres
```

o incluso localizarlo directamente desde `top` o `htop`.

---

### ⚠️ Errores habituales

Finalizar procesos únicamente por su nombre sin comprobar previamente el PID.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Además, justificaste que el objetivo era obtener el PID para poder actuar posteriormente.

Muy buen razonamiento.

---

# Pregunta 3

## Enunciado

Has identificado el proceso problemático.

¿Cómo intentarías finalizarlo?

---

## 🧠 Cadena de diagnóstico

Antes de utilizar medidas drásticas debemos intentar siempre un cierre ordenado.

Muchos servicios necesitan guardar información o liberar recursos antes de finalizar.

---

### ✅ Respuesta esperada

Primero enviaríamos la señal:

```bash
kill -15 PID
```

o

```bash
kill PID
```

ya que la señal por defecto es `SIGTERM` (15).

Esta señal solicita al proceso que finalice correctamente.

---

### 💡 Otras respuestas válidas

También sería válido:

```bash
pkill postgres
```

si queremos actuar por nombre.

---

### ⚠️ Errores habituales

Utilizar directamente:

```bash
kill -9
```

sin intentar previamente una finalización ordenada.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue excelente.

Elegiste correctamente `kill -15` antes de recurrir a otras opciones.

Eso demuestra que comprendes que no todos los procesos deben terminarse de forma forzada.

---

# Pregunta 4

## Enunciado

El proceso sigue sin detenerse.

¿Qué harías ahora?

---

## 🧠 Cadena de diagnóstico

Solo cuando un proceso ignora una finalización ordenada debemos recurrir a una señal que fuerce inmediatamente su terminación.

Debe considerarse el último recurso.

---

### ✅ Respuesta esperada

Forzaríamos la finalización mediante:

```bash
kill -9 PID
```

Esta señal (`SIGKILL`) no puede ser interceptada por el proceso.

El núcleo elimina inmediatamente su ejecución.

---

### ⚠️ Advertencia

`kill -9` puede provocar:

- pérdida de datos;
- corrupción de archivos abiertos;
- interrupciones del servicio.

Debe utilizarse únicamente cuando las alternativas anteriores han fallado.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue correcta.

Además, la utilizaste exactamente como debe hacerse: únicamente después de intentar un cierre limpio.

Muy buena práctica.

---

# Pregunta 5

## Enunciado

Tras finalizar el proceso, PostgreSQL continúa presentando problemas.

¿Qué harías?

---

## 🧠 Cadena de diagnóstico

Aquí aparece una diferencia importante entre un administrador junior y uno experimentado.

Un administrador junior suele pensar:

> "Reinicio el servicio."

Un administrador con experiencia piensa primero:

> "¿Por qué ha ocurrido?"

Antes de reiniciar un servicio crítico conviene revisar los registros para conocer el origen del problema.

---

### ✅ Respuesta esperada

El orden recomendado sería:

**1. Revisar los registros del servicio.**

Por ejemplo:

```bash
journalctl -u postgresql
```

o los archivos correspondientes en:

```text
/var/log
```

---

**2. Comprobar el estado del servicio.**

```bash
systemctl status postgresql
```

---

**3. Si procede, reiniciar el servicio.**

```bash
sudo systemctl restart postgresql
```

---

**4. Verificar que ha vuelto a iniciarse correctamente.**

```bash
systemctl status postgresql
```

---

### 💡 Otras respuestas válidas

En algunos casos podría bastar con:

```bash
systemctl reload postgresql
```

cuando únicamente sea necesario recargar la configuración.

Sin embargo, si el proceso ha quedado bloqueado, normalmente será necesario un reinicio completo.

---

### ⚠️ Errores habituales

Reiniciar servicios sin consultar previamente los registros.

El reinicio puede ocultar temporalmente el problema sin resolver su causa.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue muy buena.

Propusiste utilizar:

```bash
systemctl restart postgresql
```

y también mencionaste la posibilidad de emplear `reload`.

Durante la corrección añadimos un matiz importante: **antes de reiniciar un servicio crítico conviene revisar los registros y comprobar su estado**.

Ese pequeño detalle marca una diferencia importante en la administración profesional.

---

# ✅ Valoración del Nivel 3

**Resultado:** Excelente.

Este nivel pone a prueba la capacidad de diagnosticar incidencias antes de actuar.

Has demostrado que comprendes un principio fundamental de la administración de sistemas:

> **Diagnosticar primero, intervenir después.**

El flujo de trabajo seguido ha sido el adecuado:

1. Supervisar el sistema.
2. Identificar el proceso problemático.
3. Intentar una finalización ordenada.
4. Forzar la detención únicamente si es necesario.
5. Revisar el estado y los registros del servicio antes de reiniciarlo.

Este procedimiento coincide con las buenas prácticas habituales en la administración de servidores GNU/Linux y constituye una base sólida para afrontar incidencias reales en entornos de producción.