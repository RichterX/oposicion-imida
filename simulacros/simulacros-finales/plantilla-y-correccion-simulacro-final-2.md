# 📝 SIMULACRO GENERAL 02 · CORRECCIÓN Y SOLUCIONES
## 70 preguntas · Bloques 01 → 08

> 🏆 **Segundo y último simulacro general**
>
> Este documento contiene la plantilla de respuestas, la resolución razonada de las 70 preguntas y una guía para interpretar el resultado.

---

# 📊 PLANTILLA RÁPIDA

```text
01. B    11. A    21. B    31. A    41. A    51. B    61. A
02. C    12. A    22. A    32. B    42. A    52. A    62. B
03. B    13. A    23. B    33. B    43. A    53. B    63. A
04. A    14. B    24. B    34. A    44. B    54. A    64. B
05. A    15. B    25. C    35. A    45. A    55. A    65. A
06. A    16. A    26. B    36. A    46. A    56. A    66. A
07. C    17. A    27. A    37. C    47. A    57. A    67. A
08. B    18. B    28. A    38. A    48. A    58. A    68. A
09. A    19. B    29. C    39. A    49. A    59. A    69. B
10. B    20. A    30. A    40. A    50. A    60. B    70. B
```

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1. `df -h`

**Respuesta correcta: B) `df -h`**

`df` informa sobre el espacio utilizado y disponible en sistemas de archivos. La opción `-h` muestra las cantidades en un formato legible.

```text
df -h  → disco / sistemas de archivos
free -h → memoria RAM y swap
```

🎯 **Clave:** `df` = disk filesystem.

---

## 2. `/var`

**Respuesta correcta: C) Contiene datos variables, como determinados registros y colas.**

`/var` está destinado a datos que cambian durante el funcionamiento del sistema.

Ejemplos habituales:

```text
/var/log
/var/spool
/var/cache
```

No confundir:

```text
/etc  → configuración
/home → datos personales
/var  → datos variables
/proc → información virtual del kernel
```

---

## 3. `chmod 640`

**Respuesta correcta: B) `rw-r-----`**

La conversión es:

```text
6 → rw-
4 → r--
0 → ---
```

Por tanto:

```text
rw-r-----
```

---

## 4. Procesos PostgreSQL

**Respuesta correcta: A) `ps aux | grep postgresql`**

`ps aux` muestra procesos y `grep` permite filtrar las líneas relacionadas con PostgreSQL.

🎯 El concepto importante aquí es combinar una herramienta de consulta con un filtro.

---

## 5. `kill` frente a `systemctl stop`

**Respuesta correcta: A)**

`kill` actúa sobre un proceso mediante su PID/señal.

`systemctl stop` solicita a systemd detener un servicio.

```text
PROCESO → kill
SERVICIO → systemctl
```

---

## 6. Logs de un servicio

**Respuesta correcta: A) `journalctl -u nombre_servicio`**

La opción `-u` permite filtrar el journal por unidad/servicio.

---

## 7. Datos personales

**Respuesta correcta: C) `/home`**

Los directorios personales de los usuarios se encuentran normalmente bajo `/home`.

---

## 8. `tar`

**Respuesta correcta: B) Crear y manipular archivos de archivado.**

`tar` permite agrupar archivos y directorios en un archivo de archivado y trabajar con ellos.

🎯 Puede combinarse con compresión mediante herramientas/opciones apropiadas.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 9. Gestión centralizada mediante dominios

**Respuesta correcta: A) Active Directory Domain Services**

AD DS proporciona servicios de directorio y permite gestionar identidades, equipos y recursos en un entorno de dominio.

---

## 10. DHCP y DNS

**Respuesta correcta: B) DHCP asigna parámetros de red y DNS resuelve nombres.**

Memoriza:

```text
DHCP → configuración de red
DNS  → nombres ↔ direcciones
```

---

## 11. Políticas centralizadas

**Respuesta correcta: A) Group Policy**

Las directivas de grupo permiten aplicar configuraciones a usuarios y equipos dentro de un entorno administrado.

