# BLOQUE 4 - CORRECCIÓN DEL SIMULACRO TIPO TEST

> **Bloque:** 4 - Infraestructura  
> **Simulacro:** 70 preguntas reales  
> **Documento:** Corrección explicada  
> **Uso:** Repaso offline

---

# 📌 Cómo utilizar esta corrección

La idea no es simplemente mirar la letra correcta, sino entender **por qué**.

Para cada pregunta encontrarás:

- Respuesta correcta.
- Explicación.
- Aclaración de las opciones incorrectas cuando aporta valor.

> **Nota:** El archivo original conserva algunos encabezados antiguos que hablan de 80 preguntas, pero las preguntas efectivamente presentes terminan en la 70. fileciteturn14file0L12-L24 fileciteturn15file0L83-L93

---

# 🔑 RESUMEN RÁPIDO DE RESPUESTAS

```text
 1 A    2 B    3 C    4 D    5 A
 6 B    7 C    8 D    9 A   10 B
11 C   12 D   13 A   14 B   15 C
16 D   17 A   18 B   19 C   20 D
21 A   22 B   23 C   24 D   25 A
26 B   27 C   28 D   29 A   30 B
31 C   32 D   33 A   34 B   35 C
36 D   37 A   38 B   39 C   40 D
41 A   42 B   43 C   44 D   45 A
46 B   47 C   48 D   49 A   50 B
51 C   52 D   53 A   54 B   55 C
56 D   57 A   58 B   59 C   60 D
61 A   62 B   63 C   64 D   65 A
66 B   67 C   68 D   69 A   70 B
```

---

# Pregunta 1

**¿Qué caracteriza principalmente a una SAN?**

### ✅ Respuesta correcta: **A**

Una SAN proporciona normalmente almacenamiento a nivel de bloque.

**Por qué las demás no:** B, C y D describen conceptos incorrectos para una SAN.

---

# Pregunta 2

**¿Qué caracteriza normalmente a un NAS?**

### ✅ Respuesta correcta: **B**

Un NAS proporciona normalmente almacenamiento presentado como archivos mediante servicios de red.

**Por qué las demás no:** A, C y D no describen la función principal de un NAS.

---

# Pregunta 3

**¿Cuál es el objetivo principal de una UPS en un CPD?**

### ✅ Respuesta correcta: **C**

Una UPS proporciona continuidad eléctrica temporal y protección ante problemas de alimentación.

**Por qué las demás no:** A corresponde a almacenamiento, B a climatización y D a rendimiento de almacenamiento.

---

# Pregunta 4

**¿Cuál de los siguientes es un ejemplo de SPOF?**

### ✅ Respuesta correcta: **D**

Un único switch del que dependen todos los caminos de almacenamiento constituye un punto único de fallo.

**Por qué las demás no:** A, B y C introducen redundancia, por lo que no son el ejemplo planteado.

---

# Pregunta 5

**¿Qué elemento ayuda directamente a mantener unas condiciones térmicas adecuadas en un CPD?**

### ✅ Respuesta correcta: **A**

La climatización controla las condiciones térmicas del CPD.

**Por qué las demás no:** Zoning, LUN masking y CHAP son conceptos de almacenamiento o autenticación.

---

# Pregunta 6

**¿Qué ventaja principal aporta la virtualización?**

### ✅ Respuesta correcta: **B**

La virtualización permite consolidar cargas y utilizar los recursos físicos de forma flexible.

**Por qué las demás no:** No elimina el almacenamiento ni el backup y tampoco garantiza por sí sola el DR.

---

# Pregunta 7

**¿Qué componente proporciona los recursos físicos sobre los que se ejecutan las máquinas virtuales?**

### ✅ Respuesta correcta: **C**

El host físico proporciona CPU, RAM, red y otros recursos físicos a las VMs.

**Por qué las demás no:** Datastore y snapshot son conceptos de almacenamiento; LUN masking controla presentación de LUNs.

---

# Pregunta 8

**¿Qué ventaja proporciona un cluster VMware?**

### ✅ Respuesta correcta: **D**

