<!-- encabezado-homogeneizado -->
# Simulacros Finales - SIMULACRO
> **Bloque:** Simulacros Finales  
> **Documento:** Simulacro  
> **Preguntas de referencia:** N/D  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 📝 SIMULACRO GENERAL 01 · OPOSICIÓN IMIDA
## 70 preguntas · Bloques 01 → 08

> **Modo examen**
>
> Este simulacro está diseñado para realizarse **sin consultar apuntes**.
>
> - 70 preguntas.
> - 4 opciones por pregunta.
> - Una única respuesta correcta.
> - No se incluyen soluciones en este documento.
> - Algunas preguntas son conceptuales y otras plantean pequeños casos prácticos.
> - Las preguntas mezclan deliberadamente los bloques para evitar estudiar por "compartimentos estancos".
>
> **Consejo:** anota tus respuestas en una plantilla aparte:
>
> `1A · 2C · 3B · ...`
>
> y no cambies una respuesta salvo que detectes un error claro en tu razonamiento.

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1.
En GNU/Linux, ¿qué directorio contiene habitualmente los archivos de configuración del sistema?

A) `/home`  
B) `/etc`  
C) `/var`  
D) `/proc`

---

## 2.
¿Qué comando permite conocer la identidad del usuario actualmente autenticado?

A) `whoami`  
B) `userset`  
C) `iduser`  
D) `hostname`

---

## 3.
Un administrador ejecuta:

```bash
df -h
```

¿Qué información obtiene principalmente?

A) Memoria RAM disponible  
B) Procesos activos  
C) Espacio utilizado y disponible en sistemas de archivos  
D) Usuarios conectados

---

## 4.
¿Qué permiso representa el valor octal `755`?

A) `rwxr-xr-x`  
B) `rw-r--r--`  
C) `rwxrwxrwx`  
D) `r--r--r--`

---

## 5.
¿Qué comando permite consultar el estado de un servicio gestionado por systemd?

A) `service-check`  
B) `systemctl status`  
C) `systemd-info`  
D) `daemon status`

---

## 6.
Un administrador quiere observar procesos y consumo de recursos en tiempo real desde una interfaz interactiva. ¿Qué herramienta es especialmente adecuada?

A) `tar`  
B) `grep`  
C) `htop`  
D) `scp`

---

## 7.
¿Qué directorio virtual proporciona información sobre procesos y otros elementos del kernel?

A) `/proc`  
B) `/boot`  
C) `/opt`  
D) `/srv`

---

## 8.
¿Qué comando se utiliza habitualmente para copiar archivos entre sistemas mediante SSH?

A) `scp`  
B) `cpnet`  
C) `sshcopy`  
D) `rsyncssh`

---

## 9.
¿Cuál es la finalidad principal de `journalctl`?

A) Modificar permisos  
B) Consultar registros del sistema gestionados por journald  
C) Crear usuarios  
D) Gestionar particiones

---

## 10.
¿Qué comando permite programar tareas periódicas para un usuario mediante cron?

A) `cronjob`  
B) `crontab`  
C) `taskctl`  
D) `sched`

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 11.
En Windows Server, ¿qué tecnología proporciona servicios de directorio para centralizar la gestión de usuarios, equipos y recursos?

A) IIS  
B) Active Directory Domain Services  
C) Hyper-V  
D) BitLocker

---

## 12.
¿Qué protocolo utiliza Active Directory para proporcionar servicios de directorio?

A) LDAP  
B) FTP  
C) SMTP  
D) SNMP

---

## 13.
¿Qué elemento permite agrupar usuarios y equipos dentro de una estructura lógica de Active Directory?

A) Dominio  
B) Socket  
C) Registro  
D) Volumen lógico

---

## 14.
En NTFS, ¿qué característica permite establecer permisos detallados sobre archivos y carpetas?

A) ACL  
B) DHCP  
C) DNS  
D) RAID

---

## 15.
¿Cuál de las siguientes afirmaciones sobre NTFS es correcta?

A) Solo permite permisos de lectura y escritura  
B) Es un sistema de archivos propio de Linux  
C) Permite establecer permisos y mantener características de seguridad  
D) No permite herencia de permisos

---

## 16.
¿Qué servicio se utiliza habitualmente para resolver nombres de dominio en una red Windows?

