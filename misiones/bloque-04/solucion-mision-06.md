# BLOQUE 4 - SOLUCIONES DE LA MISIÓN INTEGRADORA

> **Bloque:** 4 - Infraestructura\
> **Capítulos:** 4.1 CPD · 4.2 Virtualización · 4.3 VMware · 4.4 RAID ·
> 4.5 NAS · 4.6 SAN\
> **Documento:** Soluciones y corrección orientativa\
> **Objetivo:** Comparar tus decisiones con una arquitectura
> técnicamente coherente.

------------------------------------------------------------------------

# 🧭 Cómo utilizar este documento

Estas soluciones son **orientativas**, no una plantilla de "una única
respuesta correcta".

En infraestructura pueden existir varias soluciones válidas.

La pregunta importante es:

``` text
¿La solución es coherente?
        ↓
¿Está justificada?
        ↓
¿Reduce los riesgos?
        ↓
¿Tiene redundancia?
        ↓
¿Puede monitorizarse?
        ↓
¿Sabemos qué ocurre si falla?
```

Por eso, si tu respuesta es diferente de la propuesta aquí pero está
bien razonada, **no significa automáticamente que esté mal**.

------------------------------------------------------------------------

# 1. FASE 1 - CPD

## Misión 1 - Problemas de la infraestructura física

Se podían identificar, entre otros:

### 1. Una sola UPS

``` text
UPS única
↓
SPOF
```

Si falla la UPS, perdemos la protección eléctrica proporcionada por
ella.

### 2. Climatización no redundante

El aire acondicionado convencional puede convertirse en un punto único
de fallo.

### 3. Falta de monitorización ambiental

No se monitorizan adecuadamente:

``` text
Temperatura
Humedad
Fugas
```

### 4. Un único switch Ethernet

``` text
Switch único
↓
SPOF
```

### 5. Falta de redundancia de conectividad

La infraestructura debería disponer de caminos alternativos.

### 6. Seguridad física incompleta

Existe control de acceso, pero faltan mecanismos como:

``` text
Detección de fugas
Monitorización ambiental
Sistemas adecuados de detección/supresión de incendios
```

### 7. Falta de CPD secundario

Un desastre físico puede afectar a todos los sistemas simultáneamente.

------------------------------------------------------------------------

# 2. Misión 2 - Mejoras del CPD

## Energía

Una arquitectura mejorada podría utilizar:

``` text
UPS A
UPS B
```

con equipos capaces de conectarse a fuentes eléctricas redundantes
cuando sea posible.

Idealmente:

``` text
Fuente A → UPS A
Fuente B → UPS B
```

y:

``` text
Servidor
├── PSU A → Fuente A
└── PSU B → Fuente B
```

No basta con tener dos UPS si ambas dependen del mismo punto eléctrico.

------------------------------------------------------------------------

## Climatización

Se debería incorporar:

``` text
Monitorización de temperatura
Monitorización de humedad
Alertas
```

y, para mayor disponibilidad:

``` text
Climatización redundante
```

------------------------------------------------------------------------

## Seguridad

Mejoras posibles:

``` text
Control de acceso
CCTV
Registro de accesos
Detección de humo/incendio
Detección de fugas de agua
Sensores ambientales
```

La solución exacta depende del CPD y normativa aplicable.

------------------------------------------------------------------------

# 3. Misión 3 - SPOF

Los principales SPOF iniciales son:

``` text
1. Switch Ethernet único
2. UPS única
3. Climatización única
4. Una única controladora efectiva para determinadas LUN
5. Falta de caminos de almacenamiento independientes
6. Un único CPD
```

Además, cualquier componente que comparta una dependencia común puede
convertirse en un SPOF.

------------------------------------------------------------------------

# 4. FASE 2 - VIRTUALIZACIÓN

## Misión 4 - Ventajas

Al menos cinco ventajas válidas:

``` text
1. Consolidación de servidores
2. Mejor utilización de recursos
3. Flexibilidad
4. Provisionamiento rápido
5. Migración de VMs
6. Alta disponibilidad
7. Gestión centralizada
8. Facilidad para recuperación
9. Aislamiento de cargas
10. Simplificación del mantenimiento físico
```

------------------------------------------------------------------------

# 5. Misión 5 - Número de hosts

La respuesta depende de la capacidad y del nivel de disponibilidad
deseado.

Con:

``` text
2 hosts
```

puede existir HA, pero la pérdida de un host supone perder el 50% de la
capacidad física.

Una propuesta razonable sería:

``` text
3 hosts
```

porque permite:

``` text
Host 1
Host 2
Host 3
```

y mantener capacidad suficiente tras un fallo de un host, siempre que el
dimensionamiento lo permita.

Para mayor crecimiento y N+1 más holgado:

``` text
4 hosts
```

también sería una opción razonable.

### Respuesta recomendada

