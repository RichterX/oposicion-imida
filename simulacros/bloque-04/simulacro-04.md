<!-- encabezado-homogeneizado -->
# Bloque 04 - SIMULACRO
> **Bloque:** Bloque 04  
> **Documento:** Simulacro  
> **Preguntas de referencia:** 70  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# BLOQUE 4 - SIMULACRO TIPO TEST

> **Bloque:** 4 - Infraestructura\
> **Capítulos:** 4.1 CPD · 4.2 Virtualización · 4.3 VMware · 4.4 RAID ·
> 4.5 NAS · 4.6 SAN\
> **Formato:** Tipo test\
> **Preguntas:** 70\
> **Opciones:** 4 por pregunta\
> **Respuestas correctas:** 1 por pregunta\
> **Nivel:** ⭐⭐⭐⭐⭐\
> **Tiempo recomendado:** 90 minutos\
> **Puntuación recomendada:** +1 por acierto, 0 por respuesta en blanco,
> -0,33 por error

------------------------------------------------------------------------

# 📋 INSTRUCCIONES

Este simulacro está diseñado para parecerse al enfoque de un examen de
oposición:

-   Una única respuesta correcta.
-   Preguntas conceptuales.
-   Preguntas de aplicación.
-   Diferencias entre conceptos muy próximos.
-   Casos de infraestructura.
-   Algunas preguntas con pequeñas trampas.
-   No se proporcionan las soluciones en este documento.

## Regla importante

No consultes los capítulos mientras realizas el examen.

Marca únicamente:

``` text
A
B
C
D
```

y continúa.

Si dudas, puedes dejar la pregunta en blanco y volver a ella al final.

------------------------------------------------------------------------

# 🧮 HOJA DE RESPUESTAS

    Nº  Resp.    Nº  Resp.    Nº  Resp.    Nº  Resp.
  ---- ------- ---- ------- ---- ------- ---- -------
     1           21           41           61 
     2           22           42           62 
     3           23           43           63 
     4           24           44           64 
     5           25           45           65 
     6           26           46           66 
     7           27           47           67 
     8           28           48           68 
     9           29           49           69 
    10           30           50           70 
    11           31           51           71 
    12           32           52           72 
    13           33           53           73 
    14           34           54           74 
    15           35           55           75 
    16           36           56           76 
    17           37           57           77 
    18           38           58           78 
    19           39           59           79 
    20           40           60           80 

------------------------------------------------------------------------

## Pregunta 1

¿Qué caracteriza principalmente a una SAN?

**A.** Proporciona normalmente almacenamiento a nivel de bloque

**B.** Proporciona exclusivamente almacenamiento de archivos

**C.** Sustituye siempre a un sistema de backup

**D.** Es un sistema de climatización del CPD

------------------------------------------------------------------------

## Pregunta 2

¿Qué caracteriza normalmente a un NAS?

**A.** Un hipervisor

**B.** Almacenamiento presentado como archivos mediante servicios de red

**C.** Almacenamiento exclusivamente a nivel de bloque

**D.** Una controladora RAID sin red

------------------------------------------------------------------------

## Pregunta 3

¿Cuál es el objetivo principal de una UPS en un CPD?

**A.** Gestionar las LUN

**B.** Sustituir la climatización

**C.** Proporcionar continuidad eléctrica temporal y protección ante
problemas de alimentación

**D.** Aumentar los IOPS de una SAN

------------------------------------------------------------------------

## Pregunta 4

¿Cuál de los siguientes es un ejemplo de SPOF?

**A.** Dos switches independientes en fabrics separadas

**B.** Dos controladoras redundantes

**C.** Dos UPS independientes

**D.** Un único switch del que dependen todos los caminos de
almacenamiento

------------------------------------------------------------------------

## Pregunta 5

¿Qué elemento ayuda directamente a mantener unas condiciones térmicas
adecuadas en un CPD?

**A.** Climatización

**B.** Zoning

**C.** LUN masking

**D.** CHAP

------------------------------------------------------------------------

