# 🧪 Misión 01 · Administrador Linux del IMIDA

> **Bloque:** 01 · Administración de Sistemas
>
> **Misión:** 01
>
> **Dificultad:** 🟢 Básico → 🔴 Avanzado
>
> **Tiempo estimado:** 45-60 minutos
>
> **Prerrequisitos:**
>
> - 1.1 Introducción a GNU/Linux
> - 1.2 Sistema de archivos
> - 1.3 Usuarios y grupos
> - 1.4 Administración de usuarios
> - 1.5 Permisos
> - 1.6 Procesos
> - 1.7 Bash
> - 1.8 systemd
> - 1.9 Gestión de paquetes
> - 1.10 Administración básica

---

# 🎯 Objetivo

Resolver una serie de incidencias simuladas utilizando los conocimientos adquiridos durante el Bloque 1.

No se pretende memorizar comandos, sino aprender a pensar como un administrador de sistemas.

---

# 📖 Contexto

Son las **08:00**.

Es lunes.

El administrador habitual del IMIDA está de vacaciones.

Al llegar a tu puesto encuentras varios avisos pendientes.

Durante las próximas horas tendrás que resolverlos tú solo.

No dispones de documentación.

Solo tienes acceso a un servidor Linux mediante terminal.

Comienza la jornada.

---

# 🟢 Nivel 1 · Reconocimiento del servidor

Antes de realizar cualquier cambio quieres conocer el estado general del sistema.

## Pregunta 1

¿Qué comando ejecutarías primero para comenzar a inspeccionar el servidor?

**Respuesta:**

---

## Pregunta 2

Necesitas conocer:

- el usuario actual;
- el nombre del servidor;
- el tiempo que lleva encendido.

¿Qué comandos utilizarías?

**Respuesta:**

---

## Pregunta 3

¿Cómo comprobarías el espacio libre disponible en disco?

**Respuesta:**

---

## Pregunta 4

¿Cómo consultarías la memoria RAM disponible?

**Respuesta:**

---

## Pregunta 5

¿Dónde consultarías los registros del sistema?

**Respuesta:**

---

# 🟡 Nivel 2 · Problemas con usuarios

La investigadora Ana llama.

> "No puedo acceder al servidor."

Solo conoces su nombre de usuario.

## Pregunta 1

¿Qué comprobarías primero?

**Respuesta:**

---

Obtienes el siguiente resultado:

```text
uid=1003(ana)
```

El usuario existe.

## Pregunta 2

Sospechas que el problema es la contraseña.

¿Qué comando utilizarías?

**Respuesta:**

---

Ana consigue acceder.

Sin embargo ahora comenta:

> "No puedo entrar en el directorio compartido."

Observas:

```text
drwxrwx---

Grupo:

investigacion
```

## Pregunta 3

¿Qué comprobarías ahora?

**Respuesta:**

---

## Pregunta 4

¿Cuál crees que es el problema?

**Respuesta:**

---

## Pregunta 5

¿Qué comando utilizarías para solucionarlo?

**Respuesta:**

---

# 🟠 Nivel 3 · El servidor va lento

Un investigador comenta:

> "Todo funciona muy despacio."

## Pregunta 1

¿Qué herramienta utilizarías para observar el sistema en tiempo real?

**Respuesta:**

---

Descubres que PostgreSQL consume prácticamente toda la CPU.

## Pregunta 2

¿Cómo localizarías el proceso?

**Respuesta:**

---

## Pregunta 3

¿Qué comando utilizarías para intentar finalizarlo correctamente?

**Respuesta:**

---

El proceso continúa bloqueado.

## Pregunta 4

¿Qué harías ahora?

**Respuesta:**

---

Una vez finalizado, PostgreSQL ha quedado detenido.

## Pregunta 5

¿Qué comando utilizarías para volver a iniciarlo?

**Respuesta:**

---

# 🔴 Nivel 4 · El servidor web no responde

La aplicación del IMIDA devuelve un error **503 Service Unavailable**.

## Pregunta 1

¿Qué comprobarías primero?

**Respuesta:**

---

Apache aparece detenido.

## Pregunta 2

¿Qué comando ejecutarías?

**Respuesta:**

---

Apache vuelve a detenerse inmediatamente.

## Pregunta 3

¿Qué registros consultarías para averiguar el motivo?

**Respuesta:**

---

También necesitas comprobar PostgreSQL.

## Pregunta 4

¿Qué comando utilizarías?

**Respuesta:**

---

Todo vuelve a funcionar.

Ahora quieres asegurarte de que Apache arranque automáticamente al reiniciar el servidor.

## Pregunta 5

¿Qué comando ejecutarías?

**Respuesta:**

---

# 🔴 Nivel 5 · Copia de seguridad urgente

Antes de las 12:00 debes generar una copia de seguridad del directorio:

```text
/home/investigacion
```

## Pregunta 1

¿Qué herramienta utilizarías?

**Respuesta:**

---

## Pregunta 2

Escribe el comando para crear un archivo comprimido llamado:

```text
backup.tar.gz
```

**Respuesta:**

---

Ahora debes copiar esa copia al servidor de respaldo.

Servidor:

```text
192.168.10.20
```

Usuario:

```text
backup
```

## Pregunta 3

¿Qué comando utilizarías?

**Respuesta:**

---

La copia debe ejecutarse automáticamente todos los días a las **02:00**.

## Pregunta 4

¿Qué herramienta utilizarías?

**Respuesta:**

---

## Pregunta 5

¿Qué comando permite editar esa programación?

**Respuesta:**

---

# 🏁 Fin de la misión

Si has llegado hasta aquí has utilizado conocimientos de:

- Usuarios
- Permisos
- Procesos
- Bash
- Servicios
- Administración básica
- Copias de seguridad

---

# 📊 Autoevaluación

| Nivel | Estado |
|--------|--------|
| 🟢 Nivel 1 | ☐ |
| 🟡 Nivel 2 | ☐ |
| 🟠 Nivel 3 | ☐ |
| 🔴 Nivel 4 | ☐ |
| 🔴 Nivel 5 | ☐ |

---

# 📝 Notas personales

¿Qué conceptos debo repasar antes de continuar con el Bloque 1?

---

# 👨‍🏫 Corrección del preparador

**No completar durante la misión.**

Este apartado se rellenará una vez revisadas las respuestas, anotando:

- Errores cometidos.
- Comandos alternativos.
- Buenas prácticas.
- Conceptos que conviene reforzar.

---

# ⭐ Valoración

Dificultad:

- ☐ Muy fácil
- ☐ Fácil
- ☐ Adecuada
- ☐ Difícil
- ☐ Muy difícil

Confianza al terminar la misión (1-5):

- ☐ 1
- ☐ 2
- ☐ 3
- ☐ 4
- ☐ 5

# Soluciones
- [Nivel 1](solucion-nivel-1.md)
- [Nivel 2](solucion-nivel-2.md)
- [Nivel 3](solucion-nivel-3.md)
- [Nivel 4](solucion-nivel-4.md)
- [Nivel 5](solucion-nivel-5.md)