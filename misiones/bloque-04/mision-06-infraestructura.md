# BLOQUE 4 - MISIÓN INTEGRADORA

> **Bloque:** 4 - Infraestructura\
> **Capítulos:** 4.1 CPD · 4.2 Virtualización · 4.3 VMware · 4.4 RAID ·
> 4.5 NAS · 4.6 SAN\
> **Tipo:** Misión práctica integradora\
> **Nivel:** ⭐⭐⭐⭐⭐\
> **Objetivo:** Aplicar conjuntamente los conocimientos del Bloque 4 en
> un escenario de infraestructura realista.\
> **Importante:** Esta misión **no incluye las soluciones**. Se
> entregarán en un documento independiente.

------------------------------------------------------------------------

# 🏢 1. CONTEXTO

Has sido incorporado al equipo de infraestructura de una organización
pública de tamaño medio.

La organización dispone actualmente de un pequeño CPD con servidores
físicos, almacenamiento local y algunos recursos de red.

El crecimiento de los servicios ha provocado:

-   Aumento del número de máquinas virtuales.
-   Problemas de capacidad.
-   Falta de redundancia.
-   Dificultad para realizar mantenimiento.
-   Riesgo ante fallos de discos.
-   Ausencia de una estrategia clara de almacenamiento compartido.
-   Backups poco estructurados.
-   Falta de documentación.
-   Ausencia de un plan formal de recuperación ante desastre.

La dirección ha aprobado un proyecto de renovación de infraestructura.

Tu misión será diseñar una propuesta completa que cubra:

``` text
CPD
↓
Virtualización
↓
VMware
↓
RAID
↓
NAS
↓
SAN
↓
Backup / Replicación / DR
```

No tendrás que realizar una implementación real.

Deberás **tomar decisiones técnicas, justificarlas y detectar
problemas**.

------------------------------------------------------------------------

# 🎯 2. OBJETIVOS DE LA MISIÓN

Al finalizar deberías ser capaz de:

``` text
✓ Diseñar una infraestructura básica de CPD.

✓ Identificar necesidades de climatización, energía y seguridad.

✓ Diseñar una plataforma de virtualización.

✓ Justificar el uso de VMware.

✓ Diseñar almacenamiento RAID.

✓ Diferenciar almacenamiento local, NAS y SAN.

✓ Diseñar una SAN redundante.

✓ Configurar conceptualmente LUNs.

✓ Aplicar zoning y LUN masking.

✓ Diseñar multipath.

✓ Definir almacenamiento para VMware.

✓ Diseñar NAS para archivos y backups.

✓ Definir una estrategia de backup.

✓ Diferenciar backup, snapshot y replicación.

✓ Definir RPO y RTO.

✓ Identificar SPOF.

✓ Detectar problemas de rendimiento.

✓ Analizar problemas de capacidad.

✓ Diseñar una estrategia de recuperación.

✓ Justificar cada decisión técnica.
```

------------------------------------------------------------------------

# 🗺️ 3. ESCENARIO INICIAL

La organización dispone actualmente del siguiente CPD.

``` text
┌─────────────────────────────────────────────┐
│                    CPD                      │
│                                             │
│  2 servidores físicos                       │
│  1 switch Ethernet                          │
│  1 cabina de almacenamiento                 │
│  1 NAS                                      │
│  1 UPS                                      │
│                                             │
└─────────────────────────────────────────────┘
```

------------------------------------------------------------------------

# 🖥️ 4. SERVIDORES ACTUALES

Existen dos servidores:

## Servidor 1

``` text
CPU:
2 × 12 cores

RAM:
128 GB

Discos:
4 × 1.92 TB SSD

NIC:
4 × 10 GbE
```

------------------------------------------------------------------------

## Servidor 2

``` text
CPU:
2 × 12 cores

RAM:
128 GB

Discos:
4 × 1.92 TB SSD

NIC:
4 × 10 GbE
```

------------------------------------------------------------------------

# 💾 5. ALMACENAMIENTO ACTUAL

La organización dispone de una cabina con:

``` text
12 × 4 TB HDD
4 × 1.92 TB SSD
```

La cabina tiene:

``` text
2 controladoras
```

pero actualmente:

``` text
Solo una controladora está configurada para las LUN principales.
```

------------------------------------------------------------------------

# 🌐 6. RED ACTUAL

Existe:

``` text
1 switch Ethernet
```

con:

``` text
48 × 1 GbE
8 × 10 GbE
```

------------------------------------------------------------------------

# 📦 7. NAS ACTUAL

El NAS dispone de:

``` text
8 × 8 TB HDD
```

