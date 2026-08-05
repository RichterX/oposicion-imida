# ✅ Soluciones · Misión 4 · Administrador de Redes

---

# 🧩 Nivel 1 · El ordenador sin red

## 1. ¿Qué tipo de dirección IP ha obtenido el equipo?

Ha obtenido una dirección **APIPA (Automatic Private IP Addressing)**.

En este caso:

```
169.254.18.42
```

Pertenece al rango:

```
169.254.0.0/16
```

---

## 2. ¿Qué significa?

Significa que el equipo **no ha conseguido obtener una dirección IP válida desde un servidor DHCP**.

Windows asigna automáticamente una dirección APIPA para permitir una comunicación limitada dentro del mismo segmento de red.

---

## 3. ¿Qué protocolo ha fallado?

El protocolo implicado es:

**DHCP (Dynamic Host Configuration Protocol).**

El cliente no ha podido completar correctamente el proceso DORA.

---

## 4. ¿Qué comprobaciones realizarías?

Antes de modificar ninguna configuración comprobaría:

- Estado del cable o de la conexión Wi-Fi.
- Estado de la interfaz de red.
- Disponibilidad del servidor DHCP.
- Configuración del switch.
- Configuración de la VLAN correspondiente.
- Posibles bloqueos en el firewall.

Siempre es preferible diagnosticar antes de cambiar parámetros.

---

## 5. ¿Qué comando utilizarías?

En Windows:

```cmd
ipconfig /release
ipconfig /renew
```

Con estos comandos se libera la concesión DHCP y se solicita una nueva dirección IP.

---

# 🧩 Nivel 2 · ¿Dónde está el problema?

## 1. ¿Qué sabemos?

Sabemos que:

- El equipo tiene una IP válida.
- El gateway responde correctamente.
- La red local funciona.

---

## 2. ¿Dónde buscarías el problema?

El problema se encuentra **más allá del gateway**.

Podría tratarse de:

- Router.
- Firewall.
- NAT.
- Conexión WAN.
- ISP.

---

## 3. ¿Qué herramientas utilizarías?

Continuaría con:

```cmd
tracert 8.8.8.8
```

y posteriormente:

```cmd
nslookup google.es
```

También revisaría el estado del firewall y del router.

---

## 4. ¿Podría ser DNS?

No.

Si:

```text
ping 8.8.8.8
```

no responde,

todavía no sabemos si DNS funciona.

Primero debe existir conectividad IP.

---

# 🧩 Nivel 3 · El misterio de Google

## 1. ¿Qué servicio está fallando?

El servicio DNS.

La conectividad IP funciona correctamente, pero no se resuelven nombres.

---

## 2. ¿Qué herramienta utilizarías?

```cmd
nslookup google.es
```

En Linux:

```bash
dig google.es
```

---

## 3. ¿Qué registros participan?

Habitualmente:

- Registro A (IPv4).
- Registro AAAA (IPv6).

En otros escenarios también podrían intervenir CNAME u otros registros.

---

## 4. ¿Qué servidor DNS utiliza el equipo?

Se obtiene mediante:

```cmd
ipconfig /all
```

o

```bash
cat /etc/resolv.conf
```

(según el sistema operativo).

---

# 🧩 Nivel 4 · El servidor desaparecido

## 1. ¿Qué concepto explica la situación?

Las VLAN constituyen redes independientes.

La comunicación entre ellas requiere:

**Inter-VLAN Routing.**

---

## 2. ¿Qué dispositivo debería comunicar ambas VLAN?

Un:

- Router.

o

- Switch de Capa 3.

---

## 3. ¿Qué revisarías?

- Configuración del gateway.
- Interfaces VLAN.
- Tabla de rutas.
- Políticas del firewall.
- ACL.
- Configuración del switch.

---

## 4. ¿Qué comando utilizarías?

```cmd
tracert
```

o

```bash
traceroute
```

Permiten identificar dónde deja de avanzar la comunicación.

---

# 🧩 Nivel 5 · El servidor Web

## 1. ¿Qué revisarías?

Lo primero sería comprobar la configuración de:

**Port Forwarding (DNAT).**

---

## 2. ¿Qué NAT interviene?

Principalmente:

**DNAT**, ya que modifica la dirección de destino para redirigir la conexión hacia el servidor interno.

---

## 3. ¿Qué función desempeña la DMZ?

La DMZ permite alojar servidores accesibles desde Internet manteniéndolos separados de la red interna.

---

## 4. ¿Por qué no situarlo en la LAN?

