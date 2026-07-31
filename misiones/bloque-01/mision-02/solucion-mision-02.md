# Mision 02 · Administrador de Windows Server
## Solucion oficial

> **Bloque:** Administracion de Sistemas
>
> **Parte:** Windows Server
>
> **Documento:** Solucion oficial
>
> **Version:** 1.0
>
> **Tiempo recomendado:** Lectura completa tras finalizar la mision
>
> **Nivel:** ⭐⭐⭐⭐☆

---

# Introduccion

La finalidad de este documento no es solo decir "la respuesta correcta".

Su objetivo es ayudarte a pensar como administrador de sistemas en Windows Server:

- identificar la herramienta adecuada;
- seguir un orden logico de diagnostico;
- minimizar riesgos en produccion;
- justificar cada decision tecnica.

En administracion real suelen existir varias respuestas validas.

Lo importante es el razonamiento y el orden de actuacion.

---

# Como corregir esta mision

No compares solo comandos.

Comprueba si tu enfoque fue correcto:

- ¿Has usado la herramienta adecuada para cada problema?
- ¿Has comprobado antes de modificar?
- ¿Has priorizado servicio, seguridad y datos?
- ¿Has explicado por que eliges cada accion?

Si la respuesta es si, tu criterio va en buena direccion.

---

# 🟢 Nivel 1 · Reconocimiento del servidor

---

# Pregunta 1

## Enunciado

¿Como comprobarias el nombre del servidor?

---

### ✅ Respuesta esperada

Con PowerShell:

```powershell
hostname
```

Tambien es valido:

```powershell
$env:COMPUTERNAME
```

o:

```powershell
Get-ComputerInfo | Select-Object CsName
```

---

Alternativa grafica: **Server Manager**.

### 💡 Criterio tecnico

`hostname` es rapido y suficiente para una comprobacion inicial.

---

# Pregunta 2

## Enunciado

¿Que herramienta utilizarias para conocer los roles instalados?

---

### ✅ Respuesta esperada

PowerShell:

```powershell
Get-WindowsFeature
```

Para ver solo instalados:

```powershell
Get-WindowsFeature | Where-Object Installed
```

Alternativa grafica: **Server Manager**.

---

### 💡 Criterio tecnico

En produccion, PowerShell facilita filtrar, documentar y automatizar.

---

# Pregunta 3

## Enunciado

¿Como comprobarias si existen actualizaciones pendientes?

---

### ✅ Respuesta esperada

Herramienta grafica:

- **Settings** / **Windows Update**

Tambien puede revisarse desde **Server Manager** (panel de estado).

---

### 💡 Criterio tecnico

La pregunta pide herramienta, no script. Lo mas directo y esperable en nivel base es Windows Update.

---

# Pregunta 4

## Enunciado

¿Que herramienta abririas para revisar los registros del sistema?

---

### ✅ Respuesta esperada

**Event Viewer** (`eventvwr.msc`).

---

### 💡 Criterio tecnico

Es el punto central para diagnosticar errores de sistema, aplicaciones y seguridad.

---

# Pregunta 5

## Enunciado

¿Donde consultarias que tareas automaticas estan programadas?

---

### ✅ Respuesta esperada

**Task Scheduler** (`taskschd.msc`).

---

### 💡 Criterio tecnico

Permite ver triggers, acciones, historico y estado de ejecucion.

---

# 🟡 Nivel 2 · Usuarios y permisos

---

# Pregunta 1

## Enunciado

¿Que herramienta utilizarias para crear el usuario?

---

### ✅ Respuesta esperada

Herramienta grafica:

- **Local Users and Groups** (`lusrmgr.msc`)

Alternativa valida en PowerShell:

```powershell
New-LocalUser
```

---

### 💡 Criterio tecnico

Para mision de consolidacion, `lusrmgr.msc` demuestra que conoces la consola base de cuentas locales.

---

# Pregunta 2

## Enunciado

¿Como añadirias ese usuario al grupo correspondiente?

---

### ✅ Respuesta esperada

En GUI: desde `lusrmgr.msc`, editar grupo **Investigacion** y agregar usuario.

En PowerShell:

```powershell
Add-LocalGroupMember -Group "Investigacion" -Member "usuario"
```

---

### 💡 Criterio tecnico

