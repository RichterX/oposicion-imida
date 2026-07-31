# SIMULACRO 01
# Corrección
## Parte 7 (Preguntas 56-70)

---

# Pregunta 56

## Enunciado

¿Cuál de las siguientes afirmaciones sobre DNS en un dominio es CORRECTA?

a) Es un servicio opcional que no interviene en Active Directory.

b) Se utiliza únicamente para acceder a Internet.

✅ c) Permite localizar los servicios del dominio y es fundamental para Active Directory.

d) Sustituye al servicio DHCP.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

DNS es uno de los pilares fundamentales de Active Directory.

Cuando un cliente desea iniciar sesión:

1. Consulta DNS.
2. Localiza un Controlador de Dominio.
3. Se autentica mediante Kerberos.

Además, DNS almacena registros SRV que permiten localizar servicios como:

- LDAP
- Kerberos
- Global Catalog

Sin un DNS correctamente configurado, Active Directory prácticamente deja de funcionar.

### ❌ ¿Por qué no las demás?

**a)** Falso. Es imprescindible.

**b)** DNS hace mucho más que resolver páginas web.

**d)** DHCP y DNS son servicios distintos.

### 🎯 Lo que busca realmente el tribunal

Detectar si el opositor comprende la dependencia entre DNS y Active Directory.

---

# Pregunta 57

## Enunciado

¿Qué comando permite cambiar de usuario en GNU/Linux?

a) sudoedit

✅ b) su

c) login

d) switch

### ✔ Respuesta correcta

**b) su**

### 📖 Explicación

El comando **su** (*Substitute User*) permite cambiar al contexto de otro usuario.

Ejemplo:

```bash
su
```

o

```bash
su root
```

Si queremos cargar también el entorno completo del usuario:

```bash
su -
```

En sistemas modernos es frecuente utilizar **sudo**, pero la pregunta solicita específicamente cambiar de usuario.

### ❌ ¿Por qué no las demás?

**sudoedit**

Edita archivos utilizando privilegios elevados.

**login**

No se utiliza para este propósito desde una sesión ya iniciada.

**switch**

No existe como comando estándar.

### 💡 Recuerda

su → cambiar de usuario.

sudo → ejecutar un comando con privilegios.

---

# Pregunta 58

## Enunciado

¿Cuál de las siguientes afirmaciones sobre las GPO es FALSA?

a) Se vinculan normalmente a OU.

b) Pueden aplicarse tanto a usuarios como a equipos.

✅ c) Modifican automáticamente la estructura física del disco.

d) Facilitan la administración centralizada.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Las Directivas de Grupo modifican configuraciones del sistema operativo, no la estructura física del almacenamiento.

Una GPO puede configurar:

- Seguridad.
- Escritorio.
- Firewall.
- Windows Update.
- Instalación de software.
- Scripts.

Nunca modifica particiones ni sistemas de archivos.

### ❌ ¿Por qué no las demás?

Las tres describen correctamente el funcionamiento de las GPO.

### 🎯 Lo que busca realmente el tribunal

Comprobar que el candidato distingue entre administración del sistema operativo y administración del almacenamiento.

---

# Pregunta 59

## Enunciado

¿Qué comando muestra información en tiempo real sobre los procesos del sistema?

a) ps

b) jobs

✅ c) top

d) ls

### ✔ Respuesta correcta

**c) top**

### 📖 Explicación

El comando **top** actualiza continuamente la información sobre:

- CPU.
- RAM.
- Procesos.
- Tiempo de ejecución.
- Load Average.

Es una de las herramientas de monitorización más utilizadas por administradores Linux.

### ❌ ¿Por qué no las demás?

**ps**

Solo muestra una instantánea.

**jobs**

Muestra trabajos de la shell actual.

**ls**

Lista directorios.

### 💡 Diferencia importante

ps

↓

Fotografía.

top

↓

Vídeo en tiempo real.

---

# Pregunta 60

## Enunciado

¿Cuál de las siguientes acciones constituye una buena práctica de administración en Active Directory?

a) Utilizar siempre la cuenta Administrador para el trabajo diario.

b) Crear usuarios duplicados cuando cambian de departamento.

✅ c) Organizar adecuadamente las OU según criterios administrativos.

d) Conceder permisos directamente a todos los usuarios.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Una estructura lógica de OU facilita enormemente:

- Administración.
- Delegación.
- Aplicación de GPO.
- Localización de objetos.

Además, reduce errores y simplifica el mantenimiento.

### ❌ ¿Por qué no las demás?

Todas representan malas prácticas administrativas.

### 🎯 Lo que busca realmente el tribunal

No basta con saber utilizar Active Directory.

Hay que conocer las **buenas prácticas**.

---

# Pregunta 61

## Enunciado

