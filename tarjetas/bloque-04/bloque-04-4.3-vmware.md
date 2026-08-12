# Tarjetas - Bloque 04 - 4.3 VMware

Formato:
P: Pregunta
R: Respuesta

---

## 4.3 VMware

P: Que es VMware en infraestructura?
R: Un ecosistema de virtualizacion y gestion de centros de datos.

P: Que es vSphere?
R: Plataforma de virtualizacion de servidores dentro del ecosistema VMware.

P: Que es ESXi?
R: Hipervisor tipo 1 de VMware que ejecuta VMs sobre hardware fisico.

P: Que es vCenter Server?
R: Componente de gestion centralizada de hosts, clusters, inventario y operaciones.

P: Que se entiende por host ESXi?
R: Servidor fisico que ejecuta ESXi y aloja VMs.

P: Que es un datastore en VMware?
R: Contenedor logico de almacenamiento usado para archivos de VMs.

P: Diferencia rapida entre vSwitch estandar y distribuido?
R: Estandar se configura por host; distribuido centraliza politica de red en multiples hosts.

P: Para que sirve vMotion?
R: Migrar una VM en ejecucion entre hosts con minima o nula parada.

P: Para que sirve HA en un cluster?
R: Reiniciar VMs en otros hosts tras fallo de un host.

P: Para que sirve DRS?
R: Balancear cargas entre hosts segun recursos y politicas.

P: Que son reservas, limites y shares?
R: Mecanismos de asignacion/prioridad de recursos para VMs.

P: Que es snapshot de VM?
R: Estado puntual de discos/configuracion para pruebas o cambios controlados.

P: Por que snapshot no equivale a backup?
R: Porque no sustituye copia independiente ni estrategia de recuperacion completa.

P: Que rol tienen PowerCLI y API?
R: Automatizar tareas de operacion y gobierno de plataforma VMware.

---

## Tarjetas de repaso transversal (4.3)

P: Mapa mental minimo de VMware?
R: Hosts ESXi + vCenter + cluster + compute/red/storage + operacion/seguridad.

P: Error tipico en examen?
R: Confundir funciones de HA y DRS o creer que vMotion es mecanismo de backup.

P: Objetivo final de VMware en empresa?
R: Gestion centralizada, alta disponibilidad y operacion escalable de cargas virtuales.
