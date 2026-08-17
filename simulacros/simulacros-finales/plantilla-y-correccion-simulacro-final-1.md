<!-- encabezado-homogeneizado -->
# Simulacros Finales - PLANTILLA Y CORRECCION
> **Bloque:** Simulacros Finales  
> **Documento:** Plantilla y correccion  
> **Preguntas de referencia:** N/D  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 📝 SIMULACRO GENERAL 01 · CORRECCIÓN Y SOLUCIONES
## 70 preguntas · Bloques 01 → 08

> **Uso recomendado:** realiza primero el simulacro completo y compara después tus respuestas con esta plantilla.
>
> La corrección incluye:
>
> - respuesta correcta;
> - explicación;
> - bloque;
> - concepto que conviene recordar.

---

# 📊 PLANTILLA RÁPIDA DE CORRECCIÓN

```text
01. B    11. B    21. B    31. B    41. B    51. A    61. A
02. A    12. A    22. B    32. B    42. A    52. A    62. A
03. C    13. A    23. B    33. B    43. A    53. A    63. A
04. A    14. A    24. B    34. A    44. B    54. B    64. C
05. B    15. C    25. B    35. B    45. B    55. A    65. A
06. C    16. A    26. A    36. B    46. A    56. A    66. B
07. A    17. B    27. B    37. B    47. B    57. A    67. B
08. A    18. A    28. B    38. A    48. A    58. A    68. B
09. B    19. B    29. B    39. A    49. B    59. A    69. B
10. B    20. A    30. B    40. B    50. A    60. A    70. B
```

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1. ¿Qué directorio contiene habitualmente los archivos de configuración?

**Respuesta: B) `/etc`**

`/etc` contiene habitualmente archivos de configuración del sistema y de numerosos servicios.

```text
/etc → configuración
/home → usuarios
/var → datos variables
/proc → información virtual del kernel/procesos
```

🎯 **Clave:** si aparece `/etc`, piensa en **configuración**.

---

## 2. ¿Qué comando identifica al usuario actual?

**Respuesta: A) `whoami`**

`whoami` muestra el nombre del usuario efectivo con el que se está ejecutando la sesión/comando.

🎯 **Clave:** `whoami` = "¿quién soy?"

---

## 3. ¿Qué muestra `df -h`?

**Respuesta: C) Espacio utilizado y disponible en sistemas de archivos**

`df` informa sobre el espacio de los sistemas de archivos. `-h` hace que las unidades sean legibles para humanos.

🎯 No confundir:

```text
df -h → almacenamiento
free -h → memoria
```

---

## 4. ¿Qué representa `755`?

**Respuesta: A) `rwxr-xr-x`**

```text
7 → rwx
5 → r-x
5 → r-x
```

Por tanto:

```text
rwxr-xr-x
```

---

## 5. Consultar el estado de un servicio systemd

**Respuesta: B) `systemctl status`**

Ejemplo:

```bash
systemctl status apache2
```

🎯 **Clave:** `systemctl` es la herramienta de administración de servicios de systemd.

---

## 6. Monitorización interactiva de procesos

**Respuesta: C) `htop`**

`htop` proporciona una interfaz interactiva para observar procesos y consumo de recursos.

---

## 7. Directorio virtual del kernel

**Respuesta: A) `/proc`**

`/proc` es un sistema de archivos virtual que proporciona información sobre procesos y diferentes aspectos del kernel.

---

## 8. Copia de archivos mediante SSH

**Respuesta: A) `scp`**

`scp` permite copiar archivos entre sistemas utilizando SSH.

---

## 9. Consultar logs de journald

**Respuesta: B) `journalctl`**

Ejemplo:

```bash
journalctl
journalctl -u apache2
```

🎯 **Clave:** `journalctl` = consultar el journal de systemd.

---

## 10. Programación de tareas mediante cron

**Respuesta: B) `crontab`**

`crontab` permite definir tareas programadas para un usuario.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 11. Servicio de directorio

**Respuesta: B) Active Directory Domain Services**

AD DS centraliza información y gestión de identidades, equipos y recursos dentro de un entorno de dominio.

---

## 12. Protocolo de servicios de directorio

**Respuesta: A) LDAP**

LDAP es un protocolo utilizado para acceder y consultar servicios de directorio.

⚠️ No confundir:

```text
LDAP → directorio
DNS → resolución de nombres
DHCP → configuración de red
```

---

## 13. Estructura lógica de AD

**Respuesta: A) Dominio**

Un dominio proporciona un límite lógico y administrativo dentro de Active Directory.

---

## 14. Permisos NTFS

**Respuesta: A) ACL**

