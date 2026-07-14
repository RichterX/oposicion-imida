# 🟡 Nivel 2 · Usuarios y grupos

---

# Pregunta 1

## Enunciado

Se incorpora una nueva investigadora llamada **Ana**.

¿Cómo comprobarías si el usuario ya existe antes de crearlo?

---

## 🧠 Cadena de diagnóstico

Antes de crear cualquier usuario debemos comprobar si ya existe.

Crear una cuenta duplicada provocará un error y, además, podría indicar que otro administrador ya había realizado esa tarea.

La primera norma de un administrador es:

> **Comprobar antes de modificar.**

---

### ✅ Respuesta esperada

Consultar la existencia del usuario mediante:

```bash
id ana
```

Si el usuario existe obtendremos una salida similar a:

```text
uid=1003(ana)
gid=1003(ana)
groups=1003(ana)
```

Si no existe aparecerá un mensaje indicando que el usuario no se encuentra en el sistema.

Una vez comprobado, podríamos crearlo con:

```bash
sudo useradd -m ana
```

La opción `-m` crea automáticamente su directorio personal en:

```text
/home/ana
```

---

### 💡 Otras respuestas válidas

También podrían utilizarse:

```bash
getent passwd ana
```

o incluso

```bash
grep "^ana:" /etc/passwd
```

Sin embargo, `id` resulta mucho más cómodo para una comprobación rápida.

---

### ⚠️ Errores habituales

Crear directamente el usuario sin comprobar previamente si existe.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue exactamente la esperada.

Además utilizaste `useradd -m`, lo cual demuestra que ya conoces la importancia de crear automáticamente el directorio personal del usuario.

Muy buena práctica.

---

# Pregunta 2

## Enunciado

El usuario existe pero no consigue iniciar sesión.

¿Qué comprobarías?

---

## 🧠 Cadena de diagnóstico

Cuando un usuario no puede iniciar sesión no debemos asumir inmediatamente que la contraseña es incorrecta.

Antes conviene comprobar:

1. Que el usuario existe.
2. Que la cuenta no está bloqueada.
3. Que la contraseña puede restablecerse.
4. Que dispone de un shell válido.

---

### ✅ Respuesta esperada

Si el problema es únicamente la contraseña, bastaría con establecer una nueva mediante:

```bash
sudo passwd ana
```

El sistema solicitará introducirla dos veces.

---

### 💡 Comprobaciones adicionales

También sería razonable consultar:

```bash
passwd -S ana
```

para conocer el estado de la cuenta.

Y comprobar el shell asignado:

```bash
grep "^ana:" /etc/passwd
```

Si el shell fuese:

```text
/usr/sbin/nologin
```

o

```text
/bin/false
```

el usuario tampoco podría iniciar sesión de forma interactiva.

---

### ⚠️ Errores habituales

Cambiar inmediatamente la contraseña sin investigar la causa del problema.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue correcta.

Como mejora profesional añadiríamos la comprobación del shell y del estado de la cuenta antes de modificar la contraseña.

Es una buena costumbre cuando administramos servidores compartidos.

---

# Pregunta 3

## Enunciado

El usuario debe pertenecer al grupo **investigacion**.

¿Cómo lo comprobarías?

---

## 🧠 Cadena de diagnóstico

En Linux los permisos suelen asignarse a grupos, no directamente a usuarios.

Por tanto, antes de modificar permisos debemos comprobar la pertenencia al grupo correspondiente.

---

### ✅ Respuesta esperada

Consultar los grupos del usuario:

```bash
groups ana
```

o

```bash
id ana
```

Si el grupo aparece en la salida, no será necesario realizar ninguna modificación.

---

### 💡 Otras respuestas válidas

También sería válido:

```bash
getent group investigacion
```

para comprobar qué usuarios pertenecen al grupo.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Elegiste el comando que utilizaría prácticamente cualquier administrador Linux.

---

# Pregunta 4

## Enunciado

El usuario no pertenece al grupo.

¿Cómo lo añadirías?

---

## 🧠 Cadena de diagnóstico

Una vez comprobado que el grupo existe, únicamente debemos incorporar al usuario manteniendo el resto de sus pertenencias.

---

### ✅ Respuesta esperada

```bash
sudo usermod -aG investigacion ana
```

---

### ❗ Muy importante

La opción:

```bash
-aG
```

significa:

- **-G** → establecer grupos suplementarios.
- **-a** → añadir sin eliminar los grupos existentes.

Si olvidamos la opción `-a`, el usuario perderá todos sus grupos suplementarios anteriores.

---

### ⚠️ Error muy frecuente

Utilizar:

```bash
sudo usermod -G investigacion ana
```

sin `-a`.

Esto sustituye completamente los grupos suplementarios del usuario.

---

### 👨‍🏫 Comentario del preparador

Aquí encontramos la única corrección importante respecto a tu respuesta original.

Inicialmente utilizaste:

```bash
useradd -aG
```

En realidad el comando correcto es:

```bash
usermod -aG
```

Porque el usuario ya existía.

Es un error muy común incluso entre administradores con cierta experiencia.

---

# Pregunta 5

## Enunciado

¿Por qué es mejor asignar permisos al grupo y no directamente al usuario?

---

## 🧠 Cadena de diagnóstico

Imagina un departamento con 50 investigadores.

Si cada permiso se asignara individualmente, la administración sería muy compleja.

Los grupos permiten administrar permisos de forma centralizada.

---

### ✅ Respuesta esperada

Asignar permisos al grupo facilita enormemente la administración.

Cuando un nuevo usuario se incorpora únicamente es necesario añadirlo al grupo correspondiente.

Los permisos ya estarán correctamente definidos.

Esto permite:

- simplificar la administración;
- reducir errores;
- mantener una configuración coherente;
- aplicar el principio de mínimo privilegio.

---

### 💡 Ejemplo

En lugar de asignar permisos individualmente a:

- Ana
- Carlos
- María
- Pedro

se asignan al grupo:

```text
investigacion
```

Posteriormente los usuarios se incorporan o abandonan ese grupo según sea necesario.

---

### 👨‍🏫 Comentario del preparador

Tu razonamiento fue excelente.

De hecho, ya utilizabas grupos de forma natural sin necesidad de que apareciera explícitamente en el enunciado.

Eso demuestra que has interiorizado una de las mejores prácticas fundamentales de la administración Linux.

---

# ✅ Valoración del Nivel 2

**Resultado:** Muy alto.

En este nivel ya no te has limitado a recordar comandos.

Has comenzado a razonar como un administrador de sistemas:

✔ Compruebas antes de modificar.

✔ Verificas la existencia del usuario.

✔ Utilizas grupos para administrar permisos.

✔ Entiendes la importancia de no asignar permisos directamente a cada usuario.

La única corrección relevante fue el uso de `usermod -aG` en lugar de `useradd -aG`, un error frecuente que conviene recordar.

En conjunto, este nivel demuestra que ya dominas la administración básica de usuarios y grupos en GNU/Linux y que estás preparado para enfrentarte a problemas más complejos relacionados con procesos, servicios y administración del sistema.