Asignar membresia de grupo antes de tocar ACL simplifica mantenimiento.

---

# Pregunta 3

## Enunciado

¿Que ventana utilizarias para modificar los permisos de la carpeta?

---

### ✅ Respuesta esperada

Ruta:

```text
Propiedades de la carpeta

→ Seguridad

→ Opciones avanzadas
```

---

### 💡 Criterio tecnico

Esa ventana permite gestionar ACL, herencia, propietario y permisos especiales.

---

# Pregunta 4

## Enunciado

¿Como comprobarias los permisos efectivos del usuario?

---

### ✅ Respuesta esperada

En la misma ventana de seguridad avanzada:

- pestaña de **acceso efectivo** / **Effective Access**;
- seleccionar usuario;
- evaluar permisos resultantes.

---

### 💡 Criterio tecnico

Evita errores de interpretacion cuando el usuario pertenece a varios grupos.

---

# Pregunta 5

## Enunciado

¿Por que resulta preferible asignar permisos al grupo y no directamente al usuario?

---

### ✅ Respuesta esperada

Porque mejora:

- escalabilidad;
- orden;
- trazabilidad;
- mantenimiento.

Además:

- reduce errores administrativos;
- facilita las auditorías;
- simplifica la incorporación y baja de usuarios;
- favorece la aplicación del principio de mínimo privilegio.

Con grupos, al entrar/salir personas solo cambias la membresia, no toda la ACL.

---

### ⚠️ Error habitual

Dar permisos directos a usuarios por urgencia y dejar una ACL dificil de auditar.

---

## 🧠 Cadena de diagnóstico

Imagina una empresa con 300 empleados.

Si cada permiso se asignara individualmente, cualquier cambio de personal implicaría modificar decenas o cientos de carpetas.

Los grupos permiten administrar los permisos de forma centralizada.

---

# 🟠 Nivel 3 · Procesos y servicios

---

# Pregunta 1

## Enunciado

¿Qué herramienta abririas primero?

---

### ✅ Respuesta esperada

**Task Manager** (Administrador de tareas).

---

### 💡 Criterio tecnico

Ofrece una vista inmediata de CPU, memoria, disco, red y procesos causantes.

---

# Pregunta 2

## Enunciado

¿Qué recurso comprobarias antes y por que?

---

### ✅ Respuesta esperada

Comprobacion inicial recomendada: **CPU** y **Memoria**.

Justificacion:

- son causas frecuentes de lentitud percibida;
- permiten detectar rapido procesos anómalos;
- guian el siguiente paso del diagnostico.

Tambien es valido priorizar disco si hay sintomas de I/O alto.

---

### 💡 Criterio tecnico

No hay una unica respuesta cerrada. Se valora razonamiento y secuencia logica.

---

# Pregunta 3

## Enunciado

Localizas un proceso que consume el 95 % de la CPU. ¿Que harias?

---

### ✅ Respuesta esperada

Orden recomendado:

1. Identificar proceso y contexto (nombre, usuario, servicio asociado).
2. Validar si es critica su parada.
3. Intentar cierre controlado desde aplicacion o servicio.
4. Si persiste, finalizar proceso desde Task Manager o PowerShell.
5. Revisar Event Viewer para causa raiz.

PowerShell posible:

```powershell
Stop-Process -Id <PID>
```

---

### ⚠️ Error habitual

Matar procesos criticos sin validar impacto.

---

# Pregunta 4

## Enunciado

Descubres que el servicio DNS esta detenido. ¿Que herramienta utilizarias?

---

### ✅ Respuesta esperada

**Services** (`services.msc`) o PowerShell con `Get-Service`.

---

### 💡 Criterio tecnico

`services.msc` permite comprobar estado, tipo de inicio y dependencias.

---

# Pregunta 5

## Enunciado

¿Como reiniciarias ese servicio mediante PowerShell?

---

### ✅ Respuesta esperada

```powershell
Restart-Service -Name DNS
```

Opcionalmente comprobar despues:

```powershell
Get-Service -Name DNS
```

---

### 💡 Criterio tecnico

Siempre confirmar estado tras la accion.

---

# 🔴 Nivel 4 · Roles y administracion

---

# Pregunta 1

## Enunciado

¿Qué herramienta grafica utilizarias?

