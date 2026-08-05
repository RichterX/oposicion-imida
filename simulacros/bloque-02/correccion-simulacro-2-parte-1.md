# 📖 Corrección razonada

## Simulacro 01 · Bloque 2 · Redes

### Parte 1 (Preguntas 1-35)

---

## Pregunta 1

**Respuesta correcta:** **B) Capa de Red.**

### Explicación

La **Capa de Red (Nivel 3 del modelo OSI)** es responsable del direccionamiento lógico mediante direcciones IP y del encaminamiento (routing) de paquetes entre redes.

Las demás opciones son incorrectas porque:

- **A)** La Capa de Enlace utiliza direcciones MAC.
- **C)** La Capa de Transporte gestiona puertos y comunicaciones extremo a extremo.
- **D)** La Capa Física transmite únicamente bits.

> ⚠️ En oposición suelen preguntar la diferencia entre **MAC (Capa 2)** e **IP (Capa 3)**.

---

## Pregunta 2

**Respuesta correcta:** **C) 192.168.30.0**

### Explicación

Una máscara **/24** deja los primeros 24 bits para la red.

La dirección:

```
192.168.30.45/24
```

pertenece a la red:

```
192.168.30.0
```

El broadcast sería:

```
192.168.30.255
```

---

## Pregunta 3

**Respuesta correcta:** **C) ARP**

### Explicación

ARP (Address Resolution Protocol) permite obtener la dirección MAC asociada a una dirección IPv4 dentro de una red local.

No debe confundirse con:

- DHCP → asigna direcciones IP.
- DNS → resuelve nombres.
- ICMP → mensajes de control.

---

## Pregunta 4

**Respuesta correcta:** **B) 172.20.0.0/16**

### Explicación

El rango privado correspondiente es:

```
172.16.0.0

↓

172.31.255.255
```

Por tanto:

```
172.20.0.0
```

pertenece a dicho rango.

Las demás opciones corresponden a direcciones públicas o reservadas para otros fines.

---

## Pregunta 5

**Respuesta correcta:** **B)**

### Explicación

TCP/IP fue desarrollado antes que el modelo OSI y constituye la base del funcionamiento de Internet.

El modelo OSI es principalmente un modelo de referencia utilizado con fines didácticos.

---

## Pregunta 6

**Respuesta correcta:** **C) Switch**

### Explicación

Un switch trabaja en la **Capa 2**, utilizando direcciones MAC para reenviar tramas únicamente al puerto correspondiente.

Los routers utilizan direcciones IP.

---

## Pregunta 7

**Respuesta correcta:** **B)**

### Explicación

La encapsulación consiste en añadir la información necesaria de cada capa durante el proceso de transmisión.

Cada protocolo añade su propia cabecera.

Posteriormente, en el destino, se realiza el proceso inverso:

**Desencapsulación.**

---

## Pregunta 8

**Respuesta correcta:** **C) ipconfig**

### Explicación

En Windows:

```cmd
ipconfig
```

permite visualizar:

- Dirección IP.
- Máscara.
- Gateway.

Mientras que:

```cmd
ipconfig /all
```

muestra información adicional como DNS, DHCP o dirección MAC.

---

## Pregunta 9

**Respuesta correcta:** **C) /26**

### Explicación

La máscara:

```
255.255.255.192
```

equivale al prefijo:

```
/26
```

Es una pregunta clásica de examen.

Conviene memorizar las máscaras más habituales:

| Máscara | CIDR |
|----------|------|
|255.255.255.0|/24|
|255.255.255.128|/25|
|255.255.255.192|/26|
|255.255.255.224|/27|

---

## Pregunta 10

**Respuesta correcta:** **C) ICMP**

### Explicación

Ping utiliza mensajes:

- Echo Request.
- Echo Reply.

Ambos pertenecen al protocolo ICMP.

No utiliza TCP ni UDP para comprobar la conectividad.

---

## Pregunta 11

**Respuesta correcta:** **C) Broadcast**