¿Qué comando muestra el manual de ayuda de otro comando en GNU/Linux?

a) help

b) info

✅ c) man

d) doc

### ✔ Respuesta correcta

**c) man**

### 📖 Explicación

El comando **man** (*manual*) muestra la documentación oficial de los comandos.

Ejemplo:

```bash
man ls
```

El manual suele incluir:

- Nombre.
- Descripción.
- Sintaxis.
- Opciones.
- Ejemplos.

### ❌ ¿Por qué no las demás?

**help** existe para algunos comandos internos de la shell, pero no sustituye al sistema de manuales.

### 💡 Muy preguntable

man = Manual.

---

# Pregunta 62

## Enunciado

Respecto a la autenticación en un dominio Windows, señale la respuesta CORRECTA.

a) Cada equipo autentica únicamente a sus propios usuarios locales.

✅ b) El Controlador de Dominio centraliza el proceso de autenticación.

c) Los usuarios deben crearse en todos los equipos.

d) Las GPO realizan la autenticación de los usuarios.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Cuando un usuario inicia sesión:

- El Controlador de Dominio verifica sus credenciales.
- Autoriza el acceso.
- Devuelve el token correspondiente.

Gracias a ello el usuario puede acceder desde distintos equipos del dominio.

### ❌ ¿Por qué no las demás?

Las opciones a) y c) describen un grupo de trabajo.

Las GPO no autentican usuarios.

### 🎯 Lo que busca realmente el tribunal

Comprender el concepto de autenticación centralizada.

---

# Pregunta 63

## Enunciado

¿Cuál de las siguientes NO suele ser una ventaja de Active Directory?

a) Administración centralizada.

b) Aplicación de políticas comunes.

✅ c) Duplicar la administración de usuarios en todos los equipos.

d) Gestión centralizada de recursos.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Precisamente Active Directory elimina la necesidad de administrar usuarios equipo por equipo.

Ese trabajo centralizado constituye una de sus principales ventajas.

### ❌ ¿Por qué no las demás?

Las demás son precisamente ventajas del uso de Active Directory.

### 💡 Truco

Cuando aparezca:

> Administración duplicada

Piensa:

"No, eso ocurre en un Workgroup."

---

# Pregunta 64

## Enunciado

¿Qué comando muestra el nombre del directorio actual?

a) cd

✅ b) pwd

c) where

d) dirname

### ✔ Respuesta correcta

**b) pwd**

### 📖 Explicación

**pwd** significa:

Print Working Directory.

Devuelve la ruta absoluta del directorio actual.

Ejemplo:

```bash
pwd
```

```
/home/pedro/documentos
```

### ❌ ¿Por qué no las demás?

**cd**

Cambia de directorio.

**dirname**

Manipula rutas, pero no muestra el directorio de trabajo actual.

---

# Pregunta 65

## Enunciado

¿Cuál de las siguientes afirmaciones sobre las cuentas deshabilitadas es CORRECTA?

a) Continúan permitiendo el inicio de sesión.

b) Deben eliminarse inmediatamente.

✅ c) No permiten autenticarse, pero conservan sus atributos y pertenencia a grupos.

d) Se convierten automáticamente en cuentas locales.

### ✔ Respuesta correcta

**c)**

### 📖 Explicación

Una cuenta deshabilitada:

- Conserva su SID.
- Conserva grupos.
- Conserva permisos.
- Conserva atributos.

Simplemente deja de poder autenticarse.

Esto facilita una posible reactivación futura.

### 💡 Buena práctica

Deshabilitar primero.

Eliminar después.

---

# Pregunta 66

## Enunciado

Un administrador desea aplicar una configuración únicamente al departamento de Informática.

¿Cuál sería la mejor opción?

✅ a) Crear una GPO vinculada a la OU Informática.

b) Cambiar el nombre del dominio.

c) Reiniciar todos los equipos.

d) Crear un nuevo bosque.

### ✔ Respuesta correcta

**a)**

### 📖 Explicación

La combinación correcta es:

OU

↓

Agrupa objetos.

GPO

↓

Aplica configuraciones.

Es exactamente el diseño para el que fue creado Active Directory.

---

# Pregunta 67

## Enunciado

¿Qué comando permite buscar una cadena de texto dentro de un archivo?

a) cat

✅ b) grep

c) less

d) nano

### ✔ Respuesta correcta

**b) grep**

### 📖 Explicación

grep busca patrones dentro de archivos.

Ejemplo:

```bash
grep root /etc/passwd
```

Es uno de los comandos más utilizados por administradores Linux.

### 💡 Muy útil

grep suele combinarse con:

- ps
- journalctl
- cat
- ls

---

# Pregunta 68

## Enunciado

¿Cuál de las siguientes afirmaciones sobre los grupos de seguridad es CORRECTA?

