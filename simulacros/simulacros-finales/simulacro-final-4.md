# 🐉 SIMULACRO FINAL · EL ÚLTIMO MONSTRUO
## 100 preguntas · Bloques 01 → 08

> **Examen final de cierre del temario**
>
> Este es el simulacro más largo de todo el entrenamiento.
>
> - **100 preguntas**
> - 4 opciones por pregunta
> - Una única respuesta correcta
> - Todos los bloques mezclados progresivamente
> - Preguntas conceptuales, técnicas, prácticas y transversales
> - Sin soluciones en este documento
>
> ### 🎯 Objetivo
>
> No es aprender contenido nuevo. Es comprobar cuánto eres capaz de recuperar **sin apuntes y sin saber qué bloque viene después**.
>
> **Hazlo offline, sin Internet y sin consultar el temario.**
>
> Marca también las dudas:
>
> `✓ = segura` · `? = dudosa`

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1.
¿Qué directorio contiene habitualmente la configuración del sistema y de muchos servicios?

A) `/home`  
B) `/etc`  
C) `/var`  
D) `/proc`

## 2.
¿Qué información proporciona principalmente `free -h`?

A) Espacio disponible en sistemas de archivos  
B) Memoria RAM y swap  
C) Procesos activos  
D) Registros del sistema

## 3.
¿Qué comando permite conocer el usuario efectivo con el que se está trabajando?

A) `whoami`  
B) `hostname`  
C) `idhost`  
D) `userctl`

## 4.
¿Qué representa `/proc`?

A) Un directorio de configuración persistente  
B) Un sistema de archivos virtual con información del kernel y procesos  
C) El directorio personal de root  
D) Un directorio para copias de seguridad

## 5.
¿Qué permisos representa `755`?

A) `rw-r--r--`  
B) `rwxr-xr-x`  
C) `rwx------`  
D) `r--r-xr-x`

## 6.
¿Qué comando permite consultar el estado de un servicio gestionado por systemd?

A) `systemctl status`  
B) `serviceinfo`  
C) `systemd check`  
D) `statusctl`

## 7.
¿Qué herramienta permite consultar los registros del journal de systemd?

A) `journalctl`  
B) `logctl`  
C) `syslog-read`  
D) `systemlog`

## 8.
¿Qué combinación permite localizar procesos relacionados con PostgreSQL?

A) `ps aux | grep postgresql`  
B) `df -h | grep postgresql`  
C) `free -h | grep postgresql`  
D) `chmod | grep postgresql`

## 9.
¿Qué herramienta es especialmente útil para monitorizar procesos y recursos de forma interactiva?

A) `tar`  
B) `htop`  
C) `scp`  
D) `crontab`

## 10.
¿Qué finalidad tiene `scp`?

A) Gestionar servicios  
B) Copiar archivos entre sistemas mediante SSH  
C) Programar tareas  
D) Modificar permisos

## 11.
¿Qué utilidad se emplea habitualmente para crear y manipular archivos de archivado?

A) `tar`  
B) `grep`  
C) `kill`  
D) `passwd`

## 12.
¿Qué comando permite programar tareas periódicas de un usuario mediante cron?

A) `crontab`  
B) `taskctl`  
C) `schedule`  
D) `cronstatus`

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 13.
¿Cuál es la función principal de Active Directory Domain Services?

A) Gestionar identidades, equipos y recursos mediante servicios de directorio  
B) Gestionar exclusivamente discos  
C) Resolver nombres de Internet  
D) Sustituir NTFS

## 14.
¿Qué protocolo está asociado directamente al acceso a servicios de directorio?

A) DHCP  
B) LDAP  
C) FTP  
D) ICMP

## 15.
¿Qué servicio proporciona normalmente de forma automática una dirección IP y otros parámetros de red?

A) DNS  
B) DHCP  
C) LDAP  
D) SMB

## 16.
Una organización quiere aplicar políticas de seguridad de forma centralizada a equipos y usuarios de un dominio. ¿Qué mecanismo resulta apropiado?

A) Group Policy  
B) NTFS exclusivamente  
C) Task Manager  
D) Disk Cleanup

## 17.
¿Qué representa una ACL en el contexto de permisos?

A) Una lista de control de acceso con reglas sobre un recurso  
B) Una dirección IP  
C) Un protocolo de resolución de nombres  
D) Una tabla de rutas

## 18.
¿Qué sistema de archivos de Windows proporciona permisos detallados mediante ACL?

