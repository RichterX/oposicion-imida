# Tarjetas - Bloque 04 - 4.2 Virtualizacion

Formato:
P: Pregunta
R: Respuesta

---

## 4.2 Virtualizacion

P: Que es virtualizacion?
R: Tecnica para crear recursos virtuales sobre hardware fisico mediante una capa de abstraccion.

P: Que problema resuelve la virtualizacion clasica?
R: La infrautilizacion de servidores fisicos y el exceso de coste operativo.

P: Que es consolidacion de servidores?
R: Ejecutar varias VMs en menos hosts fisicos para mejorar eficiencia.

P: Que es una VM?
R: Un ordenador definido por software con vCPU, vRAM, disco virtual y red virtual.

P: Que es un hipervisor?
R: Software que crea y ejecuta VMs gestionando recursos del host.

P: Diferencia entre hipervisor tipo 1 y tipo 2?
R: Tipo 1 corre sobre hardware (bare metal); tipo 2 corre sobre un SO anfitrion.

P: Que significa host y guest?
R: Host es el sistema fisico/hipervisor; guest es el SO invitado dentro de la VM.

P: Que ventaja aporta el aislamiento entre VMs?
R: Limita impacto de fallos y separa cargas en el mismo host.

P: Que riesgo introduce la consolidacion?
R: Mayor blast radius si cae un host con muchas VMs.

P: Que es oversubscription?
R: Asignar mas recursos virtuales que fisicos esperando no uso simultaneo total.

P: Que es RBAC en virtualizacion?
R: Control de acceso basado en roles para limitar acciones por perfil.

P: Por que el plano de gestion es critico?
R: Porque permite crear, borrar, migrar y reconfigurar muchas VMs.

P: Diferencia basica entre VMs y contenedores?
R: VM virtualiza hardware y lleva SO invitado; contenedor comparte kernel del host.

P: Que capa suele ser cuello de botella frecuente?
R: Storage y red virtual, ademas de CPU/memoria en picos.

---

## Tarjetas de repaso transversal (4.2)

P: Principio de seguridad clave en plataformas virtualizadas?
R: Proteger hipervisor y management plane con minimo privilegio, parches y auditoria.

P: Regla de troubleshooting util?
R: Diagnosticar por capas: compute, memoria, storage, red y gestion.

P: Objetivo final de virtualizar bien?
R: Eficiencia, flexibilidad y continuidad sin perder control operativo ni seguridad.
