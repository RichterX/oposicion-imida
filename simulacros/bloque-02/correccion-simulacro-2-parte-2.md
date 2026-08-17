<!-- encabezado-homogeneizado -->
# Bloque 02 - CORRECCION RAZONADA
> **Bloque:** Bloque 02  
> **Documento:** Correccion razonada  
> **Preguntas de referencia:** 35  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 📖 Corrección razonada

## Simulacro 01 · Bloque 2 · Redes

### Parte 3 (Preguntas 36-70)

---

## Pregunta 36

**Respuesta correcta:** **B) Para administrar dispositivos de red como switches o puntos de acceso.**

### Explicación

La **VLAN de gestión** se utiliza para acceder a los dispositivos de red y administrarlos de forma segura.

Por ella suele viajar tráfico destinado a protocolos como:

- SSH.
- HTTPS.
- SNMP.

No debe utilizarse para el tráfico habitual de los usuarios.

---

## Pregunta 37

**Respuesta correcta:** **B) Permitir el paso de varias VLAN entre ambos switches.**

### Explicación

Un enlace configurado como **trunk** permite transportar simultáneamente tráfico de varias VLAN utilizando el etiquetado IEEE 802.1Q.

Sin un enlace troncal, cada VLAN necesitaría un enlace físico independiente.

---

## Pregunta 38

**Respuesta correcta:** **C) DHCP**

### Explicación

DHCP (Dynamic Host Configuration Protocol) permite asignar automáticamente:

- Dirección IP.
- Máscara de red.
- Gateway.
- Servidores DNS.
- Otros parámetros de configuración.

Esto evita la configuración manual de cada equipo.

---

## Pregunta 39

**Respuesta correcta:** **D) Dirección MAC del switch.**

### Explicación

DHCP proporciona parámetros de configuración IP, pero **no informa de la dirección MAC del switch** al cliente.

Normalmente entrega:

- Dirección IP.
- Máscara.
- Gateway.
- DNS.
- Tiempo de concesión (Lease).

---

## Pregunta 40

**Respuesta correcta:** **B) Reserva DHCP.**

### Explicación

Una **reserva DHCP** asocia la dirección MAC de un equipo con una dirección IP concreta.

De esta forma:

- El cliente continúa utilizando DHCP.
- Siempre recibe la misma dirección IP.

Es la opción recomendada para:

- Servidores.
- Impresoras.
- Cámaras IP.
- Equipos que requieren una IP fija.

---

## Pregunta 41

**Respuesta correcta:** **B) Reenviar solicitudes DHCP entre redes distintas.**

### Explicación

Los mensajes DHCP Discover se envían mediante broadcast.

Los routers no reenvían tráfico broadcast.

Por ello, cuando el servidor DHCP está situado en otra red, se utiliza un:

**DHCP Relay**

que encapsula la petición y la reenvía al servidor correspondiente.

---

## Pregunta 42

**Respuesta correcta:** **A) Verificar que la VPN Cliente-Servidor está establecida correctamente.**

### Explicación

El usuario tiene conexión a Internet.

El problema aparece únicamente al intentar acceder a la red corporativa.

La primera comprobación debe centrarse en la VPN:

- ¿Se ha establecido correctamente?
- ¿Está autenticado el usuario?
- ¿Se ha asignado una dirección IP de la VPN?

---

## Pregunta 43

**Respuesta correcta:** **B) El Port Forwarding o la regla DNAT del firewall.**

### Explicación

Si:

- El servidor funciona.
- Desde la LAN puede accederse.

Pero desde Internet no:

Lo primero que debe revisarse es la publicación del servicio.

Normalmente:

- Port Forwarding.
- Regla DNAT.
- Política del firewall.

---

## Pregunta 44

**Respuesta correcta:** **C) Servidor Web público.**

### Explicación

En una DMZ se sitúan servicios accesibles desde Internet, por ejemplo:

- Servidores Web.
- Servidores SMTP públicos.
- Proxies inversos.
- Servidores FTP públicos.