A) FAT12  
B) NTFS  
C) ISO9660  
D) EXT4

## 19.
¿Qué afirmación sobre los permisos de grupos en NTFS es correcta?

A) Los permisos solo pueden asignarse individualmente  
B) Los grupos pueden recibir permisos y sus miembros pueden heredarlos según la configuración  
C) Los grupos no pueden tener permisos sobre carpetas  
D) DHCP determina los permisos

## 20.
¿Qué asociación es correcta?

A) DNS → asignación dinámica de IP  
B) DHCP → resolución de nombres  
C) LDAP → servicios de directorio  
D) NTFS → encaminamiento

## 21.
¿Qué elemento proporciona un límite lógico y administrativo dentro de Active Directory?

A) Dominio  
B) Puerto  
C) Socket  
D) Volumen

## 22.
¿Cuál es una ventaja principal de centralizar identidades mediante Active Directory?

A) Evitar cualquier necesidad de red  
B) Administrar usuarios, equipos y recursos de forma centralizada  
C) Eliminar todos los permisos NTFS  
D) Sustituir el protocolo TCP

## 23.
Un equipo de dominio recibe una IP, máscara, gateway y DNS automáticamente. ¿Qué servicio participa principalmente?

A) DHCP  
B) LDAP  
C) NTFS  
D) Group Policy

## 24.
¿Cuál de estas parejas NO describe correctamente la función habitual?

A) DNS → resolución de nombres  
B) DHCP → configuración automática de red  
C) LDAP → servicios de directorio  
D) NTFS → asignación dinámica de direcciones IP

---

# 🌐 BLOQUE 03 · REDES

## 25.
¿Cuál de estas direcciones pertenece a un rango privado IPv4?

A) `8.8.8.8`  
B) `172.20.10.5`  
C) `1.1.1.1`  
D) `200.20.20.20`

## 26.
¿Qué función tiene DNS?

A) Resolver nombres de dominio  
B) Asignar permisos  
C) Cifrar discos  
D) Encaminamiento exclusivamente

## 27.
¿Qué función tiene DHCP?

A) Resolver nombres  
B) Asignar dinámicamente parámetros de configuración de red  
C) Cifrar comunicaciones  
D) Traducir puertos

## 28.
¿Qué dispositivo utiliza principalmente direcciones MAC para reenviar tramas dentro de una LAN?

A) Router  
B) Switch  
C) DNS  
D) Servidor DHCP

## 29.
¿Cuál es la función principal de un router?

A) Encaminamiento entre redes  
B) Almacenar archivos  
C) Gestionar usuarios  
D) Resolver exclusivamente nombres

## 30.
¿Qué protocolo permite relacionar una dirección IPv4 con una dirección MAC en una red local?

A) ARP  
B) DNS  
C) DHCP  
D) FTP

## 31.
¿Qué característica diferencia principalmente TCP de UDP?

A) TCP ofrece comunicación orientada a conexión y mecanismos de entrega fiable y ordenada  
B) TCP no utiliza puertos  
C) UDP garantiza la entrega  
D) UDP siempre establece una conexión

## 32.
¿Qué función cumple una máscara de subred?

A) Determinar la parte de red y de host de una dirección IP  
B) Cifrar la dirección IP  
C) Resolver nombres  
D) Asignar usuarios

## 33.
¿Qué protocolo se utiliza normalmente para administrar remotamente un servidor Linux mediante una conexión segura?

A) Telnet  
B) SSH  
C) FTP  
D) TFTP

## 34.
Un equipo puede acceder a un servidor mediante su IP, pero no mediante su nombre. ¿Qué servicio comprobarías primero?

A) DNS  
B) DHCP  
C) SMTP  
D) RAID

## 35.
¿Qué dirección identifica una interfaz a nivel de enlace?

A) IP  
B) MAC  
C) URL  
D) FQDN

## 36.
¿Qué situación describe mejor una comunicación entre redes diferentes?

A) Un switch decide el encaminamiento entre subredes  
B) Un router puede realizar el encaminamiento entre ellas  
C) DNS crea automáticamente una ruta IP  
D) DHCP sustituye al router

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 37.
¿Qué sentencia SQL recupera datos?

A) `SELECT`  
B) `UPDATE`  
C) `DELETE`  
D) `ALTER`

## 38.
¿Qué sentencia modifica registros existentes?

A) `SELECT`  
B) `UPDATE`  
C) `DROP`  
D) `CREATE`

