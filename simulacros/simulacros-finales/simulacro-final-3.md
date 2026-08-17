# 🏆 SIMULACRO FINAL 03 · GRAN EXAMEN DE CIERRE
## 70 preguntas · Bloques 01 → 08

> **Este es el simulacro final de cierre.**
>
> No está pensado para enseñar contenido nuevo. Está pensado para comprobar si puedes recuperar y aplicar lo estudiado cuando los temas aparecen mezclados y sin avisar.
>
> - 70 preguntas.
> - 4 opciones.
> - Una única respuesta correcta.
> - Sin soluciones en este documento.
> - Dificultad progresiva.
> - Especial atención a conceptos que suelen confundirse.
>
> **Hazlo sin apuntes y, si puedes, de una sola sentada.**

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1.
Un administrador quiere conocer la memoria RAM disponible y utilizada en un servidor. ¿Qué comando resulta más apropiado?

A) `df -h`  
B) `free -h`  
C) `du -sh`  
D) `lsmemlog`

---

## 2.
¿Qué información es característica de `/proc`?

A) Configuración persistente de servicios.  
B) Directorios personales.  
C) Información virtual sobre procesos y el kernel.  
D) Archivos de usuarios eliminados.

---

## 3.
Un archivo tiene permisos `rw-r--r--`. ¿Cuál es su representación octal?

A) 644  
B) 755  
C) 640  
D) 600

---

## 4.
¿Qué comando permite identificar el nombre del sistema anfitrión?

A) `whoami`  
B) `hostname`  
C) `unameuser`  
D) `hostid-user`

---

## 5.
Un administrador ejecuta:

```bash
systemctl status apache2
```

¿Qué está consultando?

A) El estado del servicio Apache gestionado por systemd.  
B) El espacio ocupado por Apache.  
C) Los permisos de la carpeta Apache.  
D) La dirección MAC del servidor.

---

## 6.
¿Cuál es la finalidad principal de `scp`?

A) Copiar archivos entre sistemas utilizando SSH.  
B) Cambiar permisos.  
C) Crear usuarios.  
D) Consultar procesos.

---

## 7.
¿Qué herramienta resulta especialmente apropiada para consultar el journal de systemd?

A) `journalctl`  
B) `syslogctl`  
C) `loggrep`  
D) `systemlog`

---

## 8.
¿Qué afirmación es correcta?

A) `df` muestra principalmente memoria RAM y `free` espacio de disco.  
B) `df` y `free` realizan exactamente la misma función.  
C) `df` informa del espacio de sistemas de archivos y `free` de memoria.  
D) Ambos comandos gestionan servicios.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 9.
¿Cuál es la función principal de Active Directory Domain Services?

A) Gestionar identidades, equipos y recursos mediante servicios de directorio.  
B) Comprimir archivos NTFS.  
C) Sustituir DHCP.  
D) Monitorizar exclusivamente procesos.

---

## 10.
¿Qué protocolo está asociado con el acceso a información de servicios de directorio?

A) LDAP  
B) DHCP  
C) FTP  
D) ICMP

---

## 11.
Un equipo de dominio debe recibir automáticamente IP, máscara y gateway. ¿Qué servicio se encarga principalmente?

A) DNS  
B) DHCP  
C) LDAP  
D) Group Policy

---

## 12.
¿Qué mecanismo permite aplicar configuraciones de forma centralizada a usuarios y equipos de un dominio?

A) Group Policy  
B) NTFS únicamente  
C) Event Viewer  
D) Task Scheduler exclusivamente

---

## 13.
En NTFS, ¿qué elemento contiene las reglas de acceso asociadas a un recurso?

A) ACL  
B) DNS  
C) DHCP  
D) SID únicamente

---

## 14.
¿Qué afirmación describe mejor una ventaja de Active Directory?

A) Permite administrar de forma centralizada identidades y recursos dentro de un entorno de dominio.  
B) Elimina la necesidad de utilizar direcciones IP.  
C) Convierte automáticamente todos los equipos en servidores web.  
D) Sustituye el sistema de archivos NTFS.

---

