# 🏆 SIMULACRO FINAL · EL ÚLTIMO MONSTRUO
## Plantilla, respuestas y corrección · 100 preguntas

# 📊 PLANTILLA RÁPIDA

```text
01 B   02 B   03 A   04 B   05 B   06 A   07 A   08 A   09 B   10 B
11 A   12 A   13 A   14 B   15 B   16 A   17 A   18 B   19 B   20 C
21 A   22 B   23 A   24 D   25 B   26 A   27 B   28 B   29 A   30 A
31 A   32 A   33 B   34 A   35 B   36 B   37 A   38 B   39 A   40 A
41 A   42 A   43 A   44 A   45 A   46 A   47 C   48 D   49 B   50 A
51 A   52 A   53 A   54 A   55 A   56 C   57 A   58 A   59 A   60 A
61 A   62 A   63 A   64 A   65 A   66 A   67 A   68 A   69 A   70 A
71 A   72 A   73 B   74 C   75 A   76 A   77 A   78 B   79 A   80 A
81 A   82 A   83 A   84 A   85 A   86 A   87 A   88 A   89 A   90 A
91 A   92 A   93 A   94 A   95 A   96 A   97 A   98 A   99 B   100 B
```

> **Nota:** Las preguntas 47, 48, 56, 73 y 74 tienen respuestas deliberadamente distintas del patrón dominante para evitar que el examen pueda resolverse por distribución estadística.

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1. B · `free -h`

`free` informa de memoria RAM y swap. `-h` muestra valores legibles.

**Clave:** `df` → almacenamiento; `free` → memoria.

## 2. B · `/etc`

`/etc` contiene configuración del sistema y servicios.

## 3. A · `whoami`

Muestra el usuario efectivo actual.

## 4. B · `/proc`

Es un sistema de archivos virtual que expone información del kernel y de procesos.

## 5. B · `755`

```text
7 = rwx
5 = r-x
5 = r-x
```

## 6. A · `systemctl status`

Permite consultar el estado de una unidad, como un servicio systemd.

## 7. A · `journalctl`

Consulta los registros de journald.

## 8. A · `ps aux | grep postgresql`

Permite listar procesos y filtrar aquellos relacionados con PostgreSQL.

## 9. B · `htop`

Herramienta interactiva para observar procesos y recursos.

## 10. B · `scp`

Copia archivos entre sistemas mediante SSH.

## 11. A · `tar`

Permite crear y manipular archivos de archivado.

## 12. A · `crontab`

Permite definir tareas periódicas para un usuario.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 13. A · Active Directory Domain Services

Centraliza identidades, equipos y recursos en servicios de directorio.

## 14. B · LDAP

LDAP es el protocolo asociado al acceso y consulta de servicios de directorio.

## 15. B · DHCP

Proporciona automáticamente parámetros como IP, máscara, gateway y DNS.

## 16. A · Group Policy

Permite aplicar configuraciones y políticas de forma centralizada.

## 17. A · ACL

Una Access Control List contiene reglas de acceso a un recurso.

## 18. B · NTFS

NTFS soporta permisos detallados y mecanismos de seguridad.

## 19. B

Los permisos pueden asignarse a grupos y aplicarse a sus miembros según la configuración.

## 20. C · LDAP → servicios de directorio

Las asociaciones correctas son:

```text
DNS  → resolución de nombres
DHCP → configuración de red
LDAP → directorio
NTFS → sistema de archivos
```

## 21. A · Dominio

El dominio proporciona un límite lógico y administrativo en Active Directory.

## 22. B

Una de las grandes ventajas de AD es la administración centralizada.

## 23. A · DHCP

Es el servicio encargado de la configuración automática de red.

## 24. D

NTFS no asigna direcciones IP dinámicamente.

---

# 🌐 BLOQUE 03 · REDES

## 25. B · `172.20.10.5`

Está dentro del rango privado:

```text
172.16.0.0/12
```

## 26. A · DNS

DNS proporciona resolución de nombres.

## 27. B · DHCP

Asigna dinámicamente parámetros de configuración de red.

## 28. B · Switch

Un switch utiliza principalmente direcciones MAC para el reenvío en una LAN.

## 29. A · Router

Un router realiza encaminamiento entre redes.

## 30. A · ARP

ARP relaciona una dirección IPv4 con una MAC en la red local.

## 31. A · TCP

TCP es orientado a conexión y proporciona mecanismos para entrega fiable y ordenada.

## 32. A · Máscara de subred

Determina la parte de red y host de una dirección.

## 33. B · SSH

SSH proporciona administración remota segura mediante terminal.

## 34. A · DNS

Si la IP funciona y el nombre no, DNS es uno de los primeros servicios a comprobar.

## 35. B · MAC

La MAC identifica la interfaz en el ámbito de enlace.

## 36. B · Router

El encaminamiento entre redes corresponde principalmente al router.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 37. A · `SELECT`