## 39.
¿Qué sentencia elimina filas de una tabla sin eliminar necesariamente la estructura de la tabla?

A) `DELETE`  
B) `DROP TABLE`  
C) `DROP DATABASE`  
D) `REMOVE TABLE`

## 40.
¿Qué sentencia modifica la estructura de una tabla?

A) `ALTER TABLE`  
B) `UPDATE TABLE`  
C) `CHANGE ROW`  
D) `MODIFY DATA`

## 41.
¿Qué característica define principalmente una clave primaria?

A) Identifica inequívocamente las filas  
B) Siempre referencia otra tabla  
C) Solo contiene texto  
D) Puede repetirse libremente

## 42.
¿Qué representa normalmente una clave foránea?

A) Una relación con un registro de otra tabla  
B) Una copia de seguridad  
C) Un proceso del sistema operativo  
D) Una dirección MAC

## 43.
Una aplicación obtiene 100 clientes y después consulta los pedidos de cada cliente mediante una consulta independiente. ¿Qué patrón aparece?

A) N+1  
B) ACID  
C) DNS  
D) CI/CD

## 44.
En Eloquent, ¿qué técnica permite cargar anticipadamente una relación?

A) Eager loading  
B) Lazy route binding  
C) Middleware  
D) Migration

## 45.
¿Qué método se utiliza habitualmente para eager loading en Eloquent?

A) `with()`  
B) `loadRoute()`  
C) `joinModel()`  
D) `eager()`

## 46.
En ACID, ¿qué propiedad expresa que una transacción se ejecuta como una unidad indivisible?

A) Atomicidad  
B) Consistencia  
C) Aislamiento  
D) Durabilidad

## 47.
¿Qué propiedad ACID se refiere a que las transacciones concurrentes se comportan de manera controlada respecto a sus efectos?

A) Atomicidad  
B) Consistencia  
C) Aislamiento  
D) Durabilidad

## 48.
¿Qué propiedad ACID garantiza la persistencia de cambios confirmados ante determinados fallos posteriores?

A) Atomicidad  
B) Consistencia  
C) Aislamiento  
D) Durabilidad

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 49.
En PHP, ¿qué operador se utiliza normalmente para acceder a propiedades y métodos de una instancia?

A) `::`  
B) `->`  
C) `=>`  
D) `??`

## 50.
¿Qué mecanismo de Laravel puede intervenir durante el procesamiento de una petición antes de llegar al controlador?

A) Middleware  
B) Migration  
C) Seeder  
D) Factory

## 51.
¿Qué ventaja proporciona la inyección de dependencias?

A) Reduce el acoplamiento y facilita las pruebas y sustituciones  
B) Elimina HTTP  
C) Sustituye Git  
D) Impide utilizar interfaces

## 52.
¿Qué comando clona un repositorio remoto?

A) `git clone`  
B) `git copy`  
C) `git pull-new`  
D) `git remote-copy`

## 53.
¿Qué comando fusiona una rama con la rama actual?

A) `git merge`  
B) `git join`  
C) `git combine`  
D) `git union`

## 54.
¿Cuál es el objetivo principal de CI/CD?

A) Automatizar integración, pruebas y entrega/despliegue  
B) Sustituir la base de datos  
C) Evitar el control de versiones  
D) Eliminar las pruebas

## 55.
¿Qué método HTTP se utiliza normalmente para obtener un recurso?

A) GET  
B) POST  
C) DELETE  
D) PATCH

## 56.
¿Qué método HTTP se utiliza normalmente para eliminar un recurso?

A) GET  
B) POST  
C) DELETE  
D) OPTIONS

## 57.
¿Qué herramienta de Vue 3 se utiliza para gestionar estado compartido?

A) Pinia  
B) Composer  
C) PHPUnit  
D) Eloquent

## 58.
Una API devuelve `404 Not Found`. ¿Qué representa 404?

A) Un código de estado HTTP  
B) Un código de error SQL  
C) Un PID Linux  
D) Un código Git

## 59.
¿Cuál es una finalidad habitual de una arquitectura con separación entre frontend Vue y backend Laravel?

A) Separar responsabilidades entre presentación/cliente y lógica/servicios del servidor  
B) Eliminar la necesidad de API  
C) Evitar completamente las bases de datos  
D) Sustituir HTTP por FTP

## 60.
¿Qué afirmación describe mejor el desacoplamiento?