## Pregunta 6

¿Qué ventaja principal aporta la virtualización?

**A.** Garantiza por sí sola la recuperación ante desastres

**B.** Permite consolidar cargas y utilizar los recursos físicos de
forma flexible

**C.** Elimina cualquier necesidad de almacenamiento

**D.** Hace innecesario el backup

------------------------------------------------------------------------

## Pregunta 7

¿Qué componente proporciona los recursos físicos sobre los que se
ejecutan las máquinas virtuales?

**A.** Datastore

**B.** Snapshot

**C.** Host físico

**D.** LUN masking

------------------------------------------------------------------------

## Pregunta 8

¿Qué ventaja proporciona un cluster VMware?

**A.** Convierte automáticamente NAS en SAN

**B.** Elimina el RAID

**C.** Sustituye las UPS

**D.** Permite agrupar hosts para facilitar funciones de disponibilidad
y gestión

------------------------------------------------------------------------

## Pregunta 9

¿Qué tecnología de VMware permite migrar una VM en ejecución entre hosts
compatibles?

**A.** vMotion

**B.** CHAP

**C.** FLOGI

**D.** MPIO

------------------------------------------------------------------------

## Pregunta 10

¿Qué función está asociada a VMware HA?

**A.** Crear snapshots de NAS

**B.** Reiniciar VMs en otros hosts cuando se produce un fallo de host,
según la configuración

**C.** Crear zonas Fibre Channel

**D.** Comprimir datos

------------------------------------------------------------------------

## Pregunta 11

¿Qué es VMFS?

**A.** Un nivel RAID

**B.** Un puerto Fibre Channel

**C.** Un sistema de archivos utilizado por VMware para determinados
datastores

**D.** Un protocolo de autenticación iSCSI

------------------------------------------------------------------------

## Pregunta 12

¿Qué representa un datastore en VMware?

**A.** Una controladora FC

**B.** Una interfaz de red física

**C.** Una UPS

**D.** Un recurso de almacenamiento utilizado para alojar archivos de
máquinas virtuales

------------------------------------------------------------------------

## Pregunta 13

¿Qué describe mejor RAID?

**A.** Una tecnología para organizar/proteger datos entre varios discos

**B.** Un protocolo de autenticación

**C.** Una red de almacenamiento por sí misma

**D.** Un hipervisor

------------------------------------------------------------------------

## Pregunta 14

¿Cuál es una característica de RAID 0?

**A.** Copia remota

**B.** Distribución de datos sin redundancia

**C.** Espejo con redundancia

**D.** Doble paridad

------------------------------------------------------------------------

## Pregunta 15

¿Cuál es una característica de RAID 1?

**A.** Doble paridad

**B.** Deduplicación

**C.** Mirroring

**D.** Striping sin redundancia

------------------------------------------------------------------------

## Pregunta 16

¿Cuál es una característica de RAID 5?

**A.** Mirroring de todos los discos

**B.** Ausencia total de redundancia

**C.** Replicación entre CPD

**D.** Striping con paridad distribuida y tolerancia clásica al fallo de
un disco

------------------------------------------------------------------------

## Pregunta 17

¿Cuál es una característica de RAID 6?

**A.** Paridad doble y tolerancia clásica al fallo de dos discos

**B.** Ausencia de redundancia

**C.** Solo mirroring entre dos discos

**D.** Replicación síncrona

------------------------------------------------------------------------

## Pregunta 18

¿Qué caracteriza a RAID 10?

**A.** Backup histórico

**B.** Combinación de mirroring y striping

**C.** Doble paridad distribuida

**D.** Ausencia de redundancia

------------------------------------------------------------------------

## Pregunta 19

¿Por qué RAID no sustituye al backup?

**A.** Porque RAID no puede utilizar varios discos

**B.** Porque RAID siempre elimina los datos

**C.** Porque RAID no protege por sí mismo frente a borrados, corrupción
lógica o determinados desastres

**D.** Porque RAID solo funciona con NAS

------------------------------------------------------------------------