Un cluster agrupa hosts y facilita funciones de disponibilidad y gestión.

**Por qué las demás no:** No convierte NAS en SAN, no elimina RAID y no sustituye UPS.

---

# Pregunta 9

**¿Qué tecnología de VMware permite migrar una VM en ejecución entre hosts compatibles?**

### ✅ Respuesta correcta: **A**

vMotion permite migrar una VM en ejecución entre hosts compatibles, bajo las condiciones requeridas.

**Por qué las demás no:** CHAP, FLOGI y MPIO pertenecen a otros ámbitos.

---

# Pregunta 10

**¿Qué función está asociada a VMware HA?**

### ✅ Respuesta correcta: **B**

VMware HA puede reiniciar VMs en otros hosts cuando se produce un fallo de host, según la configuración.

**Por qué las demás no:** Crear zonas FC y snapshots de NAS no es la función de HA.

---

# Pregunta 11

**¿Qué es VMFS?**

### ✅ Respuesta correcta: **C**

VMFS es un sistema de archivos utilizado por VMware para determinados datastores.

**Por qué las demás no:** No es RAID, un puerto FC ni un protocolo de autenticación iSCSI.

---

# Pregunta 12

**¿Qué representa un datastore en VMware?**

### ✅ Respuesta correcta: **D**

Un datastore es un recurso de almacenamiento utilizado para alojar archivos de máquinas virtuales.

**Por qué las demás no:** No es una controladora, interfaz de red ni UPS.

---

# Pregunta 13

**¿Qué describe mejor RAID?**

### ✅ Respuesta correcta: **A**

RAID es una tecnología para organizar y/o proteger datos entre varios discos.

**Por qué las demás no:** No es un protocolo de autenticación, una red de almacenamiento ni un hipervisor.

---

# Pregunta 14

**¿Cuál es una característica de RAID 0?**

### ✅ Respuesta correcta: **B**

RAID 0 distribuye datos entre discos sin proporcionar redundancia.

**Por qué las demás no:** Mirroring corresponde a RAID 1; doble paridad a RAID 6; copia remota no es RAID 0.

---

# Pregunta 15

**¿Cuál es una característica de RAID 1?**

### ✅ Respuesta correcta: **C**

RAID 1 utiliza mirroring, es decir, duplicación de datos entre discos.

**Por qué las demás no:** D describe RAID 0 y A/B no corresponden a RAID 1.

---

# Pregunta 16

**¿Cuál es una característica de RAID 5?**

### ✅ Respuesta correcta: **D**

RAID 5 utiliza striping con paridad distribuida y tolera clásicamente el fallo de un disco.

**Por qué las demás no:** No es mirroring de todos los discos, RAID sin redundancia ni replicación entre CPD.

---

# Pregunta 17

**¿Cuál es una característica de RAID 6?**

### ✅ Respuesta correcta: **A**

RAID 6 utiliza doble paridad y tolera clásicamente el fallo de dos discos.

**Por qué las demás no:** B sería ausencia de redundancia; C describe mirroring; D es replicación, no RAID 6.

---

# Pregunta 18

**¿Qué caracteriza a RAID 10?**

### ✅ Respuesta correcta: **B**

RAID 10 combina mirroring y striping.

**Por qué las demás no:** No utiliza doble paridad ni carece de redundancia; tampoco es un backup histórico.

---

# Pregunta 19

**¿Por qué RAID no sustituye al backup?**

### ✅ Respuesta correcta: **C**

RAID no protege por sí mismo frente a borrados, corrupción lógica o determinados desastres.

**Por qué las demás no:** RAID sí puede utilizar varios discos, no elimina siempre los datos y no es exclusivo de NAS.

---

# Pregunta 20

**¿Qué es un Storage Pool?**

### ✅ Respuesta correcta: **D**

Es una agrupación lógica de capacidad de almacenamiento.

**Por qué las demás no:** No es un puerto de switch, HBA ni VM.

---

# Pregunta 21

**¿Qué permite el thin provisioning?**

### ✅ Respuesta correcta: **A**

