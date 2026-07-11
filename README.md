# 📘 Manual IMIDA

> Manual de preparación para la oposición de **Técnico Especialista en Tecnologías de la Información y Comunicaciones aplicadas a la Investigación (IMIDA)**.

![Estado](https://img.shields.io/badge/Estado-En%20desarrollo-blue)
![Licencia](https://img.shields.io/badge/Licencia-Privado-red)

Repositorio:
https://github.com/RichterX/oposicion-imida

[indice de contenidos del manual](manual/index.md)

---

# Objetivo

Este repositorio contiene un manual completo de estudio diseñado específicamente para preparar la oposición del IMIDA.

El objetivo no es crear un libro de informática, sino un material práctico, claro y orientado al examen oficial.

Todo el contenido se desarrollará de forma iterativa y se revisará al finalizar cada bloque temático.

---

# Filosofía del proyecto

Este manual sigue una serie de principios que no cambiarán durante el desarrollo:

- Comprender antes que memorizar.
- Priorizar preguntas reales de examen.
- Explicar únicamente aquello que aporte valor para aprobar la oposición.
- Utilizar documentación oficial siempre que sea posible.
- Mantener un formato homogéneo en todos los capítulos.

Cada capítulo debe poder estudiarse de forma independiente, pero también estar conectado con el resto del manual.

---

# Metodología de estudio

Cada capítulo seguirá siempre la misma estructura:

1. Objetivos
2. Introducción
3. Desarrollo del tema
4. Linux en acción (cuando proceda)
5. Errores frecuentes
6. Lo mínimo que debes recordar
7. Tarjetas de estudio
8. Mini test
9. Banco de preguntas tipo IMIDA

Al finalizar cada bloque se realizará:

- Simulacro completo.
- Revisión del bloque.
- Actualización del contenido si fuese necesario.

Solo después se continuará con el siguiente bloque.

---

# Estructura del repositorio

```text
oposicion-imida/
│
├── README.md
├── ROADMAP.md
├── CHANGELOG.md
│
├── manual/
│   │
│   ├── 00-introduccion/
│   │
│   ├── 01-administracion-sistemas/
│   │
│   ├── 02-redes/
│   │
│   ├── 03-bases-datos/
│   │
│   ├── 04-infraestructura/
│   │
│   ├── 05-programacion/
│   │
│   ├── 06-gestion-tic/
│   │
│   ├── 07-seguridad/
│   │
│   └── 08-imida/
│
├── tarjetas/
│   ├── bloque-01/
│   ├── bloque-02/
│   └── ...
│
├── tests/
│   ├── bloque-01/
│   ├── bloque-02/
│   └── ...
│
├── simulacros/
│   ├── bloque-01/
│   ├── bloque-02/
│   └── final/
│
└── recursos/
    ├── imagenes/
    ├── esquemas/
    └── referencias/
```

---

# Índice del manual

## Bloque 0 · Introducción

- Bienvenida
- Índice
- Progreso
- Cómo estudiar este manual

---

## Bloque 1 · Administración de Sistemas

- 1.1 Introducción a GNU/Linux
- 1.2 Sistema de archivos
- 1.3 Usuarios y grupos
- 1.4 Administración de usuarios y grupos
- 1.5 Permisos
- 1.6 Procesos
- 1.7 Bash
- 1.8 Servicios (systemd)
- 1.9 Gestión de paquetes
- 1.10 Administración básica
- 1.11 Windows Server
- 1.12 Active Directory

---

## Bloque 2 · Redes

- Modelo TCP/IP
- IPv4
- IPv6
- Ethernet
- VLAN
- VPN
- DNS
- DHCP
- Correo electrónico
- FortiGate

---

## Bloque 3 · Bases de datos

- SQL
- PostgreSQL
- Oracle
- MySQL
- PL/SQL
- PostGIS

---

## Bloque 4 · Infraestructura

- Virtualización
- VMware
- RAID
- NAS
- SAN
- CPD

---

## Bloque 5 · Programación

- Python
- Java
- Programación Orientada a Objetos
- UML
- HTML
- CSS
- JavaScript
- XML
- JSON

---

## Bloque 6 · Gestión TIC

- ITIL
- Scrum
- PRINCE2
- ISO 20000

---

## Bloque 7 · Seguridad

- Esquema Nacional de Seguridad
- RGPD
- Firewalls
- Certificados
- Ciberseguridad

---

## Bloque 8 · IMIDA

- Organización
- Legislación
- Investigación
- Buenas prácticas
- Gestión de residuos
- Muestreo

---

# Versionado

Cada modificación importante quedará reflejada en `CHANGELOG.md`.

Los capítulos se revisarán únicamente al finalizar cada bloque para mantener la coherencia del manual.

---

# Flujo de trabajo

```text
Investigación

↓

Redacción del capítulo

↓

Tarjetas

↓

Mini test

↓

Banco de preguntas

↓

Revisión

↓

Importación a Notion

↓

Estudio

↓

Feedback

↓

Siguiente capítulo
```

---

# Estado del proyecto

Actualmente se encuentra en desarrollo.

El objetivo es completar todo el temario antes de la segunda prueba de la oposición, manteniendo un único manual coherente y revisado.

---

# Nota personal

Este repositorio nace con una idea muy sencilla:

> Crear el material que nos habría gustado tener el primer día de preparación de esta oposición.

Cada capítulo pretende ser claro, práctico y orientado al examen.

La calidad tendrá siempre prioridad sobre la velocidad de desarrollo.