``` text
3 hosts como mínimo razonable
4 hosts si el presupuesto y el crecimiento lo justifican
```

------------------------------------------------------------------------

# 6. FASE 3 - CAPACIDAD DE COMPUTACIÓN

## Misión 6 - vCPU actuales

Tenemos:

``` text
AD01      2
WEB01     4
APP01     6
DB01      8
FILE01    4
MON01     2
BACKUP01  4
```

Por tanto:

``` text
2 + 4 + 6 + 8 + 4 + 2 + 4
= 30 vCPU
```

### Resultado

``` text
30 vCPU
```

------------------------------------------------------------------------

# 7. RAM actual

``` text
4
+ 8
+ 16
+ 32
+ 16
+ 8
+ 16
= 100 GB
```

### Resultado

``` text
100 GB RAM virtual asignada
```

------------------------------------------------------------------------

# 8. Crecimiento previsto

Se esperan:

``` text
8 VMs
```

con:

``` text
4 vCPU / VM
8 GB RAM / VM
```

Por tanto:

### CPU

``` text
8 × 4
= 32 vCPU adicionales
```

### RAM

``` text
8 × 8 GB
= 64 GB adicionales
```

------------------------------------------------------------------------

# 9. Capacidad futura mínima conocida

Actualmente:

``` text
30 vCPU
100 GB RAM
```

Crecimiento:

``` text
+32 vCPU
+64 GB RAM
```

Total:

``` text
62 vCPU
164 GB RAM
```

Esto es antes de considerar:

``` text
Overhead del hipervisor
HA
Reserva
Crecimiento adicional
Picos de carga
```

------------------------------------------------------------------------

# 10. Overcommit de CPU

El overcommit permite asignar más vCPU que cores físicos disponibles.

Puede ser válido dependiendo del workload.

Pero introduce riesgos:

``` text
CPU contention
Ready time
Degradación del rendimiento
```

Especialmente en cargas críticas como:

``` text
DB01
```

No debemos asumir que:

``` text
Más vCPU asignadas
=
Más rendimiento
```

------------------------------------------------------------------------

# 11. FASE 4 - VMWARE

## Diseño conceptual

Una propuesta:

``` text
              VMware Cluster
        ┌────────┼────────┐
        │        │        │
      ESXi01   ESXi02   ESXi03
        │        │        │
        └────┬───┴───┬────┘
             │       │
          Storage   Network
             │
          Datastores
             │
             VMs
```

------------------------------------------------------------------------

# 12. Cluster

El cluster permite utilizar funcionalidades como:

``` text
HA
vMotion
DRS
```

según licencia, configuración y versión.

### HA

Permite reiniciar VMs en otros hosts tras determinados fallos.

### vMotion

Permite migrar VMs en ejecución entre hosts compatibles.

### DRS

Puede ayudar a distribuir cargas entre hosts.

------------------------------------------------------------------------

# 13. Datastores

No recomendaría un único datastore gigante para absolutamente todo.

Es preferible separar según:

``` text
Workload
Performance
Availability
Capacity
Administración
```

Una propuesta posible:

``` text
DS-DB
DS-PROD
DS-GENERAL
DS-INFRA
```

No es obligatorio utilizar exactamente esos nombres.

------------------------------------------------------------------------

# 14. Ejemplo de distribución

``` text
DS-DB
→ DB01

DS-PROD
→ WEB01
→ APP01

DS-INFRA
→ AD01
→ MON01

DS-FILE
→ FILE01
```

El backup puede utilizar almacenamiento específico y no necesariamente
un datastore de producción.

------------------------------------------------------------------------

# 15. DB01

Al ser crítica, DB01 debería tener:

``` text
Storage rápido
Baja latencia
Multipath
Redundancia
Capacidad suficiente
Monitorización
Backup
```

No necesariamente significa que deba utilizar el mismo RAID o pool que
todas las demás VMs.

------------------------------------------------------------------------

# 16. FASE 5 - RAID

La elección debe tener en cuenta:

``` text
Rendimiento
Capacidad
Redundancia
Tipo de disco
Workload
```

------------------------------------------------------------------------

# 17. SSD

Tenemos:

``` text
4 × 1.92 TB SSD
```

Una opción muy razonable para cargas críticas:

``` text
RAID 10
```

### Capacidad bruta

``` text
4 × 1.92
= 7.68 TB
```

### Capacidad útil aproximada RAID 10

``` text
7.68 / 2
= 3.84 TB
```

Ventajas:

``` text
Buen rendimiento
Redundancia
Buen comportamiento de escritura
```

------------------------------------------------------------------------

# 18. ¿Podría utilizarse RAID 5?

Sí, dependiendo del workload y plataforma.

Con cuatro SSD:

``` text
RAID 5
```

tendría aproximadamente:

``` text
(4 - 1) × 1.92
= 5.76 TB
```

pero la elección debe valorar:

``` text
Write workload
Rebuild
Performance
Durabilidad
```

Por tanto, RAID 10 es una propuesta especialmente cómoda para una carga
crítica.

------------------------------------------------------------------------

# 19. HDD

Tenemos:

``` text
12 × 4 TB
```

Capacidad bruta:

``` text
48 TB
```

Una opción razonable:

``` text
RAID 6
```

Capacidad útil aproximada:

``` text
(12 - 2) × 4
= 40 TB
```

Ventaja:

``` text
Tolerancia a dos fallos de disco
```

Puede ser una elección interesante para almacenamiento de capacidad.

------------------------------------------------------------------------

# 20. ¿Podría utilizarse RAID 10 en HDD?

Sí.

Tendríamos aproximadamente:

``` text
48 / 2
= 24 TB
```

con un perfil de rendimiento y redundancia diferente.

La decisión dependería del workload.

------------------------------------------------------------------------

# 21. RAID y backup

RAID proporciona continuidad frente a determinados fallos físicos de
discos.

No protege necesariamente frente a:

``` text
Borrado accidental
Corrupción lógica
Ransomware
Destrucción de la cabina
Incendio
Pérdida del CPD
```

Por eso:

``` text
RAID ≠ Backup
```

------------------------------------------------------------------------

# 22. FASE 6 - STORAGE POOLS

Una propuesta:

``` text
POOL-SSD
    ↓
LUNs de alto rendimiento

POOL-HDD
    ↓
LUNs de capacidad
```

------------------------------------------------------------------------

# 23. Storage Tiering

Una clasificación razonable:

``` text
DB01
→ Hot

WEB01
→ Hot/Warm

FILE01
→ Warm

BACKUP01
→ Capacity-oriented / Warm-Cold
```

Pero la clasificación real debe basarse en:

``` text
IOPS
Latency
Access pattern
Growth
Business priority
```

No solamente en el nombre de la aplicación.

------------------------------------------------------------------------

# 24. FASE 7 - SAN

Una arquitectura correcta debe evitar:

``` text
Host
 ↓
Switch único
 ↓
Storage
```

y utilizar:

``` text
             ESXi
            /    \
         HBA A   HBA B
           |       |
           ▼       ▼
        Fabric A Fabric B
           |       |
           ▼       ▼
        Controller A/B
```

------------------------------------------------------------------------

# 25. Diseño FC recomendado

``` text
                 ESXi01
                /      \
             HBA-A     HBA-B
               |         |
               ▼         ▼
            Fabric A   Fabric B
               |         |
               ▼         ▼
          Controller A Controller B

                 ESXi02
                /      \
             HBA-A     HBA-B
               |         |
               ▼         ▼
            Fabric A   Fabric B

                 ESXi03
                /      \
             HBA-A     HBA-B
               |         |
               ▼         ▼
            Fabric A   Fabric B
```

La idea es:

``` text
HBA A → Fabric A
HBA B → Fabric B
```

------------------------------------------------------------------------

# 26. WWPN

Los WWPN permiten identificar puertos FC.

Se utilizan para:

``` text
Zoning
Identificación
Configuración de conectividad
```

------------------------------------------------------------------------

# 27. Zoning

Una buena práctica es limitar la conectividad a los dispositivos
necesarios.

Ejemplo:

``` text
ZONE_ESXI01_FABRIC_A

ESXi01_HBA_A
STORAGE_A_PORT_1
```

Y en Fabric B:

``` text
ZONE_ESXI01_FABRIC_B

ESXi01_HBA_B
STORAGE_B_PORT_1
```

Se repetiría el patrón para los demás hosts.

------------------------------------------------------------------------

# 28. ¿Por qué no abrir toda la fabric?

Porque un zoning demasiado permisivo:

``` text
Aumenta el dominio de fallo
Complica troubleshooting
Reduce aislamiento
Puede permitir conectividad innecesaria
```

El principio general es:

> **Permitir únicamente la conectividad necesaria.**

------------------------------------------------------------------------

# 29. LUN Masking

Después del zoning, la cabina debe determinar qué LUN puede ver cada
host.

Ejemplo:

``` text
ESXi01 → LUN10, LUN20, LUN30
ESXi02 → LUN10, LUN20
ESXi03 → LUN10, LUN20
```

Así:

``` text
LUN30
```

solo se presenta a:

``` text
ESXi01
```

------------------------------------------------------------------------

# 30. Zoning vs LUN Masking

``` text
Zoning
→ controla conectividad FC

LUN Masking
→ controla presentación de LUN
```

Son capas diferentes.

------------------------------------------------------------------------

# 31. FASE 8 - MULTIPATH

## Fallo de HBA A

Si:

``` text
HBA A → Fabric A
```

falla:

``` text
HBA B → Fabric B
```

debe mantener el acceso a las LUN siempre que la configuración sea
correcta.

------------------------------------------------------------------------

