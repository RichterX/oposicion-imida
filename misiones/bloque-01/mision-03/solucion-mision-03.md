# ✅ SOLUCIÓN
# Misión 03
# Despliegue inicial de la infraestructura del IMIDA

---

# 📝 FASE 1
## Diseñando la infraestructura

### 1. ¿Por qué implantar un dominio en lugar de un grupo de trabajo?

Un dominio permite administrar de forma centralizada todos los usuarios, equipos y recursos de la organización.

Entre sus ventajas destacan:

- Autenticación centralizada.
- Administración única de usuarios.
- Aplicación de Directivas de Grupo (GPO).
- Mayor seguridad.
- Escalabilidad.
- Administración remota.
- Compartición sencilla de recursos.

Un grupo de trabajo resulta adecuado únicamente para redes pequeñas donde cada equipo administra sus propios usuarios.

---

### 2. ¿Qué ventajas aporta Active Directory?

Entre otras:

- Administración centralizada.
- Gestión de usuarios y grupos.
- Administración de equipos.
- Aplicación de GPO.
- Autenticación única.
- Organización mediante OU.
- Delegación de administración.
- Escalabilidad.
- Mayor seguridad.
- Integración con otros servicios Windows.

Bastaba con indicar cinco correctamente explicadas.

---

### 3. Nombre del dominio

Una posible respuesta:

```
IMIDA.LOCAL
```

También serían aceptables otros nombres coherentes con la organización.

Lo importante es utilizar una nomenclatura clara y representativa.

---

### 4. Objetos del dominio

Como mínimo deberían aparecer:

- Usuarios.
- Equipos.
- Grupos.
- Unidades Organizativas (OU).

También podrían mencionarse:

- Impresoras publicadas.
- Contactos.
- Equipos de servidor.
- Objetos de directiva (GPO) como elementos administrados del entorno, aunque técnicamente se almacenan de forma diferenciada.

---

# 📝 FASE 2
## Organización del dominio

### 5. Estructura de OU

Una posible solución:

```
IMIDA.LOCAL

│

├── Dirección

├── Administración

├── Investigación

└── Informática
```

Podrían existir subOU si se justifican adecuadamente.

---

### 6. Justificación

La estructura sigue la organización real de la empresa.

Esto facilita:

- la administración;
- la aplicación de GPO;
- el crecimiento futuro;
- la localización de objetos.

---

### 7. Grupos

Sí.

Los grupos permiten administrar permisos de forma conjunta.

Ejemplos:

- Investigadores
- Administrativos
- Dirección
- Técnicos Informáticos

En lugar de asignar permisos usuario por usuario, basta con asignarlos al grupo.

---

# 📝 FASE 3
## Usuarios

### 8. Objetos

Se crearían cuatro objetos Usuario.

Cada empleado debe disponer de una cuenta independiente.

---

### 9. Información almacenada

Por ejemplo:

- Nombre.
- Apellidos.
- Usuario de inicio de sesión.
- Contraseña.
- Correo.
- Departamento.
- Cargo.
- Teléfono.
- Despacho.

---

### 10. OU

Cada usuario debería almacenarse en la OU correspondiente a su departamento.

Ejemplo:

Laura → Investigación

David → Informática

Marta → Administración

Juan → Dirección

Lo importante es justificar la organización.

---

# 📝 FASE 4
## Equipos

### 11. Pasos

Orden lógico:

1. Instalar Windows.
2. Configurar nombre del equipo.
3. Unir el equipo al dominio.
4. Reiniciar.
5. Active Directory crea el objeto Equipo.
6. Colocar el equipo en la OU adecuada.
7. Aplicar automáticamente las GPO.
8. El usuario inicia sesión.

---

### 12. ¿Qué ocurre al unirlo?

- Se crea un objeto Equipo.
- Se establece una relación de confianza con el dominio.
- El equipo puede autenticar usuarios del dominio.
- Comienza a recibir GPO.
- Puede administrarse centralizadamente.

---

### 13. Convención de nombres

Permite:

- localizar equipos fácilmente;
- identificar departamento;
- facilitar inventarios;
- mejorar la administración.

Ejemplo:

```
PC-INV-01

PC-ADM-03

SRV-DC-01
```

---

# 📝 FASE 5
## Administración

### 14.

Laura:

Mover a otra OU.

David:

Deshabilitar la cuenta.

Posteriormente eliminarla si deja de ser necesaria.

Nuevos investigadores:

Crear usuarios.

Asignarlos a la OU Investigación.

Equipo averiado:

Deshabilitar.

Posteriormente eliminar.

---

### 15.

No.

Primero conviene deshabilitar la cuenta.

Después comprobar que ya no existe ninguna dependencia.

Finalmente eliminarla.

Esta práctica reduce errores administrativos.

---

# 📝 FASE 6
## GPO

### 16.

Crearía GPO independientes para cada departamento.

Por ejemplo:

```
GPO Investigación

GPO Administración

GPO Dirección

GPO Informática
```

También podrían separarse por función:

- Seguridad
- Escritorio
- Software

Siempre que se justificara.

---

### 17.

Cada GPO se vincularía a la OU correspondiente.

```
Investigación

↓

GPO Investigación

------------------

Administración

↓

GPO Administración
```

Nunca sería necesario aplicarlas ordenador por ordenador.

---

### 18.

Porque permiten:

- administración centralizada;
- ahorro de tiempo;
- uniformidad;
- mayor seguridad;
- escalabilidad;
- reducción de errores.

---

# 📝 FASE 7
## Reflexión

### 19.

Sí.

La infraestructura está preparada para crecer.

Solo habría que:

- crear nuevas OU si fuera necesario;
- incorporar nuevos usuarios;
- unir nuevos equipos;
- aplicar nuevas GPO.

El modelo continúa siendo válido.

La escalabilidad constituye precisamente una de las principales ventajas de Active Directory.

---

### 20.

Una respuesta completa debería describir un proceso parecido al siguiente.

```
Compra del ordenador

↓

Instalación de Windows

↓

Cambio de nombre

↓

Unión al dominio

↓

Creación del objeto Equipo

↓

Ubicación en la OU

↓

Aplicación de GPO

↓

Inicio de sesión del usuario

↓

Equipo completamente integrado
```

Este recorrido resume el funcionamiento conjunto de todo el Bloque 1.

---

# 🏆 Autoevaluación

## Excelente (18-20 respuestas)

Has comprendido el funcionamiento global de Active Directory.

No solo conoces los conceptos, sino que sabes relacionarlos.

Estás preparado para afrontar preguntas de desarrollo sobre este bloque.

---

## Muy bien (15-17 respuestas)

Dominas la mayor parte del contenido.

Conviene repasar especialmente las relaciones entre OU, GPO y equipos.

---

## Aceptable (12-14 respuestas)

Los conceptos básicos están claros, pero todavía existen lagunas.

Es recomendable releer algunos capítulos antes de realizar el simulacro.

---

## Menos de 12 respuestas

Antes de continuar, conviene revisar nuevamente el bloque completo.

No te centres en memorizar definiciones.

Intenta comprender cómo se relacionan entre sí el dominio, los objetos, las OU, los equipos y las GPO.