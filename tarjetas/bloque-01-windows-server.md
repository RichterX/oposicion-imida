# Tarjetas - Bloque 01 - Parte B (Windows Server)

Formato:
P: Pregunta
R: Respuesta

---

## 1.12 Introduccion a Windows Server

P: Para que esta disenado Windows Server?
R: Para ofrecer servicios de red y administrar infraestructura, no para uso personal.

P: Diferencia clave entre Windows cliente y Windows Server?
R: Cliente orientado a usuario final; Server orientado a servicios y administracion central.

P: Que es Server Core?
R: Instalacion sin escritorio tradicional, con menor consumo y menor superficie de ataque.

## 1.13 Arquitectura de Windows

P: Que diferencia hay entre User Mode y Kernel Mode?
R: User Mode tiene acceso limitado; Kernel Mode tiene acceso total al hardware y es critico.

P: Que es la HAL?
R: Capa de abstraccion de hardware que separa el sistema operativo de detalles del hardware fisico.

P: Que es el Registro de Windows?
R: Base de datos jerarquica de configuracion del sistema, usuarios y aplicaciones.

## 1.14 NTFS

P: Por que NTFS es preferible a FAT32 en servidores?
R: Por seguridad ACL, journaling, soporte de archivos grandes y funciones avanzadas.

P: Que son permisos NTFS?
R: Reglas que controlan que puede hacer cada usuario o grupo sobre archivos y carpetas.

P: Regla basica al combinar permisos compartidos y NTFS?
R: Prevalece el permiso mas restrictivo.

## 1.15 Usuarios y grupos

P: Que es un usuario local?
R: Cuenta valida solo en ese equipo, no en todo el dominio.

P: Equivalente funcional de root en Windows?
R: La cuenta Administrator.

P: Ventaja de usar grupos para permisos?
R: Facilita administracion y escalabilidad.

## 1.16 Permisos

P: Que significa ACL?
R: Access Control List, lista de control de acceso de un recurso.

P: Diferencia entre permiso explicito y heredado?
R: Explicito se asigna directo; heredado viene de carpeta padre.

P: Que riesgo tiene usar Denegar sin criterio?
R: Puede bloquear accesos legitimos y complicar diagnostico.

## 1.17 Procesos y servicios

P: Diferencia entre proceso y servicio?
R: Proceso es programa en ejecucion; servicio suele ejecutarse en segundo plano de forma continua.

P: Herramienta grafica para revisar procesos y consumo?
R: Administrador de tareas.

P: Cmdlet para listar servicios en PowerShell?
R: Get-Service.

## 1.18 Roles y caracteristicas

P: Que es un rol en Windows Server?
R: Funcion principal del servidor, por ejemplo DNS, DHCP o AD DS.

P: Que es una caracteristica?
R: Componente adicional que amplia capacidades sin definir por si sola un servicio principal.

P: Herramienta grafica para instalar roles?
R: Server Manager con Add Roles and Features.

## 1.18.01 Roles habituales

P: Que rol gestiona dominio y autenticacion centralizada?
R: AD DS.

P: Que rol traduce nombres a IP?
R: DNS Server.

P: Que rol asigna IP automaticamente?
R: DHCP Server.

P: Que rol se usa para publicar aplicaciones web?
R: IIS (Web Server).

P: Que rol permite virtualizacion en Windows Server?
R: Hyper-V.

## 1.19 Administracion y mantenimiento

P: Herramienta principal para revisar eventos?
R: Event Viewer.

P: Por que son criticas las copias de seguridad verificadas?
R: Porque una copia no verificada puede fallar al restaurar.

P: Herramienta para programar tareas en Windows?
R: Task Scheduler.

---

## Tarjetas de repaso transversal (Windows Server)

P: Que principio debes seguir al instalar roles?
R: Instalar solo lo necesario.

P: Que debes hacer despues de reiniciar un servicio?
R: Verificar estado, revisar eventos y confirmar funcionalidad.

P: Que combinacion de herramientas es clave para diagnostico?
R: Task Manager, Services, Event Viewer y PowerShell.

P: Que ventaja aporta PowerShell frente a GUI?
R: Automatizacion, repetibilidad y gestion masiva.

P: Cual es el objetivo del mantenimiento preventivo?
R: Evitar fallos antes de que impacten al servicio.