A) DNS  
B) DHCP  
C) SMB  
D) RDP

---

## 17.
¿Qué función tiene DHCP?

A) Resolver nombres  
B) Asignar dinámicamente parámetros de configuración de red  
C) Autenticar usuarios de Active Directory  
D) Cifrar discos

---

## 18.
Una organización quiere aplicar configuraciones de seguridad de manera centralizada a usuarios y equipos de un dominio. ¿Qué mecanismo resulta especialmente apropiado?

A) Group Policy  
B) Task Manager  
C) Windows Defender Offline  
D) Disk Cleanup

---

# 🌐 BLOQUE 03 · REDES

## 19.
¿Qué dispositivo opera principalmente en la capa de enlace de datos y utiliza direcciones MAC para tomar decisiones de reenvío?

A) Router  
B) Switch  
C) Firewall de aplicación  
D) Proxy DNS

---

## 20.
¿Cuál es la función principal de un router?

A) Conectar redes diferentes y dirigir tráfico entre ellas  
B) Almacenar archivos  
C) Resolver nombres exclusivamente  
D) Gestionar usuarios

---

## 21.
¿Cuál de las siguientes direcciones pertenece al rango privado IPv4?

A) `8.8.8.8`  
B) `172.16.10.20`  
C) `1.1.1.1`  
D) `200.20.10.5`

---

## 22.
¿Qué protocolo traduce nombres de dominio a direcciones IP?

A) DHCP  
B) DNS  
C) ARP  
D) ICMP

---

## 23.
¿Qué protocolo se utiliza habitualmente para obtener automáticamente una dirección IP y otros parámetros de configuración?

A) DNS  
B) DHCP  
C) SSH  
D) HTTP

---

## 24.
¿Qué dirección se utiliza para identificar una interfaz de red a nivel de enlace?

A) IP  
B) MAC  
C) URL  
D) FQDN

---

## 25.
Un equipo puede acceder a una dirección IP externa, pero no puede resolver `www.ejemplo.com`. ¿Qué servicio debería comprobarse en primer lugar?

A) DHCP  
B) DNS  
C) FTP  
D) SSH

---

## 26.
¿Cuál es una característica fundamental de TCP frente a UDP?

A) TCP proporciona comunicación orientada a conexión y mecanismos de control de entrega  
B) TCP no utiliza puertos  
C) UDP garantiza siempre la entrega  
D) UDP establece una conexión antes de transmitir

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 27.
¿Qué sentencia SQL se utiliza para recuperar datos?

A) `GET`  
B) `SELECT`  
C) `FETCH TABLE`  
D) `READ`

---

## 28.
¿Qué característica define principalmente a una clave primaria?

A) Puede repetirse libremente  
B) Identifica de forma única cada fila  
C) Solo puede contener texto  
D) Siempre debe ser una clave foránea

---

## 29.
¿Qué tipo de relación representa habitualmente una clave foránea?

A) Una relación entre una fila y una tabla de sistema exclusivamente  
B) Una relación entre registros de diferentes tablas  
C) Una relación entre dos procesos  
D) Una relación entre usuarios del sistema operativo

---

## 30.
En Laravel, ¿qué mecanismo permite cargar anticipadamente relaciones Eloquent para evitar consultas innecesarias?

A) Lazy collection  
B) Eager loading mediante `with()`  
C) Route model binding  
D) Middleware

---

## 31.
¿Qué problema intenta evitar principalmente el eager loading cuando se trabaja con relaciones?

A) XSS  
B) N+1 queries  
C) Deadlock del sistema operativo  
D) DNS spoofing

---

## 32.
¿Qué sentencia SQL se utiliza para modificar registros existentes?

A) `CHANGE`  
B) `UPDATE`  
C) `ALTER ROW`  
D) `MODIFY DATA`

---

## 33.
¿Qué sentencia SQL elimina filas de una tabla?

A) `REMOVE`  
B) `DELETE`  
C) `DROP ROW`  
D) `ERASE`

---

## 34.
¿Qué propiedad caracteriza a una transacción ACID relacionada con la idea de que una transacción se ejecuta completamente o no se aplica?

A) Atomicidad  
B) Consistencia  
C) Aislamiento  
D) Durabilidad

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 35.
En PHP, ¿qué símbolo se utiliza para acceder a una propiedad o método de una instancia?

