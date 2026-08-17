<!-- encabezado-homogeneizado -->
# Simulacros Finales - SIMULACRO
> **Bloque:** Simulacros Finales  
> **Documento:** Simulacro  
> **Preguntas de referencia:** N/D  
> **Estructura objetivo:** datos del examen, instrucciones, hoja o plantilla de respuestas, y correccion razonada cuando aplique.  
> **Revision:** 2026-08-17

---
# 📝 SIMULACRO GENERAL 02 · EXAMEN FINAL
## 70 preguntas · Bloques 01 → 08

> 🏆 **Segundo y último simulacro general**
>
> Este simulacro es deliberadamente diferente al primero.
>
> Aquí aumenta el peso de:
>
> - preguntas de aplicación;
> - distractores muy próximos;
> - conceptos que suelen confundirse;
> - relaciones entre bloques;
> - pequeños casos prácticos;
> - detalles que obligan a leer con atención.
>
> **Una única respuesta es correcta en cada pregunta.**
>
> ⚠️ **No incluye soluciones.** Guarda tus respuestas y haz la corrección únicamente después de terminar.

---

# 🐧 BLOQUE 01 · GNU/LINUX

## 1.
Un administrador quiere consultar rápidamente cuánto espacio libre queda en los sistemas de archivos montados. ¿Qué comando es el más apropiado?

A) `free -h`  
B) `df -h`  
C) `du -p`  
D) `meminfo -h`

---

## 2.
¿Qué afirmación describe mejor `/var`?

A) Contiene exclusivamente los directorios personales de los usuarios.  
B) Contiene archivos estáticos de configuración del sistema.  
C) Contiene datos variables, como determinados registros y colas.  
D) Contiene exclusivamente información del kernel.

---

## 3.
Se ejecuta:

```bash
chmod 640 informe.txt
```

¿Qué permisos obtiene el archivo?

A) `rwxr-----`  
B) `rw-r-----`  
C) `rw-r--r--`  
D) `r--rw----`

---

## 4.
Un administrador necesita localizar procesos relacionados con PostgreSQL. ¿Cuál de las siguientes combinaciones es adecuada?

A) `ps aux | grep postgresql`  
B) `df -h | grep postgresql`  
C) `journalctl | chmod postgresql`  
D) `top | scp postgresql`

---

## 5.
¿Cuál es la diferencia fundamental entre `kill` y `systemctl stop`?

A) `kill` actúa sobre procesos, mientras `systemctl stop` gestiona servicios mediante systemd.  
B) Ambos son exactamente equivalentes.  
C) `systemctl stop` solo funciona sobre archivos.  
D) `kill` solo puede utilizarse con servicios habilitados al arranque.

---

## 6.
Un administrador quiere consultar los registros de un servicio concreto gestionado por systemd. ¿Qué opción resulta especialmente apropiada?

A) `journalctl -u nombre_servicio`  
B) `df -u nombre_servicio`  
C) `chmod -u nombre_servicio`  
D) `scp -u nombre_servicio`

---

## 7.
¿Qué directorio es el más apropiado para almacenar los datos personales de los usuarios?

A) `/proc`  
B) `/etc`  
C) `/home`  
D) `/boot`

---

## 8.
¿Cuál es una finalidad habitual de `tar`?

A) Gestionar usuarios del sistema.  
B) Crear y manipular archivos de archivado.  
C) Resolver nombres DNS.  
D) Gestionar servicios systemd.

---

# 🪟 BLOQUE 02 · WINDOWS SERVER / ACTIVE DIRECTORY

## 9.
Una empresa quiere administrar usuarios y equipos desde una estructura centralizada basada en dominios. ¿Qué tecnología es la más directamente relacionada?

A) Active Directory Domain Services  
B) IIS  
C) NTFS  
D) Hyper-V

---

## 10.
¿Cuál es la relación correcta?

A) DNS asigna direcciones IP y DHCP resuelve nombres.  
B) DHCP asigna parámetros de red y DNS resuelve nombres.  
C) LDAP asigna direcciones IP y DNS autentica usuarios.  
D) NTFS resuelve nombres y DHCP gestiona permisos.

