# Tarjetas - Bloque 01 - Parte C (Active Directory)

Formato:
P: Pregunta
R: Respuesta

---

## 1.20 Introduccion a Active Directory

P: Que problema principal resuelve Active Directory?
R: La administracion centralizada de usuarios, equipos y permisos en una red Windows.

P: Diferencia entre grupo de trabajo y dominio?
R: En grupo de trabajo cada equipo es independiente; en dominio la gestion es central.

P: Diferencia entre autenticacion y autorizacion?
R: Autenticacion verifica identidad; autorizacion decide a que recursos puede acceder.

## 1.21 Instalacion AD DS y promocion

P: Instalar AD DS crea automaticamente el dominio?
R: No. Primero se instala el rol y despues se promociona a controlador de dominio.

P: Que es un Controlador de Dominio?
R: Servidor que ejecuta AD DS y autentica usuarios/equipos del dominio.

P: Que es un bosque (forest)?
R: La estructura logica superior de Active Directory que agrupa dominios.

## 1.22 Objetos de Active Directory

P: Que es un objeto en Active Directory?
R: Representacion administrable de un recurso, por ejemplo usuario, equipo o grupo.

P: Que es un atributo?
R: Dato que describe un objeto, por ejemplo nombre, correo o departamento.

P: Por que son importantes los objetos?
R: Porque toda administracion en AD consiste en crear, modificar o eliminar objetos.

## 1.23 Unidades Organizativas (OU)

P: Que es una OU?
R: Contenedor logico para organizar objetos dentro del dominio.

P: Diferencia entre OU y grupo?
R: OU organiza objetos; grupo agrupa identidades para permisos.

P: Para que sirve la jerarquia de OU?
R: Para ordenar administracion, delegar y aplicar GPO por areas.

## 1.24 Administracion de objetos

P: Herramienta clasica para administrar objetos AD?
R: Active Directory Users and Computers.

P: Operaciones comunes sobre objetos?
R: Crear, modificar, mover, deshabilitar y eliminar.

P: Por que deshabilitar puede ser mejor que eliminar inmediatamente?
R: Permite reversibilidad y reduce riesgo de borrar por error.

## 1.25 Directivas de Grupo (GPO)

P: Que es una GPO?
R: Conjunto centralizado de configuraciones aplicadas a usuarios y equipos.

P: Que relacion hay entre OU y GPO?
R: La GPO se vincula a OU para aplicar configuracion a los objetos de esa OU.

P: Ventaja principal de GPO frente a configuracion manual equipo a equipo?
R: Escalabilidad y consistencia.

## 1.26 Administracion de equipos

P: Que significa unir un equipo al dominio?
R: Registrar el equipo en AD para gestion centralizada y uso de cuentas de dominio.

P: Que sucede al unir un equipo al dominio?
R: Se crea su objeto equipo y puede recibir GPO y autenticacion del dominio.

P: Por que no basta con que el equipo tenga Windows instalado?
R: Porque sin union al dominio sigue siendo un equipo independiente.

---

## Tarjetas de repaso transversal (Active Directory)

P: Cual es la secuencia logica minima para montar un dominio?
R: Instalar AD DS, promocionar DC, crear estructura OU, crear objetos y aplicar GPO.

P: Que principio mejora orden y seguridad en AD?
R: Estructura clara de OU, grupos por funcion y minimo privilegio.

P: Que debes documentar siempre en AD?
R: Cambios de cuentas, grupos, GPO y movimientos de objetos.

P: Que error comun rompe la escalabilidad?
R: Administrar usuarios o equipos sin estructura ni estandares.

P: Objetivo final de AD en una organizacion?
R: Control centralizado, seguro y mantenible de identidades y recursos.