A) `::`  
B) `->`  
C) `=>`  
D) `.`

---

## 36.
En Laravel, ¿qué componente se utiliza habitualmente para definir rutas HTTP?

A) Eloquent  
B) Router / archivos de rutas  
C) Blade Compiler exclusivamente  
D) Artisan Queue

---

## 37.
¿Qué ventaja principal aporta la inyección de dependencias?

A) Elimina automáticamente todas las consultas SQL  
B) Reduce el acoplamiento y facilita la sustitución y prueba de dependencias  
C) Impide utilizar interfaces  
D) Sustituye el control de versiones

---

## 38.
¿Qué herramienta de control de versiones se utiliza habitualmente en proyectos Laravel/Vue?

A) Git  
B) FTP  
C) Telnet  
D) SMTP

---

## 39.
En Git, ¿qué comando permite crear una copia local de un repositorio remoto?

A) `git clone`  
B) `git fork-local`  
C) `git pull-repository`  
D) `git copy`

---

## 40.
¿Qué objetivo principal tiene CI/CD?

A) Sustituir el sistema operativo  
B) Automatizar procesos de integración, pruebas y entrega/despliegue de software  
C) Eliminar las bases de datos  
D) Evitar el uso de Git

---

## 41.
En una API REST, ¿qué método HTTP se utiliza normalmente para obtener un recurso?

A) POST  
B) GET  
C) PATCH  
D) DELETE

---

## 42.
En Vue 3, ¿qué herramienta se utiliza habitualmente para gestionar estado global en una aplicación?

A) Pinia  
B) PHPUnit  
C) Composer  
D) Artisan

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 43.
En ITIL, ¿qué concepto representa un conjunto de capacidades organizativas y profesionales que permiten proporcionar valor mediante servicios?

A) Servicio  
B) Incidente  
C) Evento  
D) Cambio estándar

---

## 44.
¿Cuál es el objetivo principal de la gestión de incidentes?

A) Diseñar nuevos productos  
B) Restaurar el servicio normal lo antes posible y minimizar el impacto negativo  
C) Sustituir todos los servidores  
D) Crear contratos jurídicos

---

## 45.
En Scrum, ¿quién es responsable de maximizar el valor del producto y gestionar eficazmente el Product Backlog?

A) Scrum Master  
B) Product Owner  
C) Developers exclusivamente  
D) Project Manager tradicional

---

## 46.
¿Qué caracteriza principalmente a un Sprint?

A) Un periodo de tiempo fijo en el que se crea un incremento de valor  
B) Una reunión anual  
C) Una fase exclusiva de documentación  
D) Un mecanismo de auditoría

---

## 47.
PRINCE2 se caracteriza por ser:

A) Un lenguaje de programación  
B) Un método estructurado de gestión de proyectos  
C) Un sistema operativo  
D) Un protocolo de red

---

## 48.
ISO/IEC 20000 está relacionada principalmente con:

A) Gestión de servicios de TI  
B) Sistemas de archivos  
C) Criptografía asimétrica  
D) Desarrollo de videojuegos

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 49.
¿Cuál es el objetivo general del Esquema Nacional de Seguridad?

A) Regular exclusivamente las redes Wi-Fi domésticas  
B) Establecer los principios y requisitos necesarios para proteger la información y los servicios de las Administraciones Públicas  
C) Sustituir al RGPD  
D) Regular únicamente los certificados digitales

---

## 50.
¿Cuál de las siguientes dimensiones forma parte del enfoque clásico de seguridad de la información?

A) Confidencialidad  
B) Rentabilidad  
C) Usabilidad comercial  
D) Velocidad

---

## 51.
Según el RGPD, ¿qué principio exige que los datos personales sean adecuados, pertinentes y limitados a lo necesario?

A) Minimización de datos  
B) Portabilidad  
C) Exactitud  
D) Limitación de conservación

---

## 52.
¿Qué derecho permite a una persona obtener confirmación sobre si se están tratando sus datos personales y, en su caso, acceder a ellos?

A) Derecho de acceso  
B) Derecho de oposición  
C) Derecho de supresión  
D) Derecho a la limitación

---

## 53.
¿Qué característica diferencia principalmente un certificado digital de una simple contraseña?

