# 🏆 SIMULACRO FINAL 03 · CORRECCIÓN Y SOLUCIONES
## 70 preguntas · Bloques 01 → 08

> **Último simulacro general de cierre.**
>
> Aquí tienes la plantilla completa, la explicación de cada respuesta y una guía para interpretar el resultado.

---

# 📊 PLANTILLA RÁPIDA

```text
01. B    11. B    21. B    31. A    41. A    51. A    61. A
02. C    12. A    22. B    32. D    42. A    52. A    62. A
03. A    13. A    23. A    33. B    43. A    53. A    63. A
04. B    14. A    24. A    34. A    44. A    54. A    64. A
05. A    15. A    25. A    35. A    45. A    55. A    65. A
06. A    16. C    26. B    36. A    46. A    56. A    66. A
07. A    17. A    27. A    37. A    47. A    57. A    67. A
08. C    18. A    28. A    38. A    48. A    58. A    68. A
09. A    19. B    29. A    39. A    49. A    59. A    69. A
10. A    20. A    30. A    40. A    50. A    60. A    70. C
```

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1. Memoria RAM

**Respuesta correcta: B) `free -h`**

`free` muestra información sobre memoria RAM y swap. La opción `-h` presenta los valores en un formato legible.

```text
free -h → memoria
df -h   → sistemas de archivos
```

---

## 2. `/proc`

**Respuesta correcta: C) Información virtual sobre procesos y el kernel.**

`/proc` es un sistema de archivos virtual que expone información del kernel y de los procesos.

🎯 Recuerda:

```text
/etc  → configuración
/var  → datos variables
/home → usuarios
/proc → procesos / kernel
```

---

## 3. Permisos `rw-r--r--`

**Respuesta correcta: A) 644**

Conversión:

```text
rw- → 6
r-- → 4
r-- → 4
```

Por tanto:

```text
644
```

---

## 4. Nombre del sistema anfitrión

**Respuesta correcta: B) `hostname`**

`hostname` muestra o permite gestionar el nombre del host, según la opción utilizada.

No confundir:

```text
whoami   → usuario
hostname → equipo
```

---

## 5. `systemctl status apache2`

**Respuesta correcta: A)**

Consulta el estado del servicio `apache2` mediante systemd.

---

## 6. `scp`

**Respuesta correcta: A)**

`scp` permite copiar archivos entre sistemas utilizando SSH.

---

## 7. Journal de systemd

**Respuesta correcta: A) `journalctl`**

Permite consultar los registros gestionados por journald.

Por ejemplo:

```bash
journalctl -u apache2
```

---

## 8. `df` frente a `free`

**Respuesta correcta: C)**

```text
df   → espacio de sistemas de archivos
free → memoria RAM / swap
```

Esta es una distinción básica que conviene tener completamente automatizada.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 9. Active Directory Domain Services

**Respuesta correcta: A)**

AD DS proporciona servicios de directorio para gestionar identidades, equipos y recursos en entornos de dominio.

---

## 10. Servicios de directorio

**Respuesta correcta: A) LDAP**

LDAP está asociado con el acceso y consulta de servicios de directorio.

---

## 11. IP automática

**Respuesta correcta: B) DHCP**

DHCP puede proporcionar:

```text
IP
máscara
gateway
DNS
```

entre otros parámetros.

---

## 12. Configuración centralizada

**Respuesta correcta: A) Group Policy**

Las directivas de grupo permiten aplicar configuraciones de forma centralizada a usuarios y equipos.

---

## 13. Reglas de acceso NTFS

**Respuesta correcta: A) ACL**

Una ACL contiene las reglas de acceso asociadas a un recurso.

---

## 14. Ventaja de Active Directory

**Respuesta correcta: A)**

AD permite administrar centralizadamente identidades y recursos dentro de una estructura de dominio.

---

## 15. Permisos mediante grupos

**Respuesta correcta: A)**

