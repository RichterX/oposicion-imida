# Tarjetas - Bloque 05 - 5.2 Java

Formato:
P: Pregunta
R: Respuesta

---

## 5.2 Java

P: Diferencia practica entre JDK y JRE?
R: JDK incluye herramientas de desarrollo como javac; JRE se orienta a ejecucion.

P: Que ejecuta la JVM?
R: Bytecode Java (.class), aportando portabilidad entre plataformas compatibles.

P: Diferencia entre tipo primitivo y wrapper?
R: Primitivo no es objeto; wrapper (Integer, Double...) encapsula valor como objeto.

P: Que implica static en un miembro?
R: Pertenece a la clase, no a cada instancia.

P: Diferencia entre sobrecarga y sobrescritura?
R: Sobrecarga cambia firma en misma clase; sobrescritura redefine metodo heredado.

P: Para que sirve @Override?
R: Verificar en compilacion que realmente se sobrescribe un metodo.

P: Que caracteriza a una interfaz funcional?
R: Un unico metodo abstracto funcional, base de lambdas.

P: Diferencia base entre List, Set y Map?
R: List ordena y admite duplicados; Set evita duplicados; Map maneja clave/valor.

P: Que son checked exceptions?
R: Excepciones que deben capturarse o declararse con throws.

P: Que aporta try-with-resources?
R: Cierre automatico de recursos AutoCloseable.

P: Para que sirven generics?
R: Seguridad de tipos en compilacion y reutilizacion sin casts inseguros.

P: Que son streams en Java?
R: Pipeline declarativo para procesar colecciones con operaciones intermedias y terminales.

P: Diferencia entre String y StringBuilder?
R: String es inmutable; StringBuilder es mutable para concatenaciones eficientes.

P: Que aporta ExecutorService en concurrencia?
R: Gestion de hilos y ejecucion de tareas desacoplada del codigo de negocio.

---

## Tarjetas de repaso transversal (5.2)

P: Trampa habitual en equals y == con objetos?
R: == compara referencia; equals compara igualdad logica si esta implementada.

P: Trampa de volatile?
R: Aporta visibilidad, no atomicidad de operaciones compuestas.

P: Objetivo final de 5.2?
R: Entender Java moderno desde OO hasta concurrencia y APIs clave de backend.