---

## 11.
Una organización quiere aplicar de forma centralizada determinadas políticas de configuración y seguridad a equipos y usuarios de un dominio. ¿Qué utilizaría principalmente?

A) Group Policy  
B) Task Manager  
C) Disk Management  
D) Event Viewer exclusivamente

---

## 12.
En NTFS, un usuario puede tener permisos directamente asignados y además recibir permisos a través de un grupo. ¿Qué concepto es especialmente relevante para comprender este escenario?

A) Herencia y ACL  
B) DHCP y DNS  
C) NAT y PAT  
D) RAID y BIOS

---

## 13.
¿Qué protocolo está asociado directamente con el acceso a servicios de directorio?

A) LDAP  
B) SMTP  
C) FTP  
D) ICMP

---

## 14.
¿Cuál de estas afirmaciones sobre Active Directory es correcta?

A) Es exclusivamente un sistema de archivos.  
B) Permite gestionar identidades, equipos y recursos dentro de una estructura de directorio.  
C) Sustituye obligatoriamente a DNS.  
D) Solo sirve para almacenar copias de seguridad.

---

## 15.
Un administrador necesita que un equipo Windows reciba automáticamente una dirección IP y la puerta de enlace de la red. ¿Qué servicio interviene principalmente?

A) DNS  
B) DHCP  
C) LDAP  
D) SMB

---

## 16.
¿Qué afirmación describe mejor una ACL?

A) Una lista de reglas que determina accesos a un recurso.  
B) Un protocolo de resolución de nombres.  
C) Un mecanismo de asignación de IP.  
D) Un sistema de compresión de archivos.

---

# 🌐 BLOQUE 03 · REDES

## 17.
Un equipo tiene la dirección `192.168.1.25`. ¿Qué afirmación es correcta?

A) Es una dirección IPv4 privada.  
B) Es una dirección IPv6.  
C) Es necesariamente una dirección pública.  
D) Es una dirección MAC.

---

## 18.
¿Qué función cumple ARP en IPv4?

A) Resolver nombres DNS.  
B) Relacionar una dirección IP con una dirección MAC en la red local.  
C) Asignar direcciones IP dinámicamente.  
D) Cifrar tráfico HTTP.

---

## 19.
¿Qué dispositivo se utiliza principalmente para interconectar redes diferentes y tomar decisiones de encaminamiento?

A) Switch  
B) Router  
C) Hub  
D) Punto de acceso exclusivamente

---

## 20.
Un usuario puede acceder a `8.8.8.8`, pero `www.example.com` no se resuelve. ¿Qué componente investigarías primero?

A) DNS  
B) DHCP  
C) Switch  
D) RAID

---

## 21.
¿Cuál de las siguientes afirmaciones sobre TCP es correcta?

A) No establece ningún tipo de conexión.  
B) Proporciona mecanismos orientados a una entrega fiable y ordenada.  
C) No utiliza puertos.  
D) Es siempre más rápido porque no controla la entrega.

---

## 22.
¿Qué función tiene una máscara de subred?

A) Identificar qué parte de una dirección IP corresponde a la red y cuál al host.  
B) Cifrar una dirección IP.  
C) Convertir nombres DNS en MAC.  
D) Asignar automáticamente una puerta de enlace.

---

## 23.
¿Qué protocolo se asocia normalmente con la administración remota segura de sistemas mediante línea de comandos?

A) Telnet  
B) SSH  
C) FTP  
D) HTTP

---

## 24.
¿Qué afirmación diferencia mejor una dirección IP de una dirección MAC?

A) Ambas son siempre exactamente iguales.  
B) La IP identifica lógicamente un dispositivo/interfaz en una red, mientras la MAC identifica la interfaz a nivel de enlace.  
C) La MAC solo existe en Internet.  
D) La IP solo puede utilizarse dentro de una LAN.

---

# 🗄️ BLOQUE 04 · BASES DE DATOS

## 25.
¿Cuál de las siguientes operaciones modifica la estructura de una tabla?