y se utiliza para:

``` text
Documentos
Backups
Compartición de archivos
```

Actualmente:

``` text
No existe una política formal de snapshots.
```

------------------------------------------------------------------------

# ⚡ 8. ENERGÍA

El CPD dispone de:

``` text
1 UPS
```

La UPS tiene capacidad suficiente para mantener los equipos durante:

``` text
15 minutos
```

pero:

``` text
No existe una segunda UPS.
```

------------------------------------------------------------------------

# 🌡️ 9. CLIMATIZACIÓN

La sala utiliza:

``` text
Aire acondicionado convencional.
```

No existe:

``` text
Monitorización específica de temperatura
```

ni:

``` text
Redundancia de climatización.
```

------------------------------------------------------------------------

# 🔥 10. SEGURIDAD FÍSICA

La sala dispone de:

``` text
Puerta con cerradura electrónica.
```

No dispone de:

``` text
Control de acceso biométrico
Sistema de detección de fugas
Monitorización ambiental
```

Existe:

``` text
Extintor convencional.
```

------------------------------------------------------------------------

# 👥 11. CARGAS ACTUALES

Actualmente se ejecutan:

``` text
AD01
WEB01
APP01
DB01
FILE01
MON01
BACKUP01
```

Características:

  VM         Función              RAM      CPU Prioridad
  ---------- ---------------- ------- -------- -----------
  AD01       Directorio          4 GB   2 vCPU Alta
  WEB01      Web                 8 GB   4 vCPU Alta
  APP01      Aplicación         16 GB   6 vCPU Alta
  DB01       Base de datos      32 GB   8 vCPU Crítica
  FILE01     Archivos           16 GB   4 vCPU Media
  MON01      Monitorización      8 GB   2 vCPU Media
  BACKUP01   Backup             16 GB   4 vCPU Alta

------------------------------------------------------------------------

# 📈 12. CRECIMIENTO PREVISTO

Se espera:

``` text
+8 VMs
```

durante los próximos:

``` text
3 años
```

Además:

``` text
+30% de crecimiento de datos anual.
```

------------------------------------------------------------------------

# 🚨 13. PROBLEMAS DETECTADOS

El equipo ha identificado:

### Problema 1

Si falla:

``` text
Switch Ethernet
```

se pierde gran parte de la conectividad.

------------------------------------------------------------------------

### Problema 2

Si falla:

``` text
Servidor 1
```

el número de recursos disponibles disminuye considerablemente.

------------------------------------------------------------------------

### Problema 3

Si falla:

``` text
La controladora principal
```

algunas LUN dejan de estar disponibles.

------------------------------------------------------------------------

### Problema 4

No existe:

``` text
Dual Fabric
```

------------------------------------------------------------------------

### Problema 5

No existe:

``` text
Multipath correctamente diseñado.
```

------------------------------------------------------------------------

### Problema 6

El NAS y la cabina comparten determinados recursos de red.

------------------------------------------------------------------------

### Problema 7

Los backups se almacenan principalmente:

``` text
En el mismo CPD.
```

------------------------------------------------------------------------

### Problema 8

No existe:

``` text
Site de contingencia.
```

------------------------------------------------------------------------

# 🧭 14. FASE 1 - CPD

## Misión 1

Analiza la infraestructura física actual.

Identifica al menos:

``` text
5 problemas
```

relacionados con:

``` text
Energía
Climatización
Seguridad
Redundancia
Monitorización
```

------------------------------------------------------------------------

## Misión 2

Propón mejoras para:

### Energía

Debes indicar:

``` text
Número de UPS
Redundancia
Distribución eléctrica
```

------------------------------------------------------------------------

### Climatización

Debes indicar:

``` text
Monitorización
Redundancia
Distribución
```

------------------------------------------------------------------------

### Seguridad

Debes indicar:

``` text
Control de acceso
Detección
Protección física
```

------------------------------------------------------------------------

## Misión 3

Explica qué componentes deberían considerarse:

``` text
SPOF
```

en el CPD.

------------------------------------------------------------------------

# 🧭 15. FASE 2 - VIRTUALIZACIÓN

La organización quiere virtualizar completamente las cargas.

## Misión 4

Explica:

``` text
¿Qué ventajas aporta la virtualización en este escenario?
```

Debes mencionar al menos:

``` text
5 ventajas.
```

------------------------------------------------------------------------

## Misión 5

Propón una arquitectura de hosts.

Actualmente:

``` text
2 hosts
```

Decide si:

``` text
2
3
4
```

hosts serían adecuados.

Justifica la decisión.

