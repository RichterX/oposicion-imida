# 🏆 MISIÓN 03
# Despliegue inicial de la infraestructura del IMIDA

> **Bloque:** 1 - Administración de Sistemas
>
> **Dificultad:** ⭐⭐⭐⭐⭐
>
> **Tiempo estimado:** 90-120 minutos
>
> **Objetivo:** Integrar todos los conocimientos adquiridos durante el Bloque 1.

---

# 🎯 Objetivos

Durante esta misión pondrás en práctica todo lo aprendido sobre:

- Active Directory.
- Dominios.
- Objetos.
- Usuarios.
- Equipos.
- Unidades Organizativas.
- Administración de objetos.
- Directivas de Grupo.

No se trata de memorizar comandos.

Se trata de demostrar que sabes diseñar una infraestructura Windows completa.

---

# 🏢 Escenario

El Instituto Murciano de Investigación y Desarrollo Agrario y Medioambiental (IMIDA) inaugura un nuevo edificio.

Actualmente no existe ninguna infraestructura Windows.

Todo debe construirse desde cero.

La dirección solicita una administración moderna, centralizada y preparada para crecer en los próximos años.

Dispones de un servidor con Windows Server recién instalado.

Tu misión consiste en diseñar toda la infraestructura.

---

# 📋 Situación inicial

La organización dispone de cuatro departamentos.

- Dirección
- Administración
- Investigación
- Informática

Inicialmente trabajarán:

- 22 empleados
- 18 ordenadores

Se prevé que en cinco años la organización duplique su tamaño.

---

# 📝 FASE 1
## Diseñando la infraestructura

Explica brevemente las siguientes decisiones.

### 1.

¿Por qué resulta recomendable implantar un dominio en lugar de mantener un grupo de trabajo?

---

### 2.

¿Qué ventajas aportará Active Directory al IMIDA?

Menciona al menos cinco.

---

### 3.

¿Qué nombre elegirías para el dominio?

Justifica brevemente tu elección.

---

### 4.

¿Qué objetos crees que existirán dentro del dominio?

Indica todos los que consideres necesarios.

---

# 📝 FASE 2
## Organización del dominio

Ahora debes organizar Active Directory.

### 5.

Diseña una estructura de OU para los cuatro departamentos.

Puedes utilizar un esquema en forma de árbol.

---

### 6.

Explica por qué has decidido esa organización.

---

### 7.

¿Crearías grupos?

¿Para qué servirían?

Indica algunos ejemplos.

---

# 📝 FASE 3
## Incorporación de usuarios

Llegan los primeros empleados.

- Laura García
- David López
- Marta Sánchez
- Juan Pérez

### 8.

¿Qué objetos crearías?

---

### 9.

¿Qué información almacenarías en cada usuario?

---

### 10.

¿En qué OU colocarías cada uno?

Justifica tu decisión.

---

# 📝 FASE 4
## Incorporación de equipos

Llegan también los primeros ordenadores.

```
PC-ADM-01

PC-ADM-02

PC-INV-01

PC-INV-02

PC-INF-01
```

### 11.

¿Qué pasos seguirías para incorporarlos a la infraestructura?

Ordénalos cronológicamente.

---

### 12.

¿Qué ocurre dentro de Active Directory cuando un ordenador se une al dominio?

---

### 13.

¿Por qué resulta importante utilizar una convención de nombres?

---

# 📝 FASE 5
## Administración

Transcurridos varios meses suceden los siguientes acontecimientos.

Laura cambia al departamento de Dirección.

David abandona la organización.

Llegan dos nuevos investigadores.

Un ordenador queda averiado definitivamente.

### 14.

Explica qué operaciones realizarías sobre cada objeto.

---

### 15.

¿Eliminarías inmediatamente los usuarios y equipos que dejan de utilizarse?

Justifica la respuesta.

---

# 📝 FASE 6
## Administración mediante GPO

La dirección solicita las siguientes políticas.

### Departamento de Investigación

- Bloqueo automático tras 10 minutos.
- USB deshabilitado.
- Fondo corporativo.

### Departamento de Administración

- Acceso a impresoras.
- Fondo corporativo.
- Panel de control deshabilitado.

### Dirección

- Sin restricciones.

### Informática

- PowerShell habilitado.
- Herramientas administrativas disponibles.

### 16.

¿Cómo organizarías las GPO?

---

### 17.

¿Dónde las vincularías?

---

### 18.

¿Por qué utilizar GPO en lugar de configurar manualmente cada ordenador?

---

# 📝 FASE 7
## Reflexión final

Imagina que dentro de tres años el IMIDA duplica su tamaño.

Ahora existen:

- 120 usuarios.
- 95 equipos.
- Dos edificios.

### 19.

¿Crees que la infraestructura diseñada seguirá siendo válida?

Razona tu respuesta.

---

### 20.

Resume, utilizando tus propias palabras, el recorrido completo que sigue un ordenador desde que llega al IMIDA hasta que recibe automáticamente las políticas de su departamento.

Puedes apoyarte en un diagrama si lo consideras oportuno.