Porque una posible intrusión afectaría directamente a la red corporativa.

La DMZ añade una capa adicional de aislamiento.

---

# 🧩 Nivel 6 · El correo perdido

## 1. ¿Qué registro revisarías?

El registro:

**MX (Mail Exchange).**

---

## 2. ¿Qué protocolo envía el correo?

**SMTP.**

---

## 3. ¿Qué protocolo utilizaría el usuario?

Normalmente:

**IMAP.**

Permite sincronizar el correo entre varios dispositivos.

---

## 4. Recorrido del correo

1. Cliente de correo.
2. Servidor SMTP.
3. Consulta DNS.
4. Registro MX.
5. Resolución A/AAAA.
6. Servidor SMTP destino.
7. Buzón.
8. Cliente IMAP.

---

# 🧩 Nivel 7 · El teletrabajador

## 1. ¿Qué tecnología utilizarías?

Una:

**VPN.**

---

## 2. Tipos principales

- VPN Cliente-Servidor.
- VPN Site-to-Site.

---

## 3. ¿Cuál utilizarías?

En este caso:

**VPN Cliente-Servidor.**

El usuario trabaja desde su domicilio y necesita acceder a la red corporativa.

---

## 4. ¿Qué dispositivo suele gestionarla?

Habitualmente:

- Firewall.
- Router empresarial.
- FortiGate.

---

# 🧩 Nivel 8 · El administrador de redes

## 1. Función del FortiGate

Protege la red mediante:

- Firewall.
- NAT.
- VPN.
- ACL.
- Filtrado de tráfico.
- Registro de eventos.

---

## 2. ¿Por qué existen varias VLAN?

Para:

- Segmentar la red.
- Reducir el dominio de broadcast.
- Mejorar la seguridad.
- Facilitar la administración.

---

## 3. ¿Cómo obtiene un equipo su IP?

Mediante DHCP.

Proceso:

```
Discover

↓

Offer

↓

Request

↓

ACK
```

---

## 4. ¿Cómo localiza el servidor Web?

Consulta DNS.

Obtiene un registro:

- A.

o

- AAAA.

Posteriormente establece la conexión utilizando la dirección IP obtenida.

---

## 5. ¿Cómo accede a Internet?

El router o firewall realiza:

**NAT/PAT.**

Traduce la dirección privada por una dirección pública.

---

## 6. ¿Qué herramientas utilizarías?

Siguiendo un procedimiento ordenado:

1.

```cmd
ipconfig
```

2.

```cmd
ping gateway
```

3.

```cmd
ping 8.8.8.8
```

4.

```cmd
nslookup
```

5.

```cmd
tracert
```

6.

```cmd
netstat
```

7.

```bash
tcpdump
```

o

Wireshark.

---

## 7. Función del gateway

Es el dispositivo que permite salir de la red local hacia otras redes.

Todo tráfico dirigido a una red distinta pasa inicialmente por él.

---

## 8. ¿Qué ocurriría si desapareciera DNS?

Los usuarios seguirían pudiendo comunicarse mediante direcciones IP.

Sin embargo:

No podrían utilizar nombres de dominio.

Por ejemplo:

```
https://www.google.es
```

dejaría de funcionar,

mientras que:

```
142.250.xxx.xxx
```

seguiría siendo accesible.

---

# 🏆 Evaluación de la misión

| Aciertos | Nivel |
|----------:|-------|
| 90-100 % | Excelente. Dominas el bloque y estás preparado para afrontar supuestos prácticos de redes. |
| 75-89 % | Muy buen nivel. Conviene repasar algunos conceptos concretos antes del simulacro. |
| 60-74 % | Nivel aceptable, pero es recomendable revisar los capítulos de DNS, VLAN y Firewalls. |
| < 60 % | Es aconsejable volver a estudiar el bloque antes de realizar el simulacro de examen. |

---

# 📖 Conclusión

Si has resuelto correctamente esta misión significa que eres capaz de:

- Diagnosticar incidencias de red siguiendo un procedimiento lógico.
- Relacionar DHCP, DNS, VLAN, VPN, Firewalls y NAT.
- Seleccionar la herramienta adecuada para cada situación.
- Interpretar correctamente los resultados obtenidos.
- Razonar como un administrador de sistemas ante problemas reales.

La misión reproduce situaciones habituales en entornos empresariales y sirve como preparación tanto para los supuestos prácticos como para las preguntas de razonamiento que suelen aparecer en las oposiciones.