Las listas de control de acceso permiten definir qué usuarios o grupos pueden realizar determinadas acciones sobre recursos.

---

## 15. Característica de NTFS

**Respuesta: C) Permite establecer permisos y mantener características de seguridad**

NTFS soporta permisos y mecanismos relacionados con la seguridad del sistema de archivos.

---

## 16. Resolución de nombres

**Respuesta: A) DNS**

DNS traduce nombres de dominio/nombres de host a direcciones IP y permite también otras resoluciones.

---

## 17. Función de DHCP

**Respuesta: B) Asignar dinámicamente parámetros de configuración de red**

Puede proporcionar:

```text
IP
máscara
gateway
DNS
```

entre otros parámetros.

---

## 18. Configuración centralizada

**Respuesta: A) Group Policy**

Las directivas de grupo permiten aplicar configuraciones de manera centralizada a usuarios y equipos.

---

# 🌐 BLOQUE 03 · REDES

## 19. Dispositivo basado en MAC

**Respuesta: B) Switch**

Un switch de red opera principalmente en la capa 2 y utiliza direcciones MAC para decidir cómo reenviar tramas.

---

## 20. Función del router

**Respuesta: A) Conectar redes diferentes y dirigir tráfico entre ellas**

Un router opera principalmente en la capa de red y toma decisiones de encaminamiento.

---

## 21. Dirección privada IPv4

**Respuesta: B) `172.16.10.20`**

Los rangos privados IPv4 incluyen:

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

`172.16.10.20` pertenece al segundo rango.

---

## 22. Nombres → IP

**Respuesta: B) DNS**

DNS proporciona resolución de nombres.

---

## 23. Configuración IP automática

**Respuesta: B) DHCP**

DHCP permite asignar automáticamente parámetros de configuración de red.

---

## 24. Identificación a nivel de enlace

**Respuesta: B) MAC**

La dirección MAC identifica una interfaz de red en el ámbito de la capa de enlace.

---

## 25. IP funciona pero nombre no resuelve

**Respuesta: B) DNS**

Si se puede acceder directamente mediante IP pero no mediante nombre, DNS es uno de los primeros elementos que debemos comprobar.

---

## 26. TCP frente a UDP

**Respuesta: A) TCP proporciona comunicación orientada a conexión y mecanismos de control de entrega**

TCP proporciona mecanismos como:

```text
establecimiento de conexión
control de flujo
retransmisión
ordenación
```

UDP no proporciona esas garantías de la misma manera.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 27. Recuperar datos

**Respuesta: B) `SELECT`**

Ejemplo:

```sql
SELECT * FROM users;
```

---

## 28. Clave primaria

**Respuesta: B) Identifica de forma única cada fila**

Una primary key identifica inequívocamente registros de una tabla.

---

## 29. Clave foránea

**Respuesta: B) Una relación entre registros de diferentes tablas**

Una foreign key permite representar relaciones entre tablas.

---

## 30. Eager loading en Laravel

**Respuesta: B) Eager loading mediante `with()`**

Ejemplo:

```php
User::with('posts')->get();
```

Las relaciones se cargan anticipadamente.

---

## 31. Problema N+1

**Respuesta: B) N+1 queries**

El eager loading permite evitar el patrón típico:

```text
1 consulta para obtener N registros
+
N consultas adicionales para sus relaciones
```

---

## 32. Modificar registros

**Respuesta: B) `UPDATE`**

Ejemplo:

```sql
UPDATE users
SET active = 1
WHERE id = 10;
```

---

## 33. Eliminar filas

**Respuesta: B) `DELETE`**

Ejemplo:

```sql
DELETE FROM users
WHERE id = 10;
```

⚠️ No confundir `DELETE` con `DROP`, que opera sobre estructuras como tablas.

---

## 34. Propiedad ACID

**Respuesta: A) Atomicidad**

La atomicidad expresa la idea de:

```text
todo
o
nada
```

Una transacción no debería quedar aplicada parcialmente.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 35. Acceso a miembros de una instancia PHP

**Respuesta: B) `->`**

Ejemplo:

```php
$user->name;
$user->save();
```

`::` se utiliza para acceso estático.

---

## 36. Definición de rutas Laravel

**Respuesta: B) Router / archivos de rutas**

Laravel permite definir las rutas HTTP mediante sus archivos de rutas y el sistema de routing.

---

## 37. Inyección de dependencias

**Respuesta: B) Reduce el acoplamiento y facilita la sustitución y prueba de dependencias**

La DI permite que una clase reciba las dependencias que necesita en lugar de construirlas directamente.

Esto facilita:

```text
testing
mantenimiento
sustitución
desacoplamiento
```

---

## 38. Control de versiones

**Respuesta: A) Git**

Git es el sistema de control de versiones habitual en este tipo de proyectos.

---

## 39. Clonar repositorio

**Respuesta: A) `git clone`**

Ejemplo:

```bash
git clone https://...
```

---

## 40. CI/CD

**Respuesta: B) Automatizar procesos de integración, pruebas y entrega/despliegue**

CI/CD busca automatizar el ciclo que lleva desde los cambios de código hasta su validación y entrega/despliegue.

---

## 41. Obtener recurso REST

**Respuesta: B) GET**

De forma convencional:

```text
GET → obtener
POST → crear / procesar
PUT/PATCH → modificar
DELETE → eliminar
```

---

## 42. Estado global en Vue 3

**Respuesta: A) Pinia**

Pinia es una solución de gestión de estado para aplicaciones Vue.

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 43. Concepto de servicio en ITIL

**Respuesta: A) Servicio**

En ITIL, un servicio permite aportar valor facilitando resultados que el cliente quiere conseguir sin que tenga que gestionar directamente determinados costes y riesgos asociados.

---

## 44. Gestión de incidentes

**Respuesta: B) Restaurar el servicio normal lo antes posible y minimizar el impacto negativo**

La gestión de incidentes busca recuperar el funcionamiento normal del servicio y reducir el impacto.

⚠️ No confundir:

```text
Incidente → restaurar servicio
Problema → tratar causa / causas de incidentes
```

---

## 45. Product Owner

**Respuesta: B) Product Owner**

El Product Owner es responsable de maximizar el valor del producto y de gestionar eficazmente el Product Backlog.

---

## 46. Sprint

**Respuesta: A) Un periodo de tiempo fijo en el que se crea un incremento de valor**

El Sprint es un evento de duración fija dentro de Scrum.

---

## 47. PRINCE2

**Respuesta: B) Un método estructurado de gestión de proyectos**

PRINCE2 es un método para dirigir y gestionar proyectos.

---

## 48. ISO/IEC 20000

**Respuesta: A) Gestión de servicios de TI**

ISO/IEC 20000 establece requisitos y buenas prácticas relacionadas con los sistemas de gestión de servicios.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 49. Esquema Nacional de Seguridad

**Respuesta: B) Establecer los principios y requisitos necesarios para proteger la información y los servicios de las Administraciones Públicas**

El ENS establece el marco de seguridad aplicable al sector público español.

---

## 50. Dimensión clásica de seguridad

**Respuesta: A) Confidencialidad**

Las dimensiones clásicas incluyen:

```text
Confidencialidad
Integridad
Disponibilidad
```

---

## 51. RGPD y limitación de datos

**Respuesta: A) Minimización de datos**

El principio de minimización exige que los datos sean adecuados, pertinentes y limitados a lo necesario respecto a los fines para los que son tratados.

---

## 52. Derecho de acceso

**Respuesta: A) Derecho de acceso**

Permite obtener confirmación sobre si se están tratando datos personales y acceder a ellos en las condiciones previstas por el RGPD.

---

## 53. Certificado digital

**Respuesta: A) El certificado permite vincular una identidad con una clave pública mediante una infraestructura de confianza**

El certificado digital permite asociar una identidad con una clave pública y contiene información certificada por una autoridad de confianza.

---

## 54. Autoridad de certificación

**Respuesta: B) Emitir certificados digitales y establecer una relación de confianza sobre la identidad asociada**

La autoridad de certificación participa en la infraestructura de clave pública y emite certificados conforme a sus políticas.

---

## 55. Firewall

**Respuesta: A) Filtrar tráfico de red según reglas definidas**

Un firewall controla comunicaciones según reglas de seguridad.

---

## 56. Phishing

**Respuesta: A) Phishing**

El phishing utiliza técnicas de engaño para conseguir información como:

```text
credenciales
datos bancarios
información personal
```

---

## 57. Integridad

**Respuesta: A) Integridad**

La integridad busca evitar modificaciones no autorizadas y preservar la exactitud/confiabilidad de la información.

---

## 58. MFA

**Respuesta: A) MFA / autenticación multifactor**

Añadir un segundo factor reduce el riesgo de que una contraseña robada sea suficiente para acceder a una cuenta.

---

# 🧪 BLOQUE 08 · IMIDA

## 59. Función general del IMIDA

**Respuesta: A) Desarrollar y coordinar actividades de investigación, innovación y transferencia relacionadas con el sector agroalimentario y el medio ambiente**