A) `SELECT`  
B) `UPDATE`  
C) `ALTER TABLE`  
D) `WHERE`

---

## 26.
Una tabla `orders` contiene una columna `customer_id` que referencia a `customers.id`. ¿Qué representa normalmente `customer_id`?

A) Una clave primaria obligatoria de `orders`.  
B) Una clave foránea.  
C) Un índice DNS.  
D) Una transacción.

---

## 27.
¿Qué problema aparece en un patrón N+1?

A) Se ejecutan consultas adicionales innecesarias al acceder repetidamente a relaciones.  
B) Se eliminan todas las relaciones.  
C) Se bloquea necesariamente el servidor MySQL.  
D) Se convierte SQL en PHP.

---

## 28.
En Laravel/Eloquent, ¿qué opción representa eager loading?

A) `User::with('posts')->get()`  
B) `User::without('posts')->get()`  
C) `User::route('posts')`  
D) `User::middleware('posts')`

---

## 29.
¿Qué propiedad ACID se refiere a que las transacciones concurrentes deben comportarse de forma controlada, evitando que las operaciones intermedias de una transacción interfieran indebidamente?

A) Atomicidad  
B) Consistencia  
C) Aislamiento  
D) Durabilidad

---

## 30.
¿Qué sentencia se utilizaría para añadir una nueva columna a una tabla?

A) `ALTER TABLE`  
B) `UPDATE TABLE`  
C) `INSERT COLUMN`  
D) `MODIFY DATABASE`

---

## 31.
¿Cuál de estas operaciones elimina registros sin eliminar necesariamente la estructura de la tabla?

A) `DELETE`  
B) `DROP TABLE`  
C) `DROP DATABASE`  
D) `REMOVE SCHEMA`

---

## 32.
¿Qué afirmación sobre una clave primaria es correcta?

A) Puede identificar a varias filas con el mismo valor.  
B) Su función principal es identificar inequívocamente cada fila.  
C) Siempre debe ser una cadena de texto.  
D) Solo puede existir en bases de datos NoSQL.

---

# 💻 BLOQUE 05 · PROGRAMACIÓN / DESARROLLO

## 33.
En PHP, ¿qué operador se utiliza para acceder a un método de una instancia?

A) `::`  
B) `->`  
C) `=>`  
D) `??`

---

## 34.
¿Qué problema intenta resolver principalmente la inyección de dependencias?

A) El acoplamiento excesivo entre una clase y la creación de sus dependencias.  
B) La falta de espacio en disco.  
C) La resolución DNS.  
D) La gestión de permisos NTFS.

---

## 35.
En Laravel, ¿qué componente permite definir lógica que se ejecuta durante el procesamiento de una petición y puede intervenir antes de llegar al controlador?

A) Middleware  
B) Migration exclusivamente  
C) Seeder exclusivamente  
D) Model Factory exclusivamente

---

## 36.
Una API devuelve `404 Not Found` al solicitar un recurso inexistente. ¿Qué concepto está utilizando?

A) Código de estado HTTP  
B) Código de salida de Linux  
C) Código de estado de MySQL  
D) Código de Git

---

## 37.
¿Qué método HTTP es normalmente apropiado para eliminar un recurso?

A) GET  
B) POST  
C) DELETE  
D) TRACE

---

## 38.
¿Qué comando permite integrar en la rama actual los cambios de otra rama mediante una operación de fusión?

A) `git merge`  
B) `git attach`  
C) `git combine-only`  
D) `git join`

---

## 39.
¿Qué ventaja aporta una pipeline CI/CD?

A) Permite automatizar validaciones, pruebas y procesos de entrega/despliegue.  
B) Elimina la necesidad de probar software.  
C) Sustituye Git por FTP.  
D) Impide realizar despliegues automáticos.

---

## 40.
En una aplicación Vue 3, ¿qué herramienta se utiliza para centralizar y gestionar estado compartido?

A) Pinia  
B) Composer  
C) PHPUnit  
D) Eloquent

---

# 📈 BLOQUE 06 · GESTIÓN TIC