Los permisos pueden asignarse a grupos y los miembros del grupo pueden obtener esos permisos.

Esto permite administrar permisos de forma mucho más eficiente que asignarlos individualmente a cada usuario.

---

## 16. Asociación correcta

**Respuesta correcta: C) LDAP → servicios de directorio**

Las otras asociaciones son incorrectas:

```text
DNS  → resolución de nombres
DHCP → configuración de red
LDAP → servicios de directorio
NTFS → sistema de archivos
```

---

# 🌐 BLOQUE 03 · REDES

## 17. Rango privado

**Respuesta correcta: A) `10.25.4.8`**

El rango privado correspondiente es:

```text
10.0.0.0/8
```

Por tanto, cualquier dirección `10.x.x.x` pertenece a ese rango privado.

---

## 18. DNS

**Respuesta correcta: A)**

DNS proporciona el sistema de resolución de nombres de dominio.

---

## 19. Switch y MAC

**Respuesta correcta: B) Switch**

Un switch opera principalmente en la capa de enlace y utiliza direcciones MAC para decidir el reenvío de tramas.

---

## 20. Router

**Respuesta correcta: A) Encaminamiento entre redes.**

El router conecta/interconecta redes y toma decisiones de encaminamiento.

---

## 21. TCP

**Respuesta correcta: B) TCP**

TCP proporciona comunicación orientada a conexión y mecanismos de entrega fiable y ordenada.

---

## 22. Administración remota segura

**Respuesta correcta: B) SSH**

SSH permite administrar remotamente sistemas mediante una comunicación protegida.

---

## 23. ARP

**Respuesta correcta: A)**

ARP permite asociar una dirección IPv4 con una dirección MAC en la red local.

---

## 24. Máscara de subred

**Respuesta correcta: A)**

La máscara permite determinar qué parte de una dirección corresponde a la red y cuál al host.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 25. Obtener datos

**Respuesta correcta: A) `SELECT`**

`SELECT` recupera datos de una tabla o conjunto de tablas.

---

## 26. `user_id`

**Respuesta correcta: B) Clave foránea.**

Si `user_id` referencia `users.id`, normalmente actúa como foreign key.

---

## 27. Modificar valores

**Respuesta correcta: A) `UPDATE`**

`UPDATE` modifica registros existentes.

---

## 28. `DELETE` frente a `DROP TABLE`

**Respuesta correcta: A)**

```text
DELETE FROM users
→ elimina filas

DROP TABLE users
→ elimina la tabla
```

Es una diferencia fundamental.

---

## 29. Eager loading

**Respuesta correcta: A) Eager loading**

En Eloquent puede realizarse, por ejemplo, mediante:

```php
User::with('posts')->get();
```

---

## 30. N+1

**Respuesta correcta: A) N+1**

El patrón consiste en:

```text
1 consulta inicial
+
N consultas adicionales
```

normalmente por acceder repetidamente a una relación.

El eager loading puede evitarlo cuando corresponda.

---

## 31. Atomicidad

**Respuesta correcta: A) Atomicidad**

Una transacción debe comportarse como una unidad:

```text
todo
o
nada
```

---

## 32. Durabilidad

**Respuesta correcta: D) Durabilidad**

La durabilidad significa que los cambios confirmados permanecen incluso ante determinados fallos posteriores.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 33. Acceso a instancia PHP

**Respuesta correcta: B) `->`**

Ejemplo:

```php
$user->name;
$user->save();
```

`::` se utiliza para acceso estático.

---

## 34. Middleware

**Respuesta correcta: A) Middleware**

El middleware puede intervenir durante el procesamiento de una petición y aplicar comprobaciones o modificar el flujo.

---

## 35. Inyección de dependencias

**Respuesta correcta: A)**

La DI reduce el acoplamiento entre una clase y la creación de sus dependencias.

Favorece:

```text
testabilidad
mantenimiento
sustitución de implementaciones
```

---

## 36. Clonar repositorio