No es recomendable ubicar:

- Controladores de Dominio.
- Bases de datos internas.
- Servidores DHCP.

---

## Pregunta 45

**Respuesta correcta:** **C) Fortinet.**

### Explicación

FortiGate es una familia de firewalls desarrollada por:

**Fortinet.**

Es uno de los fabricantes más utilizados en empresas y administraciones públicas.

---

## Pregunta 46

**Respuesta correcta:** **D) Todas las anteriores.**

### Explicación

Un FortiGate moderno puede integrar numerosas funciones:

- Firewall.
- VPN.
- NAT.
- IPS.
- Filtrado Web.
- Control de aplicaciones.
- Inspección SSL.

Por ello se considera un:

**NGFW (Next Generation Firewall).**

---

## Pregunta 47

**Respuesta correcta:** **B)**

### Explicación

Si:

- Cada VLAN funciona internamente.
- Pero no existe comunicación entre ellas.

Las causas más probables son:

- Trunk mal configurado.
- Inter-VLAN Routing inexistente.
- Política de firewall que bloquea el tráfico.

No guarda relación con DHCP ni con DNS.

---

## Pregunta 48

**Respuesta correcta:** **A) Se utiliza para enviar correo electrónico.**

### Explicación

SMTP es el protocolo utilizado para:

- Enviar mensajes desde el cliente al servidor.
- Transportar correo entre servidores.

La recepción normalmente se realiza mediante:

- IMAP.
- POP3.

---

## Pregunta 49

**Respuesta correcta:** **C)**

### Explicación

Una buena práctica consiste en:

- Mantener el firmware actualizado.
- Revisar periódicamente los registros.
- Cambiar las contraseñas por defecto.
- Aplicar el principio de mínimo privilegio.

Nunca es recomendable:

- Permitir todo el tráfico.
- Desactivar los logs.
- Mantener configuraciones por defecto.

---

## Pregunta 50

**Respuesta correcta:** **B) Colocar el servidor en una DMZ protegida por un firewall.**

### Explicación

La DMZ permite publicar servicios accesibles desde Internet manteniendo separada la red interna.

Si el servidor fuera comprometido:

El atacante no accedería directamente a la LAN.

Es una de las arquitecturas más utilizadas en entornos empresariales.

---

## Pregunta 51

**Respuesta correcta:** **C) nslookup**

### Explicación

`nslookup` permite consultar directamente un servidor DNS.

Por ejemplo:

```cmd
nslookup www.imida.es
```

Es muy útil para verificar:

- Resolución de nombres.
- Registros DNS.
- Servidor DNS utilizado.

En Linux suele emplearse también:

```bash
dig
```

---

## Pregunta 52

**Respuesta correcta:** **B) traceroute**

### Explicación

En Linux:

```bash
traceroute
```

permite visualizar todos los saltos (hops) hasta el destino.

En Windows el comando equivalente es:

```cmd
tracert
```

Esta herramienta resulta especialmente útil para localizar problemas de enrutamiento.

---

> ⚠️ **Ojo en oposición:** Es frecuente que el tribunal combine varias herramientas en una misma pregunta. Conviene recordar rápidamente qué responde cada una:
>
> - `ipconfig` / `ip addr` → Configuración IP.
> - `ping` → Conectividad.
> - `tracert` / `traceroute` → Recorrido de los paquetes.
> - `nslookup` / `dig` → Resolución DNS.
> - `arp` → Correspondencia IP ↔ MAC.
> - `netstat` / `ss` → Conexiones activas.
> - `tcpdump` / `Wireshark` → Captura y análisis de tráfico.

---

## Pregunta 53

**Respuesta correcta:** **B) arp -a**

### Explicación

El comando:

```cmd
arp -a
```

permite visualizar la tabla ARP del equipo.

En ella aparece la correspondencia entre:

- Direcciones IPv4.
- Direcciones MAC.

Ejemplo:

```
192.168.1.1

↓

00-1A-2B-3C-4D-5E
```