------------------------------------------------------------------------

# 🧮 16. FASE 3 - CAPACIDAD DE COMPUTACIÓN

Calcula aproximadamente los recursos actuales.

## CPU

Suma las vCPU:

``` text
AD01 = 2
WEB01 = 4
APP01 = 6
DB01 = 8
FILE01 = 4
MON01 = 2
BACKUP01 = 4
```

### Pregunta

¿Cuántas vCPU existen actualmente?

------------------------------------------------------------------------

## RAM

Suma:

``` text
4
8
16
32
16
8
16
```

### Pregunta

¿Cuánta RAM virtual está asignada actualmente?

------------------------------------------------------------------------

# 🧮 17. CRECIMIENTO

Se esperan:

``` text
+8 VMs
```

Supón para el cálculo:

``` text
4 vCPU / VM
8 GB RAM / VM
```

### Pregunta

¿Cuánta capacidad adicional deberías reservar aproximadamente?

------------------------------------------------------------------------

# ⚠️ 18. SOBREASIGNACIÓN

Supón que decides utilizar:

``` text
CPU overcommit
```

Responde:

``` text
¿Qué riesgos introduce?
```

Y:

``` text
¿Por qué no deberíamos utilizar overcommit sin analizar las cargas?
```

------------------------------------------------------------------------

# 🧭 19. FASE 4 - VMWARE

Se utilizará VMware como plataforma de virtualización.

## Misión 6

Diseña conceptualmente:

``` text
Cluster
Hosts
Datastores
Networking
Storage
```

------------------------------------------------------------------------

# 🖥️ 20. CLUSTER

Explica:

``` text
¿Qué ventajas proporciona agrupar los hosts en un cluster?
```

Incluye:

``` text
HA
vMotion
DRS
```

cuando sean aplicables.

------------------------------------------------------------------------

# 💾 21. DATASTORES

Debes decidir si utilizarías:

``` text
Un único datastore
```

o:

``` text
Varios datastores
```

Justifica.

------------------------------------------------------------------------

# 🧩 22. DISEÑO DE DATASTORES

Propón una estructura semejante a:

``` text
Datastore-01
Datastore-02
Datastore-03
```

e indica:

``` text
Qué cargas colocarías en cada uno.
```

------------------------------------------------------------------------

# 🚦 23. PRIORIDADES

La base de datos:

``` text
DB01
```

es crítica.

Explica cómo garantizarías que tenga:

``` text
Storage performance
Availability
Redundancy
```

------------------------------------------------------------------------

# 🧭 24. FASE 5 - RAID

La cabina dispone de:

``` text
12 × 4 TB HDD
4 × 1.92 TB SSD
```

Debes diseñar una propuesta RAID.

------------------------------------------------------------------------

# 🧩 25. RAID PARA SSD

Decide qué RAID utilizarías para:

``` text
4 × 1.92 TB SSD
```

Opciones:

``` text
RAID 1
RAID 5
RAID 6
RAID 10
```

Justifica:

``` text
Rendimiento
Redundancia
Capacidad
```

------------------------------------------------------------------------

# 🧩 26. RAID PARA HDD

Decide qué RAID utilizarías para:

``` text
12 × 4 TB HDD
```

Justifica.

------------------------------------------------------------------------

# 🧮 27. CAPACIDAD RAID

Calcula aproximadamente la capacidad útil de las configuraciones que
hayas elegido.

Indica:

``` text
Capacidad bruta
Capacidad útil aproximada
Capacidad sacrificada para redundancia
```

------------------------------------------------------------------------

# ⚠️ 28. RAID Y BACKUP

Explica:

``` text
¿Por qué tu RAID no sustituye al backup?
```

------------------------------------------------------------------------

# 🧭 29. FASE 6 - STORAGE POOLS

Diseña conceptualmente:

``` text
Pool SSD
Pool HDD
```

o una alternativa que consideres mejor.

Indica:

``` text
Qué workloads utilizarían cada pool.
```

------------------------------------------------------------------------

# 🔥 30. STORAGE TIERS

Clasifica:

``` text
DB01
WEB01
FILE01
BACKUP01
```

como:

``` text
Hot
Warm
Cold
```

o propón una clasificación equivalente.

Justifica.

------------------------------------------------------------------------

# 🧭 31. FASE 7 - SAN

La organización decide implementar Fibre Channel.

El diseño dispone de:

``` text
2 HBA por host
2 FC switches
2 controladoras de almacenamiento
```

------------------------------------------------------------------------

# 🏗️ 32. DISEÑO FC

Dibuja mediante ASCII una arquitectura:

``` text
Host
↓
HBA
↓
Fabric
↓
Storage
```

que elimine los principales SPOF.

------------------------------------------------------------------------

# 🧩 33. WWPN

Cada HBA tiene un:

``` text
WWPN
```

Explica:

``` text
¿Para qué utilizarías esos WWPN?
```

------------------------------------------------------------------------

# 🧩 34. ZONING

Diseña conceptualmente las zonas necesarias.

Supón:

``` text
ESXi01
HBA-A
HBA-B

ESXi02
HBA-A
HBA-B

ESXi03
HBA-A
HBA-B
```

y:

``` text
Storage Controller A
Port A
Port B

Storage Controller B
Port A
Port B
```

No necesitas inventar WWPN reales.

Utiliza nombres como:

``` text
ESXi01_HBA_A
STORAGE_A_PORT_1
```

------------------------------------------------------------------------

# 🧠 35. ZONING

Explica:

``` text
¿Por qué no permitirías que todos los hosts vieran todos los puertos sin restricciones?
```

------------------------------------------------------------------------

# 🧩 36. LUN MASKING

Después del zoning:

``` text
ESXi01
ESXi02
ESXi03
```

deben acceder a:

``` text
LUN 10
LUN 20
```

pero:

``` text
LUN 30
```

solo debe estar disponible para:

``` text
ESXi01
```

Explica cómo resolverías esto mediante:

``` text
LUN masking / mapping.
```

------------------------------------------------------------------------

# 🧭 37. FASE 8 - MULTIPATH

Cada host dispone de:

``` text
HBA A
HBA B
```

y cada uno conecta con un fabric diferente.

## Misión 7

Explica qué ocurre si:

``` text
HBA A
```

falla.

------------------------------------------------------------------------

## Misión 8

Explica qué ocurre si:

``` text
Fabric A
```

falla.

------------------------------------------------------------------------

## Misión 9

Explica qué ocurre si:

``` text
Controller A
```

falla.

------------------------------------------------------------------------

# 🧠 38. ALUA

La cabina utiliza ALUA.

Explica:

``` text
¿Qué diferencia existe entre una ruta Active/Optimized y una Active/Non-Optimized?
```

------------------------------------------------------------------------

# 🧭 39. FASE 9 - iSCSI

Aunque el diseño principal utilizará Fibre Channel, la organización
mantiene un NAS con soporte iSCSI.

## Misión 10

Explica:

``` text
¿Cómo configurarías conceptualmente un servidor para utilizar iSCSI?
```

Debes mencionar:

``` text
Initiator
Target
IQN
Discovery
TCP 3260
Login
Session
LUN
Multipath
```

------------------------------------------------------------------------

# 🧩 40. CHAP

Explica:

``` text
¿Qué función tendría CHAP?
```

Y:

``` text
¿Es lo mismo autenticación que cifrado?
```

------------------------------------------------------------------------

# 🧭 41. FASE 10 - NAS

El NAS actual tiene:

``` text
8 × 8 TB HDD
```

Se utilizará para:

``` text
Documentos
Backups
```

------------------------------------------------------------------------

# 🧩 42. RAID DEL NAS

Propón un RAID para el NAS.

Justifica:

``` text
Capacidad
Redundancia
Rendimiento
```

------------------------------------------------------------------------

# 🧩 43. NAS vs SAN

Explica qué cargas colocarías preferentemente en:

``` text
SAN
```

y cuáles en:

``` text
NAS
```

------------------------------------------------------------------------

# 🧭 44. FASE 11 - BACKUP

La organización actualmente guarda los backups en el mismo CPD.

Debes diseñar una política nueva.

------------------------------------------------------------------------

# 🧩 45. REGLA 3-2-1

Explica cómo aplicarías:

``` text
3-2-1
```

al escenario.

------------------------------------------------------------------------

# 🧩 46. SNAPSHOTS

El equipo propone:

> "Como tenemos snapshots, ya no necesitamos backup."

¿Estás de acuerdo?

Justifica.

------------------------------------------------------------------------

# 🧩 47. REPLICACIÓN

La organización plantea:

> "Podemos replicar la cabina al NAS y así tendremos backup."

Analiza la afirmación.

------------------------------------------------------------------------

# 🧭 48. FASE 12 - RPO Y RTO

La dirección establece:

``` text
Base de datos:
RPO ≤ 15 minutos
RTO ≤ 1 hora

Servicios web:
RPO ≤ 1 hora
RTO ≤ 2 horas

Documentos:
RPO ≤ 24 horas
RTO ≤ 8 horas
```