Recupera datos.

## 38. B · `UPDATE`

Modifica registros existentes.

## 39. A · `DELETE`

Elimina filas sin eliminar necesariamente la estructura de la tabla.

## 40. A · `ALTER TABLE`

Modifica la estructura de una tabla.

## 41. A · Clave primaria

Identifica inequívocamente cada fila.

## 42. A · Clave foránea

Representa normalmente una relación con otra tabla.

## 43. A · N+1

Una consulta inicial seguida de una consulta por cada elemento es el patrón clásico N+1.

## 44. A · Eager loading

Carga anticipadamente las relaciones.

## 45. A · `with()`

Ejemplo:

```php
User::with('posts')->get();
```

## 46. A · Atomicidad

La transacción se comporta como una unidad indivisible.

## 47. C · Aislamiento

Isolation controla cómo interactúan las transacciones concurrentes.

## 48. D · Durabilidad

Los cambios confirmados deben persistir ante determinados fallos posteriores.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 49. B · `->`

Se utiliza para acceder a propiedades y métodos de una instancia.

## 50. A · Middleware

Puede intervenir en el ciclo de procesamiento de una petición.

## 51. A

La inyección de dependencias reduce acoplamiento y facilita pruebas y sustituciones.

## 52. A · `git clone`

Crea una copia local de un repositorio remoto.

## 53. A · `git merge`

Fusiona una rama en la rama actual.

## 54. A · CI/CD

Automatiza integración, pruebas y procesos de entrega o despliegue.

## 55. A · GET

Se utiliza normalmente para obtener recursos.

## 56. C · DELETE

Se utiliza normalmente para eliminar recursos.

## 57. A · Pinia

Gestiona estado compartido en Vue.

## 58. A · Código HTTP

404 significa que el recurso solicitado no se ha encontrado.

## 59. A

Separar frontend y backend permite separar responsabilidades y facilita una arquitectura cliente-servidor/API.

## 60. A

El desacoplamiento busca reducir dependencias innecesarias respecto de implementaciones concretas.

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 61. A · Gestión de incidentes

Busca restaurar el servicio y minimizar el impacto.

## 62. A · Gestión de problemas

Investiga y gestiona causas de incidentes.

## 63. A · Gestión de cambios

Gestiona modificaciones planificadas de servicios.

## 64. A · Product Owner

Responsable de maximizar el valor del producto.

## 65. A · Sprint Review

Inspecciona el resultado del Sprint y permite considerar adaptaciones futuras.

## 66. A · Sprint Retrospective

Se centra en mejorar la forma de trabajo.

## 67. A · Product Backlog

Contiene el trabajo conocido y potencial para evolucionar el producto.

## 68. A · PRINCE2

Es un método estructurado de gestión de proyectos.

## 69. A · ISO/IEC 20000

Se relaciona con sistemas de gestión de servicios de TI.

## 70. A

ITIL se centra en la gestión de servicios; Scrum es un marco de trabajo para desarrollar/adaptar productos de forma iterativa e incremental.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 71. A · Confidencialidad, integridad y disponibilidad

La tríada CIA:

```text
C → Confidencialidad
I → Integridad
A → Disponibilidad
```

## 72. A · Confidencialidad

Acceso no autorizado a información.

## 73. B · Integridad

Una modificación no autorizada afecta principalmente a la integridad.

## 74. C · Disponibilidad

La caída de un servidor compromete la disponibilidad.

## 75. A · ENS

Establece principios y requisitos de seguridad para proteger información y servicios dentro de su ámbito.

## 76. A · Minimización

Los datos deben limitarse a lo necesario respecto a los fines del tratamiento.

## 77. A · Acceso

Permite conocer y acceder a los datos personales tratados en las condiciones previstas.

## 78. B · Supresión

Permite solicitar la eliminación cuando concurren las condiciones establecidas.

## 79. A · Certificado digital

Vincula una identidad con una clave pública dentro de una infraestructura de confianza.

## 80. A · Autoridad de certificación

Emite certificados digitales conforme a sus políticas y procedimientos.

## 81. A · Firewall

Filtra comunicaciones según reglas.

## 82. A · Phishing

Engaño para obtener credenciales u otra información.

## 83. A · MFA

Un segundo factor reduce el riesgo de que una contraseña robada sea suficiente.

## 84. A · Mínimo privilegio

Cada usuario o proceso debe tener solo los permisos necesarios.

---

# 🧪 BLOQUE 08 · IMIDA

## 85. A · BPL

Las Buenas Prácticas de Laboratorio buscan favorecer la calidad, integridad, trazabilidad y documentación adecuada de determinados estudios.

## 86. A · Protocolo

Establece previamente objetivos y metodología.

## 87. A · Garantía de Calidad

Debe mantener independencia respecto de la ejecución del estudio que supervisa.

## 88. A

Código, procedencia, fecha/hora y responsable contribuyen a identificar y mantener la trazabilidad de la muestra.