## Pregunta 20

¿Qué es un Storage Pool?

**A.** Un puerto de switch

**B.** Un HBA

**C.** Una VM

**D.** Una agrupación lógica de capacidad de almacenamiento

------------------------------------------------------------------------

## Pregunta 21

¿Qué permite el thin provisioning?

**A.** Presentar capacidad lógica de forma flexible y potencialmente
sobreasignada respecto a la capacidad física

**B.** Eliminar la necesidad de monitorizar capacidad

**C.** Garantizar capacidad física infinita

**D.** Sustituir el RAID

------------------------------------------------------------------------

## Pregunta 22

¿Cuál es un riesgo del thin provisioning?

**A.** Eliminar el zoning

**B.** Agotar la capacidad física aunque todavía exista capacidad lógica
provisionada

**C.** Perder automáticamente todos los WWPN

**D.** Desactivar VMware HA

------------------------------------------------------------------------

## Pregunta 23

¿Qué hace la deduplicación?

**A.** Proporciona alimentación eléctrica

**B.** Sustituye el filesystem

**C.** Reduce datos redundantes evitando almacenar repetidamente bloques
iguales, según la implementación

**D.** Crea rutas FC

------------------------------------------------------------------------

## Pregunta 24

¿Qué hace la compresión?

**A.** Asigna WWPN

**B.** Crea una LUN

**C.** Configura MPIO

**D.** Reduce la representación física de los datos mediante algoritmos
de compresión

------------------------------------------------------------------------

## Pregunta 25

¿Qué es una snapshot?

**A.** Una representación de un punto en el tiempo de los datos

**B.** Un sustituto universal del backup

**C.** Un switch FC

**D.** Un tipo de HBA

------------------------------------------------------------------------

## Pregunta 26

¿Por qué una snapshot no equivale necesariamente a un backup?

**A.** Porque solo existe en Windows

**B.** Porque puede depender de la misma infraestructura primaria y
perderse con ella

**C.** Porque nunca puede recuperarse

**D.** Porque siempre está fuera del CPD

------------------------------------------------------------------------

## Pregunta 27

¿Qué diferencia fundamental existe entre replicación y backup?

**A.** La replicación solo sirve para RAID 0

**B.** El backup nunca permite recuperar datos

**C.** La replicación mantiene otra copia operativa; el backup está
orientado a recuperación histórica

**D.** Son exactamente lo mismo

------------------------------------------------------------------------

## Pregunta 28

¿Qué significa RPO?

**A.** Recovery Performance Operation

**B.** RAID Protection Objective

**C.** Remote Path Operation

**D.** Recovery Point Objective

------------------------------------------------------------------------

## Pregunta 29

¿Qué pregunta responde principalmente el RPO?

**A.** ¿Cuántos datos puedo perder como máximo según el objetivo?

**B.** ¿Cuántos hosts tengo?

**C.** ¿Cuánto almacenamiento bruto existe?

**D.** ¿Cuántos puertos FC tiene el switch?

------------------------------------------------------------------------

## Pregunta 30

¿Qué significa RTO?

**A.** Recovery Target Output

**B.** Recovery Time Objective

**C.** Remote Transfer Operation

**D.** RAID Throughput Optimization

------------------------------------------------------------------------

## Pregunta 31

¿Qué pregunta responde principalmente el RTO?

**A.** ¿Cuántos discos tiene el RAID?

**B.** ¿Cuántas LUN existen?

**C.** ¿Cuánto tiempo objetivo puede tardar la recuperación del
servicio?

**D.** ¿Cuántos datos pueden duplicarse?

------------------------------------------------------------------------

## Pregunta 32

¿Qué mide IOPS?

**A.** Cantidad de datos por segundo exclusivamente

**B.** Tiempo de respuesta

**C.** Capacidad total

**D.** Operaciones de entrada/salida por segundo

------------------------------------------------------------------------

## Pregunta 33

¿Qué mide throughput?

**A.** Cantidad de datos transferidos por unidad de tiempo