Es una herramienta muy útil para diagnosticar problemas dentro de una red local.

---

## Pregunta 54

**Respuesta correcta:** **B) Capturar y analizar el tráfico de red.**

### Explicación

Wireshark es un analizador de protocolos.

Permite:

- Capturar paquetes.
- Analizar protocolos.
- Filtrar tráfico.
- Detectar errores.
- Comprobar el proceso DORA.
- Ver consultas DNS.
- Analizar sesiones TCP.

Es una de las herramientas más utilizadas por administradores de redes.

---

## Pregunta 55

**Respuesta correcta:** **B) ss**

### Explicación

En Linux, el comando moderno para visualizar conexiones de red es:

```bash
ss
```

Sustituye en gran medida a:

```bash
netstat
```

ya que es más rápido y proporciona información más completa.

---

## Pregunta 56

**Respuesta correcta:** **B) Capturar paquetes desde la línea de comandos.**

### Explicación

`tcpdump` permite capturar tráfico de red desde la terminal.

Ejemplo:

```bash
tcpdump -i eth0
```

Es especialmente útil en servidores sin entorno gráfico.

Mientras que Wireshark ofrece una interfaz visual, tcpdump resulta ideal para tareas de administración remota.

---

## Pregunta 57

**Respuesta correcta:** **B) Traducir direcciones IP entre redes.**

### Explicación

La función principal de NAT consiste en sustituir direcciones privadas por direcciones públicas (o viceversa).

No:

- Asigna IP.
- Resuelve nombres.
- Filtra tráfico.

Aunque suele estar integrado en routers y firewalls.

---

## Pregunta 58

**Respuesta correcta:** **C) NAT estático**

### Explicación

En NAT estático existe una relación fija.

Ejemplo:

```
192.168.1.10

↓

83.45.120.10
```

Siempre se utiliza la misma dirección pública.

Es habitual en:

- Servidores Web.
- Servidores VPN.
- Servidores FTP.

---

## Pregunta 59

**Respuesta correcta:** **B) Traduce también los números de puerto.**

### Explicación

PAT significa:

```
Port Address Translation
```

Además de modificar la dirección IP:

También modifica el puerto.

Gracias a ello:

Cientos o miles de equipos pueden compartir una única dirección IP pública.

> ⚠️ Una de las preguntas más habituales en redes consiste precisamente en diferenciar NAT y PAT.

---

## Pregunta 60

**Respuesta correcta:** **B) Port Forwarding**

### Explicación

El Port Forwarding permite redirigir conexiones procedentes de Internet hacia un servidor interno.

Ejemplo:

```
83.45.120.10:80

↓

192.168.1.100:80
```

Es imprescindible para publicar servicios como:

- Web.
- FTP.
- VPN.
- Escritorio remoto.

---

## Pregunta 61

**Respuesta correcta:** **B) SNAT**

### Explicación

SNAT (**Source NAT**) modifica:

La dirección IP de origen.

Es el tipo de NAT utilizado habitualmente cuando los equipos de la red interna acceden a Internet.

---

## Pregunta 62

**Respuesta correcta:** **C) DNAT**

### Explicación

DNAT (**Destination NAT**) modifica:

La dirección IP de destino.

Se emplea principalmente para:

- Publicar servidores.
- Port Forwarding.
- Balanceadores de carga.

---

## Pregunta 63

**Respuesta correcta:** **B) El cliente no ha obtenido una concesión DHCP.**

### Explicación

La dirección:

```
169.254.x.x
```

identifica inmediatamente una dirección:

**APIPA**

Significa que el cliente no ha conseguido comunicarse con el servidor DHCP.

No existe todavía:

- Gateway.
- Dirección IP válida.

---

## Pregunta 64

**Respuesta correcta:** **B) Problema de DNS.**

### Explicación

La situación es muy clara:

```
8.8.8.8

↓

Responde
```

Existe conectividad IP.

Sin embargo:

```
www.google.es

↓

No se resuelve
```

Por tanto:

El problema está en la resolución DNS.

No en Internet.

---

## Pregunta 65

**Respuesta correcta:** **B)**

### Explicación

Sabemos que:

- DHCP funciona.
- DNS funciona.
- Cada VLAN funciona correctamente.

El problema aparece únicamente al comunicar dos VLAN.

La causa más probable es:

- Falta de Inter-VLAN Routing.
- Regla del firewall.
- ACL.

---

## Pregunta 66

**Respuesta correcta:** **A) Revisar el Port Forwarding o la regla DNAT.**

### Explicación

El servidor funciona.

La LAN puede acceder.

Solo falla el acceso desde Internet.

Lo primero que debe revisarse es:

- Publicación del servicio.
- Regla DNAT.
- Port Forwarding.

---

## Pregunta 67

**Respuesta correcta:** **A)**

### Explicación

La VPN consigue establecerse.

Por tanto:

La autenticación parece correcta.

Sin embargo:

El usuario no alcanza la red interna.

La primera comprobación debe centrarse en:

- Rutas.
- Políticas del firewall.
- Redes permitidas por la VPN.

---

## Pregunta 68

**Respuesta correcta:** **C) Alojar el servidor en una DMZ protegida mediante un firewall.**

### Explicación

La DMZ proporciona un equilibrio entre:

- Accesibilidad.
- Seguridad.

En ella se sitúan normalmente:

- Servidores Web.
- Servidores SMTP.
- Proxies.

Nunca deberían situarse directamente junto a los equipos de usuario.

---

## Pregunta 69

**Respuesta correcta:** **C) PAT (Port Address Translation).**

### Explicación

Una única dirección IP pública puede ser compartida por cientos de dispositivos gracias a PAT.

El router mantiene una tabla de traducciones donde asocia:

```
IP privada

+

Puerto

↓

IP pública

+

Puerto
```

Así consigue identificar correctamente cada conexión.

---

## Pregunta 70

**Respuesta correcta:** **C)**

### Explicación

Todas las comprobaciones básicas han resultado correctas:

✅ Dirección IP.

✅ Gateway.

✅ Internet.

✅ DNS.

Por tanto:

El problema probablemente reside en:

- La propia aplicación.
- El servidor Web.
- Una regla del firewall.
- El recorrido hasta el servidor (`tracert`).

Cambiar el servidor DHCP o configurar una dirección APIPA no tiene ninguna relación con la incidencia descrita.

---

# 🎓 Conclusión del simulacro

Este examen ha recorrido prácticamente todos los contenidos del Bloque 2:

- Modelo OSI y TCP/IP.
- Direccionamiento IPv4.
- Ethernet y ARP.
- DNS.
- DHCP.
- VPN.
- VLAN.
- Correo electrónico.
- Firewalls.
- DMZ.
- FortiGate.
- Herramientas de diagnóstico.
- NAT y PAT.

Más allá de comprobar conocimientos teóricos, el objetivo principal ha sido entrenar el razonamiento ante incidencias reales de red, un enfoque muy habitual en las pruebas de oposición y en el trabajo diario de un administrador de sistemas.

---

# 🏆 Balance del Bloque 2

Si has estudiado el manual, resuelto la **Misión 4**, realizado este **simulacro** y revisado toda la **corrección razonada**, deberías ser capaz de:

- Comprender el funcionamiento de una red corporativa de principio a fin.
- Diagnosticar las incidencias más frecuentes relacionadas con conectividad, resolución de nombres, segmentación, acceso remoto y publicación de servicios.
- Seleccionar la herramienta adecuada en función del problema.
- Afrontar con garantías tanto las preguntas tipo test como los supuestos prácticos habituales en la oposición.

El Bloque 2 constituye uno de los pilares fundamentales del temario. Los conceptos estudiados aquí volverán a aparecer en bloques posteriores, especialmente en Virtualización, Cloud, Seguridad, Linux y Windows Server, por lo que dominar esta base facilitará enormemente el estudio del resto del programa.