**Respuesta correcta: A) `git clone`**

`git clone` crea una copia local de un repositorio remoto.

---

## 37. Fusionar ramas

**Respuesta correcta: A) `git merge`**

Integra los cambios de una rama en la rama actual mediante una operación de merge.

---

## 38. CI/CD

**Respuesta correcta: A)**

CI/CD permite automatizar procesos como:

```text
integración
↓
pruebas
↓
validaciones
↓
entrega/despliegue
```

---

## 39. HTTP 401

**Respuesta correcta: A) Código de estado HTTP**

`401 Unauthorized` indica que la petición requiere autenticación válida o que las credenciales proporcionadas no permiten autenticar correctamente la petición.

---

## 40. Estado compartido Vue 3

**Respuesta correcta: A) Pinia**

Pinia se utiliza para gestionar estado compartido en aplicaciones Vue.

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 41. Servicio caído

**Respuesta correcta: A) Gestión de incidentes**

El objetivo principal de la gestión de incidentes es restaurar el servicio normal y minimizar el impacto.

---

## 42. Causa subyacente

**Respuesta correcta: A) Gestión de problemas**

La gestión de problemas busca investigar y gestionar las causas de los incidentes y prevenir su recurrencia cuando sea posible.

---

## 43. Maximizar valor

**Respuesta correcta: A) Product Owner**

El Product Owner es responsable de maximizar el valor del producto y de gestionar eficazmente el Product Backlog.

---

## 44. Inspeccionar incremento

**Respuesta correcta: A) Sprint Review**

En la Sprint Review se inspecciona el resultado del Sprint y se consideran adaptaciones futuras.

---

## 45. Mejorar la forma de trabajo

**Respuesta correcta: A) Sprint Retrospective**

La Retrospective se centra en inspeccionar cómo se desarrolló el Sprint y en identificar mejoras para el siguiente.

---

## 46. PRINCE2

**Respuesta correcta: A) Un método de gestión de proyectos**

PRINCE2 proporciona un método estructurado para dirigir y gestionar proyectos.

---

## 47. ISO/IEC 20000

**Respuesta correcta: A) Gestión de servicios de TI**

Su ámbito está relacionado con los sistemas de gestión de servicios de TI.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 48. Confidencialidad

**Respuesta correcta: A)**

Si una persona no autorizada obtiene acceso a información privada, se ve comprometida principalmente la confidencialidad.

---

## 49. Integridad

**Respuesta correcta: A)**

Una modificación no autorizada de los datos afecta principalmente a su integridad.

---

## 50. Disponibilidad

**Respuesta correcta: A)**

Si un servidor crítico deja de estar disponible, se compromete principalmente la disponibilidad.

---

## 51. ENS

**Respuesta correcta: A)**

El ENS establece principios y requisitos para proteger la información y los servicios dentro de su ámbito de aplicación en el sector público.

---

## 52. Minimización

**Respuesta correcta: A) Minimización de datos**

Los datos personales tratados deben ser adecuados, pertinentes y limitados a lo necesario respecto a los fines del tratamiento.

---

## 53. Derecho de acceso

**Respuesta correcta: A) Acceso**

Permite obtener confirmación sobre si se están tratando datos personales y acceder a ellos en las condiciones previstas.

---

## 54. Certificado digital

**Respuesta correcta: A) Certificado digital**

Un certificado permite vincular una identidad con una clave pública dentro de una infraestructura de confianza.

---

## 55. Autoridad de certificación

**Respuesta correcta: A)**

La CA emite certificados digitales conforme a sus procedimientos y políticas.

---

## 56. Firewall

**Respuesta correcta: A) Firewall**

Un firewall filtra comunicaciones de red según reglas configuradas.

---

## 57. Phishing

**Respuesta correcta: A) Phishing**

El atacante intenta engañar al usuario para obtener credenciales u otra información mediante una comunicación fraudulenta.

---

