# Tarjetas - Bloque 05 - 5.1 Python

Formato:
P: Pregunta
R: Respuesta

---

## 5.1 Python

P: Que caracteriza a Python frente a tipados estaticos clasicos?
R: Tipado dinamico y fuerte; el tipo pertenece al objeto, no al nombre.

P: Diferencia entre / y // en Python?
R: / hace division real; // hace division entera por suelo.

P: Que diferencia hay entre list y tuple?
R: list es mutable; tuple es inmutable.

P: Que devuelve dict.get("clave") si no existe?
R: None o el valor por defecto indicado, sin lanzar KeyError.

P: Que hace una list comprehension?
R: Construye listas de forma declarativa con expresion, iteracion y filtro opcional.

P: Diferencia entre sorted() y .sort()?
R: sorted devuelve lista nueva; .sort modifica la lista original.

P: Para que sirve *args y **kwargs?
R: *args recoge posicionales extra; **kwargs recoge nombrados extra.

P: Regla LEGB en resolucion de nombres?
R: Local, Enclosing, Global, Built-in.

P: Que papel tienen try/except/else/finally?
R: try ejecuta, except captura, else corre sin excepcion, finally se ejecuta para limpieza.

P: Que aporta with open(...) as f?
R: Gestion automatica del recurso, incluso si hay excepciones.

P: Que diferencia hay entre modulo y paquete?
R: Modulo es un archivo .py; paquete es una carpeta de modulos.

P: Que representa __name__ == "__main__"?
R: Que el archivo se esta ejecutando como programa principal.

P: Que es un generador en Python?
R: Una funcion con yield que produce valores bajo demanda.

P: Que aportan type hints?
R: Documentacion y analisis estatico; normalmente no fuerzan tipos en ejecucion.

---

## Tarjetas de repaso transversal (5.1)

P: Trampa clasica con parametros por defecto mutables?
R: Se crean una vez; pueden compartir estado entre llamadas.

P: Trampa clasica de igualdad vs identidad?
R: == compara valor; is compara identidad del objeto.

P: Objetivo final de 5.1?
R: Dominar sintaxis, estructuras y patrones de Python para leer y escribir codigo fiable.