### Explicación

Cuando el cliente todavía no dispone de dirección IP desconoce dónde se encuentra el servidor DHCP.

Por ello envía el mensaje:

```
DHCP Discover
```

mediante broadcast.

---

## Pregunta 12

**Respuesta correcta:** **C) MX**

### Explicación

Los registros:

**MX (Mail Exchange)**

indican qué servidores reciben el correo de un dominio.

Ejemplo:

```
empresa.es

↓

mail.empresa.es
```

---

## Pregunta 13

**Respuesta correcta:** **C) Router**

### Explicación

Los routers comunican redes IP distintas.

Un switch de capa 2 únicamente trabaja dentro de la misma red.

---

## Pregunta 14

**Respuesta correcta:** **C) 169.254.x.x**

### Explicación

Las direcciones:

```
169.254.0.0/16
```

corresponden a:

**APIPA**

e indican normalmente que el cliente no ha conseguido obtener una dirección IP mediante DHCP.

> ⚠️ Muy preguntado en oposiciones.

---

## Pregunta 15

**Respuesta correcta:** **B)**

### Explicación

Una VLAN es una segmentación lógica de una red de Capa 2.

Permite dividir un mismo switch físico en varias redes independientes.

---

## Pregunta 16

**Respuesta correcta:** **B)**

### Explicación

Un puerto configurado como:

```
Access
```

pertenece únicamente a una VLAN.

Es el tipo de puerto utilizado para conectar equipos finales.

---

## Pregunta 17

**Respuesta correcta:** **C) IEEE 802.1Q**

### Explicación

El estándar IEEE 802.1Q permite etiquetar tramas Ethernet para transportar múltiples VLAN a través de un mismo enlace físico (trunk).

---

## Pregunta 18

**Respuesta correcta:** **B)**

### Explicación

Si el cliente:

- llega al gateway,
- pero no puede acceder a 8.8.8.8,

la red local funciona correctamente.

El problema debe encontrarse más allá del gateway:

- Router.
- Firewall.
- NAT.
- ISP.
- Salida a Internet.

Todavía no podemos culpar al DNS, ya que ni siquiera existe conectividad IP hacia Internet.

> ⚠️ **Trampa clásica:** muchos candidatos responden "DNS". Sin embargo, DNS solo debe sospecharse cuando **las direcciones IP funcionan**, pero **los nombres no**.

---

## Pregunta 19

**Respuesta correcta:** **C) SMTP**

### Explicación

SMTP (**Simple Mail Transfer Protocol**) es el protocolo utilizado para el **envío de correo electrónico**.

Se emplea:

- Del cliente al servidor de correo.
- Entre servidores de correo.

No debe confundirse con:

- **POP3** → descarga correo.
- **IMAP** → sincroniza correo.

---

## Pregunta 20

**Respuesta correcta:** **B) Sincroniza el buzón entre varios dispositivos.**

### Explicación

La principal ventaja de IMAP consiste en que los mensajes permanecen almacenados en el servidor.

Esto permite acceder al mismo buzón desde:

- Ordenador.
- Móvil.
- Tablet.

Manteniendo siempre la misma información sincronizada.

---

## Pregunta 21

**Respuesta correcta:** **B) Traducir nombres de dominio en direcciones IP.**

### Explicación

DNS funciona como la "agenda telefónica" de Internet.

Por ejemplo:

```
www.imida.es

↓

150.xxx.xxx.xxx
```

Sin DNS sería necesario memorizar direcciones IP para acceder a cualquier servicio.

---

## Pregunta 22

**Respuesta correcta:** **C) tracert**

### Explicación

En Windows:

```cmd
tracert
```

muestra el recorrido seguido por los paquetes hasta el destino.

En Linux el comando equivalente es:

```bash
traceroute
```

---

## Pregunta 23

**Respuesta correcta:** **B) Falta el enrutamiento entre VLAN.**

### Explicación

Cada VLAN constituye una red independiente.