A) Las partes del sistema dependen lo menos posible de implementaciones concretas innecesarias  
B) Todas las clases deben crear directamente sus dependencias  
C) Todas las funciones deben estar en un único archivo  
D) El código no puede utilizar interfaces

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 61.
Un servicio TIC deja de funcionar y se necesita restaurarlo rápidamente. ¿Qué práctica de ITIL está directamente relacionada?

A) Gestión de incidentes  
B) Gestión de problemas  
C) Gestión financiera  
D) Gestión de proveedores

## 62.
Tras varios incidentes similares, se investiga su causa subyacente. ¿Qué práctica está directamente relacionada?

A) Gestión de problemas  
B) Gestión de incidentes exclusivamente  
C) Sprint Review  
D) Gestión de cambios exclusivamente

## 63.
Se pretende introducir una modificación planificada en un servicio TIC. ¿Qué práctica está directamente relacionada?

A) Gestión de cambios  
B) Gestión de incidentes exclusivamente  
C) Gestión de capacidad exclusivamente  
D) Gestión de usuarios

## 64.
En Scrum, ¿quién es responsable de maximizar el valor del producto?

A) Product Owner  
B) Scrum Master  
C) Developers como grupo jerárquico  
D) Project Manager obligatorio

## 65.
¿Qué evento inspecciona el resultado del Sprint y permite considerar adaptaciones futuras?

A) Sprint Review  
B) Sprint Retrospective  
C) Daily Scrum  
D) Sprint Planning

## 66.
¿Qué evento se centra en identificar mejoras en la forma de trabajo del equipo?

A) Sprint Retrospective  
B) Sprint Review  
C) Daily Scrum  
D) Product Backlog

## 67.
¿Qué elemento contiene el trabajo conocido que puede realizarse sobre el producto?

A) Product Backlog  
B) Sprint Review  
C) Daily Scrum  
D) Increment exclusivamente

## 68.
PRINCE2 es:

A) Un método de gestión de proyectos  
B) Un protocolo de red  
C) Un sistema operativo  
D) Un lenguaje de programación

## 69.
ISO/IEC 20000 está relacionada con:

A) Gestión de servicios de TI  
B) Sistemas de archivos  
C) Criptografía asimétrica  
D) Programación PHP

## 70.
¿Qué afirmación distingue mejor ITIL y Scrum?

A) ITIL se centra en gestión de servicios, mientras Scrum es un marco de trabajo para desarrollar/adaptar productos de forma iterativa e incremental  
B) Ambos son lenguajes de programación  
C) Scrum sustituye siempre a ITIL  
D) ITIL es exclusivamente una metodología de bases de datos

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 71.
¿Cuáles son las tres dimensiones clásicas de la seguridad de la información?

A) Confidencialidad, integridad y disponibilidad  
B) Rendimiento, coste y velocidad  
C) Autenticación, compresión y almacenamiento  
D) Privacidad, latencia y usabilidad

## 72.
Un atacante accede a información sin autorización. ¿Qué dimensión se ve comprometida principalmente?

A) Confidencialidad  
B) Integridad  
C) Disponibilidad  
D) Durabilidad

## 73.
Un atacante modifica registros sin autorización. ¿Qué dimensión se ve comprometida principalmente?

A) Confidencialidad  
B) Integridad  
C) Disponibilidad  
D) Portabilidad

## 74.
Un servidor crítico deja de estar disponible por un ataque. ¿Qué dimensión se ve comprometida principalmente?

A) Confidencialidad  
B) Integridad  
C) Disponibilidad  
D) Minimización

## 75.
¿Cuál es la finalidad general del ENS?

A) Establecer principios y requisitos de seguridad para proteger información y servicios dentro de su ámbito de aplicación en el sector público  
B) Regular exclusivamente contraseñas domésticas  
C) Sustituir el RGPD  
D) Regular exclusivamente certificados

## 76.
¿Qué principio del RGPD exige que los datos tratados sean adecuados, pertinentes y limitados a lo necesario?

A) Minimización de datos  
B) Portabilidad  
C) Supresión  
D) Exactitud exclusivamente

## 77.
¿Qué derecho permite a una persona acceder a sus datos personales y conocer si están siendo tratados?

A) Acceso  
B) Supresión  
C) Portabilidad  
D) Limitación

## 78.
¿Qué derecho permite solicitar la eliminación de datos personales cuando concurren las condiciones previstas?

A) Acceso  
B) Supresión  
C) Rectificación  
D) Portabilidad