## 15.
Un usuario pertenece a un grupo al que se le han concedido determinados permisos sobre una carpeta NTFS. ¿Puede obtener permisos por pertenecer al grupo?

A) Sí, los permisos pueden asignarse a grupos y aplicarse a sus miembros.  
B) No, los permisos solo pueden asignarse a ordenadores.  
C) No, NTFS no admite grupos.  
D) Solo si DHCP lo autoriza.

---

## 16.
¿Cuál es la asociación correcta?

A) DNS → asignación dinámica de IP.  
B) DHCP → resolución de nombres.  
C) LDAP → servicios de directorio.  
D) NTFS → encaminamiento IP.

---

# 🌐 BLOQUE 03 · REDES

## 17.
¿Cuál de estas direcciones pertenece al rango privado `10.0.0.0/8`?

A) `10.25.4.8`  
B) `11.25.4.8`  
C) `172.32.1.1`  
D) `192.169.1.1`

---

## 18.
¿Qué función tiene DNS?

A) Resolver nombres y direcciones mediante el sistema de nombres de dominio.  
B) Asignar permisos NTFS.  
C) Cifrar conexiones SSH.  
D) Crear VLAN automáticamente.

---

## 19.
¿Qué dispositivo utiliza principalmente direcciones MAC para tomar decisiones de reenvío dentro de una LAN?

A) Router  
B) Switch  
C) Servidor DNS  
D) Firewall de aplicación exclusivamente

---

## 20.
¿Qué función cumple un router?

A) Encaminamiento entre redes.  
B) Gestión de usuarios de dominio.  
C) Asignación exclusiva de direcciones MAC.  
D) Compilación de aplicaciones.

---

## 21.
¿Qué protocolo ofrece una comunicación orientada a conexión con mecanismos de entrega fiable y ordenada?

A) UDP  
B) TCP  
C) ARP  
D) DNS

---

## 22.
Un administrador quiere acceder remotamente a un servidor Linux de forma segura mediante terminal. ¿Qué protocolo utilizaría normalmente?

A) Telnet  
B) SSH  
C) FTP  
D) TFTP

---

## 23.
¿Qué hace ARP en una red IPv4 local?

A) Asocia una IP con una dirección MAC.  
B) Asigna automáticamente IP mediante DHCP.  
C) Resuelve nombres de dominio.  
D) Cifra paquetes.

---

## 24.
¿Qué función tiene la máscara de subred?

A) Determinar la parte de red y de host de una dirección IP.  
B) Identificar físicamente la tarjeta de red.  
C) Resolver nombres DNS.  
D) Autenticar usuarios.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 25.
¿Qué sentencia obtiene datos de una tabla?

A) `SELECT`  
B) `UPDATE`  
C) `ALTER`  
D) `DELETE`

---

## 26.
Una columna `user_id` de una tabla referencia a `users.id`. ¿Qué representa normalmente?

A) Clave primaria.  
B) Clave foránea.  
C) Índice DNS.  
D) Trigger de sistema.

---

## 27.
¿Qué sentencia modifica valores existentes?

A) `UPDATE`  
B) `SELECT`  
C) `ALTER`  
D) `CREATE USER`

---

## 28.
¿Cuál es la diferencia fundamental entre `DELETE` y `DROP TABLE`?

A) `DELETE` elimina filas, mientras `DROP TABLE` elimina la tabla.  
B) `DELETE` elimina la base de datos y `DROP TABLE` filas.  
C) Son equivalentes.  
D) `DROP TABLE` solo cambia permisos.

---

## 29.
En Eloquent, ¿qué técnica se utiliza para cargar anticipadamente una relación?

A) Eager loading.  
B) Route binding.  
C) Middleware.  
D) Migration rollback.

---

## 30.
¿Qué problema aparece cuando una aplicación ejecuta una consulta para obtener una colección y después una consulta adicional por cada elemento para obtener una relación?

A) N+1.  
B) DNS poisoning.  
C) Deadlock obligatorio.  
D) XSS.

---

## 31.
¿Qué propiedad ACID representa que una transacción se aplica completamente o no se aplica?

A) Atomicidad.  
B) Consistencia.  
C) Aislamiento.  
D) Durabilidad.

---