Esta es la formulación general utilizada para contextualizar la actividad del IMIDA en el temario.

---

## 60. Independencia en BPL

**Respuesta: A) Garantía de Calidad**

La función de Garantía de Calidad debe mantener independencia respecto de la realización del estudio que supervisa.

🎯 **Muy importante para examen.**

---

## 61. Documento previo del estudio BPL

**Respuesta: A) Protocolo**

El protocolo establece previamente los objetivos y metodología del estudio.

---

## 62. Trazabilidad de una muestra

**Respuesta: A) Identificarla inequívocamente y registrar su procedencia y datos relevantes**

La identificación debe permitir relacionar la muestra con su origen y con el resto de registros.

En el material de examen se destaca expresamente la combinación de:

```text
técnico
+
fecha/hora
+
código
+
procedencia
```

como información relevante para la identificación y trazabilidad. fileciteturn28file0L43-L50

---

## 63. Residuos peligrosos

**Respuesta: A) Identificarlos, envasarlos y etiquetarlos adecuadamente y gestionarlos conforme a la normativa**

No deben:

```text
mezclarse indiscriminadamente
+
diluirse para eliminar su peligrosidad
+
verterse directamente
```

---

## 64. Almacenamiento de residuos peligrosos

**Respuesta: C) 6 meses**

La regla general estudiada es:

```text
PELIGROSOS → 6 MESES
```

con posibilidad de ampliación excepcional en los términos establecidos por la normativa.

🎯 **Número de memoria.**

---

## 65. Propiedad fundamental del muestreo

**Respuesta: A) Representatividad**

Si queremos obtener conclusiones sobre el conjunto, la muestra debe representar adecuadamente las características relevantes del mismo.

---

## 66. Selección de plantas sintomáticas

**Respuesta: B) Falta de representatividad / sesgo de muestreo**

Se han seleccionado deliberadamente elementos que presentan una característica concreta.

Eso puede ser útil para estudiar esa zona, pero no permite automáticamente extrapolar los resultados a toda la parcela.

---

## 67. Pérdida de condiciones de conservación

**Respuesta: B) Registrar y evaluar la incidencia según el procedimiento aplicable**

La muestra no debe declararse automáticamente válida ni inválida sin evaluar:

```text
tipo de muestra
+
condiciones requeridas
+
duración de la desviación
+
impacto potencial
```

---

## 68. Cadena de trazabilidad

**Respuesta: B) Origen → toma → identificación → conservación/transporte → recepción → análisis → resultado**

Esta es la secuencia que mejor representa la trazabilidad de una muestra.

---

# 🧠 BLOQUE TRANSVERSAL

## 69. Análisis perfecto + muestra sesgada

**Respuesta: B) Existe principalmente un problema de muestreo, no necesariamente de análisis**

Esta pregunta es especialmente importante.

Tenemos:

```text
EQUIPO CORRECTO
+
MÉTODO CORRECTO
+
ANÁLISIS CORRECTO
```

pero:

```text
MUESTRA NO REPRESENTATIVA
```

Por tanto, el problema principal está en el muestreo.

🎯 **Frase para recordar:**

> Un análisis perfecto no convierte una muestra sesgada en representativa.

---

## 70. Proyecto público con gestión, desarrollo y seguridad

**Respuesta: B) Gestión TIC + Seguridad + IMIDA**

El escenario combina:

```text
Gestión TIC
→ ITIL / Scrum / PRINCE2 / ISO 20000

Seguridad
→ ENS / RGPD / ciberseguridad

IMIDA
→ investigación / BPL / procedimientos / actividad del organismo
```

La pregunta busca comprobar que eres capaz de **conectar bloques**, no solo estudiarlos por separado.

---

# 📊 DISTRIBUCIÓN DE LAS RESPUESTAS

Para evitar que el patrón de respuestas sea demasiado evidente:

```text
A → 24
B → 31
C → 10
D → 5
```

⚠️ Esto **no debe utilizarse para intentar acertar preguntas**. Es simplemente una característica del diseño del simulacro.

---

# 📈 ¿CÓMO CALCULAR TU RESULTADO?

Si todas las preguntas tienen el mismo valor:

```text
NOTA = aciertos / 70 × 10
```

Ejemplos:

| Aciertos | Nota sobre 10 |
|---:|---:|
| 35 | 5,00 |
| 40 | 5,71 |
| 45 | 6,43 |
| 50 | 7,14 |
| 55 | 7,86 |
| 60 | 8,57 |
| 65 | 9,29 |
| 70 | 10,00 |

### ⚠️ Importante