------------------------------------------------------------------------

# 🧩 49. DISEÑO

Para cada servicio indica:

``` text
Backup
Snapshot
Replication
DR
```

y justifica qué mecanismos utilizarías.

------------------------------------------------------------------------

# 🧭 50. FASE 13 - DISASTER RECOVERY

Se dispone de una segunda ubicación a:

``` text
80 km
```

del CPD principal.

La conexión entre ambos centros es:

``` text
10 Gb/s
```

------------------------------------------------------------------------

# 🧩 51. DISEÑO DR

Propón una arquitectura:

``` text
CPD PRINCIPAL
      │
      │
      ▼
  REPLICACIÓN
      │
      ▼
CPD SECUNDARIO
```

Indica:

``` text
Qué replicarías
Qué respaldarías
Qué servicios arrancarían primero
```

------------------------------------------------------------------------

# 🚨 52. DESASTRE

A las:

``` text
02:15
```

se produce un incendio en el CPD principal.

Se pierde:

``` text
Hosts
SAN
NAS
Switches
```

El CPD secundario sigue operativo.

------------------------------------------------------------------------

# 🧩 53. MISIÓN DE RECUPERACIÓN

Describe paso a paso:

``` text
Qué harías primero
Qué servicios recuperarías
Cómo recuperarías las VMs
Cómo recuperarías los datos
Cómo validarías el servicio
```

------------------------------------------------------------------------

# 🧭 54. FASE 14 - INCIDENTE DE ALMACENAMIENTO

Ahora vuelve a la situación normal.

Una mañana:

``` text
DB01
```

empieza a presentar:

``` text
Latencia elevada
```

------------------------------------------------------------------------

# 📊 55. MÉTRICAS

El equipo obtiene:

``` text
CPU VM:
35%

RAM:
55%

Network:
normal

Storage latency:
28 ms

IOPS:
muy altas

Throughput:
moderado
```

------------------------------------------------------------------------

# 🧩 56. DIAGNÓSTICO

Propón al menos:

``` text
8 comprobaciones
```

que realizarías.

------------------------------------------------------------------------

# 🧭 57. INCIDENTE 2

Un administrador informa:

> "ESXi01 ya no ve la LUN 20."

Pero:

``` text
ESXi02 → LUN 20 visible
ESXi03 → LUN 20 visible
```

------------------------------------------------------------------------

# 🧩 58. DIAGNÓSTICO

Explica qué revisarías específicamente en:

``` text
ESXi01
HBA
Fabric
Zoning
LUN masking
Multipath
Rescan
```

------------------------------------------------------------------------

# 🧭 59. INCIDENTE 3

Aparece:

``` text
Path A → DOWN
Path B → UP
```

Las máquinas siguen funcionando.

------------------------------------------------------------------------

# 🧩 60. PREGUNTA

¿Consideras que:

``` text
"El problema no es importante porque las VMs siguen funcionando."
```

?

Justifica.

------------------------------------------------------------------------

# 🧭 61. INCIDENTE 4

El pool thin tiene:

``` text
100 TB provisionados
```

pero:

``` text
95 TB físicos utilizados
```

El departamento solicita:

``` text
+20 TB
```

de nuevas LUN.

------------------------------------------------------------------------

# 🧩 62. DECISIÓN

¿Aceptarías inmediatamente la solicitud?

Explica:

``` text
Riesgos
Capacidad
Monitorización
Alternativas
```

------------------------------------------------------------------------

# 🧭 63. INCIDENTE 5 - FIRMWARE

El fabricante publica:

``` text
Firmware v12.0
```

El administrador quiere instalarlo inmediatamente.

------------------------------------------------------------------------

# 🧩 64. DECISIÓN

¿Qué comprobarías antes?

Menciona:

``` text
Compatibility Matrix
HBA
Switch
Storage
Drivers
ESXi
Rollback
Maintenance window
Backup configuration
```

------------------------------------------------------------------------

# 🧭 65. FASE 15 - DISEÑO FINAL

Ahora debes crear tu propuesta definitiva.

Diseña una arquitectura completa.

Debe incluir:

``` text
CPD
Hosts
VMware
Networking
FC Fabric
Storage
RAID
Pools
LUNs
Datastores
NAS
Backup
Replication
DR
Monitoring
```

------------------------------------------------------------------------

# 🖼️ 66. DIAGRAMA FINAL

Realiza un diagrama ASCII similar a:

``` text
                         INTERNET
                            │
                         FIREWALL
                            │
                       CORE NETWORK
                       /           \
                      /             \
                SWITCH A          SWITCH B
                    │                 │
              ┌─────┴─────┐     ┌────┴─────┐
              │           │     │          │
           ESXi01      ESXi02  ESXi01   ESXi02
              │           │     │          │
             HBA         HBA   HBA        HBA
               \           /     \          /
                \         /       \        /
                 FABRIC A          FABRIC B
                      \             /
                       \           /
                       STORAGE ARRAY
                    ┌──────┴──────┐
                 Controller A  Controller B
                       │             │
                       └──────┬──────┘
                              │
                         STORAGE POOLS
                         /            \
                      SSD             HDD
                       │               │
                     LUNs            LUNs
                       │               │
                    VMFS            Backup
                       │
                   DATASTORES
                       │
                      VMs

                         +
                         │
                        NAS
                         │
                     BACKUPS
                         │
                         ▼
                   CPD SECUNDARIO
```

Puedes modificarlo completamente.

------------------------------------------------------------------------

# 🧠 67. JUSTIFICACIÓN GLOBAL

No basta con dibujar.

Debes explicar:

### CPD

¿Por qué has elegido:

``` text
UPS
Climatización
Seguridad
Monitorización
```

------------------------------------------------------------------------

### Virtualización

¿Por qué:

``` text
Número de hosts
Cluster
HA
vMotion
DRS
```

------------------------------------------------------------------------

### VMware

¿Por qué:

``` text
Datastores
VMFS
Multipath
VAAI
SIOC
```

------------------------------------------------------------------------

### RAID

¿Por qué:

``` text
RAID elegido
```

para cada tipo de disco.

------------------------------------------------------------------------

### NAS

¿Por qué:

``` text
NAS
```

para determinadas cargas.

------------------------------------------------------------------------

### SAN

¿Por qué:

``` text
FC
Dual Fabric
Zoning
LUN Masking
Multipath
ALUA
```

------------------------------------------------------------------------

### Backup

¿Por qué:

``` text
Backup
Snapshot
Replication
DR
```

------------------------------------------------------------------------

# 🧭 68. FASE 16 - PREGUNTAS DE ARQUITECTURA

Responde brevemente.

## 1

¿Por qué no utilizarías el NAS como almacenamiento principal de todas
las VMs si dispones de una SAN?

------------------------------------------------------------------------

## 2

¿Por qué no utilizarías RAID 0 para una base de datos crítica?

------------------------------------------------------------------------

## 3

¿Por qué dos controladoras son mejores que una?

------------------------------------------------------------------------

## 4

¿Por qué dos HBAs conectadas al mismo switch no proporcionan una
redundancia completa?

------------------------------------------------------------------------

## 5

¿Por qué separarías management y storage traffic?

------------------------------------------------------------------------

## 6

¿Por qué monitorizarías la capacidad física de un pool thin?

------------------------------------------------------------------------

## 7

¿Por qué una snapshot no sustituye al backup?

------------------------------------------------------------------------

## 8

¿Por qué replication no sustituye necesariamente al backup?

------------------------------------------------------------------------

## 9

¿Por qué necesitas probar el DR?

------------------------------------------------------------------------

## 10

¿Por qué un firmware nuevo no debe instalarse automáticamente?

------------------------------------------------------------------------

# 🧭 69. FASE 17 - PREGUNTAS DE CONCEPTOS

Define con tus propias palabras:

``` text
SAN
NAS
LUN
HBA
WWPN
WWNN
FCID
Fabric
Zoning
LUN Masking
FLOGI
PLOGI
IQN
CHAP
Multipath
ALUA
VMFS
Datastore
NAA
VAAI
SIOC
Storage Pool
Thin Provisioning
Snapshot
Replication
Backup
RPO
RTO
IOPS
Throughput
Latency
SPOF
```

------------------------------------------------------------------------

# 🧭 70. FASE 18 - VERDADERO O FALSO

Indica:

``` text
V
```

o:

``` text
F
```

y justifica las falsas.

------------------------------------------------------------------------

### 1

Una SAN proporciona normalmente almacenamiento a nivel de archivo.

------------------------------------------------------------------------

### 2

Una LUN es una unidad lógica de almacenamiento.

------------------------------------------------------------------------

### 3

WWPN identifica un puerto Fibre Channel.

------------------------------------------------------------------------

### 4

WWNN identifica un puerto Ethernet.

------------------------------------------------------------------------

### 5

F_Port conecta un dispositivo final al switch FC.

------------------------------------------------------------------------

### 6

E_Port se utiliza para interconectar switches FC.

------------------------------------------------------------------------

### 7

Zoning y LUN masking son exactamente lo mismo.