## 32.
¿Qué propiedad ACID se relaciona con la conservación de los cambios confirmados incluso ante determinados fallos posteriores?

A) Atomicidad.  
B) Consistencia.  
C) Aislamiento.  
D) Durabilidad.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 33.
En PHP, ¿qué operador se utiliza normalmente para acceder a propiedades y métodos de una instancia?

A) `::`  
B) `->`  
C) `=>`  
D) `??`

---

## 34.
¿Qué mecanismo de Laravel puede interceptar una petición antes de llegar al controlador y aplicar determinadas comprobaciones?

A) Middleware.  
B) Migration.  
C) Seeder.  
D) Factory.

---

## 35.
¿Cuál es una ventaja de la inyección de dependencias?

A) Reduce el acoplamiento entre una clase y sus dependencias.  
B) Elimina la necesidad de pruebas.  
C) Sustituye HTTP.  
D) Convierte automáticamente SQL en NoSQL.

---

## 36.
¿Qué comando Git permite obtener una copia inicial de un repositorio remoto?

A) `git clone`  
B) `git copy`  
C) `git download`  
D) `git init-remote`

---

## 37.
¿Qué comando integra una rama dentro de la rama actual mediante una fusión?

A) `git merge`  
B) `git join`  
C) `git union`  
D) `git combine`

---

## 38.
¿Qué objetivo persigue CI/CD?

A) Automatizar integración, pruebas y procesos de entrega o despliegue.  
B) Eliminar la necesidad de control de versiones.  
C) Sustituir la base de datos.  
D) Impedir despliegues automatizados.

---

## 39.
Una API REST devuelve `401 Unauthorized` cuando faltan credenciales válidas. ¿Qué representa `401`?

A) Código de estado HTTP.  
B) Código de error de MySQL.  
C) Código de proceso Linux.  
D) Código de Git.

---

## 40.
¿Qué herramienta se utiliza en Vue 3 para gestionar estado compartido?

A) Pinia.  
B) Composer.  
C) PHPUnit.  
D) Eloquent.

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 41.
Un servicio deja de funcionar correctamente y el equipo busca restaurarlo cuanto antes. ¿Qué concepto de ITIL encaja mejor?

A) Gestión de incidentes.  
B) Gestión de problemas exclusivamente.  
C) Gestión de proveedores exclusivamente.  
D) Gestión financiera.

---

## 42.
Después de varios incidentes similares, la organización quiere investigar la causa subyacente para evitar recurrencias. ¿Qué práctica resulta especialmente relacionada?

A) Gestión de problemas.  
B) Gestión de incidentes exclusivamente.  
C) Sprint Review.  
D) Gestión de activos físicos exclusivamente.

---

## 43.
En Scrum, ¿quién es responsable de maximizar el valor del producto?

A) Product Owner.  
B) Scrum Master.  
C) Todos los stakeholders conjuntamente.  
D) Project Manager obligatorio.

---

## 44.
¿Qué evento de Scrum permite inspeccionar el incremento y adaptar el Product Backlog si procede?

A) Sprint Review.  
B) Daily Scrum.  
C) Sprint Retrospective.  
D) Sprint Planning.

---

## 45.
¿Qué evento se centra específicamente en analizar cómo fue el Sprint y cómo mejorar la forma de trabajo?

A) Sprint Retrospective.  
B) Sprint Review.  
C) Product Backlog Refinement exclusivamente.  
D) Daily Scrum.

---

## 46.
PRINCE2 es principalmente:

A) Un método de gestión de proyectos.  
B) Un sistema operativo.  
C) Un protocolo de red.  
D) Un estándar de bases de datos.

---

## 47.
ISO/IEC 20000 se relaciona principalmente con:

A) Gestión de servicios de TI.  
B) Gestión de certificados digitales.  
C) Sistemas de archivos.  
D) Programación funcional.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 48.
¿Cuál de las siguientes situaciones afecta principalmente a la confidencialidad?

A) Una persona no autorizada obtiene acceso a información privada.  
B) Un archivo queda corrupto.  
C) Un servidor deja de responder.  
D) Un disco falla.

---

## 49.
¿Cuál afecta principalmente a la integridad?