---

## 12. ACL y herencia

**Respuesta correcta: A) Herencia y ACL**

Las ACL contienen las reglas de acceso y la herencia permite que determinados permisos se propaguen desde recursos superiores, según la configuración.

---

## 13. Protocolo de directorio

**Respuesta correcta: A) LDAP**

LDAP está directamente asociado con el acceso y consulta de servicios de directorio.

---

## 14. Active Directory

**Respuesta correcta: B)**

Active Directory permite gestionar:

```text
usuarios
equipos
grupos
recursos
políticas
```

dentro de una estructura de directorio.

---

## 15. Configuración IP automática

**Respuesta correcta: B) DHCP**

DHCP puede proporcionar automáticamente dirección IP y otros parámetros como máscara, gateway y DNS.

---

## 16. ACL

**Respuesta correcta: A) Una lista de reglas que determina accesos a un recurso.**

Las ACL permiten expresar qué sujetos pueden realizar determinadas acciones sobre un recurso.

---

# 🌐 BLOQUE 03 · REDES

## 17. `192.168.1.25`

**Respuesta correcta: A) Es una dirección IPv4 privada.**

Pertenece al rango:

```text
192.168.0.0/16
```

que está reservado para redes privadas.

---

## 18. ARP

**Respuesta correcta: B) Relacionar una dirección IP con una dirección MAC en la red local.**

ARP permite averiguar la dirección MAC asociada a una IP dentro de la red local IPv4.

---

## 19. Interconectar redes

**Respuesta correcta: B) Router**

El router toma decisiones de encaminamiento y permite comunicar diferentes redes.

---

## 20. IP funciona, nombre no

**Respuesta correcta: A) DNS**

Si la conectividad mediante IP funciona pero la resolución del nombre falla, DNS es uno de los primeros elementos que debe comprobarse.

---

## 21. TCP

**Respuesta correcta: B)**

TCP proporciona comunicación orientada a conexión y mecanismos destinados a una entrega fiable y ordenada.

---

## 22. Máscara de subred

**Respuesta correcta: A)**

Permite determinar qué parte de una dirección IPv4 corresponde a la red y cuál al host.

---

## 23. Administración remota segura

**Respuesta correcta: B) SSH**

SSH permite acceder y administrar sistemas remotamente mediante una comunicación protegida.

---

## 24. IP frente a MAC

**Respuesta correcta: B)**

La IP es una dirección lógica utilizada para el encaminamiento y la comunicación a nivel de red.

La MAC identifica la interfaz en el ámbito de enlace.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 25. Modificar estructura

**Respuesta correcta: C) `ALTER TABLE`**

`ALTER TABLE` permite modificar la definición de una tabla.

---

## 26. `customer_id`

**Respuesta correcta: B) Una clave foránea.**

Si referencia `customers.id`, actúa normalmente como foreign key que relaciona el pedido con su cliente.

---

## 27. N+1

**Respuesta correcta: A)**

El problema aparece cuando se ejecuta una consulta inicial y después se realizan consultas adicionales repetitivas para cada registro obtenido.

Ejemplo conceptual:

```text
1 consulta → usuarios
+
100 consultas → posts de cada usuario
=
101 consultas
```

cuando podría utilizarse una estrategia de carga anticipada apropiada.

---

## 28. Eager loading

**Respuesta correcta: A) `User::with('posts')->get()`**

`with()` permite indicar relaciones que deben cargarse anticipadamente.

---

## 29. Aislamiento

**Respuesta correcta: C) Aislamiento**

Isolation se ocupa del comportamiento de transacciones concurrentes y de cómo se aíslan entre sí.

Recordatorio:

```text
A → Atomicidad
C → Consistencia
I → Aislamiento
D → Durabilidad
```

---

## 30. Añadir una columna

**Respuesta correcta: A) `ALTER TABLE`**

Por ejemplo:

```sql
ALTER TABLE users
ADD COLUMN active BOOLEAN;
```

---

## 31. Eliminar registros

**Respuesta correcta: A) `DELETE`**