------------------------------------------------------------------------

### 8

FLOGI significa Fabric Login.

------------------------------------------------------------------------

### 9

PLOGI significa Port Login.

------------------------------------------------------------------------

### 10

iSCSI utiliza TCP/IP.

------------------------------------------------------------------------

### 11

El puerto habitual de iSCSI es TCP 3260.

------------------------------------------------------------------------

### 12

CHAP proporciona autenticación.

------------------------------------------------------------------------

### 13

Multipath implica necesariamente dos switches independientes.

------------------------------------------------------------------------

### 14

ALUA permite distinguir caminos optimizados y no optimizados.

------------------------------------------------------------------------

### 15

VMFS es un filesystem utilizado por VMware.

------------------------------------------------------------------------

### 16

VAAI puede descargar determinadas operaciones hacia la cabina.

------------------------------------------------------------------------

### 17

Una snapshot es equivalente a un backup externo.

------------------------------------------------------------------------

### 18

RPO mide el tiempo máximo de recuperación.

------------------------------------------------------------------------

### 19

RTO está relacionado con el tiempo de recuperación.

------------------------------------------------------------------------

### 20

IOPS y throughput son exactamente la misma métrica.

------------------------------------------------------------------------

### 21

Un pool thin puede sobreasignarse lógicamente.

------------------------------------------------------------------------

### 22

RAID sustituye a la estrategia de backup.

------------------------------------------------------------------------

### 23

Dos caminos pueden compartir un SPOF.

------------------------------------------------------------------------

### 24

Un DR completo incluye procedimientos y pruebas.

------------------------------------------------------------------------

### 25

La última versión de firmware siempre es automáticamente compatible.

------------------------------------------------------------------------

# 🧭 71. FASE 19 - PREGUNTAS DE DIAGNÓSTICO

## Caso A

``` text
Host:
ESXi01

LUN:
Invisible

Other hosts:
LUN visible
```

¿Cuál es tu procedimiento?

------------------------------------------------------------------------

## Caso B

``` text
All hosts
↓
Storage latency high
```

¿Dónde buscarías?

------------------------------------------------------------------------

## Caso C

``` text
One path down
```

¿Qué comprobarías?

------------------------------------------------------------------------

## Caso D

``` text
Pool 92%
```

¿Qué riesgos existen?

------------------------------------------------------------------------

## Caso E

``` text
Storage controller failed
```

¿Qué debería ocurrir en una arquitectura redundante?

------------------------------------------------------------------------

## Caso F

``` text
Switch A failed
```

¿Qué debería ocurrir si el diseño es correcto?

------------------------------------------------------------------------

## Caso G

``` text
Site A destroyed
```

¿Qué mecanismos deberían permitir recuperar el servicio?

------------------------------------------------------------------------

# 🧭 72. FASE 20 - GRAN PREGUNTA FINAL

Imagina que debes presentar el proyecto ante la dirección.

Dispones de:

``` text
10 minutos.
```

Explica verbalmente:

> **"Cómo diseñaría una infraestructura virtualizada, redundante y
> recuperable para esta organización."**

Debes cubrir:

``` text
1. CPD
2. Hosts
3. VMware
4. Storage
5. RAID
6. SAN
7. NAS
8. Backup
9. Replication
10. DR
```

No leas tus apuntes.

Intenta explicarlo como si realmente fueras el responsable de
infraestructura.

------------------------------------------------------------------------

# 🧪 73. RETO EXTRA

Si quieres llevar la misión a nivel:

``` text
⭐⭐⭐⭐⭐⭐
```

añade:

### Reto A

Calcula aproximadamente:

``` text
Capacidad útil RAID
```

para tus diseños.

------------------------------------------------------------------------

### Reto B

Calcula:

``` text
Capacidad necesaria a 3 años
```

considerando:

``` text
30% crecimiento anual
```

------------------------------------------------------------------------

### Reto C

Propón:

``` text
Número de datastores
```

y capacidad de cada uno.

------------------------------------------------------------------------

### Reto D

Diseña:

``` text
Zoning completo
```

para:

``` text
3 hosts
2 fabrics
2 storage controllers
```

------------------------------------------------------------------------

### Reto E

Diseña:

``` text
Matriz Host → LUN
```

------------------------------------------------------------------------

### Reto F

Diseña:

``` text
Matriz de caminos
```

por ejemplo:

  Host     HBA     Fabric   Storage Port    LUN
  -------- ------- -------- --------------- -------
  ESXi01   HBA-A   A        Ctrl-A Port-1   LUN10
  ESXi01   HBA-B   B        Ctrl-B Port-1   LUN10
  ESXi02   HBA-A   A        Ctrl-A Port-1   LUN10
  ESXi02   HBA-B   B        Ctrl-B Port-1   LUN10