**B.** Número de operaciones independientemente del tamaño

**C.** Tiempo de recuperación

**D.** Número de paths

------------------------------------------------------------------------

## Pregunta 34

¿Qué mide latency?

**A.** Número de LUN

**B.** Tiempo de respuesta de una operación

**C.** Capacidad del pool

**D.** Número de discos

------------------------------------------------------------------------

## Pregunta 35

¿Qué puede provocar una queue depth excesiva?

**A.** Creación automática de RAID

**B.** Eliminación del multipath

**C.** Contención y aumento de latencia

**D.** Más capacidad física

------------------------------------------------------------------------

## Pregunta 36

¿Qué es oversubscription?

**A.** Una técnica de backup

**B.** Un tipo de RAID

**C.** Un método de autenticación

**D.** Una situación donde la demanda potencial agregada supera la
capacidad de un recurso o enlace

------------------------------------------------------------------------

## Pregunta 37

¿Qué objetivo tiene capacity planning?

**A.** Prever capacidad futura considerando crecimiento, consumo y
reservas

**B.** Configurar únicamente WWPN

**C.** Sustituir el monitoring

**D.** Eliminar snapshots

------------------------------------------------------------------------

## Pregunta 38

¿Qué es headroom?

**A.** Una política de zoning

**B.** Capacidad o margen reservado para crecimiento, contingencias y
operaciones

**C.** Una dirección IP

**D.** Un tipo de LUN

------------------------------------------------------------------------

## Pregunta 39

¿Qué identifica un WWPN?

**A.** Un datastore

**B.** Un IQN

**C.** Un puerto Fibre Channel

**D.** Una LUN

------------------------------------------------------------------------

## Pregunta 40

¿Qué identifica un WWNN?

**A.** Un puerto TCP

**B.** Una LUN

**C.** Una VM

**D.** Un nodo Fibre Channel

------------------------------------------------------------------------

## Pregunta 41

¿Qué representa un FCID?

**A.** Un identificador utilizado dentro de una fabric Fibre Channel

**B.** Un identificador iSCSI

**C.** Un filesystem

**D.** Un nivel RAID

------------------------------------------------------------------------

## Pregunta 42

¿Qué es un F_Port?

**A.** Una LUN

**B.** Un puerto de switch FC que conecta un dispositivo final

**C.** Un enlace entre dos switches FC

**D.** Un puerto Ethernet

------------------------------------------------------------------------

## Pregunta 43

¿Qué es un E_Port?

**A.** Un puerto iSCSI

**B.** Una controladora de almacenamiento

**C.** Un puerto utilizado para interconectar switches Fibre Channel

**D.** Un puerto de un HBA

------------------------------------------------------------------------

## Pregunta 44

¿Qué significa ISL?

**A.** Internet Storage Login

**B.** Internal SAN LUN

**C.** iSCSI Storage Layer

**D.** Inter-Switch Link

------------------------------------------------------------------------

## Pregunta 45

¿Qué función tiene zoning?

**A.** Controlar qué dispositivos pueden comunicarse dentro de la fabric

**B.** Determinar exclusivamente qué LUN ve un host

**C.** Crear RAID

**D.** Asignar capacidad física

------------------------------------------------------------------------

## Pregunta 46

¿Qué función tiene LUN masking?

**A.** Crear snapshots

**B.** Controlar qué LUN puede ver un determinado host

**C.** Interconectar switches FC

**D.** Autenticar usuarios de Windows

------------------------------------------------------------------------

## Pregunta 47

¿Qué significa FLOGI?

**A.** Fibre Logical Group Identifier

**B.** Fabric Link Operation

**C.** Fabric Login

**D.** File Login

------------------------------------------------------------------------

## Pregunta 48

¿Qué significa PLOGI?

**A.** Path Login

**B.** Physical Login

**C.** Pool Login

**D.** Port Login

------------------------------------------------------------------------

## Pregunta 49

¿Qué protocolo transporta SCSI sobre TCP/IP?

**A.** iSCSI