A) Modificación no autorizada de datos.  
B) Lectura autorizada de información.  
C) Caída de un servicio.  
D) Falta de espacio de almacenamiento.

---

## 50.
¿Cuál afecta principalmente a la disponibilidad?

A) Un servidor crítico queda fuera de servicio.  
B) Un atacante lee información confidencial.  
C) Un usuario modifica un registro sin autorización.  
D) Una contraseña se almacena mediante hash.

---

## 51.
El ENS tiene como finalidad establecer principios y requisitos para proteger:

A) La información y los servicios dentro de su ámbito de aplicación en el sector público.  
B) Únicamente los equipos personales.  
C) Exclusivamente las redes inalámbricas.  
D) Únicamente los datos médicos.

---

## 52.
¿Qué principio del RGPD establece que deben tratarse solo los datos personales necesarios para los fines previstos?

A) Minimización de datos.  
B) Portabilidad.  
C) Exactitud exclusivamente.  
D) Limitación de conservación exclusivamente.

---

## 53.
Una persona solicita conocer qué datos personales están siendo tratados sobre ella. ¿Qué derecho está ejerciendo principalmente?

A) Acceso.  
B) Supresión.  
C) Portabilidad.  
D) Oposición exclusivamente.

---

## 54.
¿Qué elemento permite vincular una identidad con una clave pública dentro de una infraestructura de confianza?

A) Certificado digital.  
B) Dirección MAC.  
C) Registro DNS.  
D) ACL.

---

## 55.
¿Qué función tiene una autoridad de certificación?

A) Emitir certificados digitales conforme a sus procedimientos y políticas.  
B) Asignar direcciones IP.  
C) Gestionar tablas SQL.  
D) Filtrar paquetes de red.

---

## 56.
¿Qué mecanismo permite filtrar comunicaciones de red según reglas?

A) Firewall.  
B) Compiler.  
C) Cron.  
D) Eloquent.

---

## 57.
Un empleado recibe un correo que imita a su banco y le pide introducir sus credenciales en una página falsa. ¿Qué técnica se está utilizando?

A) Phishing.  
B) Ransomware.  
C) RAID.  
D) NAT.

---

# 🧪 BLOQUE 08 · IMIDA

## 58.
¿Qué finalidad general tienen las Buenas Prácticas de Laboratorio?

A) Favorecer la calidad, integridad, trazabilidad y adecuada documentación de determinados estudios.  
B) Sustituir toda la legislación medioambiental.  
C) Gestionar exclusivamente residuos urbanos.  
D) Administrar redes informáticas.

---

## 59.
¿Qué documento establece previamente los objetivos y metodología de un estudio BPL?

A) Protocolo.  
B) Informe final.  
C) Acta de recepción de residuos.  
D) Registro de usuarios.

---

## 60.
¿Qué función tiene Garantía de Calidad?

A) Supervisar de manera independiente el cumplimiento de los principios aplicables al estudio.  
B) Ejecutar necesariamente todos los análisis.  
C) Sustituir al director del estudio.  
D) Gestionar exclusivamente el presupuesto.

---

## 61.
¿Cuál de los siguientes datos contribuye directamente a la identificación y trazabilidad de una muestra?

A) Código, procedencia, fecha/hora y responsable de la toma.  
B) Solo el color del recipiente.  
C) Únicamente el resultado analítico.  
D) El nombre del fabricante del ordenador.

---

## 62.
¿Qué característica debe perseguirse cuando un muestreo pretende obtener conclusiones sobre un conjunto?

A) Representatividad.  
B) Tamaño máximo de cada muestra.  
C) Selección únicamente de casos extremos.  
D) Rapidez por encima de cualquier otro criterio.

---

## 63.
Un técnico quiere estudiar una parcela completa, pero selecciona exclusivamente los puntos donde ya observa síntomas. ¿Cuál es el principal riesgo?

A) Sesgo de selección y falta de representatividad para extrapolar al conjunto.  
B) Mejora automática de la representatividad.  
C) Error de compilación.  
D) Fallo de autenticación.

---

## 64.
Durante la toma, el técnico utiliza la misma herramienta sin limpiarla entre dos muestras. ¿Qué puede producirse?