## 41.
En ITIL, ¿qué afirmación diferencia mejor un incidente de un problema?

A) Un incidente busca restaurar el servicio; un problema busca gestionar la causa o causas de incidentes.  
B) Un incidente siempre requiere modificar el hardware; un problema nunca lo requiere.  
C) Son exactamente lo mismo.  
D) Un problema solo puede ser de seguridad.

---

## 42.
Una organización desea introducir una modificación planificada en un servicio TIC. ¿Qué concepto de ITIL está directamente relacionado?

A) Gestión de cambios  
B) Gestión de incidentes exclusivamente  
C) Gestión de usuarios  
D) Gestión de archivos

---

## 43.
En Scrum, ¿qué elemento contiene el trabajo conocido que podría realizarse sobre el producto?

A) Product Backlog  
B) Sprint Review  
C) Daily Scrum  
D) Increment exclusivamente

---

## 44.
¿Qué afirmación sobre el Scrum Master es correcta?

A) Es el jefe jerárquico obligatorio de Developers.  
B) Ayuda a establecer Scrum y a mejorar la efectividad del equipo.  
C) Es siempre quien decide el orden del Product Backlog.  
D) Es responsable de aprobar jurídicamente el producto.

---

## 45.
¿Qué evento de Scrum sirve para inspeccionar el resultado del Sprint y determinar futuras adaptaciones?

A) Sprint Review  
B) Daily Scrum  
C) Sprint Planning exclusivamente  
D) Retrospective exclusivamente

---

## 46.
PRINCE2 se centra principalmente en:

A) Gestión estructurada de proyectos.  
B) Administración de bases de datos.  
C) Cifrado de comunicaciones.  
D) Desarrollo exclusivo en PHP.

---

## 47.
ISO/IEC 20000 está relacionada con:

A) Sistemas de gestión de servicios de TI.  
B) Sistemas de archivos Linux.  
C) Protocolos de correo.  
D) Certificados digitales exclusivamente.

---

# 🔐 BLOQUE 07 · SEGURIDAD

## 48.
¿Cuál de las siguientes combinaciones representa las tres dimensiones clásicas de la seguridad de la información?

A) Confidencialidad, integridad y disponibilidad.  
B) Velocidad, coste y usabilidad.  
C) Autenticación, facturación y compresión.  
D) Rendimiento, latencia y almacenamiento.

---

## 49.
El ENS establece un marco de seguridad para:

A) Los sistemas de información del ámbito previsto para las Administraciones Públicas.  
B) Exclusivamente los ordenadores personales domésticos.  
C) Exclusivamente las redes sociales.  
D) Únicamente los sistemas de videovigilancia.

---

## 50.
¿Qué principio del RGPD exige que los datos no se conserven durante más tiempo del necesario para los fines del tratamiento, salvo excepciones aplicables?

A) Limitación del plazo de conservación  
B) Minimización  
C) Exactitud  
D) Portabilidad

---

## 51.
Una persona solicita que sus datos personales sean eliminados cuando se cumplen las condiciones previstas por el RGPD. ¿Qué derecho está ejerciendo?

A) Derecho de acceso  
B) Derecho de supresión  
C) Derecho de portabilidad  
D) Derecho de rectificación

---

## 52.
¿Qué mecanismo permite demostrar criptográficamente la autenticidad e integridad de determinados datos mediante una firma digital?

A) Firma digital  
B) DHCP  
C) NAT  
D) RAID

---

## 53.
¿Qué relación existe entre una clave privada y una clave pública en criptografía asimétrica?

A) Son dos copias idénticas que deben compartirse públicamente.  
B) Forman un par relacionado criptográficamente con funciones complementarias.  
C) La clave privada debe publicarse junto al certificado.  
D) Solo se utiliza una de las dos.

---

## 54.
¿Qué hace principalmente un firewall con reglas de filtrado?

A) Decide qué comunicaciones se permiten o bloquean según las reglas configuradas.  
B) Garantiza que ningún malware pueda existir.  
C) Sustituye a los sistemas de autenticación.  
D) Cifra automáticamente todos los archivos del equipo.

---