Permite presentar capacidad lógica de forma flexible y potencialmente sobreasignada respecto a la capacidad física.

**Por qué las demás no:** No elimina la monitorización, no crea capacidad física infinita y no sustituye RAID.

---

# Pregunta 22

**¿Cuál es un riesgo del thin provisioning?**

### ✅ Respuesta correcta: **B**

Puede agotarse la capacidad física aunque todavía exista capacidad lógica provisionada.

**Por qué las demás no:** No elimina zoning, no hace perder WWPN automáticamente ni desactiva HA.

---

# Pregunta 23

**¿Qué hace la deduplicación?**

### ✅ Respuesta correcta: **C**

Reduce datos redundantes evitando almacenar repetidamente bloques iguales, según la implementación.

**Por qué las demás no:** No proporciona alimentación, sustituye el filesystem ni crea rutas FC.

---

# Pregunta 24

**¿Qué hace la compresión?**

### ✅ Respuesta correcta: **D**

Reduce la representación física de los datos mediante algoritmos de compresión.

**Por qué las demás no:** No asigna WWPN, crea LUNs ni configura MPIO.

---

# Pregunta 25

**¿Qué es una snapshot?**

### ✅ Respuesta correcta: **A**

Una snapshot representa un punto en el tiempo de los datos.

**Por qué las demás no:** No es un sustituto universal del backup ni un switch, HBA o dispositivo FC.

---

# Pregunta 26

**¿Por qué una snapshot no equivale necesariamente a un backup?**

### ✅ Respuesta correcta: **B**

Puede depender de la misma infraestructura primaria y perderse junto con ella.

**Por qué las demás no:** No es cierto que nunca pueda recuperarse ni que siempre esté fuera del CPD.

---

# Pregunta 27

**¿Qué diferencia fundamental existe entre replicación y backup?**

### ✅ Respuesta correcta: **C**

La replicación mantiene otra copia operativa; el backup está orientado a recuperación histórica.

**Por qué las demás no:** No son exactamente lo mismo y la replicación no se limita a RAID 0.

---

# Pregunta 28

**¿Qué significa RPO?**

### ✅ Respuesta correcta: **D**

RPO significa Recovery Point Objective.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 29

**¿Qué pregunta responde principalmente el RPO?**

### ✅ Respuesta correcta: **A**

Indica cuántos datos se pueden perder como máximo según el objetivo.

**Por qué las demás no:** No mide hosts, capacidad bruta ni puertos FC.

---

# Pregunta 30

**¿Qué significa RTO?**

### ✅ Respuesta correcta: **B**

RTO significa Recovery Time Objective.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 31

**¿Qué pregunta responde principalmente el RTO?**

### ✅ Respuesta correcta: **C**

Indica cuánto tiempo objetivo puede tardar la recuperación del servicio.

**Por qué las demás no:** No indica discos, LUNs ni cantidad de datos duplicados.

---

# Pregunta 32

**¿Qué mide IOPS?**

### ✅ Respuesta correcta: **D**

IOPS mide operaciones de entrada/salida por segundo.

**Por qué las demás no:** Throughput mide cantidad de datos por unidad de tiempo y latency mide tiempo de respuesta.

---

# Pregunta 33

**¿Qué mide throughput?**

### ✅ Respuesta correcta: **A**

Throughput mide la cantidad de datos transferidos por unidad de tiempo.

**Por qué las demás no:** No es número de operaciones, tiempo de recuperación ni número de paths.

---

# Pregunta 34

**¿Qué mide latency?**

### ✅ Respuesta correcta: **B**

Latency mide el tiempo de respuesta de una operación.

**Por qué las demás no:** No mide LUNs, capacidad del pool ni número de discos.

---

# Pregunta 35

**¿Qué puede provocar una queue depth excesiva?**

### ✅ Respuesta correcta: **C**

Una cola excesiva puede producir contención y aumentar la latencia.

**Por qué las demás no:** No crea RAID, elimina multipath ni aumenta la capacidad física.

---

# Pregunta 36

**¿Qué es oversubscription?**

### ✅ Respuesta correcta: **D**

