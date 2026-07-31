# 📚 Índice del Manual IMIDA

> **Manual de preparación para la oposición de Técnico Especialista en Tecnologías de la Información y Comunicaciones aplicadas a la Investigación (IMIDA)**

---

# 📖 Introducción

- Bienvenida
- Índice
- Progreso
- Cómo estudiar este manual

---

# 🖥️ Bloque 1 · Administración de Sistemas
### Parte A (Linux)

## [1.1 Introducción a GNU/Linux](01-administracion-sistemas/parte-a-linux/01.01-introduccion-gnu-linux.md)

- ¿Qué es GNU/Linux?
- Kernel
- GNU
- Shell
- Distribuciones Linux

## [1.2 Sistema de archivos](01-administracion-sistemas/parte-a-linux/01.02-sistema-archivos.md)

- Directorio raíz
- Jerarquía del sistema
- Directorios principales
- FHS (Filesystem Hierarchy Standard)

## [1.3 Navegación y gestión básica de archivos](01-administracion-sistemas/parte-a-linux/01.03-navegacion-gestion-archivos.md)

- Navegar por el sistema de archivos.
- Crear directorios y archivos.
- Copiar y mover información.
- Eliminar archivos de forma segura.
- Visualizar el contenido de archivos.
- Buscar archivos dentro del sistema.

## [1.4 Usuarios y grupos](01-administracion-sistemas/parte-a-linux/01.04-usuarios-y-grupos.md)

- Usuarios
- UID
- Grupos
- Usuario root

## [1.5 Administración de usuarios y grupos](01-administracion-sistemas/parte-a-linux/01.05-administracion-usuarios-y-grupos.md)

- useradd
- usermod
- userdel
- passwd
- id
- groups
- who
- whoami

## [1.6 Permisos](01-administracion-sistemas/parte-a-linux/01.06-permisos.md)

- Propietario
- Grupo
- Otros
- chmod
- chown
- chgrp
- umask

## [1.7 Procesos](01-administracion-sistemas/parte-a-linux/01.07-procesos.md)

- PID
- PPID
- ps
- top
- htop
- kill
- nice
- jobs

## [1.8 Bash](01-administracion-sistemas/parte-a-linux/01.08-bash.md)

- Variables
- Redirecciones
- Pipes
- Alias
- Scripts
- Variables de entorno

## [1.9 Servicios (systemd)](01-administracion-sistemas/parte-a-linux/01.09-servicios.md)

- systemctl
- journalctl
- Servicios
- Targets

## [1.10 Gestión de paquetes](01-administracion-sistemas/parte-a-linux/01.10-gestion-paquetes.md)

- apt
- dnf
- Repositorios
- Actualizaciones

## [1.11 Administración básica](01-administracion-sistemas/parte-a-linux/01.11-administracion-basica.md)

- SSH
- SCP
- SFTP
- Cron
- Logs
- Copias de seguridad

### Parte B (Windows Server)

## [1.12 Introducción a Windows Server](01-administracion-sistemas/parte-b-windows-server/01.12-introduccion-windows-server.md)

- Qué es Windows Server
- Windows cliente vs Windows Server
- Versiones (2016, 2019, 2022)
- LTSC
- Desktop Experience y Server Core
- Server Manager

## [1.13 Arquitectura de Windows](01-administracion-sistemas/parte-b-windows-server/01.13-arquitectura-windows.md)

- User Mode y Kernel Mode
- Windows Executive
- Kernel y HAL
- Servicios y procesos
- Registro de Windows
- Capas de arquitectura

## [1.14 NTFS](01-administracion-sistemas/parte-b-windows-server/01.14-ntfs.md)

- NTFS y FAT32
- ACL
- Herencia de permisos
- Permisos efectivos
- Permisos NTFS y compartidos
- EFS, compresión y cuotas

## [1.15 Usuarios y Grupos](01-administracion-sistemas/parte-b-windows-server/01.15-usuarios-grupos.md)

- Usuarios locales
- Cuenta Administrator
- Perfiles de usuario
- Grupos locales
- lusrmgr.msc y compmgmt.msc
- New-LocalUser y Add-LocalGroupMember

## [1.16 Permisos](01-administracion-sistemas/parte-b-windows-server/01.16-permisos.md)

- ACL
- Permisos explícitos y heredados
- Permisos efectivos
- Permitir y Denegar
- Propietario del recurso
- Principio de mínimo privilegio

## [1.17 Procesos y Servicios](01-administracion-sistemas/parte-b-windows-server/01.17-procesos-y-servicios.md)

- Proceso vs servicio
- PID y recursos
- Administrador de tareas
- services.msc
- Service Control Manager (SCM)
- Get-Process y Get-Service

## [1.18 Roles, características y administración del servidor](01-administracion-sistemas/parte-b-windows-server/01.18-roles-y-caracteristicas.md)

- Roles y características
- Server Manager
- Add Roles and Features
- Get-WindowsFeature
- Install-WindowsFeature
- Roles: AD DS, DNS, DHCP, IIS, Hyper-V
- [1.18.01 Roles habituales en Windows Server](01-administracion-sistemas/parte-b-windows-server/01.18.01-roles-habituales.md)

## [1.19 Administración y mantenimiento](01-administracion-sistemas/parte-b-windows-server/01.19-administracion-y-mantenimiento.md)

- Mantenimiento preventivo
- Event Viewer
- Windows Update
- Windows Server Backup
- RDP y PowerShell Remoting
- Task Scheduler y monitorización

### Parte C (Active Directory)

## [1.20 Introducción a Active Directory](01-administracion-sistemas/parte-c-active-directory/01.20-introduccion-active-directory.md)

- Active Directory
- Dominio vs Grupo de trabajo
- Controlador de Dominio
- Autenticación y autorización
- Administración centralizada
- Componentes de AD