Para que dos VLAN puedan comunicarse es necesario:

- Inter-VLAN Routing.

Este proceso suele realizarlo:

- Un router.
- Un switch de Capa 3.

---

## Pregunta 24

**Respuesta correcta:** **C) Discover → Offer → Request → ACK**

### Explicación

El proceso DORA consta de cuatro pasos:

```
Discover

↓

Offer

↓

Request

↓

ACK
```

Es uno de los conceptos más preguntados sobre DHCP.

---

## Pregunta 25

**Respuesta correcta:** **B) Revisar el servicio DNS utilizando nslookup o dig.**

### Explicación

El escenario nos indica que:

- Existe dirección IP.
- El gateway responde.
- Internet funciona (8.8.8.8 responde).

Sin embargo:

```
empresa.local
```

no puede resolverse.

Todo apunta a un problema de resolución DNS.

La herramienta adecuada es:

```
nslookup
```

o

```
dig
```

---

## Pregunta 26

**Respuesta correcta:** **B) IPsec**

### Explicación

IPsec es el protocolo más utilizado para implementar VPN Site-to-Site.

Proporciona:

- Confidencialidad.
- Integridad.
- Autenticación.

---

## Pregunta 27

**Respuesta correcta:** **B)**

### Explicación

Una VPN Cliente-Servidor conecta un usuario remoto con la red corporativa.

Por el contrario:

Una VPN Site-to-Site conecta dos redes completas.

---

## Pregunta 28

**Respuesta correcta:** **C) VPN Site-to-Site**

### Explicación

Cuando dos sedes deben permanecer conectadas de forma permanente:

La solución adecuada es:

```
VPN Site-to-Site
```

No tendría sentido crear una VPN Cliente-Servidor para cada usuario.

---

## Pregunta 29

**Respuesta correcta:** **C) IMAP**

### Explicación

IMAP permite consultar el correo manteniendo el contenido sincronizado en múltiples dispositivos.

Actualmente es el protocolo más utilizado en entornos corporativos.

---

## Pregunta 30

**Respuesta correcta:** **B)**

### Explicación

Una DMZ es una red independiente destinada a alojar servidores accesibles desde Internet.

Su objetivo consiste en evitar que dichos servidores formen parte directamente de la red interna.

---

## Pregunta 31

**Respuesta correcta:** **C)**

### Explicación

El firewall controla el tráfico de red mediante reglas de seguridad.

Puede:

- Permitir.
- Denegar.
- Registrar.

las comunicaciones según las políticas configuradas.

---

## Pregunta 32

**Respuesta correcta:** **B) Stateful Inspection**

### Explicación

Stateful Inspection mantiene información sobre las conexiones activas.

Gracias a ello puede distinguir:

- Conexiones nuevas.
- Conexiones establecidas.
- Respuestas válidas.

A diferencia del simple filtrado de paquetes.

---

## Pregunta 33

**Respuesta correcta:** **B)**

### Explicación

Una ACL (Access Control List) es un conjunto ordenado de reglas.

Cada paquete se compara con dichas reglas.

Cuando encuentra la primera coincidencia:

Se aplica la acción correspondiente.

---

## Pregunta 34

**Respuesta correcta:** **C)**

### Explicación

Las ACL se procesan de arriba hacia abajo.

La primera regla que coincide determina la acción.

El firewall no continúa evaluando el resto.

Por ello:

El orden de las reglas resulta fundamental.

---

## Pregunta 35

**Respuesta correcta:** **B)**

### Explicación

La VLAN nativa es aquella utilizada para transportar tráfico **sin etiquetar** en un enlace troncal 802.1Q.

No debe confundirse con:

- VLAN de gestión.
- VLAN de acceso.

Cada una cumple una función distinta.

> ⚠️ **Trampa habitual:** muchos candidatos confunden la VLAN nativa con la VLAN de gestión. La primera define cómo se trata el tráfico sin etiqueta en un troncal; la segunda se utiliza para administrar dispositivos de red.

---