# 🧪 BLOQUE 08 · IMIDA

## 58. BPL

**Respuesta correcta: A)**

Las Buenas Prácticas de Laboratorio buscan establecer un marco que favorezca la calidad, integridad, trazabilidad y documentación adecuada de determinados estudios.

---

## 59. Protocolo

**Respuesta correcta: A) Protocolo**

El protocolo establece previamente los objetivos y metodología del estudio.

---

## 60. Garantía de Calidad

**Respuesta correcta: A)**

La función de Garantía de Calidad supervisa de manera independiente el cumplimiento de los principios aplicables.

🎯 **Concepto clave:** independencia.

---

## 61. Identificación y trazabilidad

**Respuesta correcta: A)**

Una identificación robusta puede relacionar:

```text
código
+
procedencia
+
fecha/hora
+
responsable
```

con la muestra y el resto de documentación.

---

## 62. Representatividad

**Respuesta correcta: A) Representatividad**

Si queremos extraer conclusiones sobre un conjunto, el diseño debe buscar que las muestras sean representativas de aquello que queremos estudiar.

---

## 63. Selección únicamente de síntomas

**Respuesta correcta: A)**

Seleccionar exclusivamente las zonas sintomáticas introduce un posible sesgo de selección.

Puede servir para estudiar específicamente las zonas afectadas, pero no permite afirmar automáticamente que esas muestras representan toda la parcela.

---

## 64. Herramienta sin limpiar

**Respuesta correcta: A) Contaminación cruzada**

La herramienta puede transferir material de una muestra a otra y alterar los resultados.

---

## 65. Recipiente roto

**Respuesta correcta: A)**

La actuación correcta es:

```text
registrar incidencia
↓
evaluar integridad
↓
seguir procedimiento
↓
documentar decisión
```

No se debe ocultar la incidencia.

---

## 66. Trazabilidad

**Respuesta correcta: A)**

La cadena adecuada es:

```text
Origen
↓
Toma
↓
Identificación
↓
Conservación / transporte
↓
Recepción
↓
Análisis
↓
Resultado
```

---

# 🧠 BLOQUE TRANSVERSAL

## 67. MySQL consumiendo CPU

**Respuesta correcta: A)**

La respuesta correcta es diagnosticar antes de realizar acciones destructivas.

Una aproximación razonable:

```text
procesos
↓
CPU / memoria / carga
↓
actividad MySQL
↓
consultas
↓
índices / concurrencia / configuración
```

El dato de que hay espacio de disco y memoria disponible ayuda a descartar algunas causas inmediatas, pero no identifica por sí solo el origen del problema.

---

## 68. Laravel + 500 clientes + pedidos

**Respuesta correcta: A) N+1**

El patrón es:

```text
1 consulta → clientes
+
500 consultas → pedidos
```

Una estrategia de eager loading puede reducir este patrón cuando la relación y el caso de uso lo permiten.

---

## 69. Proyecto transversal

**Respuesta correcta: A)**

El escenario combina:

```text
Gestión TIC
→ gestión del servicio

Desarrollo
→ desarrollo iterativo

Seguridad
→ protección de sistemas

RGPD
→ datos personales

IMIDA
→ investigación y trazabilidad de muestras
```

Por tanto, intervienen varios bloques simultáneamente.

---

## 70. Muestreo sesgado

**Respuesta correcta: C) Existe un problema de representatividad derivado del diseño del muestreo.**

Esta es una de las preguntas más importantes del simulacro.

Tenemos:

```text
IDENTIFICACIÓN CORRECTA
        +
CONSERVACIÓN CORRECTA
        +
ANÁLISIS CORRECTO
```

pero:

```text
SELECCIÓN SESGADA
        ↓
MUESTRA NO REPRESENTATIVA
```

La trazabilidad garantiza que sepamos qué muestra es y de dónde procede. No convierte una muestra sesgada en representativa.