Amplíala para todos los hosts.

------------------------------------------------------------------------

# 🧠 74. REGLA DE LA MISIÓN

No busques:

``` text
"La respuesta perfecta."
```

Busca:

``` text
Una arquitectura coherente.
```

En infraestructura normalmente existen varias soluciones válidas.

Lo importante es que puedas explicar:

``` text
Qué haces
Por qué lo haces
Qué problema resuelve
Qué riesgo introduce
Cómo lo monitorizas
Qué ocurre si falla
```

------------------------------------------------------------------------

# 🏆 75. CRITERIOS DE AUTOEVALUACIÓN

Cuando termines, puntúate:

## CPD

``` text
0 → No sé por dónde empezar
1 → Identifico algunos problemas
2 → Propongo mejoras coherentes
3 → Puedo diseñar una infraestructura básica
```

------------------------------------------------------------------------

## Virtualización

``` text
0 → No entiendo el diseño
1 → Entiendo hosts y VMs
2 → Entiendo clusters y HA
3 → Puedo diseñar una plataforma
```

------------------------------------------------------------------------

## VMware

``` text
0 → No sé relacionar datastore y VM
1 → Entiendo VMFS
2 → Entiendo HA/vMotion/storage
3 → Puedo diseñar un entorno VMware
```

------------------------------------------------------------------------

## RAID

``` text
0 → No sé elegir
1 → Conozco RAID básicos
2 → Puedo justificar una elección
3 → Puedo calcular capacidad
```

------------------------------------------------------------------------

## NAS

``` text
0 → Confundo NAS y SAN
1 → Entiendo file storage
2 → Sé cuándo utilizar NAS
3 → Puedo integrarlo en una arquitectura
```

------------------------------------------------------------------------

## SAN

``` text
0 → Las siglas me destruyen
1 → Reconozco conceptos
2 → Entiendo el flujo completo
3 → Puedo diseñar una SAN redundante
```

------------------------------------------------------------------------

## Backup / DR

``` text
0 → Todo me parece lo mismo
1 → Distingo backup y replication
2 → Entiendo RPO/RTO
3 → Puedo diseñar un DR
```

------------------------------------------------------------------------

# 🎯 76. PUNTUACIÓN FINAL

Puedes utilizar:

``` text
CPD:             /3
Virtualización:  /3
VMware:           /3
RAID:             /3
NAS:              /3
SAN:              /3
Backup/DR:        /3
────────────────────
TOTAL:            /21
```

Interpretación:

``` text
0-7
→ Necesitas repaso importante.

8-12
→ Base razonable.

13-16
→ Buen dominio.

17-19
→ Muy buen dominio.

20-21
→ Nivel excelente.
```

------------------------------------------------------------------------

# 🛑 77. IMPORTANTE: NO MIRES LAS SOLUCIONES TODAVÍA

Cuando termines la misión:

``` text
GUARDA TU RESPUESTA
```

antes de consultar las soluciones.

La misión está diseñada para que algunas decisiones sean deliberadamente
discutibles.

No buscamos:

``` text
"Copiar la respuesta."
```

Buscamos:

``` text
Pensar como administrador de infraestructura.
```

------------------------------------------------------------------------

# 🏁 FIN DE LA MISIÓN

Has recibido un escenario que integra:

``` text
4.1 CPD
      ↓
4.2 Virtualización
      ↓
4.3 VMware
      ↓
4.4 RAID
      ↓
4.5 NAS
      ↓
4.6 SAN
      ↓
Backup
      ↓
Replication
      ↓
Disaster Recovery
```

La misión no termina cuando el diagrama funciona.

Termina cuando puedes responder:

> **¿Qué ocurre si falla cada pieza?**

Porque esa es, en esencia, una de las ideas centrales de todo el Bloque
4:

``` text
                 DISEÑO
                   │
          ┌────────┴────────┐
          │                 │
      FUNCIONA           FALLA
          │                 │
          ▼                 ▼
     OPERACIÓN          RECUPERACIÓN
          │                 │
          └────────┬────────┘
                   │
              DISPONIBILIDAD
```

------------------------------------------------------------------------

# 🧠 FRASE FINAL

> **Una buena infraestructura no es aquella que funciona cuando todo
> funciona. Es aquella cuyo diseño ya ha previsto qué hacer cuando algo
> deje de funcionar.**

**Misión del Bloque 4 - COMPLETA.**
