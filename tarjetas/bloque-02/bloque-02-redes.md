# Tarjetas - Bloque 02 (Redes)

Formato:
P: Pregunta
R: Respuesta

---

## 2.1 Introduccion a redes

P: Que es una red informatica?
R: Un conjunto de dispositivos interconectados que comparten informacion, recursos y servicios mediante protocolos.

P: Que son los protocolos de red?
R: Reglas que definen como se comunican los dispositivos.

P: Cuales son componentes basicos de una red?
R: Clientes, servidores, dispositivos de interconexion y medio de transmision.

## 2.2 Direccionamiento IP

P: Para que sirve una direccion IP?
R: Para identificar de forma logica un dispositivo en una red.

P: Diferencia principal entre IPv4 e IPv6?
R: IPv4 usa 32 bits; IPv6 usa 128 bits y permite muchas mas direcciones.

P: Que indica una mascara de red?
R: Que parte de la direccion identifica la red y que parte identifica el host.

## 2.3 Ethernet

P: Que es Ethernet?
R: Tecnologia de red LAN estandar para comunicacion por tramas en capa de enlace.

P: Que dispositivo trabaja principalmente en redes Ethernet LAN?
R: El switch.

P: Que identifica de forma unica a una interfaz de red en Ethernet?
R: La direccion MAC.

## 2.4 DNS

P: Para que sirve DNS?
R: Para resolver nombres de dominio a direcciones IP.

P: Que ventaja ofrece DNS frente a memorizar IP?
R: Facilita acceso a servicios con nombres legibles por humanos.

P: Que es un registro A en DNS?
R: Un registro que asocia un nombre con una direccion IPv4.

## 2.5 DHCP

P: Para que sirve DHCP?
R: Para asignar automaticamente configuracion IP a clientes.

P: Que parametros suele entregar DHCP?
R: IP, mascara, puerta de enlace y servidores DNS.

P: Que beneficio operativo aporta DHCP?
R: Reduce errores manuales y acelera el despliegue de equipos.

## 2.6 VPN

P: Que es una VPN?
R: Un tunel cifrado sobre una red publica para conectar usuarios o sedes de forma segura.

P: Para que se usa una VPN en administracion?
R: Para acceso remoto seguro a recursos internos.

P: Que mejora principal aporta frente a trafico sin tunel?
R: Confidencialidad e integridad de la comunicacion.

## 2.7 VLAN

P: Que es una VLAN?
R: Una red logica que segmenta una red fisica en dominios de broadcast separados.

P: Beneficio principal de usar VLAN?
R: Mejorar seguridad, orden y rendimiento al separar trafico.

P: Que tipo de enlace transporta varias VLAN entre switches?
R: Un enlace trunk.

## 2.8 Correo electronico

P: Protocolo tipico para envio de correo?
R: SMTP.

P: Protocolos habituales para recepcion de correo?
R: IMAP o POP3.

P: Que componente filtra spam y malware en correo?
R: Pasarelas de correo y motores antispam/antimalware.

## 2.9 Firewalls

P: Que es un firewall?
R: Sistema que filtra trafico de red segun reglas de seguridad.

P: Que principio se recomienda al definir reglas?
R: Minimo privilegio: permitir solo lo necesario.

P: Diferencia rapida entre firewall de red y firewall de host?
R: El de red protege segmentos completos; el de host protege un equipo concreto.

## 2.10 Herramientas de diagnostico

P: Para que sirve ping?
R: Verificar conectividad IP basica y latencia aproximada.

P: Para que sirve traceroute/tracert?
R: Mostrar saltos intermedios hasta un destino.

P: Para que sirve nslookup o dig?
R: Consultar y diagnosticar resolucion DNS.

## 2.11 NAT y PAT

P: Que es NAT?
R: Traduccion de direcciones IP entre redes, normalmente privadas y publicas.

P: Que es PAT?
R: Variante de NAT que tambien traduce puertos para multiplexar multiples hosts sobre una IP publica.

P: Ventaja principal de PAT en redes corporativas?
R: Permite salida a Internet de muchos equipos con pocas IP publicas.

---

## Tarjetas de repaso transversal (Redes)

P: Cual es la secuencia basica para diagnosticar una caida de servicio de red?
R: Verificar capa fisica, IP local, puerta de enlace, DNS, rutas y filtrado de firewall.

P: Que combinacion de servicios suele ser critica para usuarios finales?
R: DHCP para obtener IP y DNS para resolver nombres.

P: Que error comun provoca problemas intermitentes en red?
R: Solapamiento de IP o configuraciones manuales inconsistentes.

P: Que principio de diseno mejora seguridad y operacion?
R: Segmentacion por VLAN y politicas de minimo privilegio.

P: Objetivo final de una red bien administrada?
R: Conectividad estable, segura, documentada y facil de escalar.
