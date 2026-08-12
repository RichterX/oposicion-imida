# Tarjetas - Bloque 04 - 4.4 RAID

Formato:
P: Pregunta
R: Respuesta

---

## 4.4 RAID

P: Que significa RAID?
R: Redundant Array of Independent Disks.

P: Que objetivo general tiene RAID?
R: Combinar discos para optimizar capacidad, rendimiento y/o tolerancia a fallos.

P: Que es un RAID array?
R: Conjunto de discos fisicos organizados bajo un nivel RAID concreto.

P: Diferencia entre disco fisico y disco logico en RAID?
R: Fisico es el dispositivo real; logico es el volumen presentado por el controlador.

P: Diferencia entre RAID hardware y software?
R: Hardware usa controlador dedicado; software lo gestiona el SO.

P: Que es un hot spare?
R: Disco de reserva que entra automaticamente al fallar uno del array.

P: Que es rebuild?
R: Proceso de reconstruccion de datos tras fallo/sustitucion de disco.

P: Que significa estado degradado?
R: El RAID sigue operando pero con menor resiliencia y posible penalizacion de rendimiento.

P: RAID es backup?
R: No. RAID mejora disponibilidad local, no protege frente a borrado, ransomware o corrupcion logica.

P: Que aporta RAID 0?
R: Alto rendimiento y capacidad total, sin tolerancia a fallos.

P: Que aporta RAID 1?
R: Espejo de datos con alta tolerancia, pero menor capacidad util.

P: Diferencia clave RAID 5 vs RAID 6?
R: RAID 5 tolera 1 disco; RAID 6 tolera 2 discos.

P: Que caracteriza RAID 10?
R: Combinacion de mirror + striping con buen rendimiento y resiliencia.

P: Que metricas de almacenamiento debes vigilar?
R: IOPS, throughput y latencia.

---

## Tarjetas de repaso transversal (4.4)

P: Donde se ubica RAID en arquitectura real?
R: Es una capa dentro del stack de almacenamiento, no toda la solucion.

P: Error comun de diseno?
R: Elegir nivel RAID solo por capacidad sin considerar carga, ventana de rebuild y riesgo.

P: Objetivo final al disenar RAID?
R: Equilibrio realista entre coste, rendimiento, resiliencia y operabilidad.