`DELETE` elimina filas.

`DROP TABLE` elimina la propia estructura de la tabla.

---

## 32. Clave primaria

**Respuesta correcta: B)**

Una primary key permite identificar inequívocamente las filas de una tabla.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 33. Método de instancia PHP

**Respuesta correcta: B) `->`**

Ejemplo:

```php
$user->save();
```

Mientras que:

```php
ClassName::method();
```

se utiliza para acceso estático.

---

## 34. Inyección de dependencias

**Respuesta correcta: A)**

La DI evita que una clase tenga que construir directamente sus dependencias, reduciendo el acoplamiento.

Esto favorece:

```text
testabilidad
mantenimiento
sustitución de implementaciones
```

---

## 35. Middleware

**Respuesta correcta: A) Middleware**

El middleware puede intervenir durante el procesamiento de una petición, antes o después de que llegue a determinadas partes de la aplicación.

---

## 36. HTTP 404

**Respuesta correcta: A) Código de estado HTTP**

`404 Not Found` indica que el servidor no ha encontrado el recurso solicitado.

---

## 37. Eliminar recurso REST

**Respuesta correcta: C) DELETE**

Convencionalmente:

```text
GET    → obtener
POST   → crear/procesar
PUT    → reemplazar
PATCH  → modificar parcialmente
DELETE → eliminar
```

---

## 38. Fusionar ramas Git

**Respuesta correcta: A) `git merge`**

`git merge` integra los cambios de otra rama en la rama actual.

---

## 39. CI/CD

**Respuesta correcta: A)**

Una pipeline puede automatizar:

```text
build
↓
tests
↓
quality checks
↓
deploy
```

según el diseño del proyecto.

---

## 40. Estado compartido Vue

**Respuesta correcta: A) Pinia**

Pinia es la solución de gestión de estado utilizada habitualmente en Vue moderno.

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 41. Incidente vs problema

**Respuesta correcta: A)**

```text
INCIDENTE
→ restaurar el servicio

PROBLEMA
→ investigar / gestionar causas de incidentes
```

No son sinónimos.

---

## 42. Modificación planificada de un servicio

**Respuesta correcta: A) Gestión de cambios**

Los cambios deben evaluarse y gestionarse de acuerdo con el proceso establecido para minimizar riesgos e impactos.

---

## 43. Trabajo conocido del producto

**Respuesta correcta: A) Product Backlog**

El Product Backlog contiene el trabajo necesario y potencial para evolucionar el producto.

---

## 44. Scrum Master

**Respuesta correcta: B)**

El Scrum Master ayuda a que Scrum se comprenda y aplique correctamente y contribuye a mejorar la efectividad del equipo.

No es simplemente un jefe tradicional del equipo.

---

## 45. Inspeccionar el resultado

**Respuesta correcta: A) Sprint Review**

En la Sprint Review se inspecciona el resultado del Sprint y se consideran adaptaciones futuras.

⚠️ No confundir con:

```text
Daily Scrum → inspección/adaptación del trabajo diario
Sprint Review → inspección del resultado y colaboración sobre el futuro
Retrospective → mejora del proceso/equipo
```

---

## 46. PRINCE2

**Respuesta correcta: A) Gestión estructurada de proyectos**

PRINCE2 proporciona un enfoque estructurado para dirigir y gestionar proyectos.

---

## 47. ISO/IEC 20000

**Respuesta correcta: A) Sistemas de gestión de servicios de TI**

Su ámbito es la gestión de servicios de TI.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 48. CIA

**Respuesta correcta: A) Confidencialidad, integridad y disponibilidad.**

La conocida tríada:

```text
C → Confidentiality
I → Integrity
A → Availability
```

---

## 49. ENS

**Respuesta correcta: A)**

El ENS establece principios y requisitos de seguridad para los sistemas de información dentro de su ámbito de aplicación en el sector público.

---

## 50. Conservación

**Respuesta correcta: A) Limitación del plazo de conservación**

Los datos no deben conservarse durante más tiempo del necesario para los fines del tratamiento, salvo las excepciones previstas.

