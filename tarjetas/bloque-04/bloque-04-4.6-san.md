# Tarjetas - Bloque 04 - 4.6 SAN

Formato:
P: Pregunta
R: Respuesta

---

## 4.6 SAN

P: Que significa SAN?
R: Storage Area Network.

P: Que tipo de almacenamiento entrega normalmente SAN?
R: Almacenamiento a nivel de bloque (block-level).

P: Diferencia fundamental NAS vs SAN?
R: NAS entrega archivos; SAN entrega dispositivos de bloque.

P: Que es una LUN?
R: Unidad logica de almacenamiento presentada por la cabina al host.

P: Que es un initiator y un target en iSCSI?
R: Initiator es el cliente/host que inicia sesion; target es el sistema que ofrece bloques.

P: Que es un HBA?
R: Adaptador especializado de host para conectividad SAN (p. ej., Fibre Channel).

P: Que es Fibre Channel fabric?
R: Tejido de red SAN FC formado por switches y enlaces FC.

P: Diferencia entre WWNN y WWPN?
R: WWNN identifica nodo; WWPN identifica puerto FC.

P: Que es zoning?
R: Mecanismo FC para controlar que initiators ven que targets.

P: Que es LUN masking?
R: Control en cabina para limitar que host accede a cada LUN.

P: Para que sirve multipath (MPIO)?
R: Usar multiples rutas para resiliencia y, segun politica, reparto de carga.

P: Puerto habitual de iSCSI?
R: TCP 3260.

P: Por que SAN es clave en virtualizacion empresarial?
R: Permite almacenamiento compartido para clusters, HA y movilidad de VMs.

P: Que diferencia hay entre FCID y WWPN?
R: FCID es direccion en el fabric; WWPN es identidad persistente de puerto.

---

## Tarjetas de repaso transversal (4.6)

P: Que principio evita errores graves en SAN?
R: Separar claramente identidad, visibilidad y permisos (zoning + masking + autenticacion).

P: Error comun en examen sobre SAN?
R: Confundir acceso por archivos con acceso por bloques.

P: Objetivo final de una SAN bien diseniada?
R: Almacenamiento de bloques de alto rendimiento, resiliente y controlado para servicios criticos.
