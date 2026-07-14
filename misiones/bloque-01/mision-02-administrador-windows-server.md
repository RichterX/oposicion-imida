# Misión 02 · Administrador de Windows Server

> **Bloque:** Administración de Sistemas
>
> **Parte:** Windows Server
>
> **Nivel:** ⭐⭐⭐⭐☆
>
> **Tiempo recomendado:** 90-120 minutos
>
> **Modo:** Sin apuntes (recomendado)

---

# 🎬 Escenario

Enhorabuena.

Has sido contratado como nuevo administrador de sistemas del IMIDA.

Tu compañero ha dejado preparado un servidor Windows Server 2022.

Antes de marcharse únicamente te deja una nota.

---

> "El servidor funciona...
>
> ...pero quiero comprobar que eres capaz de administrarlo."

---

No puedes consultar Internet.

No puedes utilizar apuntes.

Solo dispones del propio servidor.

Tu misión consiste en diagnosticar distintos problemas y proponer la mejor solución.

No es necesario escribir exactamente el comando correcto.

Lo importante es demostrar que sabes **qué herramienta utilizarías y por qué.**

---

# 🟢 Nivel 1 · Reconocimiento del servidor

## Pregunta 1

¿Cómo comprobarías el nombre del servidor?

---

## Pregunta 2

¿Qué herramienta utilizarías para conocer los roles instalados?

---

## Pregunta 3

¿Cómo comprobarías si existen actualizaciones pendientes?

---

## Pregunta 4

¿Qué herramienta abrirías para revisar los registros del sistema?

---

## Pregunta 5

¿Dónde consultarías qué tareas automáticas están programadas?

---

# 🟡 Nivel 2 · Usuarios y permisos

Se incorpora una nueva investigadora.

Debe disponer de una cuenta local.

Debe pertenecer al grupo:

```text
Investigacion
```

Y únicamente debe poder leer los documentos almacenados en:

```text
D:\Investigacion
```

## Pregunta 1

¿Qué herramienta utilizarías para crear el usuario?

---

## Pregunta 2

¿Cómo añadirías ese usuario al grupo correspondiente?

---

## Pregunta 3

¿Qué ventana utilizarías para modificar los permisos de la carpeta?

---

## Pregunta 4

¿Cómo comprobarías los permisos efectivos del usuario?

---

## Pregunta 5

¿Por qué resulta preferible asignar permisos al grupo y no directamente al usuario?

---

# 🟠 Nivel 3 · Procesos y servicios

Los investigadores indican que el servidor responde lentamente.

## Pregunta 1

¿Qué herramienta abrirías primero?

---

## Pregunta 2

¿Qué recurso comprobarías antes?

- CPU
- Memoria
- Disco
- Red

Explica por qué.

---

## Pregunta 3

Localizas un proceso que consume el 95 % de la CPU.

¿Qué harías?

---

## Pregunta 4

Descubres que el servicio DNS está detenido.

¿Qué herramienta utilizarías?

---

## Pregunta 5

¿Cómo reiniciarías ese servicio mediante PowerShell?

---

# 🔴 Nivel 4 · Roles y administración

El director quiere convertir este servidor en servidor DNS.

## Pregunta 1

¿Qué herramienta gráfica utilizarías?

---

## Pregunta 2

¿Qué cmdlet de PowerShell instalaría un rol?

(No es necesario escribir todos los parámetros.)

---

## Pregunta 3

¿Qué diferencia existe entre un rol y una característica?

---

## Pregunta 4

¿Por qué no conviene instalar todos los roles disponibles?

---

## Pregunta 5

¿Qué rol instalarás dentro de unos días para comenzar Active Directory?

---

# 🔵 Nivel 5 · Administrador Senior

Llegas una mañana y recibes las siguientes incidencias:

✔ Los usuarios indican que el servidor responde muy lentamente.

✔ Algunos recursos compartidos no permiten escribir.

✔ Windows Update indica que existen actualizaciones críticas.

✔ En el Visor de eventos aparecen varios errores.

✔ La última copia de seguridad no puede verificarse.

---

Describe **el orden en el que actuarías**.

No hace falta indicar todos los comandos.

Lo importante es justificar tu razonamiento.

---

# ⭐ Nivel Bonus

Imagina que debes explicar a un compañero que solo conoce GNU/Linux cómo funciona Windows Server.

Haz una comparación entre ambos sistemas indicando, al menos, diez equivalencias.

Ejemplo:

| GNU/Linux | Windows Server |
|------------|----------------|
| Bash | PowerShell |

Continúa la tabla hasta completar diez equivalencias.

---

# 🎯 Objetivos de la misión

Si eres capaz de completar correctamente esta misión significa que dominas:

- Arquitectura de Windows.
- NTFS.
- Usuarios.
- Permisos.
- Procesos.
- Servicios.
- Roles.
- Herramientas administrativas.
- Administración y mantenimiento.

En ese momento estarás preparado para comenzar Active Directory.

---

# 📝 Autoevaluación

Marca cada apartado cuando seas capaz de resolverlo sin consultar apuntes.

- [ ] Reconozco las herramientas principales de Windows Server.
- [ ] Sé crear usuarios y grupos.
- [ ] Comprendo los permisos NTFS.
- [ ] Sé diagnosticar procesos y servicios.
- [ ] Comprendo los roles de Windows Server.
- [ ] Sé administrar el servidor de forma básica.
- [ ] Me siento preparado para comenzar Active Directory.