# 32. Fallo de Fabric A

Si:

``` text
Fabric A
```

falla:

``` text
Fabric B
```

debe continuar proporcionando conectividad.

Esto demuestra por qué:

``` text
Dual Fabric
```

es importante.

------------------------------------------------------------------------

# 33. Fallo de Controller A

Si la cabina está correctamente configurada con redundancia y ALUA:

``` text
Controller B
```

debería asumir las rutas correspondientes.

El comportamiento exacto depende de la cabina.

------------------------------------------------------------------------

# 34. ALUA

ALUA permite al host conocer que algunas rutas son:

``` text
Active / Optimized
```

mientras otras pueden ser:

``` text
Active / Non-Optimized
```

Las rutas optimizadas suelen ser preferibles para el tráfico normal.

------------------------------------------------------------------------

# 35. FASE 9 - iSCSI

Proceso conceptual:

``` text
1. Configurar Initiator
2. Identificar IQN
3. Configurar Target
4. Configurar IQN del Target
5. Realizar Discovery
6. Detectar portal
7. Login
8. Establecer Session
9. Presentar LUN
10. Configurar Multipath
```

------------------------------------------------------------------------

# 36. TCP 3260

El puerto habitual:

``` text
TCP 3260
```

------------------------------------------------------------------------

# 37. CHAP

CHAP proporciona:

``` text
Autenticación
```

No debemos decir que CHAP es un mecanismo de cifrado.

``` text
Autenticación ≠ Cifrado
```

------------------------------------------------------------------------

# 38. FASE 10 - NAS

NAS se utilizaría especialmente para:

``` text
File sharing
Documentos
Backups
```

mientras que SAN sería especialmente apropiada para:

``` text
Block storage
VMware datastores
Bases de datos
```

si los requisitos del entorno lo justifican.

------------------------------------------------------------------------

# 39. RAID del NAS

Con:

``` text
8 × 8 TB
```

tenemos:

``` text
64 TB brutos
```

Una opción razonable podría ser:

``` text
RAID 6
```

Capacidad aproximada:

``` text
(8 - 2) × 8
= 48 TB
```

Es especialmente interesante para un NAS de capacidad por su tolerancia
a dos fallos de disco.

------------------------------------------------------------------------

# 40. FASE 11 - BACKUP

La estrategia actual:

``` text
Backup
↓
Mismo CPD
```

es insuficiente para un desastre físico.

------------------------------------------------------------------------

# 41. Regla 3-2-1

Una posible aplicación:

``` text
Copia 1
→ Producción

Copia 2
→ NAS local

Copia 3
→ Ubicación externa / almacenamiento offsite
```

Y procurando:

``` text
2 medios diferentes
1 copia offsite
```

La estrategia concreta debe adaptarse al entorno.

------------------------------------------------------------------------

# 42. Snapshots

La afirmación:

> "Tenemos snapshots, así que no necesitamos backup."

es incorrecta.

Las snapshots pueden desaparecer junto con la infraestructura primaria.

``` text
Cabina perdida
↓
Snapshot local perdida
```

------------------------------------------------------------------------

# 43. Replicación

La afirmación:

> "Replicar la cabina al NAS equivale a tener backup."

también es incorrecta.

La replicación puede mantener una copia operativa, pero:

``` text
Borrado accidental
↓
Replicación
↓
Borrado replicado
```

Por eso se necesita una estrategia de backup independiente.

------------------------------------------------------------------------

# 44. FASE 12 - RPO/RTO

## DB01

``` text
RPO ≤ 15 min
RTO ≤ 1 h
```

Requiere una estrategia de protección de alta prioridad.

Posible combinación:

``` text
Snapshots frecuentes
+
Backup frecuente
+
Replicación
+
DR
```

------------------------------------------------------------------------

## Servicios web

``` text
RPO ≤ 1 h
RTO ≤ 2 h
```

Podría utilizarse:

``` text
Backup periódico
+
Replicación según criticidad
```

------------------------------------------------------------------------

## Documentos

``` text
RPO ≤ 24 h
RTO ≤ 8 h
```

Puede bastar con:

``` text
Backup diario
+
Copia offsite
```

si los requisitos reales lo permiten.

------------------------------------------------------------------------

# 45. FASE 13 - DR

Disponemos de:

``` text
CPD principal
        │
        │ 10 Gb/s
        │
        ▼
CPD secundario
```

La solución debería contemplar:

``` text
Replicación
Backups
Hosts
Networking
Storage
Procedimientos
```

------------------------------------------------------------------------

# 46. Priorización de recuperación

Una posible secuencia:

``` text
1. Infraestructura de red
2. Servicios de identidad
3. Storage
4. Hipervisores
5. Bases de datos
6. Aplicaciones
7. Web
8. Servicios secundarios
```

La prioridad exacta debe definirse según dependencias reales.

------------------------------------------------------------------------