## [1.21 Instalación de AD DS y promoción a Controlador de Dominio](01-administracion-sistemas/parte-c-active-directory/01.21-instalacion-active-directory.md)

- Rol AD DS
- Instalación vs promoción
- Controlador de Dominio (DC)
- Bosque y dominio raíz
- Base de datos NTDS
- Primer dominio de la organización

## [1.22 Objetos de Active Directory](01-administracion-sistemas/parte-c-active-directory/01.22-objetos-active-directory.md)

- Objeto y atributo
- Usuarios, grupos y equipos
- Contactos e impresoras
- Objetos lógicos y físicos
- Identidad de recursos
- Representación en el dominio

## [1.23 Unidades Organizativas (OU)](01-administracion-sistemas/parte-c-active-directory/01.23-unidades-organizativas.md)

- OU (Organizational Unit)
- Jerarquía padre/hija
- Contenedores lógicos
- OU vs grupos
- Delegación administrativa
- Base para aplicar GPO

## [1.24 Administración de objetos](01-administracion-sistemas/parte-c-active-directory/01.24-administracion-objetos.md)

- Crear y modificar usuarios
- Crear grupos y miembros
- Administrar equipos
- Mover objetos entre OU
- Deshabilitar y eliminar cuentas
- Atributos y papelera de AD

## [1.25 Directivas de Grupo (GPO)](01-administracion-sistemas/parte-c-active-directory/01.25-directivas-de-grupo-gpo.md)

- GPO (Group Policy Object)
- Configuración centralizada
- GPO local vs dominio
- Vinculación a OU
- Herencia de directivas
- Políticas de seguridad

## [1.26 Administración de equipos](01-administracion-sistemas/parte-c-active-directory/01.26-administracion-equipos.md)

- Unión al dominio
- Objeto equipo
- Cuenta de equipo
- Relación OU y GPO
- Movimiento y cambio de nombre
- Gestión de equipos del dominio

---

[## Tarjetas de estudio](/tarjetas/index-tarjetas-bloque-01.md)
[## Simulacro de examen](/simulacros/bloque-01/simulacro-01.md)

---

# 🌐 Bloque 2 · Redes

## 2.1 Introducción a redes

- Conceptos básicos
- LAN, MAN, WAN
- Topologías
- Modelo OSI
- Modelo TCP/IP
- Encapsulación
- Protocolos

## 2.2 Direccionamiento IP

- IPv4
- IPv6
- Máscaras de red
- CIDR
- Subredes
- Direcciones públicas y privadas
- Dirección de red
- Broadcast
- Gateway

## 2.3 Ethernet

- IEEE 802.3
- Direcciones MAC
- Tramas Ethernet
- Switches
- ARP

## 2.4 DNS

- Funcionamiento
- Resolución de nombres
- Registros DNS
- DNS recursivo
- DNS autoritativo
- Caché DNS

## 2.5 DHCP

- Funcionamiento
- Proceso DORA
- Concesiones (Leases)
- Reservas
- Exclusiones
- Relay DHCP

## 2.6 VPN

- Conceptos
- VPN Site-to-Site
- VPN Cliente-Servidor
- IPsec
- SSL VPN

## 2.7 VLAN

- Conceptos
- VLAN de acceso
- VLAN nativa
- VLAN de gestión
- Troncales
- IEEE 802.1Q
- Inter-VLAN Routing

## 2.8 Correo electrónico

- SMTP
- POP3
- IMAP
- Flujo del correo
- Registros MX

## 2.9 Firewalls

- Concepto
- Filtrado de paquetes
- Stateful Inspection
- ACL
- NAT
- PAT
- DMZ
- FortiGate (administración básica)

## 2.10 Herramientas de diagnóstico de red

## 2.11 Seguridad básica en redes

- Segmentación
- Principio de mínimo privilegio
- IDS
- IPS
- Proxy
- Bastionado

---

# 🗄️ Bloque 3 · Bases de datos

## 3.1 SQL

## 3.2 PostgreSQL

## 3.3 Oracle

## 3.4 MySQL

## 3.5 PL/SQL

## 3.6 PostGIS

---

# 🖥️ Bloque 4 · Infraestructura

## 4.1 CPD

## 4.2 Virtualización

## 4.3 VMware

## 4.4 RAID

## 4.5 NAS

## 4.6 SAN

---

# 💻 Bloque 5 · Programación

## 5.1 Python

## 5.2 Java

## 5.3 Programación Orientada a Objetos

## 5.4 UML

## 5.5 HTML

## 5.6 CSS

## 5.7 JavaScript

## 5.8 XML

## 5.9 JSON

---

# 📈 Bloque 6 · Gestión TIC

## 6.1 ITIL

## 6.2 Scrum

## 6.3 PRINCE2

## 6.4 ISO 20000

---

# 🔐 Bloque 7 · Seguridad

## 7.1 Esquema Nacional de Seguridad

## 7.2 RGPD

## 7.3 Certificados digitales

## 7.4 Firewalls

## 7.5 Ciberseguridad

---

# 🧪 Bloque 8 · IMIDA

## 8.1 Organización del IMIDA

## 8.2 Legislación

## 8.3 Investigación

## 8.4 Buenas prácticas de laboratorio

## 8.5 Gestión de residuos

## 8.6 Muestreo

---

# 📑 Recursos del proyecto

- Tarjetas de estudio
- Mini tests
- [Misiones](misiones/readme.md)
- Simulacros

---

# 🎯 Objetivo final

Completar todos los bloques del temario, hacer las misiones, realizar un simulacro por bloque y un simulacro final antes de la segunda prueba de la oposición.

> **Principio del proyecto:** *Comprender antes que memorizar.*