---

## 51. Derecho de supresión

**Respuesta correcta: B) Derecho de supresión**

Es el conocido derecho al "olvido" en determinadas circunstancias.

---

## 52. Firma digital

**Respuesta correcta: A) Firma digital**

Una firma digital utiliza técnicas criptográficas para proporcionar garantías sobre la autenticidad/integridad de los datos firmados.

---

## 53. Clave pública y privada

**Respuesta correcta: B)**

Constituyen un par criptográfico relacionado.

En términos simplificados:

```text
CLAVE PRIVADA
→ debe mantenerse secreta

CLAVE PÚBLICA
→ puede distribuirse
```

---

## 54. Firewall

**Respuesta correcta: A)**

Un firewall aplica reglas para permitir o bloquear determinadas comunicaciones.

⚠️ Un firewall es una medida de control, no una garantía absoluta contra cualquier malware.

---

## 55. Archivos cifrados + pago

**Respuesta correcta: A) Ransomware**

El ransomware cifra o bloquea recursos y exige normalmente un rescate para recuperar el acceso.

---

## 56. Contraseña robada

**Respuesta correcta: A) Autenticación multifactor**

Si un atacante obtiene la contraseña, un segundo factor puede impedir que esa contraseña sea suficiente para acceder.

---

## 57. Mínimo privilegio

**Respuesta correcta: A) Mínimo privilegio**

Cada usuario, proceso o servicio debería disponer solo de los permisos necesarios para realizar su función.

---

# 🧪 BLOQUE 08 · IMIDA

## 58. BPL

**Respuesta correcta: A)**

Las Buenas Prácticas de Laboratorio establecen un marco de organización, realización, registro, supervisión e informe de determinados estudios para garantizar su calidad e integridad.

---

## 59. Protocolo

**Respuesta correcta: A) Protocolo**

El protocolo establece previamente los objetivos y la metodología del estudio.

---

## 60. Garantía de Calidad

**Respuesta correcta: B)**

Garantía de Calidad verifica de forma independiente que el estudio se realiza conforme a los principios aplicables.

🎯 **Punto importante:** independencia respecto de la ejecución del estudio.

---

## 61. Muestra sin responsable

**Respuesta correcta: A) Trazabilidad incompleta**

Aunque tengamos:

```text
código
+
fecha
+
hora
+
procedencia
```

la ausencia del responsable de la toma deja incompleta la trazabilidad.

El material de examen presta especial atención a esta identificación.

---

## 62. Representatividad

**Respuesta correcta: B)**

La representatividad depende del diseño del muestreo y de la selección adecuada de los puntos respecto al objetivo y al conjunto estudiado.

No se consigue simplemente tomando una muestra más grande.

---

## 63. Herramienta contaminada

**Respuesta correcta: A) Contaminación cruzada**

Una herramienta puede transferir material de una muestra a otra y alterar los resultados.

---

## 64. Incumplimiento de conservación

**Respuesta correcta: B)**

La incidencia debe:

```text
registrarse
↓
evaluarse
↓
gestionarse según procedimiento
↓
documentarse
```

No se debe ocultar ni declarar automáticamente válida o inválida sin evaluación.

---

## 65. Gestión de residuos

**Respuesta correcta: A)**

La gestión adecuada incluye, según el tipo de residuo:

```text
identificación
+
segregación
+
envasado
+
etiquetado
+
almacenamiento
+
gestión autorizada
```

---

## 66. Residuo peligroso

**Respuesta correcta: A)**

La clasificación depende de las características del residuo y de la normativa aplicable.

No todo residuo de laboratorio es automáticamente peligroso, pero tampoco debe asumirse lo contrario.

---

# 🧠 BLOQUE TRANSVERSAL

## 67. MySQL consumiendo CPU

**Respuesta correcta: A)**

El enfoque razonable comienza por observar:

```text
procesos
+
CPU
+
memoria
+
carga
```

y posteriormente investigar qué está provocando la actividad elevada de MySQL.

Puede incluir revisar consultas, índices, concurrencia y otros factores.