A) Contaminación cruzada.  
B) Mayor trazabilidad.  
C) Mayor disponibilidad.  
D) Cifrado de la muestra.

---

## 65.
Una muestra llega al laboratorio con el recipiente roto. ¿Cuál es la actuación más adecuada?

A) Registrar la incidencia, evaluar la integridad de la muestra y actuar según el procedimiento.  
B) Ocultar el incidente si el código sigue siendo visible.  
C) Cambiar el código.  
D) Analizarla siempre sin registrar nada.

---

## 66.
¿Cuál de estas cadenas representa mejor la trazabilidad de una muestra?

A) Origen → toma → identificación → conservación/transporte → recepción → análisis → resultado.  
B) Resultado → usuario → contraseña → origen.  
C) Análisis → eliminación → origen → toma.  
D) Código → factura → correo → servidor.

---

# 🧠 BLOQUE TRANSVERSAL · EXAMEN FINAL

## 67.
Un servidor Linux presenta una carga elevada. El administrador comprueba:

```text
CPU alta
MySQL consumiendo gran parte de CPU
espacio de disco suficiente
memoria disponible
```

¿Cuál sería el siguiente enfoque más razonable?

A) Investigar procesos y actividad de MySQL, incluyendo consultas y carga, antes de realizar cambios destructivos.  
B) Borrar todos los logs inmediatamente.  
C) Cambiar las direcciones IP de los clientes.  
D) Reiniciar Active Directory.

---

## 68.
Una aplicación Laravel obtiene 500 clientes y, posteriormente, realiza una consulta adicional para cada cliente para obtener sus pedidos.

¿Qué problema se está produciendo probablemente?

A) N+1.  
B) DHCP.  
C) Phishing.  
D) Atomicidad.

---

## 69.
Una organización pública desarrolla una aplicación para gestionar información de investigación. El proyecto requiere:

```text
gestión de un servicio TIC
desarrollo iterativo
protección de sistemas
tratamiento de datos personales
trazabilidad de muestras
```

¿Qué conjunto de bloques aparece directamente implicado?

A) Gestión TIC + Desarrollo + Seguridad + IMIDA.  
B) Solo Redes.  
C) Solo Linux.  
D) Solo Bases de Datos.

---

## 70.
Se realiza un muestreo de una parcela. Las muestras están perfectamente identificadas, conservadas y analizadas. Sin embargo, todos los puntos fueron seleccionados deliberadamente en la zona que se sospechaba contaminada y posteriormente se pretende extrapolar el resultado a toda la parcela.

¿Cuál es la afirmación más correcta?

A) El análisis correcto garantiza la representatividad.  
B) La trazabilidad compensa el sesgo de selección.  
C) Existe un problema de representatividad derivado del diseño del muestreo.  
D) Al existir varias muestras, el resultado es necesariamente representativo.

---

# 📝 PLANTILLA DE RESPUESTAS

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

# 🎯 REGLAS

### 1. No consultes apuntes.

Si una pregunta no la recuerdas, marca la duda y continúa.

### 2. No te quedes atrapado.

Si llevas demasiado tiempo con una pregunta:

```text
marcar ?
↓
elegir
↓
continuar
```

### 3. Revisa al final

Especialmente:

```text
NO
SIEMPRE
EXCLUSIVAMENTE
PRINCIPALMENTE
ÚNICAMENTE
```

Esas palabras son pequeñas minas antipersona de examen.

---

# 🏆 OBJETIVO

Este simulacro pretende responder a una única pregunta:

> **¿Puedes enfrentarte a los ocho bloques sin saber de antemano cuál te van a preguntar?**

No busques únicamente una nota alta.

Busca detectar:

```text
CONOCIMIENTO
+
COMPRENSIÓN
+
CAPACIDAD DE DISCRIMINAR
+
RESISTENCIA
```

---

# 🏁 FIN DEL SIMULACRO FINAL 03

**70 preguntas.**

**8 bloques.**

**Una única respuesta correcta.**

> Cuando termines, guarda tus 70 respuestas. La corrección debe hacerse después, no durante el combate.

## 🎓 FIN