Es una situación en la que la demanda potencial agregada supera la capacidad de un recurso o enlace.

**Por qué las demás no:** No es una técnica de backup, RAID ni autenticación.

---

# Pregunta 37

**¿Qué objetivo tiene capacity planning?**

### ✅ Respuesta correcta: **A**

Prever capacidad futura considerando crecimiento, consumo y reservas.

**Por qué las demás no:** No consiste solo en configurar WWPN ni sustituye la monitorización.

---

# Pregunta 38

**¿Qué es headroom?**

### ✅ Respuesta correcta: **B**

Es el margen de capacidad reservado para crecimiento, contingencias y operaciones.

**Por qué las demás no:** No es una política de zoning, dirección IP ni tipo de LUN.

---

# Pregunta 39

**¿Qué identifica un WWPN?**

### ✅ Respuesta correcta: **C**

WWPN identifica un puerto Fibre Channel.

**Por qué las demás no:** IQN pertenece a iSCSI; datastore y LUN son conceptos diferentes.

---

# Pregunta 40

**¿Qué identifica un WWNN?**

### ✅ Respuesta correcta: **D**

WWNN identifica un nodo Fibre Channel.

**Por qué las demás no:** No identifica un puerto TCP, LUN ni VM.

---

# Pregunta 41

**¿Qué representa un FCID?**

### ✅ Respuesta correcta: **A**

FCID es un identificador utilizado dentro de una fabric Fibre Channel.

**Por qué las demás no:** No es un identificador iSCSI, filesystem ni nivel RAID.

---

# Pregunta 42

**¿Qué es un F_Port?**

### ✅ Respuesta correcta: **B**

Un F_Port es un puerto del switch FC que conecta un dispositivo final.

**Por qué las demás no:** Un enlace entre switches corresponde a E_Port; las otras opciones no corresponden.

---

# Pregunta 43

**¿Qué es un E_Port?**

### ✅ Respuesta correcta: **C**

E_Port se utiliza para interconectar switches Fibre Channel.

**Por qué las demás no:** No es un puerto iSCSI, controladora ni puerto de HBA.

---

# Pregunta 44

**¿Qué significa ISL?**

### ✅ Respuesta correcta: **D**

ISL significa Inter-Switch Link.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 45

**¿Qué función tiene zoning?**

### ✅ Respuesta correcta: **A**

Zoning controla qué dispositivos pueden comunicarse dentro de la fabric.

**Por qué las demás no:** No determina por sí solo qué LUN ve un host, no crea RAID ni asigna capacidad física.

---

# Pregunta 46

**¿Qué función tiene LUN masking?**

### ✅ Respuesta correcta: **B**

LUN masking controla qué LUN puede ver un determinado host.

**Por qué las demás no:** No crea snapshots, interconecta switches FC ni autentica usuarios Windows.

---

# Pregunta 47

**¿Qué significa FLOGI?**

### ✅ Respuesta correcta: **C**

FLOGI significa Fabric Login.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 48

**¿Qué significa PLOGI?**

### ✅ Respuesta correcta: **D**

PLOGI significa Port Login.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 49

**¿Qué protocolo transporta SCSI sobre TCP/IP?**

### ✅ Respuesta correcta: **A**

iSCSI transporta SCSI sobre redes TCP/IP.

**Por qué las demás no:** NFS y SMB son protocolos de archivos; Fibre Channel no es SCSI sobre TCP/IP.

---

# Pregunta 50

**¿Qué identificador es característico de iSCSI?**

### ✅ Respuesta correcta: **B**

IQN, iSCSI Qualified Name, es un identificador característico de iSCSI.

**Por qué las demás no:** WWPN y FCID pertenecen al ámbito Fibre Channel; NAA es otro tipo de identificador de dispositivos.

---

# Pregunta 51

**¿Cuál es el puerto TCP habitual de iSCSI?**

### ✅ Respuesta correcta: **C**

El puerto TCP habitual de iSCSI es 3260.

**Por qué las demás no:** 443 es HTTPS, 22 SSH y 80 HTTP.

---

# Pregunta 52

**¿Qué función tiene CHAP?**