---

### ✅ Respuesta esperada

**Server Manager** → **Add Roles and Features**.

---

# Pregunta 2

## Enunciado

¿Qué cmdlet de PowerShell instalaria un rol?

---

### ✅ Respuesta esperada

```powershell
Install-WindowsFeature
```

Ejemplo para DNS:

```powershell
Install-WindowsFeature -Name DNS
```

---

# Pregunta 3

## Enunciado

¿Que diferencia existe entre un rol y una caracteristica?

---

### ✅ Respuesta esperada

- **Rol:** define una funcion de servicio del servidor (DNS, DHCP, AD DS, IIS).
- **Caracteristica:** componente adicional que amplia capacidades, pero no define por si sola un servicio principal.

---

# Pregunta 4

## Enunciado

¿Por que no conviene instalar todos los roles disponibles?

---

### ✅ Respuesta esperada

Porque aumenta:

- consumo de recursos;
- complejidad operativa;
- superficie de ataque;
- riesgo de conflictos y mantenimiento.

Mejor principio: instalar solo lo necesario.

---

# Pregunta 5

## Enunciado

¿Que rol instalaras dentro de unos dias para comenzar Active Directory?

---

### ✅ Respuesta esperada

**Active Directory Domain Services (AD DS)**.

Normalmente junto con DNS en escenarios de dominio.

---

# 🔵 Nivel 5 · Administrador Senior

---

## Enunciado

Describe el orden en el que actuarias ante incidencias simultaneas.

---

### ✅ Respuesta esperada (orden recomendado)

1. **Estabilizar servicio y evaluar impacto inmediato**
   - Confirmar sintomas de lentitud (Task Manager, Resource Monitor).
   - Identificar si hay saturacion critica en CPU, RAM o disco.

2. **Asegurar continuidad de servicios criticos**
   - Revisar servicios clave (DNS, comparticion, autenticacion).
   - Recuperar rapidamente servicios caidos con minimo cambio.

3. **Resolver fallo de escritura en recursos compartidos**
   - Revisar ACL NTFS, permisos compartidos y permisos efectivos.
   - Corregir por grupo, no por usuario individual.

4. **Analizar errores del Event Viewer**
   - Correlacionar por hora con las incidencias observadas.
   - Priorizar errores repetitivos o de servicios nucleares.

5. **Atender actualizaciones criticas con control**
   - Verificar criticidad y ventana de mantenimiento.
   - Planificar reinicio fuera de horario si aplica.

6. **Verificar y recuperar estrategia de backup**
   - Comprobar por que no se verifica la ultima copia.
   - Ejecutar prueba de restauracion de validacion.

7. **Documentar y dejar seguimiento**
   - Registrar causa, accion, resultado y pasos pendientes.

---

### 💡 Criterio tecnico

Se prioriza:

- disponibilidad del servicio;
- integridad de datos;
- seguridad;
- correccion de causa raiz;
- trazabilidad.

---

# ⭐ Nivel Bonus · Equivalencias GNU/Linux vs Windows Server

| GNU/Linux | Windows Server |
|-----------|----------------|
| Bash | PowerShell |
| root | Administrator |
| /etc | Registro de Windows + configuracion del sistema |
| systemd / systemctl | Service Control Manager + Services.msc |
| ps / top / htop | Task Manager / Get-Process |
| kill | Stop-Process |
| journalctl | Event Viewer |
| cron | Task Scheduler |
| SSH | RDP / PowerShell Remoting |
| chmod/chown | ACL NTFS / Propietario |
| apt/dnf/yum | Roles y Features + mecanismos de actualizacion |
| ext4/xfs | NTFS |

---

# Cierre de evaluacion

Si tu enfoque coincide de forma razonable con este solucionario:

- ya tienes una base solida de administracion en Windows Server;
- puedes pasar con confianza a Active Directory;
- tu siguiente salto de nivel sera consolidar diagnostico por eventos y automatizacion con PowerShell.

---

# Siguiente paso recomendado

Tras revisar este documento, repite la mision en modo estricto:

- sin apuntes;
- limitando cada respuesta a herramienta + razonamiento en dos lineas;
- corrigiendo luego con este solucionario.

Esa segunda vuelta suele fijar mucho mejor los conceptos.