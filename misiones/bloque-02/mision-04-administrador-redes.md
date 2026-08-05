# 🗡️ Misión 4 · Administrador de Redes

**Bloque:** Redes

**Nivel:** ⭐⭐⭐⭐⭐

**Duración estimada:** 3-5 horas

**Objetivo:** Diagnosticar y resolver incidencias de red utilizando los conocimientos adquiridos en el Bloque 2.

---

# 📖 Introducción

Es tu primer día como Administrador de Sistemas en una empresa con unos 250 empleados.

La infraestructura de red fue renovada hace pocos días y varios usuarios han comenzado a reportar incidencias.

Tu responsable te entrega la siguiente información:

## Infraestructura

- Router/Firewall FortiGate.
- Switch gestionable.
- VLAN para Administración.
- VLAN para RRHH.
- VLAN para Servidores.
- VLAN para Invitados.
- Servidor DHCP.
- Servidor DNS interno.
- Servidor Web en DMZ.
- Servidor de correo.
- VPN para teletrabajadores.

No puedes modificar la infraestructura sin antes localizar correctamente el problema.

Tu trabajo consiste en diagnosticar cada incidencia siguiendo un procedimiento lógico.

---

# 🎯 Objetivos de la misión

Durante esta misión deberás demostrar que eres capaz de:

- Analizar problemas de conectividad.
- Diagnosticar incidencias utilizando las herramientas adecuadas.
- Comprender el funcionamiento de DHCP, DNS, VLAN y NAT.
- Identificar errores de configuración habituales.
- Razonar antes de actuar.

---

# 🧩 Nivel 1 · El ordenador sin red

Un usuario del departamento de Administración llama indicando:

> "No tengo Internet."

Ejecutas:

```cmd
ipconfig
```

Obtienes:

```text
IPv4.............169.254.18.42

Máscara..........255.255.0.0

Gateway..........(vacío)
```

## Preguntas

1. ¿Qué tipo de dirección IP ha obtenido el equipo?

2. ¿Qué significa?

3. ¿Qué protocolo ha fallado?

4. ¿Qué comprobaciones realizarías antes de cambiar ninguna configuración?

5. ¿Qué comando utilizarías para obtener una nueva concesión DHCP?

---

# 🧩 Nivel 2 · ¿Dónde está el problema?

Tras renovar la concesión DHCP:

```text
IPv4

192.168.10.25

Gateway

192.168.10.1

DNS

192.168.30.5
```

Ahora ejecutas:

```cmd
ping 192.168.10.1
```

Respuesta:

Correcta.

Posteriormente:

```cmd
ping 8.8.8.8
```

No responde.

## Preguntas

1. ¿Qué sabemos ya con seguridad?

2. ¿En qué parte de la red buscarías el problema?

3. ¿Qué herramientas utilizarías a continuación?

4. ¿Podría tratarse de un problema DNS? Justifica la respuesta.

---

# 🧩 Nivel 3 · El misterio de Google

Ahora ocurre lo siguiente:

```cmd
ping 8.8.8.8
```

Funciona.

Sin embargo:

```cmd
ping google.es
```

Devuelve:

```
No se puede resolver el nombre.
```

## Preguntas

1. ¿Qué servicio está fallando?

2. ¿Qué herramienta utilizarías para confirmarlo?

3. ¿Qué registros DNS participan normalmente cuando un navegador accede a una página web?

4. ¿Qué servidor DNS está utilizando el equipo?

---

# 🧩 Nivel 4 · El servidor desaparecido

Los usuarios de Administración necesitan acceder a un servidor situado en la VLAN de Servidores.

Las configuraciones IP son correctas.

El servidor responde desde otros equipos de la misma VLAN.

Sin embargo:

Los equipos de Administración no pueden acceder.

## Preguntas

1. ¿Qué concepto explica esta situación?

2. ¿Qué dispositivo debería permitir la comunicación?

3. ¿Qué configuración revisarías?

4. ¿Qué comando utilizarías para comprobar hasta dónde llegan los paquetes?

---

# 🧩 Nivel 5 · El servidor Web

La empresa publica su página web corporativa.

Los usuarios internos pueden acceder.

Los usuarios desde Internet reciben:

```
Tiempo de espera agotado.
```

Sabes que:

- El servidor funciona.
- La DMZ existe.
- El firewall está operativo.

## Preguntas

1. ¿Qué mecanismo revisarías primero?

2. ¿Qué tipo de NAT podría intervenir?

3. ¿Qué función desempeña la DMZ?

4. ¿Por qué no conviene colocar este servidor dentro de la LAN?

---

# 🧩 Nivel 6 · El correo perdido

Un cliente afirma que los correos enviados a:

```
usuario@empresa.es
```

Nunca llegan.

La página web funciona correctamente.

## Preguntas

1. ¿Qué registro DNS revisarías primero?

2. ¿Qué protocolo utiliza el servidor para enviar correo?

3. ¿Qué protocolo utilizará normalmente el usuario para consultar su buzón desde varios dispositivos?

4. Describe el recorrido completo que sigue un correo electrónico desde el remitente hasta el destinatario.

---

# 🧩 Nivel 7 · El teletrabajador

Un empleado trabaja desde casa.

Puede conectarse a Internet.

Pero no puede acceder a los recursos internos de la empresa.

## Preguntas

1. ¿Qué tecnología debería utilizar?

2. ¿Qué dos tipos principales de VPN has estudiado?

3. ¿Cuál utilizarías en este caso? Justifica la respuesta.

4. ¿Qué dispositivo suele gestionar estas conexiones?

---

# 🧩 Nivel 8 · El administrador de redes

Finalmente, tu responsable te muestra el siguiente diseño lógico:

```
                    INTERNET
                         │
                  ┌─────────────┐
                  │ FortiGate   │
                  └──────┬──────┘
                         │
          ┌──────────────┼──────────────┐
          │              │              │
      VLAN 10        VLAN 20        VLAN 30
   Administración      RRHH        Servidores
                                          │
                                         DNS
                                          │
                                       DHCP
                                          │
                                         Web
```

Te pide que expliques, con tus propias palabras:

1. ¿Qué función desempeña el FortiGate?

2. ¿Por qué existen varias VLAN?

3. ¿Cómo obtiene un equipo su dirección IP?

4. ¿Cómo localiza el servidor web utilizando un nombre de dominio?

5. ¿Cómo consigue acceder a Internet utilizando una dirección privada?

6. ¿Qué herramientas utilizarías si un usuario afirma que "Internet no funciona"?

7. ¿Qué papel desempeña el gateway?

8. ¿Qué ocurriría si desapareciera el servidor DNS?

---

# 🏆 Objetivo final

Si has sido capaz de resolver correctamente esta misión, deberías ser capaz de:

- Diagnosticar la mayoría de incidencias básicas de red.
- Comprender cómo colaboran DHCP, DNS, VLAN, Firewalls, NAT y VPN.
- Elegir la herramienta adecuada en cada situación.
- Seguir un procedimiento lógico de resolución de problemas.
- Afrontar con garantías los supuestos prácticos relacionados con redes que puedan aparecer en la oposición.