Si la convocatoria real establece penalización por respuestas incorrectas, esta tabla **no sería la nota oficial**. Para este simulacro la utilizamos únicamente como referencia de rendimiento.

---

# 📚 ANÁLISIS POR BLOQUES

Una vez terminado, no te quedes únicamente con:

> "He sacado X sobre 10."

Divide tus resultados:

```text
01 · GNU/Linux              / 10
02 · Windows / AD           / 8
03 · Redes                  / 8
04 · Bases de datos         / 8
05 · Desarrollo             / 8
06 · Gestión TIC            / 6
07 · Seguridad              / 10
08 · IMIDA                  / 12
```

> **Nota:** el número de preguntas por bloque no es idéntico en el simulacro, por lo que conviene comparar porcentajes y no solo aciertos absolutos.

---

# 🧠 CÓMO INTERPRETAR LOS FALLOS

No todos los errores significan lo mismo.

### 🔴 Tipo 1 · Desconocimiento

No sabías la respuesta.

➡️ Hay que repasar el concepto.

### 🟠 Tipo 2 · Confusión

Sabías ambas opciones pero mezclaste conceptos.

Ejemplos:

```text
df vs free
DNS vs DHCP
TCP vs UDP
DELETE vs DROP
Incidente vs Problema
Muestra dirigida vs representativa
```

➡️ Necesitas una comparación.

### 🟡 Tipo 3 · Despiste

Conocías perfectamente la respuesta pero leíste mal.

➡️ Entrenamiento de examen.

### 🟣 Tipo 4 · Duda

Acertaste, pero estabas entre dos.

➡️ No lo consideres un dominio completo todavía.

Marca:

```text
✓ seguro
? dudoso
```

---

# 🏆 ESCALA ORIENTATIVA

No es una nota oficial de la oposición. Es una herramienta para interpretar este primer diagnóstico.

| Resultado | Lectura |
|---|---|
| **0–34** | 🔴 Hay que consolidar bastante base |
| **35–44** | 🟠 Base existente, pero con lagunas |
| **45–52** | 🟡 Buen punto de partida |
| **53–59** | 🟢 Nivel bastante sólido |
| **60–65** | 🟢 Muy buen nivel |
| **66–70** | 🏆 Dominio excelente del simulacro |

Pero recuerda:

> **El objetivo del primer simulacro no es demostrar que sabes. Es descubrir qué necesitas reforzar.**

---

# 🎯 LOS CONCEPTOS MÁS IMPORTANTES QUE ESTE SIMULACRO QUERÍA COMPROBAR

```text
GNU/Linux
→ /etc, /proc, df, permisos, systemctl, journalctl

Windows
→ AD DS, LDAP, NTFS, DNS, DHCP, Group Policy

Redes
→ switch/router, IP privada, DNS/DHCP, MAC, TCP/UDP

Bases de datos
→ SQL, claves, relaciones, N+1, eager loading, ACID

Desarrollo
→ PHP, Laravel, DI, Git, CI/CD, REST, Vue/Pinia

Gestión TIC
→ ITIL, incidentes, Scrum, Product Owner, Sprint,
  PRINCE2, ISO 20000

Seguridad
→ ENS, CIA, RGPD, certificados, CA, firewall,
  phishing, MFA

IMIDA
→ función del organismo, BPL, residuos, trazabilidad,
  muestreo, representatividad
```

---

# 🧨 LAS 10 PREGUNTAS QUE QUIERO QUE REVISES CON ESPECIAL ATENCIÓN

Aunque las hayas acertado, merece la pena comprobar que sabes explicar:

```text
04 → permisos 755
18 → Group Policy
26 → TCP vs UDP
30 → eager loading
31 → N+1
34 → atomicidad
44 → gestión de incidentes
45 → Product Owner
60 → Garantía de Calidad BPL
66 → sesgo de muestreo
```

Son preguntas cortas, pero representan conceptos que pueden reaparecer con escenarios mucho más complicados.

---

# 🏁 FIN DE LA CORRECCIÓN

## 📊 SIMULACRO GENERAL 01

```text
70 PREGUNTAS
       ↓
8 BLOQUES
       ↓
CONCEPTOS BÁSICOS
       +
CASOS PRÁCTICOS
       +
PREGUNTAS TRANSVERSALES
```

### Siguiente paso recomendado

Cuando tengas tus respuestas, podemos construir una tabla:

```text
PREGUNTA | TU RESPUESTA | CORRECTA | RESULTADO | BLOQUE | DUDA
```

y a partir de ella detectar exactamente dónde están tus puntos débiles.

> **No buscamos simplemente una nota alta. Buscamos que cada simulacro elimine una parte de tus errores.**