## 55.
Un atacante cifra los archivos de una organización y exige un pago para recuperarlos. ¿Qué amenaza describe mejor este escenario?

A) Ransomware  
B) Phishing  
C) Spoofing DNS exclusivamente  
D) Escaneo de puertos

---

## 56.
¿Qué medida es especialmente eficaz para reducir el riesgo derivado del robo de una contraseña?

A) Autenticación multifactor  
B) Reutilización de contraseñas  
C) Desactivar registros  
D) Eliminar las actualizaciones

---

## 57.
¿Qué principio establece que una persona solo debería disponer de los privilegios necesarios para realizar sus funciones?

A) Mínimo privilegio  
B) Máxima disponibilidad  
C) Publicidad de datos  
D) Replicación

---

# 🧪 BLOQUE 08 · IMIDA

## 58.
¿Cuál es la finalidad general de las Buenas Prácticas de Laboratorio?

A) Establecer un marco de organización, realización, registro, supervisión e informe de determinados estudios para asegurar su calidad e integridad.  
B) Sustituir todas las normas de seguridad laboral.  
C) Regular únicamente la eliminación de residuos urbanos.  
D) Servir como sistema operativo del laboratorio.

---

## 59.
¿Qué documento describe previamente los objetivos y metodología previstos para un estudio?

A) Protocolo  
B) Informe final  
C) Registro de residuos  
D) Factura

---

## 60.
¿Cuál es la función de Garantía de Calidad en BPL?

A) Realizar directamente todos los análisis del estudio.  
B) Verificar de forma independiente que el estudio se realiza conforme a los principios aplicables.  
C) Sustituir al director del estudio.  
D) Gestionar exclusivamente las compras.

---

## 61.
Una muestra llega al laboratorio con código, fecha, hora y procedencia correctamente registrados, pero sin indicar quién realizó la toma. ¿Qué problema existe principalmente?

A) Trazabilidad incompleta.  
B) Error de compilación.  
C) Problema de DNS.  
D) Fallo de firewall.

---

## 62.
¿Cuál de las siguientes actuaciones favorece la representatividad de un muestreo?

A) Seleccionar únicamente los elementos que parecen anómalos y extrapolarlos a todo el conjunto.  
B) Diseñar previamente la selección de puntos teniendo en cuenta el objetivo y las características del conjunto.  
C) Elegir siempre el punto más cercano al laboratorio.  
D) Tomar una muestra más grande en un único punto.

---

## 63.
Durante una toma de muestras se utiliza una herramienta contaminada previamente con otra muestra. ¿Qué riesgo aparece?

A) Contaminación cruzada.  
B) Mayor disponibilidad.  
C) Autenticación multifactor.  
D) Compresión de datos.

---

## 64.
Una muestra requiere unas determinadas condiciones de conservación establecidas por el procedimiento. Durante el transporte se incumplen esas condiciones. ¿Cuál es la actuación correcta?

A) Modificar manualmente la etiqueta para indicar que se conservaron correctamente.  
B) Registrar la incidencia y evaluar sus consecuencias conforme al procedimiento aplicable.  
C) Eliminar inmediatamente todas las muestras del proyecto.  
D) Continuar siempre sin registrar nada.

---

## 65.
¿Cuál de los siguientes elementos forma parte de una adecuada gestión de residuos?

A) Identificación, segregación, envasado, etiquetado, almacenamiento y gestión conforme al tipo de residuo y normativa aplicable.  
B) Mezclar todos los residuos para simplificar la gestión.  
C) Verterlos al desagüe si se diluyen suficientemente.  
D) Eliminar cualquier residuo químico junto con residuos urbanos.

---

## 66.
En términos generales, ¿qué diferencia existe entre un residuo peligroso y uno no peligroso?

A) El peligro se determina por sus características y por la normativa aplicable, no simplemente por el lugar donde se genera.  
B) Todo residuo generado en un laboratorio es necesariamente peligroso.  
C) Ningún residuo de laboratorio puede ser peligroso.  
D) La clasificación depende exclusivamente de su color.

---