a) Su finalidad principal es organizar visualmente Active Directory.

✅ b) Se utilizan para asignar permisos de forma colectiva.

c) Sustituyen completamente a las OU.

d) No pueden contener otros grupos.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

La filosofía correcta es:

Usuarios

↓

Grupos

↓

Permisos

Esto simplifica enormemente la administración.

### 🎯 Lo que busca realmente el tribunal

Comprobar si conoces el modelo AGDLP (o sus variantes) de asignación de permisos mediante grupos, una práctica recomendada en entornos Active Directory.

---

# Pregunta 69

## Enunciado

En relación con la administración de un dominio, ¿cuál de las siguientes actuaciones resulta MÁS recomendable?

a) Conceder permisos directamente a cada usuario.

✅ b) Asignar permisos a grupos y administrar los usuarios mediante dichos grupos.

c) Añadir todos los usuarios al grupo Administradores.

d) Crear una OU distinta para cada usuario.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Administrar permisos mediante grupos:

- Reduce errores.
- Facilita auditorías.
- Simplifica altas y bajas.
- Favorece el principio de mínimo privilegio.

Es una de las mejores prácticas fundamentales en Active Directory.

### ❌ ¿Por qué no las demás?

Las otras opciones incrementan la complejidad, dificultan el mantenimiento o suponen riesgos de seguridad.

### 💡 Consejo de examen

Cuando veas la expresión **"mejor práctica"**, descarta las soluciones que funcionan pero no escalan o complican la administración.

---

# Pregunta 70

## Enunciado

¿Cuál de las siguientes afirmaciones resume mejor la principal ventaja de una infraestructura basada en Active Directory frente a un grupo de trabajo?

a) Permite instalar Windows Server más rápidamente.

✅ b) Facilita la administración centralizada de usuarios, equipos, recursos y políticas.

c) Reduce el consumo de memoria de los equipos cliente.

d) Elimina la necesidad de utilizar DNS.

### ✔ Respuesta correcta

**b)**

### 📖 Explicación

Esta pregunta resume prácticamente todo el bloque.

Active Directory existe para centralizar:

- Usuarios.
- Equipos.
- Recursos.
- Políticas.
- Autenticación.
- Administración.

Todo el resto de servicios (GPO, DNS, grupos, OU...) gira alrededor de este objetivo.

### 🎯 Lo que busca realmente el tribunal

Si solo pudieras recordar **una idea** de todo el tema de Active Directory, debería ser esta: **la administración centralizada es su razón de ser**.

---

# 🎓 Resumen final del Simulacro 01

## Conceptos imprescindibles

### GNU/Linux

| Comando | Función |
|----------|----------|
| `whoami` | Usuario actual |
| `hostname` | Nombre del equipo |
| `pwd` | Directorio actual |
| `cd` | Cambiar directorio |
| `ls` | Listar contenido |
| `df -h` | Espacio en disco |
| `free -h` | Memoria RAM |
| `ps` | Instantánea de procesos |
| `top` | Procesos en tiempo real |
| `grep` | Buscar texto |
| `kill` | Finalizar procesos |
| `man` | Manual de comandos |
| `useradd` | Crear usuario |
| `passwd` | Cambiar contraseña |
| `chmod` | Cambiar permisos |
| `chown` | Cambiar propietario |

### Active Directory

- DNS es imprescindible.
- NTDS.DIT almacena la base de datos.
- Las OU organizan.
- Los grupos conceden permisos.
- Las GPO aplican configuraciones.
- El Controlador de Dominio autentica usuarios.
- Los equipos también tienen cuentas en Active Directory.
- Un dominio centraliza la administración.
- La buena práctica consiste en asignar permisos a grupos, no directamente a usuarios.

### Errores clásicos

❌ Confundir OU con grupos.

❌ Confundir GPO con permisos.

❌ Pensar que DNS solo sirve para Internet.

❌ Administrar permisos usuario a usuario.

❌ Utilizar siempre la cuenta Administrador.

❌ Confundir `ps` con `top`.

❌ Confundir `df` con `free`.

❌ Confundir `chmod` con `chown`.

---

# 🏁 Conclusión

Has completado el **Simulacro 01**, compuesto por 70 preguntas y un solucionario detallado. La estructura que hemos construido va más allá de un simple listado de respuestas: cada corrección refuerza el concepto, explica los distractores y pone el foco en las buenas prácticas y en la lógica que suele seguir un tribunal de oposición.

Mi propuesta para el **Simulacro 02** sería mantener este formato, pero subir un escalón el nivel: menos preguntas de definición directa y más escenarios reales de administración, comparaciones entre tecnologías y decisiones basadas en buenas prácticas. Creo que ese enfoque preparará mucho mejor para el examen oficial y hará que el material gane todavía más valor como manual de estudio.