A) El certificado permite vincular una identidad con una clave pública mediante una infraestructura de confianza  
B) El certificado nunca caduca  
C) El certificado solo funciona sin criptografía  
D) El certificado sustituye siempre a cualquier mecanismo de autenticación

---

## 54.
¿Qué función cumple una autoridad de certificación?

A) Generar direcciones IP  
B) Emitir certificados digitales y establecer una relación de confianza sobre la identidad asociada  
C) Gestionar discos duros  
D) Asignar puertos TCP

---

## 55.
¿Cuál es una función fundamental de un firewall?

A) Filtrar tráfico de red según reglas definidas  
B) Sustituir el sistema operativo  
C) Crear copias de seguridad  
D) Compilar programas

---

## 56.
Un atacante intenta engañar a empleados mediante un correo electrónico falso para obtener sus credenciales. ¿Qué tipo de ataque es?

A) Phishing  
B) DDoS  
C) ARP legítimo  
D) Backup incremental

---

## 57.
¿Qué principio de seguridad busca garantizar que la información no sea modificada de forma no autorizada?

A) Integridad  
B) Disponibilidad  
C) Confidencialidad  
D) Replicación

---

## 58.
¿Qué medida reduce especialmente el impacto de una contraseña robada?

A) MFA / autenticación multifactor  
B) Desactivar las actualizaciones  
C) Utilizar la misma contraseña en todos los servicios  
D) Compartir credenciales con el equipo

---

# 🧪 BLOQUE 08 · IMIDA

## 59.
¿Cuál es la función general del IMIDA dentro del ámbito de la Región de Murcia?

A) Desarrollar y coordinar actividades de investigación, innovación y transferencia relacionadas con el sector agroalimentario y el medio ambiente  
B) Gestionar exclusivamente los impuestos regionales  
C) Administrar únicamente las carreteras regionales  
D) Gestionar exclusivamente hospitales

---

## 60.
En el contexto de las Buenas Prácticas de Laboratorio, ¿qué función debe mantener independencia respecto a la realización del estudio que supervisa?

A) Garantía de Calidad  
B) Dirección administrativa  
C) Servicio de limpieza  
D) Compras

---

## 61.
En BPL, ¿qué documento establece de antemano los objetivos y la metodología de un estudio?

A) Protocolo  
B) Factura  
C) Albarán  
D) Registro de usuarios

---

## 62.
¿Cuál de las siguientes actuaciones es especialmente importante para garantizar la trazabilidad de una muestra?

A) Identificarla inequívocamente y registrar su procedencia y datos relevantes  
B) Eliminar los registros una vez iniciado el análisis  
C) Cambiar su código en cada fase  
D) Mezclarla con otras muestras

---

## 63.
¿Cuál es una obligación básica relacionada con los residuos peligrosos?

A) Identificarlos, envasarlos y etiquetarlos adecuadamente y gestionarlos conforme a la normativa  
B) Mezclarlos siempre para reducir el número de recipientes  
C) Diluirlos antes de entregarlos  
D) Eliminarlos directamente por el desagüe

---

## 64.
¿Cuál es, con carácter general, el plazo máximo de almacenamiento de residuos peligrosos en el lugar de producción?

A) 1 mes  
B) 3 meses  
C) 6 meses  
D) 2 años

---

## 65.
¿Cuál es la propiedad fundamental que debe perseguirse cuando se diseña un muestreo para obtener conclusiones sobre un conjunto?

A) Representatividad  
B) Tamaño máximo  
C) Rapidez exclusivamente  
D) Selección de los elementos más llamativos

---

## 66.
Un técnico selecciona únicamente plantas que presentan síntomas y utiliza esas muestras para afirmar que toda la parcela está contaminada. ¿Cuál es el principal problema?

A) Error analítico  
B) Falta de representatividad / sesgo de muestreo  
C) Error de compilación  
D) Fallo de autenticación

---

## 67.
Durante el transporte, una muestra pierde las condiciones de conservación establecidas. ¿Cuál es la actuación más adecuada?

A) Ignorar la incidencia si el código sigue siendo legible  
B) Registrar y evaluar la incidencia según el procedimiento aplicable  
C) Cambiar el resultado esperado manualmente  
D) Eliminar toda la documentación

---

## 68.
¿Cuál de estas cadenas representa mejor la trazabilidad de una muestra?