### ✅ Respuesta correcta: **D**

CHAP proporciona autenticación.

**Por qué las demás no:** No es compresión, RAID ni multipath.

---

# Pregunta 53

**¿Qué es multipath?**

### ✅ Respuesta correcta: **A**

Multipath utiliza múltiples caminos hacia un recurso de almacenamiento.

**Por qué las demás no:** No significa duplicación de archivos, compresión ni snapshots.

---

# Pregunta 54

**¿Qué ventaja proporciona una dual fabric bien diseñada?**

### ✅ Respuesta correcta: **B**

Reduce determinados puntos únicos de fallo de la conectividad de almacenamiento.

**Por qué las demás no:** No duplica automáticamente datos, elimina RAID ni sustituye al backup.

---

# Pregunta 55

**¿Qué significa ALUA?**

### ✅ Respuesta correcta: **C**

ALUA significa Asymmetric Logical Unit Access.

**Por qué las demás no:** Las demás expansiones son incorrectas.

---

# Pregunta 56

**¿Qué puede indicar ALUA?**

### ✅ Respuesta correcta: **D**

ALUA permite identificar qué caminos hacia una LUN son optimizados o no optimizados.

**Por qué las demás no:** No indica RAID 0, administradores ni snapshots.

---

# Pregunta 57

**¿Qué tecnología proporciona multipathing en Windows?**

### ✅ Respuesta correcta: **A**

MPIO proporciona multipathing en Windows.

**Por qué las demás no:** VMFS, VAAI y CHAP cumplen otras funciones.

---

# Pregunta 58

**¿Qué tecnología proporciona multipathing en Linux?**

### ✅ Respuesta correcta: **B**

Device Mapper Multipath proporciona multipathing en Linux.

**Por qué las demás no:** FLOGI, VMFS y SIOC no son la respuesta.

---

# Pregunta 59

**¿Qué es VAAI?**

### ✅ Respuesta correcta: **C**

VAAI son APIs de integración de VMware con cabinas para determinadas operaciones de almacenamiento.

**Por qué las demás no:** No es RAID, filesystem Linux ni protocolo de routing.

---

# Pregunta 60

**¿Qué permite Storage I/O Control?**

### ✅ Respuesta correcta: **D**

Storage I/O Control permite gestionar determinadas prioridades de I/O en VMware.

**Por qué las demás no:** No crea fabrics, configura CHAP ni crea UPS.

---

# Pregunta 61

**¿Qué debe ocurrir idealmente si falla una ruta de almacenamiento en un sistema multipath?**

### ✅ Respuesta correcta: **A**

El tráfico puede continuar por otra ruta disponible.

**Por qué las demás no:** El objetivo del multipath es precisamente mantener acceso mediante caminos alternativos.

---

# Pregunta 62

**¿Qué debe comprobarse antes de instalar firmware nuevo en una infraestructura SAN?**

### ✅ Respuesta correcta: **B**

Hay que comprobar compatibilidad, matriz de soporte, dependencias, rollback y ventana de mantenimiento.

**Por qué las demás no:** No basta con que sea la versión más nueva.

---

# Pregunta 63

**¿Qué componente debe mantenerse separado o protegido especialmente en una arquitectura empresarial?**

### ✅ Respuesta correcta: **C**

El plano de administración debe aislarse/protegerse adecuadamente para reducir riesgos y facilitar la gestión segura.

**Por qué las demás no:** Las otras opciones no son el componente de arquitectura al que se refiere la pregunta.

---

# Pregunta 64

**¿Cuál es una estrategia clásica de backup?**

### ✅ Respuesta correcta: **D**

La regla 3-2-1 es una estrategia clásica de backup.

**Por qué las demás no:** Las demás combinaciones no corresponden a la regla planteada.

---

# Pregunta 65

**¿Qué describe mejor un diseño de DR completo?**

### ✅ Respuesta correcta: **A**

Un DR completo incluye tecnología, procedimientos, personas, documentación y pruebas.

**Por qué las demás no:** Una snapshot, RAID 6 o una segunda HBA por sí solos no constituyen un plan de DR completo.