🎯 La clave es **diagnosticar antes de actuar destructivamente**.

---

## 68. Laravel + N+1

**Respuesta correcta: A) N+1; utilizar eager loading cuando corresponda.**

Tenemos:

```text
1 consulta → usuarios
+
N consultas → posts
```

Una estrategia de eager loading como:

```php
User::with('posts')->get();
```

puede reducir este patrón.

---

## 69. Proyecto público transversal

**Respuesta correcta: B)**

El escenario combina diferentes disciplinas:

```text
CI/CD
→ desarrollo

controles de seguridad
→ Seguridad

datos personales
→ RGPD

responsabilidades del servicio
→ Gestión TIC

muestras / investigación
→ IMIDA
```

El objetivo de la pregunta es comprobar que puedes relacionar conocimientos de distintos bloques.

---

## 70. Muestreo sesgado

**Respuesta correcta: B)**

La correcta identificación y el análisis correcto no solucionan un diseño de muestreo sesgado.

La secuencia es:

```text
DISEÑO SESGADO
      ↓
MUESTRA NO REPRESENTATIVA
      ↓
ANÁLISIS CORRECTO
      ↓
RESULTADO CORRECTAMENTE MEDIDO
      ↓
PERO NO NECESARIAMENTE EXTRAPOLABLE
```

🎯 Esta es una de las ideas más importantes de todo el capítulo 8.6.

---

# 📊 RESULTADO DEL SIMULACRO

Si cada pregunta tiene el mismo valor:

```text
NOTA = aciertos / 70 × 10
```

| Aciertos | Nota /10 |
|---:|---:|
| 35 | 5,00 |
| 40 | 5,71 |
| 45 | 6,43 |
| 50 | 7,14 |
| 55 | 7,86 |
| 60 | 8,57 |
| 65 | 9,29 |
| 70 | 10,00 |

⚠️ Esta equivalencia es orientativa. Si el examen oficial aplica penalización por errores, habría que utilizar la fórmula de la convocatoria.

---

# 📈 LECTURA DEL RESULTADO

| Aciertos | Diagnóstico orientativo |
|---:|---|
| 0–34 | 🔴 Necesita bastante consolidación |
| 35–44 | 🟠 Base razonable con lagunas |
| 45–52 | 🟡 Buen punto de partida |
| 53–59 | 🟢 Nivel sólido |
| 60–65 | 🟢 Muy buen nivel |
| 66–70 | 🏆 Dominio excelente |

Pero **no compares únicamente la nota del simulacro 01 y 02**.

El segundo tiene una intención más aplicada. Es posible obtener una puntuación similar y, sin embargo, haber mejorado mucho en comprensión.

---

# 🧩 DIAGNÓSTICO POR BLOQUES

Para conocer realmente tu nivel, calcula:

```text
BLOQUE 01 → aciertos / 8
BLOQUE 02 → aciertos / 8
BLOQUE 03 → aciertos / 8
BLOQUE 04 → aciertos / 8
BLOQUE 05 → aciertos / 8
BLOQUE 06 → aciertos / 7
BLOQUE 07 → aciertos / 10
BLOQUE 08 → aciertos / 9
TRANSVERSAL → aciertos / 4
```

Y conviértelo a porcentaje.

### 🟢 80–100 %

Muy sólido.

### 🟡 60–79 %

Conviene repasar.

### 🟠 40–59 %

Hay lagunas importantes.

### 🔴 <40 %

Bloque prioritario.

---

# 🔍 CLASIFICA TUS ERRORES

No basta con saber cuántas has fallado.

Clasifica cada error:

### 🔴 A · Desconocimiento

> "No tenía ni idea."

### 🟠 B · Confusión

> "Conocía ambos conceptos, pero los mezclé."

Ejemplos:

```text
DNS / DHCP
DELETE / DROP
TCP / UDP
Incidente / Problema
Product Owner / Scrum Master
Muestra dirigida / representativa
```

### 🟡 C · Despiste

> "Sabía la respuesta y leí mal."