A) Resultado → usuario → contraseña → servidor  
B) Origen → toma → identificación → conservación/transporte → recepción → análisis → resultado  
C) Análisis → eliminación → toma → origen  
D) Código → correo → factura → servidor

---

# 🧠 BLOQUE TRANSVERSAL · MEZCLA DE CONCEPTOS

## 69.
Un laboratorio del IMIDA recibe una muestra correctamente identificada. El análisis se realiza con un método válido y el equipo está correctamente calibrado. Sin embargo, posteriormente se descubre que la muestra fue tomada exclusivamente de la zona que presentaba síntomas y se utilizó para representar toda la parcela.

¿Cuál es la conclusión más correcta?

A) El resultado es necesariamente representativo porque el equipo estaba calibrado  
B) Existe principalmente un problema de muestreo, no necesariamente de análisis  
C) El problema es exclusivamente de ciberseguridad  
D) La calibración convierte automáticamente la muestra en representativa

---

## 70.
Un organismo público quiere implantar un servicio TIC. Durante el proyecto se plantea:

```text
- gestionar el servicio siguiendo buenas prácticas de gestión de servicios,
- desarrollar el producto de forma iterativa,
- proteger la información y los servicios,
- tratar correctamente los datos personales,
- documentar los procedimientos del laboratorio relacionados con el proyecto.
```

¿Cuál de las siguientes combinaciones representa mejor los bloques del temario que podrían intervenir?

A) Únicamente GNU/Linux  
B) Gestión TIC + Seguridad + IMIDA  
C) Únicamente Bases de Datos  
D) Únicamente Redes

---

# 📝 PLANTILLA DE RESPUESTAS

No mires ninguna solución. Completa esta plantilla al terminar.

```text
01. ___
02. ___
03. ___
04. ___
05. ___
06. ___
07. ___
08. ___
09. ___
10. ___

11. ___
12. ___
13. ___
14. ___
15. ___
16. ___
17. ___
18. ___
19. ___
20. ___

21. ___
22. ___
23. ___
24. ___
25. ___
26. ___
27. ___
28. ___
29. ___
30. ___

31. ___
32. ___
33. ___
34. ___
35. ___
36. ___
37. ___
38. ___
39. ___
40. ___

41. ___
42. ___
43. ___
44. ___
45. ___
46. ___
47. ___
48. ___
49. ___
50. ___

51. ___
52. ___
53. ___
54. ___
55. ___
56. ___
57. ___
58. ___
59. ___
60. ___

61. ___
62. ___
63. ___
64. ___
65. ___
66. ___
67. ___
68. ___
69. ___
70. ___
```

---

# 🎯 REGLAS PARA ESTE SIMULACRO

### No consultes los apuntes.

Si dudas entre dos:

```text
1. Lee de nuevo.
2. Elimina las claramente incorrectas.
3. Elige la mejor.
4. Marca la duda para revisarla después.
```

### No cambies respuestas continuamente.

La primera respuesta razonada suele ser mejor que entrar en un bucle de:

> "¿Y si era la C...? Pero quizá la B..."

Eso es el pantano del opositor. 🫠

### Registra también las dudas

Puedes marcar:

```text
✓ = segura
? = dudosa
```

Ejemplo:

```text
23. B ✓
24. A ?
25. B ✓
```

Esto nos permitirá distinguir después:

```text
ERROR POR DESCONOCIMIENTO
```

de:

```text
ERROR POR DUDA
```

que son problemas de entrenamiento diferentes.

---

# 🏁 FIN DEL SIMULACRO GENERAL 01

**70 preguntas.**

**8 bloques.**

**Una sola respuesta correcta por pregunta.**

Cuando termines, conserva tu plantilla de respuestas.

Después podremos hacer la corrección completa con:

```text
PREGUNTA
↓
TU RESPUESTA
↓
RESPUESTA CORRECTA
↓
EXPLICACIÓN
↓
BLOQUE
↓
CONCEPTO A REPASAR
```

Y, sobre todo, podremos calcular tu rendimiento **por bloque**, no solamente una nota global.

---

# 🧠 OBJETIVO

No busques sacar 70/70.

Este primer simulacro es nuestro:

> **diagnóstico de combate.**

Lo importante es descubrir **dónde muerde el temario**.