## 79.
¿Qué elemento vincula una identidad con una clave pública mediante una infraestructura de confianza?

A) Certificado digital  
B) ACL  
C) Dirección MAC  
D) Registro DHCP

## 80.
¿Qué entidad emite certificados digitales dentro de una infraestructura de clave pública?

A) Autoridad de certificación  
B) Servidor DHCP  
C) Router  
D) Firewall

## 81.
¿Qué función tiene principalmente un firewall?

A) Filtrar comunicaciones según reglas  
B) Garantizar que ningún malware exista  
C) Gestionar usuarios de Active Directory  
D) Sustituir copias de seguridad

## 82.
Un atacante envía un correo falso para obtener credenciales. ¿Qué técnica utiliza?

A) Phishing  
B) Ransomware  
C) ARP  
D) RAID

## 83.
¿Qué medida reduce especialmente el riesgo de una contraseña robada?

A) Autenticación multifactor  
B) Reutilización de contraseñas  
C) Desactivar actualizaciones  
D) Compartir cuentas

## 84.
¿Qué principio establece que un usuario o proceso debe disponer solo de los privilegios necesarios?

A) Mínimo privilegio  
B) Máxima disponibilidad  
C) Publicidad  
D) Replicación

---

# 🧪 BLOQUE 08 · IMIDA

## 85.
¿Cuál es la finalidad general de las Buenas Prácticas de Laboratorio?

A) Favorecer la calidad, integridad, trazabilidad y adecuada documentación de determinados estudios  
B) Sustituir toda la legislación de residuos  
C) Gestionar exclusivamente redes  
D) Administrar servidores

## 86.
¿Qué documento establece previamente los objetivos y metodología de un estudio?

A) Protocolo  
B) Informe final  
C) Albarán  
D) Registro de residuos

## 87.
¿Qué función debe mantener independencia respecto a la realización del estudio?

A) Garantía de Calidad  
B) Dirección del estudio  
C) Personal de laboratorio  
D) Responsable de compras

## 88.
¿Cuál de los siguientes datos contribuye directamente a identificar una muestra?

A) Código, procedencia, fecha/hora y responsable de la toma  
B) Solo el color del recipiente  
C) Solo el resultado analítico  
D) Solo el fabricante del material

## 89.
¿Cuál es el objetivo principal de la representatividad en un muestreo?

A) Que la muestra refleje adecuadamente las características relevantes del conjunto estudiado  
B) Que la muestra sea siempre la más grande posible  
C) Que se seleccionen únicamente los casos extremos  
D) Que se reduzca al mínimo el número de puntos independientemente del objetivo

## 90.
Un investigador selecciona únicamente los puntos donde observa síntomas y utiliza los resultados para representar toda una parcela. ¿Cuál es el principal problema?

A) Sesgo de selección / falta de representatividad  
B) Error analítico necesariamente  
C) Error de compilación  
D) Fallo de autenticación

## 91.
Una herramienta utilizada en una muestra anterior no se limpia antes de tomar la siguiente. ¿Qué riesgo aparece?

A) Contaminación cruzada  
B) Mayor trazabilidad  
C) Disponibilidad  
D) Cifrado

## 92.
Una muestra llega con el recipiente roto. ¿Qué actuación es más adecuada?

A) Registrar la incidencia, evaluar la integridad y seguir el procedimiento aplicable  
B) Ocultar la incidencia  
C) Cambiar el código  
D) Dar por válida la muestra automáticamente

## 93.
Durante el transporte se incumplen las condiciones de conservación establecidas. ¿Qué debe hacerse?

A) Registrar y evaluar la incidencia según el procedimiento  
B) Ignorarla si el código es correcto  
C) Modificar el registro para indicar condiciones correctas  
D) Eliminar automáticamente todo el proyecto

## 94.
¿Cuál de estas cadenas representa mejor la trazabilidad?

A) Origen → toma → identificación → conservación/transporte → recepción → análisis → resultado  
B) Resultado → usuario → contraseña → origen  
C) Análisis → eliminación → toma → resultado  
D) Código → factura → correo → servidor

## 95.
¿Cuál es una gestión adecuada de residuos?

A) Identificación, segregación, envasado, etiquetado, almacenamiento y gestión conforme al tipo y normativa aplicable  
B) Mezclar todos los residuos  
C) Verterlos al desagüe si se diluyen  
D) Eliminar todos como residuos urbanos

---

# 🧠 BLOQUE TRANSVERSAL · EL JEFE FINAL

