# 🔴 Nivel 4 · Administración de servicios

---

# Pregunta 1

## Enunciado

Los usuarios indican que la página web del servidor ha dejado de funcionar.

¿Cuál sería tu primera comprobación?

---

## 🧠 Cadena de diagnóstico

Cuando un servicio deja de responder, lo primero es determinar si realmente está en ejecución.

No debemos asumir que el problema está en la red, en el navegador o en la aplicación.

Primero debemos comprobar el estado del servicio responsable.

---

### ✅ Respuesta esperada

Consultar el estado del servidor web mediante:

```bash
systemctl status apache2
```

(o `httpd` dependiendo de la distribución).

La salida permitirá conocer:

- si el servicio está activo;
- si ha fallado recientemente;
- cuándo se inició;
- el código de salida;
- los últimos mensajes registrados.

---

### 💡 Otras respuestas válidas

También sería válido:

```bash
service apache2 status
```

aunque actualmente `systemctl` es la herramienta recomendada en sistemas con `systemd`.

---

### ⚠️ Errores habituales

Reiniciar Apache sin comprobar previamente si realmente está detenido.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue exactamente la esperada.

Incluso añadiste la revisión de los registros mediante:

```bash
journalctl -u apache2 -n 20
```

Ese detalle es propio de una administración profesional.

Muy buena decisión.

---

# Pregunta 2

## Enunciado

Compruebas que Apache está detenido.

¿Cómo actuarías?

---

## 🧠 Cadena de diagnóstico

Si el servicio simplemente está detenido y no existen indicios de un problema mayor, el siguiente paso lógico consiste en intentar iniciarlo.

Después debemos comprobar que realmente ha arrancado correctamente.

---

### ✅ Respuesta esperada

Iniciar el servicio:

```bash
sudo systemctl start apache2
```

Y verificar inmediatamente su estado:

```bash
systemctl status apache2
```

No basta con ejecutar el comando de inicio.

Siempre debemos confirmar que el servicio permanece activo.

---

### 💡 Otras respuestas válidas

También podría utilizarse:

```bash
service apache2 start
```

en distribuciones compatibles.

---

### ⚠️ Errores habituales

Dar por hecho que el servicio ha arrancado correctamente sin comprobar el resultado.

---

### 👨‍🏫 Comentario del preparador

Respuesta completamente correcta.

Lo más importante fue que verificaste el estado tras el arranque.

Ese paso suele olvidarse y evita muchos diagnósticos erróneos.

---

# Pregunta 3

## Enunciado

Apache vuelve a detenerse pocos segundos después.

¿Qué harías ahora?

---

## 🧠 Cadena de diagnóstico

Cuando un servicio se inicia y vuelve a detenerse inmediatamente, normalmente el problema no es el servicio en sí.

Suele deberse a:

- errores de configuración;
- dependencias;
- permisos;
- puertos ocupados;
- módulos defectuosos.

Reiniciarlo repetidamente no solucionará la causa.

---

### ✅ Respuesta esperada

El orden recomendado sería:

**1. Revisar los registros del servicio**

```bash
journalctl -u apache2 -n 20
```

o consultar los archivos de registro correspondientes en:

```text
/var/log/apache2/
```

---

**2. Verificar la configuración**

En Apache puede utilizarse:

```bash
apache2ctl configtest
```

(o `httpd -t` según la distribución).

Esto permite detectar errores de sintaxis antes de reiniciar el servicio.

---

**3. Si la configuración es correcta, recargarla**

```bash
sudo systemctl reload apache2
```

---

**4. Si continúa fallando, realizar un reinicio completo**

```bash
sudo systemctl restart apache2
```

---

### ⚠️ Errores habituales

Entrar en un bucle de reinicios sin investigar el origen del fallo.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue excelente.

Durante la corrección únicamente añadimos un paso previo muy recomendable:

```bash
apache2ctl configtest
```

Muchísimos problemas de Apache se detectan inmediatamente con este comando.

Es una herramienta que todo administrador debería conocer.

---

# Pregunta 4

## Enunciado

Poco después también deja de responder PostgreSQL.

¿Cómo actuarías?

---

## 🧠 Cadena de diagnóstico

Aunque se trate de un servicio diferente, el procedimiento debe ser exactamente el mismo.

Los administradores no cambian de método según el servicio.

Aplican siempre una rutina de diagnóstico.

---

### ✅ Respuesta esperada

Seguiríamos el mismo orden:

1. Comprobar el estado:

```bash
systemctl status postgresql
```

---

2. Revisar los registros:

```bash
journalctl -u postgresql
```

---

3. Verificar la causa del problema.

---

4. Reiniciar únicamente si procede:

```bash
sudo systemctl restart postgresql
```

---

5. Confirmar que permanece activo.

---

### 💡 Idea clave

La metodología es mucho más importante que memorizar comandos específicos.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue muy buena.

Lo más interesante es que entendiste que el procedimiento no cambia.

Eso demuestra que ya estás desarrollando una forma de trabajar propia de un administrador de sistemas.

---

# Pregunta 5

## Enunciado

¿Cómo configurarías Apache para que se iniciara automáticamente al arrancar el servidor?

---

## 🧠 Cadena de diagnóstico

Los servicios críticos deben estar disponibles tras un reinicio del sistema.

Para ello es necesario habilitar su inicio automático.

---

### ✅ Respuesta esperada

```bash
sudo systemctl enable apache2
```

Este comando crea los enlaces necesarios para que el servicio se inicie automáticamente durante el arranque del sistema.

---

### 💡 Comprobación

Puede verificarse mediante:

```bash
systemctl is-enabled apache2
```

La salida esperada será:

```text
enabled
```

---

### ⚠️ Errores habituales

Confundir:

```bash
systemctl start
```

con

```bash
systemctl enable
```

- `start` inicia el servicio únicamente en la sesión actual.
- `enable` configura el inicio automático tras reiniciar el sistema.

En muchos casos será necesario ejecutar ambos comandos.

---

### 👨‍🏫 Comentario del preparador

Tu respuesta fue completamente correcta.

Además, elegiste exactamente el comando que utilizan los administradores para preparar un servidor antes de ponerlo en producción.

Muy buena respuesta.

---

# ✅ Valoración del Nivel 4

**Resultado:** Excelente.

Este nivel ya no evalúa únicamente conocimientos técnicos, sino la capacidad de seguir un procedimiento ordenado ante una incidencia.

Has demostrado una forma de trabajar muy cercana a la utilizada en entornos profesionales:

1. Comprobar el estado del servicio.
2. Analizar los registros.
3. Validar la configuración.
4. Aplicar la acción correctiva más adecuada.
5. Verificar el resultado.
6. Garantizar el arranque automático si el servicio es crítico.

Especialmente destacable fue tu insistencia en consultar los registros antes de reiniciar los servicios. Esa práctica reduce considerablemente el tiempo de diagnóstico y evita ocultar problemas que podrían reproducirse más adelante.

Este nivel confirma que ya dominas la administración básica de servicios en sistemas GNU/Linux y que eres capaz de afrontar incidencias habituales con un enfoque metódico y profesional.s