# Tarjetas - Bloque 01 - Parte A (Linux)

Formato:
P: Pregunta
R: Respuesta

---

## 1.1 Introduccion a GNU/Linux

P: Que es GNU/Linux?
R: Un sistema operativo tipo Unix formado por el kernel Linux y las herramientas del proyecto GNU.

P: Que es el kernel?
R: El nucleo del sistema operativo que gestiona hardware, procesos, memoria y dispositivos.

P: Que funcion tiene la shell?
R: Es la interfaz de comandos que permite interactuar con el sistema operativo.

## 1.2 Sistema de archivos

P: Cual es la raiz del sistema de archivos en Linux?
R: El directorio /.

P: Para que sirve /etc?
R: Almacena configuraciones del sistema y de servicios.

P: Para que sirve /var?
R: Guarda datos variables como logs, colas y caches.

## 1.3 Navegacion y gestion de archivos

P: Que comando muestra la ruta actual?
R: pwd.

P: Que comando lista archivos y carpetas?
R: ls.

P: Diferencia basica entre cp y mv?
R: cp copia; mv mueve o renombra.

## 1.4 Usuarios y grupos

P: Que identifica de forma unica a un usuario?
R: El UID.

P: Para que sirven los grupos?
R: Para gestionar permisos de forma colectiva.

P: Quien es root?
R: El superusuario con maximos privilegios administrativos.

## 1.5 Administracion de usuarios y grupos

P: Comando tipico para crear un usuario?
R: useradd.

P: Comando para cambiar la contrasena de un usuario?
R: passwd.

P: Comando para ver identidad y grupos de un usuario?
R: id.

## 1.6 Permisos

P: Que tres ambitos de permisos existen en Linux?
R: Propietario, grupo y otros.

P: Que comando cambia permisos?
R: chmod.

P: Que comando cambia propietario?
R: chown.

## 1.7 Procesos

P: Que es un PID?
R: El identificador unico de un proceso.

P: Herramienta clasica para ver procesos en tiempo real?
R: top (o htop si esta instalado).

P: Para que sirve kill?
R: Enviar senales a procesos, por ejemplo para terminarlos.

## 1.8 Bash

P: Que es una variable de entorno?
R: Una variable global de sesion usada por sistema y programas.

P: Para que sirve un pipe (|)?
R: Para enviar la salida de un comando como entrada de otro.

P: Para que sirve un alias?
R: Para crear atajos de comandos frecuentes.

## 1.9 Servicios (systemd)

P: Comando para ver estado de un servicio con systemd?
R: systemctl status nombre-servicio.

P: Comando para iniciar un servicio?
R: systemctl start nombre-servicio.

P: Comando para ver logs de un servicio?
R: journalctl -u nombre-servicio.

## 1.10 Gestion de paquetes

P: Gestor de paquetes comun en Debian/Ubuntu?
R: apt.

P: Gestor de paquetes comun en Fedora/RHEL modernos?
R: dnf.

P: Diferencia entre actualizar indice y actualizar paquetes en apt?
R: apt update actualiza indice de repositorios; apt upgrade instala actualizaciones disponibles.

## 1.11 Administracion basica

P: Protocolo habitual para administracion remota segura?
R: SSH.

P: Herramienta para transferir archivos sobre SSH de forma simple?
R: scp.

P: Para que sirve cron?
R: Para programar tareas periodicas.

---

## Tarjetas de repaso transversal (Linux)

P: Que principio reduce riesgos de seguridad en administracion diaria?
R: Minimo privilegio, usar solo permisos necesarios.

P: Que debes comprobar antes de aplicar cambios en produccion?
R: Usuario actual, servidor correcto, copia de seguridad y impacto.

P: Que diferencia hay entre logs y metricas?
R: Logs registran eventos detallados; metricas cuantifican estado y rendimiento.

P: Por que automatizar tareas repetitivas?
R: Reduce errores manuales y mejora consistencia.

P: Que es mas importante que memorizar un comando exacto?
R: Entender el diagnostico y elegir herramienta adecuada.