### 🟣 D · Duda

> "Acerté, pero estaba entre dos."

Esta última categoría es especialmente importante.

Un acierto con duda **no debería considerarse dominio completo**.

---

# 🎯 CONCEPTOS QUE DEBERÍAS PODER EXPLICAR SIN APUNTES

Al terminar ambos simulacros, deberías ser capaz de explicar oralmente:

```text
1. df vs free
2. /etc vs /var vs /home vs /proc
3. permisos 640 / 755
4. systemctl vs kill
5. AD DS
6. LDAP
7. DNS vs DHCP
8. switch vs router
9. IP vs MAC
10. TCP vs UDP
11. clave primaria vs clave foránea
12. DELETE vs DROP
13. ACID
14. N+1
15. eager loading
16. inyección de dependencias
17. middleware
18. Git merge
19. CI/CD
20. ITIL: incidente vs problema
21. Scrum: Product Owner vs Scrum Master
22. Sprint Review vs Retrospective
23. PRINCE2
24. ISO 20000
25. ENS
26. CIA
27. principios RGPD
28. certificados digitales
29. criptografía asimétrica
30. firewall
31. MFA
32. mínimo privilegio
33. BPL
34. Garantía de Calidad
35. protocolo
36. residuos
37. trazabilidad
38. representatividad
39. error de muestreo
40. error analítico
```

---

# 🏆 LAS 10 IDEAS QUE MÁS QUIERO QUE TE LLEVES

## 1. Linux

> `df` habla de sistemas de archivos; `free` habla de memoria.

## 2. Windows

> AD centraliza identidades y recursos; DNS y DHCP cumplen funciones diferentes.

## 3. Redes

> IP y MAC no son lo mismo; router y switch tampoco.

## 4. Bases de datos

> Una clave primaria identifica; una foránea relaciona.

## 5. Laravel

> Eager loading ayuda a evitar patrones N+1.

## 6. Gestión TIC

> Incidente y problema tienen objetivos diferentes.

## 7. Scrum

> Product Owner maximiza valor y gestiona el Product Backlog; Scrum Master facilita la correcta aplicación de Scrum.

## 8. Seguridad

> Confidencialidad + Integridad + Disponibilidad.

## 9. RGPD

> Los datos personales deben tratarse respetando los principios y derechos establecidos.

## 10. IMIDA

> Un análisis correcto no puede arreglar un muestreo incorrecto.

---

# 🧠 COMPARACIÓN ENTRE LOS DOS SIMULACROS

El entrenamiento queda así:

```text
SIMULACRO 01
     ↓
BASE + DIAGNÓSTICO
     ↓
DETECTAR LAGUNAS
     ↓
REPASAR
     ↓
SIMULACRO 02
     ↓
APLICACIÓN + INTEGRACIÓN
     ↓
DETECTAR ÚLTIMOS FALLOS
```

Y a partir de aquí, si aparecen errores repetidos en ambos simulacros, esos son los conceptos que merecen una última revisión prioritaria.

---

# 🏁 FIN DE LA CORRECCIÓN

## 🎉 HAS COMPLETADO LOS DOS SIMULACROS GENERALES

```text
╔════════════════════════════════════╗
║                                    ║
║       SIMULACRO GENERAL 01         ║
║               ✓                    ║
║                                    ║
║       SIMULACRO GENERAL 02         ║
║               ✓                    ║
║                                    ║
║       BLOQUES 01 → 08              ║
║               ✓                    ║
║                                    ║
║          TEMARIO COMPLETO          ║
║               ✓                    ║
║                                    ║
╚════════════════════════════════════╝
```

## 📚 El temario está terminado.

Ahora la prioridad ya no debería ser añadir contenido indiscriminadamente, sino:

```text
REPASAR
   ↓
RECORDAR
   ↓
PRACTICAR
   ↓
ANALIZAR ERRORES
   ↓
VOLVER A REPASAR
```

> **El objetivo final no es saber reconocer la respuesta correcta al verla. Es ser capaz de producirla cuando el examen te la pida sin avisar.**