---

# Pregunta 66

**¿Cuál sería una respuesta adecuada ante un pool thin con 95% de capacidad física utilizada?**

### ✅ Respuesta correcta: **B**

Hay que analizar crecimiento y capacidad disponible antes de aceptar nuevas asignaciones.

**Por qué las demás no:** Asignar más capacidad lógica sin capacidad física suficiente aumenta el riesgo.

---

# Pregunta 67

**Una LUN es visible para ESXi02 y ESXi03 pero no para ESXi01. ¿Qué debe investigarse especialmente?**

### ✅ Respuesta correcta: **C**

Hay que revisar ESXi01, sus paths, HBA, zoning, mapping/masking y realizar un rescan cuando corresponda.

**Por qué las demás no:** Al ser visible desde otros hosts, conviene centrarse inicialmente en el camino/configuración específica de ESXi01.

---

# Pregunta 68

**Una VM presenta 28 ms de latencia de almacenamiento, IOPS muy altas y throughput moderado. ¿Qué métrica merece especial atención?**

### ✅ Respuesta correcta: **D**

La latencia es especialmente relevante porque ya está elevada y puede indicar contención o un cuello de botella de I/O.

**Por qué las demás no:** Capacidad bruta, WWPN y RTO no explican directamente este síntoma de rendimiento.

---

# Pregunta 69

**¿Qué ocurre si dos HBAs de un host dependen del mismo switch FC?**

### ✅ Respuesta correcta: **A**

El switch sigue siendo un posible SPOF.

**Por qué las demás no:** Tener dos HBAs no elimina la dependencia común del mismo switch.

---

# Pregunta 70

**¿Qué principio debe guiar una arquitectura de infraestructura?**

### ✅ Respuesta correcta: **B**

La arquitectura debe diseñarse pensando también en qué ocurre cuando una pieza falla.

**Por qué las demás no:** Las otras opciones contradicen los principios de redundancia y diseño resiliente.

---

# 📚 CORRECCIÓN POR ÁREAS

## 4.1 CPD

Preguntas principales:

```text
1-5
```

Conceptos:

```text
SAN
NAS
UPS
SPOF
Climatización
```

### Lo esencial

```text
UPS
→ continuidad/protección eléctrica

SPOF
→ componente cuya caída puede provocar una pérdida de servicio

Redundancia
→ evitar dependencias únicas

Climatización
→ mantener condiciones ambientales adecuadas
```

---

## 4.2 Virtualización / VMware

Preguntas:

```text
6-12
```

Conceptos:

```text
Virtualización
Host
Cluster
vMotion
HA
VMFS
Datastore
```

---

## 4.3 RAID

Preguntas:

```text
13-19
```

| RAID | Idea principal |
|---|---|
| RAID 0 | Striping sin redundancia |
| RAID 1 | Mirroring |
| RAID 5 | Paridad distribuida, tolerancia clásica a 1 disco |
| RAID 6 | Doble paridad, tolerancia clásica a 2 discos |
| RAID 10 | Mirroring + striping |

### Regla de oro

```text
RAID ≠ Backup
```

---

## 4.4 Storage / protección

Preguntas:

```text
20-38
```

Conceptos:

```text
Storage Pool
Thin Provisioning
Deduplicación
Compresión
Snapshot
Replication
Backup
RPO
RTO
IOPS
Throughput
Latency
Queue Depth
Oversubscription
Capacity Planning
Headroom
```

---

## 4.5 SAN

Preguntas:

```text
39-70
```

Conceptos:

```text
WWPN
WWNN
FCID
F_Port
E_Port
ISL
Zoning
LUN Masking
FLOGI
PLOGI
iSCSI
IQN
TCP 3260
CHAP
Multipath
Dual Fabric
ALUA
MPIO
Device Mapper Multipath
VAAI
SIOC
Firmware
DR
Troubleshooting
SPOF
```

---

# 🧠 TABLA DE CONCEPTOS QUE NO DEBES CONFUNDIR