# 47. Incendio del CPD

Situación:

``` text
CPD A
🔥
```

Se pierde:

``` text
Hosts
SAN
NAS
Switches
```

La estrategia correcta es activar el:

``` text
Disaster Recovery Plan
```

------------------------------------------------------------------------

# 48. Procedimiento de recuperación

## Paso 1

Confirmar:

``` text
Alcance del desastre
```

y activar el plan correspondiente.

## Paso 2

Validar:

``` text
CPD secundario
Red
Storage
Hosts
```

## Paso 3

Recuperar:

``` text
Identity services
```

## Paso 4

Recuperar:

``` text
Storage / replicated data
```

## Paso 5

Arrancar:

``` text
Critical VMs
```

## Paso 6

Validar:

``` text
Database
Application
Web
```

## Paso 7

Realizar:

``` text
Functional validation
```

------------------------------------------------------------------------

# 49. FASE 14 - INCIDENTE DE STORAGE

Tenemos:

``` text
CPU = 35%
RAM = 55%
Network = normal
Latency = 28 ms
IOPS = muy altas
Throughput = moderado
```

No debemos concluir automáticamente:

``` text
"El disco está roto."
```

------------------------------------------------------------------------

# 50. Comprobaciones recomendadas

Al menos:

``` text
1. Latencia del datastore
2. Latencia de la LUN
3. IOPS
4. Throughput
5. Queue depth
6. Paths
7. Estado de HBA
8. Estado de switches
9. Estado de controladoras
10. Cache
11. Pool
12. RAID
13. Discos
14. Otras VMs usando el mismo pool
15. Logs
```

------------------------------------------------------------------------

# 51. Interpretación

La combinación:

``` text
IOPS altas
Throughput moderado
Latency alta
```

puede ser compatible con:

``` text
Random I/O
Contention
Queueing
Storage bottleneck
```

Hay que investigar antes de concluir.

------------------------------------------------------------------------

# 52. INCIDENTE 2 - ESXi01 no ve LUN20

Como:

``` text
ESXi02 → LUN20 OK
ESXi03 → LUN20 OK
```

el problema probablemente está relacionado con ESXi01 o su camino
específico.

Revisar:

``` text
1. HBA
2. Link
3. SFP
4. Cable
5. Fabric
6. Zoning
7. WWPN
8. LUN masking
9. Host mapping
10. Multipath
11. Storage adapters
12. Rescan
13. Logs
```

------------------------------------------------------------------------

# 53. INCIDENTE 3 - Path A DOWN

Situación:

``` text
Path A → DOWN
Path B → UP
```

El servicio continúa, pero:

``` text
La redundancia está degradada.
```

No es correcto decir:

> "No importa porque las VMs siguen funcionando."

La respuesta correcta es:

``` text
El servicio sigue disponible,
pero existe un riesgo mayor ante un segundo fallo.
```

Hay que investigar y restaurar el path.

------------------------------------------------------------------------

# 54. INCIDENTE 4 - Thin Pool al 95%

Situación:

``` text
Physical usage:
95 TB / 100 TB
```

Solicitud:

``` text
+20 TB
```

No debe aceptarse automáticamente.

Porque:

``` text
5 TB físicos disponibles
```

y se pretenden provisionar:

``` text
20 TB adicionales
```

Hay que analizar:

``` text
Growth
Actual consumption
Overprovisioning
Snapshots
Replication
Expansion options
```

------------------------------------------------------------------------

# 55. Decisión

Una respuesta razonable:

``` text
No aprobar inmediatamente.
```

Primero:

``` text
Analizar capacidad física
Prever crecimiento
Ampliar pool si es necesario
Revisar consumo
Definir alertas
```

------------------------------------------------------------------------

# 56. INCIDENTE 5 - Firmware

Antes de instalar:

``` text
Firmware v12.0
```

comprobar:

``` text
Compatibility Matrix
Storage firmware
Switch firmware
HBA firmware
Drivers
ESXi version
Multipath software
Vendor support
Known issues
Rollback
Maintenance window
Configuration backup
```

------------------------------------------------------------------------

# 57. Regla fundamental

``` text
Latest
≠
Automatically best
```

La versión correcta es:

``` text
Supported
+
Compatible
+
Tested
```

------------------------------------------------------------------------

# 58. FASE 15 - DISEÑO FINAL

Una arquitectura coherente podría ser:

``` text
                         INTERNET
                            │
                         FIREWALL
                            │
                    CORE NETWORK
                       /       \
                      /         \
               SWITCH A       SWITCH B
                  │               │
             ┌────┴────┐     ┌────┴────┐
             │         │     │         │
           ESXi01    ESXi02 ESXi01   ESXi02
             │         │     │         │
             └────┬────┴────┴────┬────┘
                  │               │
               HBA A           HBA B
                  │               │
                  ▼               ▼
               FABRIC A        FABRIC B
                  │               │
                  ▼               ▼
             Controller A    Controller B
                  └──────┬────────┘
                         │
                    STORAGE POOLS
                    /           \
                  SSD            HDD
                   │              │
                 LUNs           LUNs
                   │              │
                 VMFS           Data
                   │
               DATASTORES
                   │
                    VMs

                    +
                   NAS
                    │
                 BACKUP
                    │
                    ▼
              OFFSITE / DR
                    │
                    ▼
              CPD SECUNDARIO
```

------------------------------------------------------------------------

# 59. Arquitectura de almacenamiento

Una propuesta:

``` text
SSD Pool
↓
DB01
Critical workloads

HDD Pool
↓
General workloads
Capacity workloads

NAS
↓
File sharing
Backup repository
```

------------------------------------------------------------------------

# 60. FASE 16 - PREGUNTAS DE ARQUITECTURA

## 1. ¿Por qué no NAS para todas las VMs?

Porque NAS proporciona normalmente:

``` text
File storage
```

mientras que una SAN proporciona:

``` text
Block storage
```

La elección depende del workload, pero para determinadas cargas VMware y
bases de datos una SAN puede ofrecer características y rendimiento más
adecuados.

------------------------------------------------------------------------

## 2. ¿Por qué no RAID 0 para DB01?

Porque:

``` text
RAID 0
=
Sin redundancia
```

Un fallo de disco puede comprometer el volumen.

------------------------------------------------------------------------

## 3. ¿Por qué dos controladoras?

Porque permiten reducir el impacto de:

``` text
Controller failure
```

si el sistema está correctamente configurado.

------------------------------------------------------------------------

## 4. ¿Por qué dos HBAs en el mismo switch no bastan?

Porque:

``` text
Switch
```

continúa siendo un:

``` text
SPOF
```

------------------------------------------------------------------------

## 5. ¿Por qué separar management y storage?

Para:

``` text
Aislamiento
Seguridad
Rendimiento predecible
Troubleshooting
```

y reducir interferencias entre tráfico de gestión y tráfico de
almacenamiento.

------------------------------------------------------------------------

## 6. ¿Por qué monitorizar thin provisioning?

Porque la capacidad lógica puede superar la capacidad física.

El riesgo es:

``` text
Pool full
```

------------------------------------------------------------------------

## 7. ¿Por qué snapshot no sustituye backup?

Porque puede depender de:

``` text
La misma infraestructura primaria.
```

------------------------------------------------------------------------

## 8. ¿Por qué replication no sustituye backup?

Porque determinados errores pueden replicarse:

``` text
Delete
↓
Replication
↓
Delete at replica
```

------------------------------------------------------------------------

## 9. ¿Por qué probar DR?

Porque:

``` text
Plan no probado
=
Plan cuyo funcionamiento real no está demostrado
```

------------------------------------------------------------------------

## 10. ¿Por qué no instalar firmware automáticamente?

Porque pueden existir:

``` text
Incompatibilidades
Bugs
Dependencias
Problemas de drivers
Problemas de interoperabilidad
```

------------------------------------------------------------------------

# 61. FASE 17 - CONCEPTOS

## SAN

Red especializada que proporciona normalmente almacenamiento de bloques
a servidores.

## NAS

Dispositivo o sistema que proporciona almacenamiento de archivos
mediante red.

## LUN

Unidad lógica de almacenamiento presentada a un host.

## HBA

Host Bus Adapter. Adaptador utilizado para conectar el host a
determinadas infraestructuras de almacenamiento, especialmente FC.

## WWPN

World Wide Port Name. Identifica un puerto Fibre Channel.

## WWNN

World Wide Node Name. Identifica un nodo Fibre Channel.

## FCID

Identificador utilizado dentro de una fabric Fibre Channel.

## Fabric

Infraestructura lógica Fibre Channel formada por switches
interconectados.

## Zoning

Control de qué dispositivos pueden comunicarse dentro de una fabric.

## LUN Masking

Control de qué LUN se presenta a cada host.

## FLOGI

Fabric Login.

## PLOGI

Port Login.

## IQN

iSCSI Qualified Name.

## CHAP

Protocolo de autenticación.

## Multipath

Utilización de múltiples caminos hacia el almacenamiento.

## ALUA

Asymmetric Logical Unit Access. Permite conocer características de las
rutas de acceso a una LUN.

## VMFS

Virtual Machine File System.

## Datastore

Recurso de almacenamiento utilizado por VMware para alojar archivos de
VMs.

## NAA

Network Address Authority. Identificador utilizado en VMware para
identificar determinados dispositivos de almacenamiento.

## VAAI

vSphere APIs for Array Integration.

## SIOC

Storage I/O Control.

## Storage Pool

Agrupación lógica de capacidad.

## Thin Provisioning

Presentación flexible de capacidad lógica que puede implicar
sobreasignación respecto a la capacidad física.