El análisis puede ser técnicamente perfecto y aun así no permitir extrapolar el resultado a toda la parcela.

---

# 📊 RESULTADO

Si todas las preguntas tienen el mismo peso:

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

⚠️ Si la convocatoria real aplica penalización por respuestas incorrectas, debe utilizarse la fórmula oficial.

---

# 🧠 INTERPRETACIÓN

| Aciertos | Diagnóstico |
|---:|---|
| 0–34 | 🔴 Hay lagunas importantes |
| 35–44 | 🟠 Base razonable, necesita consolidación |
| 45–52 | 🟡 Buen nivel |
| 53–59 | 🟢 Nivel sólido |
| 60–65 | 🟢 Muy buen nivel |
| 66–70 | 🏆 Dominio excelente |

Pero esta tabla no es una sentencia. Lo verdaderamente útil es observar **qué has fallado**.

---

# 🔍 CLASIFICACIÓN DE FALLOS

## 🔴 A · No lo sabía

Hay que volver al temario.

## 🟠 B · Confusión

Sabías los conceptos, pero los intercambiaste.

Especialmente peligrosos:

```text
df / free
DNS / DHCP
switch / router
IP / MAC
DELETE / DROP
incidente / problema
Product Owner / Scrum Master
Review / Retrospective
confidencialidad / integridad / disponibilidad
muestra dirigida / representativa
muestreo / análisis
```

## 🟡 C · Despiste

Lo sabías, pero leíste mal o contestaste demasiado rápido.

## 🟣 D · Duda

Acertaste, pero estabas entre dos.

Estos aciertos deben revisarse también.

---

# 🏆 CHECKLIST FINAL

Si puedes explicar sin consultar apuntes estas parejas, tienes una base muy sólida:

```text
☑ df / free
☑ /etc / /var / /home / /proc
☑ permisos octales
☑ systemctl / kill
☑ AD DS
☑ LDAP
☑ DNS / DHCP
☑ switch / router
☑ IP / MAC
☑ TCP / UDP
☑ clave primaria / foránea
☑ DELETE / DROP
☑ ACID
☑ N+1 / eager loading
☑ middleware
☑ DI
☑ Git clone / merge
☑ CI/CD
☑ incidente / problema
☑ Product Owner / Scrum Master
☑ Sprint Review / Retrospective
☑ PRINCE2
☑ ISO 20000
☑ ENS
☑ CIA
☑ RGPD
☑ certificado / autoridad de certificación
☑ firewall
☑ phishing
☑ BPL
☑ Garantía de Calidad
☑ protocolo
☑ residuos
☑ trazabilidad
☑ representatividad
☑ error de muestreo / error analítico
```

---

# 📈 LOS TRES SIMULACROS EN CONJUNTO

Ya tienes:

```text
SIMULACRO GENERAL 01
        ↓
70 preguntas
        ↓
DIAGNÓSTICO

SIMULACRO GENERAL 02
        ↓
70 preguntas
        ↓
APLICACIÓN

SIMULACRO FINAL 03
        ↓
70 preguntas
        ↓
CIERRE
```

**210 preguntas generales** entre los tres simulacros.

Y a eso se suman las misiones y ejercicios realizados durante los ocho bloques.

---

# 🎓 FIN DE LA FASE DE SIMULACROS

```text
╔════════════════════════════════════╗
║                                    ║
║        BLOQUES 01 → 08       ✓     ║
║        MISIONES 01 → 16      ✓     ║
║        SIMULACRO 01          ✓     ║
║        SIMULACRO 02          ✓     ║
║        SIMULACRO FINAL 03    ✓     ║
║                                    ║
║          210 PREGUNTAS             ║
║                                    ║
║        TEMARIO COMPLETO            ║
║              ✓                     ║
║                                    ║
╚════════════════════════════════════╝
```

> **A partir de aquí, el objetivo cambia: menos contenido nuevo y más recuperación activa, repasos selectivos y análisis de errores.**

