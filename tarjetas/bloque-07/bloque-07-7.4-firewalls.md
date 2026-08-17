# Tarjetas - Bloque 07 - 7.4 Firewalls

Formato:
P: Pregunta
R: Respuesta

---

## 7.4 Firewalls

P: Que es un firewall?
R: Mecanismo que controla trafico de red permitiendo o denegando segun reglas de seguridad.

P: Un firewall solo filtra trafico entrante?
R: No; tambien puede controlar trafico saliente.

P: Criterios basicos de filtrado?
R: IP origen/destino, puerto, protocolo y estado de conexion.

P: Packet filtering vs stateful inspection?
R: Packet filtering evalua paquetes por reglas; stateful ademas mantiene tabla de estado de conexiones.

P: Que aporta DPI?
R: Inspeccion profunda para analizar contenido/protocolo mas alla de cabeceras.

P: Que es un NGFW?
R: Firewall de nueva generacion con control de aplicaciones e inspeccion avanzada.

P: UTM que enfoque tiene?
R: Integrar varias funciones de seguridad en una unica solucion.

P: UTM y NGFW son excluyentes?
R: No; pueden solaparse en funcionalidades segun producto.

P: Que protege especificamente un WAF?
R: Aplicaciones web y trafico HTTP/HTTPS frente a ataques como SQLi o XSS.

P: WAF sustituye al firewall de red?
R: No; son capas complementarias con funciones distintas.

P: Para que sirve segmentacion/microsegmentacion?
R: Limitar comunicaciones y reducir movimiento lateral.

P: Politica por usuario/aplicacion en NGFW permite?
R: Reglas mas granulares que solo IP/puerto.

P: Principio clave de diseno de reglas?
R: Minimo acceso necesario con permisos explicitos y controlados.

---

## Tarjetas de repaso transversal (7.4)

P: Trampa clasica en firewalls?
R: Confundir permitir TCP/443 con permitir siempre trafico legitimo.

P: Regla corta de comparacion?
R: Firewall tradicional trafico; NGFW trafico+aplicacion+contexto; WAF foco web.

P: Objetivo final de 7.4?
R: Distinguir tecnologias y aplicarlas a escenarios reales de red.