# 🧠 BLOQUE TRANSVERSAL · NIVEL FINAL

## 67.
Un servidor Linux aloja una aplicación web. Los usuarios informan de que la aplicación funciona, pero responde lentamente. El administrador observa un consumo elevado de CPU del proceso de MySQL.

¿Cuál sería una actuación inicial razonable?

A) Analizar procesos y consumo de recursos y, a continuación, investigar qué consultas o actividad de MySQL están provocando la carga.  
B) Borrar `/var` inmediatamente.  
C) Reiniciar todos los usuarios de Active Directory.  
D) Cambiar todas las direcciones MAC.

---

## 68.
Una aplicación Laravel realiza una consulta para obtener 100 usuarios y después ejecuta una consulta adicional para obtener los posts de cada usuario.

¿Qué patrón describe mejor la situación y qué solución sería apropiada?

A) N+1; utilizar eager loading cuando corresponda.  
B) DHCP; utilizar DNS.  
C) ACID; utilizar firewall.  
D) Phishing; utilizar MFA.

---

## 69.
Una organización pública quiere desplegar una aplicación que trata datos personales. El equipo propone:

```text
- utilizar CI/CD;
- aplicar controles de seguridad;
- limitar los datos tratados a los necesarios;
- definir responsabilidades sobre el servicio;
- mantener trazabilidad sobre determinadas muestras utilizadas
  en un módulo de investigación.
```

¿Cuál es la interpretación más adecuada?

A) Solo interviene programación.  
B) El proyecto puede involucrar simultáneamente desarrollo, gestión TIC, seguridad, protección de datos e investigación del ámbito IMIDA.  
C) Solo interviene redes.  
D) El RGPD sustituye todas las demás disciplinas.

---

## 70.
Durante una investigación del IMIDA se obtienen muestras de diferentes zonas de una parcela. Las muestras están correctamente identificadas y el laboratorio realiza correctamente los análisis. Sin embargo, al revisar el diseño se descubre que los puntos se seleccionaron únicamente en las zonas donde el investigador esperaba encontrar el fenómeno estudiado.

¿Cuál es la conclusión más correcta?

A) La correcta identificación y el buen análisis garantizan automáticamente la representatividad.  
B) Existe un posible sesgo de muestreo que puede comprometer la capacidad de extrapolar los resultados al conjunto.  
C) El problema es exclusivamente de ciberseguridad.  
D) El problema desaparece porque se utilizaron varias muestras.

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

# 🎯 MODO EXAMEN

Para este segundo simulacro, intenta hacerlo de una sentada.

### Primera vuelta

Responde las preguntas seguras.

### Segunda vuelta

Vuelve a las dudosas.

### Tercera vuelta

Revisa exclusivamente:

```text
¿He leído "NO"?
¿He confundido dos conceptos?
¿Estoy eligiendo una opción porque suena bien
o porque puedo justificarla?
```

Marca las dudas:

```text
✓ segura
? dudosa
```

No cambies una respuesta solo por nervios.

---

# 🏆 OBJETIVO DEL SIMULACRO 02

El primer simulacro buscaba principalmente detectar lagunas.

Este segundo intenta comprobar algo diferente:

> **¿Puedes aplicar el conocimiento cuando los bloques empiezan a mezclarse?**

Especial atención a:

```text
Linux ↔ administración
Windows ↔ redes
Bases de datos ↔ Laravel
Laravel ↔ REST
ITIL ↔ Scrum
ENS ↔ RGPD
BPL ↔ muestreo
Muestreo ↔ trazabilidad
```

Y las últimas cuatro preguntas son deliberadamente transversales.

---

# 🏁 FIN DEL SIMULACRO GENERAL 02

## 70 preguntas · 8 bloques

Cuando termines, guarda tus respuestas.

Después prepararemos el **solucionario completo**, pero no lo abras antes de tiempo.

> 🧠 **Último consejo:** no intentes demostrar que sabes el temario. Intenta resolver cada pregunta con la información que realmente contiene. El examen no premia al que reconoce palabras bonitas, sino al que distingue la respuesta correcta de tres impostoras con bigote.