## 89. A · Representatividad

La muestra debe reflejar adecuadamente las características relevantes del conjunto que se pretende estudiar.

## 90. A

Seleccionar exclusivamente zonas sintomáticas puede introducir sesgo y hacer que las muestras no sean representativas del conjunto.

## 91. A · Contaminación cruzada

Una herramienta contaminada puede transferir material de una muestra a otra.

## 92. A

Una incidencia debe registrarse, evaluarse y gestionarse según el procedimiento.

## 93. A

La desviación de conservación debe registrarse y evaluarse.

## 94. A

La trazabilidad sigue el recorrido:

```text
origen
↓
toma
↓
identificación
↓
conservación/transporte
↓
recepción
↓
análisis
↓
resultado
```

## 95. A

La gestión correcta depende del tipo de residuo y de la normativa aplicable, incluyendo identificación, segregación, envasado, etiquetado, almacenamiento y gestión adecuada.

---

# 🧠 BLOQUE TRANSVERSAL

## 96. A

La actuación correcta es diagnosticar antes de realizar cambios destructivos.

Una aproximación razonable:

```text
procesos
↓
recursos
↓
MySQL
↓
consultas
↓
índices / concurrencia / configuración
```

## 97. A · N+1 + eager loading

La aplicación realiza una consulta inicial y consultas adicionales por cada elemento.

## 98. A

El proyecto combina:

```text
Gestión TIC
+
Desarrollo
+
Seguridad
+
RGPD
+
IMIDA
```

## 99. B

El problema está en el diseño del muestreo.

Un análisis correcto no convierte una muestra sesgada en representativa.

## 100. B

El escenario combina gestión TIC, desarrollo, seguridad, protección de datos e investigación/actividad del ámbito IMIDA.

---

# 📊 PUNTUACIÓN

Si todas las preguntas tienen el mismo peso:

```text
NOTA = aciertos / 100 × 10
```

| Aciertos | Nota /10 |
|---:|---:|
| 50 | 5,00 |
| 55 | 5,50 |
| 60 | 6,00 |
| 65 | 6,50 |
| 70 | 7,00 |
| 75 | 7,50 |
| 80 | 8,00 |
| 85 | 8,50 |
| 90 | 9,00 |
| 95 | 9,50 |
| 100 | 10,00 |

> Si la convocatoria establece penalización por respuestas incorrectas, utiliza la fórmula oficial en lugar de esta conversión simple.

---

# 🎯 INTERPRETACIÓN ORIENTATIVA

| Aciertos | Lectura |
|---:|---|
| 0–49 | 🔴 Hay que reforzar contenidos |
| 50–64 | 🟠 Base razonable, pero con lagunas |
| 65–74 | 🟡 Nivel aceptable |
| 75–84 | 🟢 Buen nivel |
| 85–94 | 🟢 Muy buen nivel |
| 95–100 | 🏆 Dominio extraordinario |

Pero hay una regla más importante:

> **Un error repetido en varios simulacros vale más que diez errores aislados.**

---

# 🔍 CLASIFICACIÓN DE LOS FALLOS

Para cada pregunta fallada, marca una categoría:

### A · Desconocimiento
No conocías el concepto.

### B · Confusión
Conocías las dos opciones, pero mezclaste conceptos.

### C · Despiste
Lo sabías, pero leíste mal.

### D · Duda
Acertaste, pero dudaste.

### E · Razonamiento
Conocías la teoría, pero no supiste aplicarla al escenario.

La categoría **E** es especialmente importante en este último monstruo.

---

# 🧠 REPASO DE ALTO RENDIMIENTO

Si haces este simulacro offline y detectas errores, no vuelvas a estudiar las 100 preguntas por igual.

Haz esto:

```text
ERROR
 ↓
¿POR QUÉ FALLÉ?
 ↓
CONCEPTO
 ↓
EXPLICARLO SIN MIRAR
 ↓
HACER UNA PREGUNTA NUEVA
```

Y clasifica los conceptos en:

```text
🔴 NO SÉ
🟠 CONFUNDO
🟡 DUDO
🟢 DOMINO
```

---

# 🏆 EL ÚLTIMO MONSTRUO

Has llegado a:

```text
8 BLOQUES
      ↓
16 MISIONES
      ↓
3 SIMULACROS DE 70
      ↓
210 PREGUNTAS
      ↓
1 SIMULACRO FINAL
      ↓
100 PREGUNTAS
      ↓
310 PREGUNTAS GENERALES
```

A partir de aquí, el objetivo ya no es construir otro temario.

Es:

```text
REPASO
  ↓
RECUPERACIÓN ACTIVA
  ↓
CORRECCIÓN
  ↓
ERRORES
  ↓
REPASO SELECTIVO
  ↓
NUEVO TEST
```

## 🎓 FIN DEL ÚLTIMO MONSTRUO