| Concepto | Qué hace |
|---|---|
| SAN | Proporciona normalmente almacenamiento de bloque |
| NAS | Proporciona normalmente almacenamiento de archivos |
| WWPN | Identifica un puerto FC |
| WWNN | Identifica un nodo FC |
| IQN | Identificador de iSCSI |
| FCID | Identificador dentro de una fabric FC |
| Zoning | Controla conectividad dentro de la fabric |
| LUN Masking | Controla qué LUN ve un host |
| FLOGI | Fabric Login |
| PLOGI | Port Login |
| Multipath | Múltiples caminos hacia almacenamiento |
| ALUA | Distingue características de los caminos |
| MPIO | Multipathing en Windows |
| Device Mapper Multipath | Multipathing en Linux |
| VAAI | Integración VMware-cabina para determinadas operaciones |
| SIOC | Prioridades/control de I/O en VMware |
| Snapshot | Punto temporal |
| Backup | Recuperación de datos |
| Replication | Otra copia operativa |
| RPO | Pérdida de datos objetivo |
| RTO | Tiempo de recuperación objetivo |
| IOPS | Operaciones por segundo |
| Throughput | Datos por unidad de tiempo |
| Latency | Tiempo de respuesta |

---

# 🚨 PREGUNTAS ESPECIALMENTE IMPORTANTES

```text
14-18
→ RAID

19
→ RAID vs Backup

25-27
→ Snapshot / Backup / Replication

28-31
→ RPO / RTO

32-38
→ Rendimiento y capacidad

39-48
→ Fibre Channel

49-53
→ iSCSI / CHAP / Multipath

54-60
→ Dual Fabric / ALUA / VMware Storage

61-70
→ Troubleshooting y arquitectura
```

---

# 🧮 PUNTUACIÓN

```text
+1 → acierto
 0 → blanco
-0,33 → error
```

```text
Puntuación = Aciertos - (Errores × 0,33)
```

Como el simulacro contiene realmente:

```text
70 preguntas
```

el máximo es:

```text
70 puntos
```

---

# 📊 INTERPRETACIÓN ORIENTATIVA

| Puntuación | Nivel |
|---:|---|
| < 35 | 🔴 Necesita bastante repaso |
| 35-44,99 | 🟠 Base irregular |
| 45-54,99 | 🟡 Buen nivel con lagunas |
| 55-61,99 | 🟢 Muy buen nivel |
| 62-66,99 | 🔵 Excelente |
| 67-70 | 🏆 Dominio extraordinario |

---

# 🧠 CÓMO INTERPRETAR TUS FALLOS

### ❌ No tenía ni idea

Prioridad alta. Volver al concepto.

### ❓ Dudé entre dos

Revisar la diferencia entre ambos conceptos.

### 🎲 Acerté de casualidad

No contarlo como dominio consolidado.

### ⚠️ Leí mal

Trabajar lectura y descarte, no necesariamente volver a estudiar todo el tema.

---

# 🏁 CONCLUSIÓN

La idea que deberías poder reconstruir mentalmente es:

```text
CPD
 ↓
Servidores
 ↓
Virtualización
 ↓
VMware
 ↓
Storage
 ↓
RAID
 ↓
NAS / SAN
 ↓
LUN
 ↓
Datastore
 ↓
VMs
 ↓
Backup
 ↓
Replication
 ↓
DR
```

Y dentro de SAN:

```text
Host
 ↓
HBA
 ↓
Fabric
 ↓
Zoning
 ↓
Storage
 ↓
LUN Masking
 ↓
Multipath
 ↓
ALUA
 ↓
Datastore
```

La pregunta que debe acompañar todo el recorrido es:

> **"¿Qué ocurre si esta pieza falla?"**

Si puedes contestarla, ya no estás solamente memorizando infraestructura. Estás empezando a pensar como administrador de infraestructura.

---

# 🎓 FIN DE LA CORRECCIÓN

```text
BLOQUE 4
├── ✓ Teoría
├── ✓ Misión
├── ✓ Soluciones de misión
├── ✓ Simulacro
├── ✓ Plantilla de corrección
└── ✓ Corrección explicada
```