## 96.
Un servidor Linux presenta una carga elevada. MySQL consume gran parte de la CPU, mientras la memoria y el espacio de disco disponibles son normales.

¿Cuál es la actuación inicial más razonable?

A) Investigar procesos, actividad de MySQL y consultas antes de realizar cambios destructivos  
B) Borrar inmediatamente `/var`  
C) Cambiar las direcciones IP  
D) Reiniciar Active Directory

## 97.
Una aplicación Laravel obtiene una lista de usuarios y después realiza una consulta adicional para obtener la relación de cada usuario.

¿Qué problema debe sospecharse y qué solución puede ser adecuada?

A) N+1; eager loading cuando corresponda  
B) DHCP; DNS  
C) Phishing; MFA  
D) ACID; firewall

## 98.
Una organización pública desarrolla un servicio que trata datos personales y además gestiona muestras de investigación. El proyecto utiliza desarrollo iterativo, controles de seguridad y gestión formal del servicio.

¿Qué conjunto de áreas está claramente implicado?

A) Gestión TIC + Desarrollo + Seguridad + IMIDA  
B) Solo Redes  
C) Solo Linux  
D) Solo Bases de Datos

## 99.
Un laboratorio obtiene resultados analíticos técnicamente correctos, pero posteriormente descubre que las muestras fueron seleccionadas exclusivamente en las zonas donde se esperaba encontrar contaminación.

¿Qué conclusión es más correcta?

A) El análisis correcto garantiza la representatividad  
B) Existe un problema de muestreo que puede impedir extrapolar los resultados al conjunto  
C) La trazabilidad elimina el sesgo  
D) Varias muestras siempre garantizan representatividad

## 100.
Un proyecto público necesita:

```text
- gestionar un servicio TIC;
- desarrollar una aplicación web;
- proteger sus sistemas;
- tratar datos personales;
- mantener trazabilidad de muestras de investigación.
```

¿Cuál es la conclusión más completa?

A) El proyecto requiere conocimientos exclusivamente de programación  
B) El proyecto puede involucrar simultáneamente Gestión TIC, Desarrollo, Seguridad, RGPD e IMIDA  
C) El proyecto pertenece exclusivamente al ámbito de redes  
D) El proyecto puede resolverse únicamente mediante Active Directory

---

# 📝 PLANTILLA DE RESPUESTAS

```text
01. ___    26. ___    51. ___    76. ___
02. ___    27. ___    52. ___    77. ___
03. ___    28. ___    53. ___    78. ___
04. ___    29. ___    54. ___    79. ___
05. ___    30. ___    55. ___    80. ___
06. ___    31. ___    56. ___    81. ___
07. ___    32. ___    57. ___    82. ___
08. ___    33. ___    58. ___    83. ___
09. ___    34. ___    59. ___    84. ___
10. ___    35. ___    60. ___    85. ___
11. ___    36. ___    61. ___    86. ___
12. ___    37. ___    62. ___    87. ___
13. ___    38. ___    63. ___    88. ___
14. ___    39. ___    64. ___    89. ___
15. ___    40. ___    65. ___    90. ___
16. ___    41. ___    66. ___    91. ___
17. ___    42. ___    67. ___    92. ___
18. ___    43. ___    68. ___    93. ___
19. ___    44. ___    69. ___    94. ___
20. ___    45. ___    70. ___    95. ___
21. ___    46. ___    71. ___    96. ___
22. ___    47. ___    72. ___    97. ___
23. ___    48. ___    73. ___    98. ___
24. ___    49. ___    74. ___    99. ___
25. ___    50. ___    75. ___    100. ___
```

---

# 🎯 MODO EXAMEN

## Primera vuelta
Responde todas las preguntas que tengas claras.

## Segunda vuelta
Regresa a las dudosas.

## Tercera vuelta
Comprueba especialmente:

```text
NO
SIEMPRE
EXCLUSIVAMENTE
PRINCIPALMENTE
NECESARIAMENTE
```

Estas palabras pueden cambiar completamente una respuesta.

### Marca las dudas

```text
✓ segura
? dudosa
```

Un acierto con `?` merece revisión igual que un fallo.

---

# 🏁 FIN DEL ÚLTIMO MONSTRUO

**100 preguntas.**

**8 bloques.**

**Todo el temario.**

> Cuando termines, guarda las respuestas. La corrección debe hacerse después, como en un examen real.

## 🎓 FIN