## Snapshot

Representación de un estado de datos en un punto temporal.

## Replication

Mantenimiento de otra copia de datos en otro sistema o ubicación.

## Backup

Copia destinada a permitir recuperación de datos.

## RPO

Recovery Point Objective. Objetivo relacionado con la cantidad de datos
que se puede perder.

## RTO

Recovery Time Objective. Objetivo relacionado con el tiempo de
recuperación.

## IOPS

Input/Output Operations Per Second.

## Throughput

Cantidad de datos transferidos por unidad de tiempo.

## Latency

Tiempo de respuesta de una operación.

## SPOF

Single Point of Failure.

------------------------------------------------------------------------

# 62. FASE 18 - VERDADERO/FALSO

  -----------------------------------------------------------------------
                       Nº           Respuesta           Explicación
  ----------------------- ----------------------------- -----------------
                        1               F               SAN trabaja
                                                        normalmente con
                                                        block storage, no
                                                        file storage.

                        2               V               Una LUN es una
                                                        unidad lógica de
                                                        almacenamiento.

                        3               V               WWPN identifica
                                                        un puerto FC.

                        4               F               WWNN identifica
                                                        un nodo FC.

                        5               V               F_Port conecta un
                                                        dispositivo final
                                                        al switch.

                        6               V               E_Port se utiliza
                                                        para
                                                        interconectar
                                                        switches FC.

                        7               F               Zoning controla
                                                        conectividad; LUN
                                                        masking controla
                                                        presentación de
                                                        LUNs.

                        8               V               FLOGI = Fabric
                                                        Login.

                        9               V               PLOGI = Port
                                                        Login.

                       10               V               iSCSI utiliza
                                                        TCP/IP.

                       11               V               El puerto
                                                        habitual es TCP
                                                        3260.

                       12               V               CHAP proporciona
                                                        autenticación.

                       13               F               Pueden existir
                                                        varios paths y
                                                        seguir
                                                        dependiendo de un
                                                        mismo SPOF.

                       14               V               ALUA diferencia
                                                        rutas optimizadas
                                                        y no optimizadas.

                       15               V               VMFS es un
                                                        filesystem
                                                        utilizado por
                                                        VMware.

                       16               V               VAAI permite
                                                        determinadas
                                                        operaciones de
                                                        offload.

                       17               F               Una snapshot no
                                                        es equivalente a
                                                        un backup
                                                        externo.

                       18               F               RPO se relaciona
                                                        con pérdida de
                                                        datos; RTO con
                                                        tiempo de
                                                        recuperación.

                       19               V               RTO está
                                                        relacionado con
                                                        el tiempo de
                                                        recuperación.

                       20               F               IOPS y throughput
                                                        son métricas
                                                        diferentes.

                       21               V               Thin provisioning
                                                        puede
                                                        sobreasignar
                                                        capacidad lógica.

                       22               F               RAID no sustituye
                                                        al backup.

                       23               V               Varios caminos
                                                        pueden compartir
                                                        un mismo SPOF.

                       24               V               DR debe incluir
                                                        procedimientos y
                                                        pruebas.

                       25               F               El firmware debe
                                                        ser compatible y
                                                        soportado.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 63. FASE 19 - DIAGNÓSTICO

## Caso A - LUN invisible en ESXi01

Orden razonable:

``` text
ESXi01
 ↓
HBA
 ↓
Link
 ↓
Fabric
 ↓
WWPN
 ↓
Zoning
 ↓
LUN Masking
 ↓
Host Mapping
 ↓
Multipath
 ↓
Rescan
 ↓
Logs
```

Como otros hosts ven la LUN:

``` text
Storage general
```

es menos probable que el problema sea una pérdida global de la LUN.

------------------------------------------------------------------------

# 64. Caso B - Todos los hosts tienen latencia alta

Al afectar a:

``` text
Todos los hosts
```

debemos buscar componentes compartidos:

``` text
Storage controller
Storage pool
RAID
Disks
Fabric
Network
Congestion
Queue depth
Storage cache
```

------------------------------------------------------------------------

# 65. Caso C - Un path DOWN

Comprobar:

``` text
Cable
SFP
HBA
Switch port
Fabric
Storage port
Controller
Multipath software
Logs
```

Después:

``` text
Restaurar path
```

------------------------------------------------------------------------

# 66. Caso D - Pool al 92%

Riesgos:

``` text
Agotamiento de capacidad
Snapshots sin espacio
Thin provisioning overcommit
Problemas de rendimiento
Imposibilidad de crear nuevos volúmenes
```

Acciones:

``` text
Analizar crecimiento
Liberar capacidad
Expandir pool
Revisar snapshots
Revisar provisioning
Establecer alertas
```

------------------------------------------------------------------------

# 67. Caso E - Controller failure

En una cabina redundante correctamente configurada:

``` text
Controller B
```

debería asumir las operaciones correspondientes.

Puede haber:

``` text
Path failover
ALUA state change
```

según implementación.

------------------------------------------------------------------------

# 68. Caso F - Switch A failure

Con:

``` text
Dual Fabric
```

debería continuar el acceso por:

``` text
Fabric B
```

siempre que no existan dependencias ocultas.

------------------------------------------------------------------------

# 69. Caso G - Site A destroyed

La recuperación debería apoyarse en:

``` text
Offsite backup
Replication
DR site
Recovery procedures
```

y los servicios se recuperarían según:

``` text
Prioridad
RPO
RTO
Dependencias
```

------------------------------------------------------------------------

# 70. GRAN PREGUNTA FINAL

Una respuesta verbal razonable podría estructurarse así:

``` text
1. Diseñaría un CPD con energía y climatización redundantes.

2. Implementaría varios hosts físicos en un cluster VMware.

3. Utilizaría HA para recuperación ante fallos de host.

4. Utilizaría vMotion para mantenimiento y movilidad de VMs.

5. Separaría redes de gestión, producción y almacenamiento.

6. Diseñaría almacenamiento con pools según rendimiento y capacidad.

7. Utilizaría RAID adecuado al workload.

8. Implementaría una SAN con dos fabrics independientes.

9. Cada host tendría dos caminos de almacenamiento.

10. Aplicaría zoning restrictivo.

11. Aplicaría LUN masking según las necesidades de cada host.

12. Configuraría multipath y ALUA cuando corresponda.

13. Utilizaría NAS para file services y determinados repositorios de backup.

14. Mantendría una estrategia de backup independiente.

15. Aplicaría 3-2-1 y, cuando sea posible, mecanismos de inmutabilidad.

16. Definiría RPO y RTO según criticidad.

17. Replicaría los servicios críticos hacia el CPD secundario.

18. Documentaría el procedimiento de DR.

19. Monitorizaría capacidad, IOPS, throughput, latencia y paths.

20. Probaría periódicamente la recuperación.
```

------------------------------------------------------------------------

# 71. 🏆 Qué debería haber demostrado la misión

Si has podido resolver la mayoría de los escenarios, ya no estás
simplemente memorizando:

``` text
SAN
RAID
NAS
VMware
```

Estás empezando a pensar en:

``` text
Arquitectura
```

Y ese era precisamente el objetivo de esta misión.

------------------------------------------------------------------------

# 72. 🔍 Errores especialmente importantes

Si has cometido alguno de estos errores, conviene repasarlos antes del
simulacro:

``` text
❌ SAN = NAS

❌ RAID = Backup

❌ Snapshot = Backup

❌ Replication = Backup

❌ Zoning = LUN Masking

❌ WWPN = LUN

❌ IQN = WWPN

❌ Dos HBAs = redundancia completa

❌ Dos paths = dos fabrics necesariamente

❌ RPO = tiempo de recuperación

❌ RTO = cantidad de datos perdidos

❌ IOPS = throughput

❌ Thin provisioning = capacidad física infinita

❌ DR = simplemente replicación

❌ Firmware más nuevo = automáticamente mejor
```

------------------------------------------------------------------------

# 73. 🧠 REPASO FINAL DE LA MISIÓN

La arquitectura completa puede resumirse así:

``` text
                         CPD
                          │
              ┌───────────┴───────────┐
              │                       │
           POWER                   COOLING
              │                       │
              └───────────┬───────────┘
                          │
                       NETWORK
                     /         \
                    /           \
               HOSTS          STORAGE
                 │               │
             VMware           SAN/NAS
                 │               │
              Cluster         RAID/Pools
                 │               │
             Datastores         LUNs
                 │               │
                 └───────┬───────┘
                         │
                     WORKLOADS
                         │
               ┌─────────┴─────────┐
               │                   │
            BACKUP             REPLICATION
               │                   │
               └─────────┬─────────┘
                         │
                         DR
                         │
                  CPD SECUNDARIO
```

------------------------------------------------------------------------

# 74. 🏁 CONCLUSIÓN

La idea central del Bloque 4 no es memorizar una lista de tecnologías.

Es entender cómo encajan:

``` text
CPD
 ↓
Servidores
 ↓
Virtualización
 ↓
VMware
 ↓
Red
 ↓
SAN / NAS
 ↓
RAID
 ↓
LUN / Datastore
 ↓
VMs
 ↓
Backup
 ↓
Replication
 ↓
DR
```

Y sobre todo:

``` text
¿Qué pasa si falla?
```

Ese es el hilo conductor de todo el bloque.

------------------------------------------------------------------------

# 🎓 FIN DE LAS SOLUCIONES

**Bloque 4 - Infraestructura**

``` text
✓ Misión
✓ Soluciones
→ Simulacro tipo test
→ Corrección
→ Repaso de errores
```
