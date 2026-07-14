# Misión 01 · Administrador Linux
## Soluciones oficiales

> **Bloque:** Administración de Sistemas
>
> **Parte:** GNU/Linux
>
> **Documento:** Soluciones oficiales
>
> **Versión:** 1.0
>
> **Tiempo recomendado:** Lectura completa tras finalizar la misión
>
> **Nivel:** ⭐⭐⭐⭐☆

---

# Introducción

La finalidad de este documento no es únicamente proporcionar la respuesta correcta a cada pregunta.

Su objetivo es enseñar la forma de pensar de un administrador de sistemas.

En muchas ocasiones existen varios comandos capaces de resolver un mismo problema. Lo realmente importante no es memorizar un comando concreto, sino comprender el proceso de diagnóstico y elegir la herramienta más adecuada en cada situación.

En este solucionario se muestran:

- La respuesta esperada.
- La explicación técnica.
- Posibles alternativas válidas.
- Errores frecuentes.
- Comentarios del preparador.
- Buenas prácticas profesionales.

---

# Cómo corregir esta misión

No busques haber escrito exactamente el mismo comando.

Pregúntate:

- ¿Mi razonamiento era correcto?
- ¿Elegí una herramienta adecuada?
- ¿Existe una alternativa mejor?
- ¿He seguido un orden lógico de diagnóstico?

Si la respuesta es sí, probablemente habrías actuado correctamente en un servidor real.

---

# 🟢 Nivel 1 · Reconocimiento del sistema

---

# Pregunta 1

## Enunciado

¿Cómo comprobarías con qué usuario estás trabajando?

---

### ✅ Respuesta esperada

El comando más sencillo es:

```bash
whoami
```

Este comando muestra el nombre del usuario con el que se está ejecutando la sesión actual.

Ejemplo:

```text
ana
```

---

### 💡 Otras respuestas válidas

También podrían utilizarse:

```bash
id
```

o

```bash
echo $USER
```

Sin embargo, para responder a esta pregunta `whoami` resulta la opción más clara y directa.

---

### ⚠️ Errores habituales

- Confundir el usuario actual con el propietario del directorio.
- Utilizar comandos excesivamente complejos para una comprobación sencilla.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue exactamente la esperada.

Elegiste el comando más simple y más utilizado por cualquier administrador Linux.

Es una buena práctica comenzar cualquier intervención comprobando con qué usuario estamos trabajando, especialmente si se trata de un servidor compartido o si hemos utilizado `sudo` previamente.

---

# Pregunta 2

## Enunciado

¿Qué información básica comprobarías nada más iniciar sesión en un servidor?

---

### ✅ Respuesta esperada

Una primera comprobación razonable sería obtener:

- usuario actual;
- nombre del servidor;
- tiempo que lleva encendido.

Por ejemplo:

```bash
whoami
```

```bash
hostname
```

```bash
uptime
```

Con estos tres comandos obtenemos rápidamente una visión general del entorno de trabajo.

---

### 💡 ¿Por qué comprobar esta información?

- `whoami` confirma nuestra identidad.
- `hostname` evita trabajar sobre un servidor equivocado.
- `uptime` permite detectar reinicios recientes o conocer la carga media del sistema.

Son tres comprobaciones muy habituales antes de realizar cualquier tarea administrativa.

---

### 💡 Otras respuestas válidas

También sería correcto utilizar:

```bash
hostnamectl
```

ya que proporciona información adicional sobre el sistema.

---

### ⚠️ Errores habituales

Comenzar a ejecutar comandos administrativos sin verificar previamente en qué servidor estamos trabajando.

En entornos con varios servidores este error puede tener consecuencias importantes.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue excelente.

No solo identificaste correctamente los tres comandos, sino que explicaste para qué servía cada uno de ellos.

Ese tipo de razonamiento es propio de un administrador y no de alguien que únicamente memoriza comandos.

---

# Pregunta 3

## Enunciado

¿Cómo comprobarías el espacio disponible en disco?

---

### ✅ Respuesta esperada

```bash
df -h
```

---

### Explicación

Este comando muestra:

- sistemas de archivos;
- tamaño;
- espacio utilizado;
- espacio disponible;
- porcentaje de ocupación.

La opción `-h` presenta la información en un formato fácilmente legible (MB, GB, TB).

---

### 💡 Otras respuestas válidas

Para conocer el tamaño de un directorio concreto también podría utilizarse:

```bash
du -sh directorio
```

Sin embargo, `df -h` es la respuesta esperada porque permite comprobar el estado general del almacenamiento.

---

### ⚠️ Errores habituales

Confundir `df` con `du`.

- `df` informa sobre el sistema de archivos.
- `du` calcula el tamaño de archivos y directorios.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Además, demuestra que ya distingues cuándo utilizar `df` y cuándo utilizar `du`, algo muy habitual en la administración diaria.

---

# Pregunta 4

## Enunciado

¿Cómo consultarías la memoria RAM disponible?

---

### ✅ Respuesta esperada

```bash
free -h
```

---

### Explicación

Este comando muestra:

- memoria total;
- memoria utilizada;
- memoria libre;
- memoria compartida;
- buffers y caché;
- memoria de intercambio (swap).

La opción `-h` facilita la lectura utilizando unidades comprensibles.

---

### 💡 Otras respuestas válidas

También podrían utilizarse:

```bash
top
```

```bash
htop
```

```bash
vmstat
```

pero `free -h` responde exactamente a la pregunta planteada.

---

### 👨‍🏫 Comentario del preparador

Respuesta correcta.

Elegiste el comando más apropiado para obtener una visión rápida del estado de la memoria.

---

# Pregunta 5

## Enunciado

¿Dónde consultarías los registros del sistema?

---

### ✅ Respuesta esperada

En la mayoría de distribuciones Linux los registros se almacenan en:

```text
/var/log
```

---

### Explicación

Dentro de este directorio encontraremos numerosos archivos de registro.

Ejemplos:

- auth.log
- syslog
- kern.log
- dmesg
- messages (según la distribución)

En sistemas modernos también es habitual consultar:

```bash
journalctl
```

cuando el sistema utiliza `systemd`.

---

### 💡 Otras respuestas válidas

Consultar directamente:

```bash
journalctl
```

también sería una respuesta completamente válida.

De hecho, en muchas distribuciones actuales es la herramienta más utilizada.

---

### ⚠️ Errores habituales

Pensar que todos los registros están almacenados exclusivamente en archivos dentro de `/var/log`.

Actualmente muchos sistemas utilizan el Journal de `systemd`.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue correcta.

Identificaste correctamente el directorio `/var/log`.

Como mejora profesional, añadiríamos que en sistemas modernos conviene complementar esta búsqueda utilizando `journalctl`, ya que muchos servicios registran allí toda su actividad.

---

# ✅ Valoración del Nivel 1

**Resultado:** Excelente.

Has identificado correctamente todas las herramientas básicas que un administrador utilizaría al conectarse por primera vez a un servidor Linux.

Lo más destacable no ha sido memorizar comandos, sino el orden lógico de comprobación:

1. Identidad del usuario.
2. Identidad del servidor.
3. Estado general del sistema.
4. Recursos disponibles.
5. Registros del sistema.

Ese orden refleja una forma de trabajar organizada y constituye una buena base para afrontar incidencias más complejas en los siguientes niveles de la misión.