**B.** Fibre Channel exclusivamente

**C.** NFS

**D.** SMB

------------------------------------------------------------------------

## Pregunta 50

¿Qué identificador es característico de iSCSI?

**A.** NAA

**B.** IQN

**C.** WWPN

**D.** FCID

------------------------------------------------------------------------

## Pregunta 51

¿Cuál es el puerto TCP habitual de iSCSI?

**A.** 443

**B.** 22

**C.** 3260

**D.** 80

------------------------------------------------------------------------

## Pregunta 52

¿Qué función tiene CHAP?

**A.** Compresión

**B.** RAID

**C.** Multipath

**D.** Autenticación

------------------------------------------------------------------------

## Pregunta 53

¿Qué es multipath?

**A.** El uso de múltiples caminos hacia un recurso de almacenamiento

**B.** La duplicación de archivos

**C.** La compresión de bloques

**D.** La creación de snapshots

------------------------------------------------------------------------

## Pregunta 54

¿Qué ventaja proporciona una dual fabric bien diseñada?

**A.** Duplica automáticamente todos los datos

**B.** Reduce determinados puntos únicos de fallo de la conectividad de
almacenamiento

**C.** Elimina la necesidad de RAID

**D.** Sustituye al backup

------------------------------------------------------------------------

## Pregunta 55

¿Qué significa ALUA?

**A.** Automatic LUN Utility Access

**B.** Array Link User Architecture

**C.** Asymmetric Logical Unit Access

**D.** Advanced Logical User Authentication

------------------------------------------------------------------------

## Pregunta 56

¿Qué puede indicar ALUA?

**A.** Qué discos tienen RAID 0

**B.** Qué usuarios son administradores

**C.** Qué VMs tienen snapshots

**D.** Qué caminos hacia una LUN son optimizados o no optimizados

------------------------------------------------------------------------

## Pregunta 57

¿Qué tecnología proporciona multipathing en Windows?

**A.** MPIO

**B.** VMFS

**C.** VAAI

**D.** CHAP

------------------------------------------------------------------------

## Pregunta 58

¿Qué tecnología proporciona multipathing en Linux?

**A.** FLOGI

**B.** Device Mapper Multipath

**C.** VMFS

**D.** SIOC

------------------------------------------------------------------------

## Pregunta 59

¿Qué es VAAI?

**A.** Un tipo de RAID

**B.** Un sistema de archivos Linux

**C.** APIs de integración de VMware con cabinas para determinadas
operaciones de almacenamiento

**D.** Un protocolo de routing

------------------------------------------------------------------------

## Pregunta 60

¿Qué permite Storage I/O Control?

**A.** Crear una fabric FC

**B.** Configurar CHAP

**C.** Crear una UPS

**D.** Gestionar determinadas prioridades de I/O en VMware

------------------------------------------------------------------------

## Pregunta 61

¿Qué debe ocurrir idealmente si falla una ruta de almacenamiento en un
sistema multipath?

**A.** El tráfico puede continuar por otra ruta disponible

**B.** Todas las VMs deben apagarse inmediatamente

**C.** Se elimina la LUN

**D.** Se destruye el RAID

------------------------------------------------------------------------

## Pregunta 62

¿Qué debe comprobarse antes de instalar firmware nuevo en una
infraestructura SAN?

**A.** Que las LUN estén llenas

**B.** Compatibilidad, matriz de soporte, dependencias, procedimiento de
rollback y ventana de mantenimiento

**C.** Solo que el número de versión sea el mayor

**D.** Que exista RAID 0

------------------------------------------------------------------------

## Pregunta 63

¿Qué componente debe mantenerse separado o protegido especialmente en
una arquitectura empresarial?

**A.** El nombre de la VM

**B.** El tamaño del monitor

**C.** El plano de administración

**D.** El extintor

------------------------------------------------------------------------

## Pregunta 64

¿Cuál es una estrategia clásica de backup?

**A.** 1-1-1

**B.** 2-0-0

**C.** 10-0-0

**D.** 3-2-1

------------------------------------------------------------------------

## Pregunta 65

¿Qué describe mejor un diseño de DR completo?

**A.** Tecnología, procedimientos, personas, documentación y pruebas

**B.** Solo una snapshot local

**C.** Solo RAID 6

**D.** Solo una segunda HBA

------------------------------------------------------------------------

## Pregunta 66

¿Cuál sería una respuesta adecuada ante un pool thin con 95% de
capacidad física utilizada?

**A.** Eliminar el multipath

**B.** Analizar crecimiento y capacidad disponible antes de aceptar
nuevas asignaciones

**C.** Asignar inmediatamente más capacidad lógica

**D.** Desactivar las alertas

------------------------------------------------------------------------

## Pregunta 67

Una LUN es visible para ESXi02 y ESXi03 pero no para ESXi01. ¿Qué debe
investigarse especialmente?

**A.** El RPO únicamente

**B.** El tamaño de la UPS únicamente

**C.** Configuración de ESXi01, paths, zoning, mapping/masking y rescan

**D.** La climatización únicamente

------------------------------------------------------------------------

## Pregunta 68

Una VM presenta 28 ms de latencia de almacenamiento, IOPS muy altas y
throughput moderado. ¿Qué métrica merece especial atención?

**A.** Capacidad bruta

**B.** Número de WWPN

**C.** RTO

**D.** Latency

------------------------------------------------------------------------

## Pregunta 69

¿Qué ocurre si dos HBAs de un host dependen del mismo switch FC?

**A.** El switch sigue siendo un posible SPOF

**B.** La redundancia es perfecta

**C.** RAID deja de funcionar

**D.** Se convierten automáticamente en dos fabrics

------------------------------------------------------------------------

## Pregunta 70

¿Qué principio debe guiar una arquitectura de infraestructura?

**A.** Evitar toda redundancia para ahorrar capacidad

**B.** Diseñar también pensando en qué ocurre cuando una pieza falla

**C.** Maximizar siempre el número de LUN

**D.** Usar siempre el RAID más grande

------------------------------------------------------------------------

# 📊 RESULTADO

## Fórmula

``` text
Puntuación = aciertos - (errores × 0,33)
```

Las preguntas en blanco:

``` text
0 puntos
```

------------------------------------------------------------------------

# 🎯 INTERPRETACIÓN

    Puntuación Nivel
  ------------ ---------------------------------
         \< 35 🔴 Necesita bastante repaso
         35-49 🟠 Base todavía irregular
         50-59 🟡 Buen nivel, pero con lagunas
         60-69 🟢 Muy buen nivel
         70-75 🔵 Nivel excelente
         76-80 🏆 Dominio extraordinario

> **Nota:** La puntuación de la tabla es orientativa. Para estudiar
> interesa más analizar **qué preguntas has fallado y por qué** que
> quedarse únicamente con el número final.

------------------------------------------------------------------------

# 🧠 DESPUÉS DEL SIMULACRO

Cuando termines, guarda:

``` text
Aciertos:
Errores:
En blanco:
Puntuación:
Tiempo:
```

Y, sobre todo, anota las preguntas en las que:

``` text
1. No sabías la respuesta.
2. Dudaste entre dos.
3. Acertaste por intuición.
4. Cambiaste una respuesta y la empeoraste.
```

Estas cuatro categorías son mucho más útiles para el repaso que el
porcentaje bruto.

------------------------------------------------------------------------

# 🚫 NO INCLUYE SOLUCIONES

Este documento termina deliberadamente aquí.

La **plantilla de corrección** debe ser un documento separado para que
puedas hacer el simulacro sin spoilers.

------------------------------------------------------------------------

# 🏁 FIN DEL SIMULACRO

**Bloque 4 - Infraestructura**

``` text
4.1 CPD
4.2 Virtualización
4.3 VMware
4.4 RAID
4.5 NAS
4.6 SAN
```

**80 preguntas.**

Ahora toca enfrentarse al monstruo. 🏗️🧠

