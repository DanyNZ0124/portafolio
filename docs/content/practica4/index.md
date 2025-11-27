+++
date = '2025-11-27T13:15:05-08:00'
draft = false
title = 'Practica4: el paradigma logico'
+++

# Reporte Practica 4

**Autor:** Daniel Mojica Salgado

**Fecha:** 21 de Noviembre de 2025

## Introducción

## ¿Qué es Prolog?

**Prolog** (Programming in Logic) es un lenguaje de programación basado en **lógica matemática**, especialmente la lógica de predicados de primer orden. A diferencia de lenguajes imperativos como C o Java, Prolog no indica cómo resolver un problema paso a paso, sino que se enfoca en qué es cierto mediante hechos, reglas y consultas.

Es ampliamente utilizado en áreas como:

* Inteligencia artificial.
* Sistemas expertos.
* Procesamiento de lenguaje natural.
* Representación de conocimiento.
* Resolución automática de problemas y razonamiento lógico.

## Características principales de Prolog

* **Basado en lógica declarativa:** Se programa declarando hechos y reglas, y Prolog deduce respuestas.
* **Unificación:** Prolog compara estructuras y encuentra sustituciones para que coincidan.
* **Backtracking automático:** Si una solución falla, Prolog retrocede y prueba otras alternativas.
* **Consultas:** Se realizan preguntas a la base de conocimiento para obtener respuestas.
* **No tiene variables tradicionales:** Sus variables comienzan con mayúscula y representan valores desconocidos.
* **Recursión como base del control:** No existen ciclos tradicionales; todo se hace mediante recursión y backtracking.

### Ventajas de Prolog

* Ideal para IA y razonamiento lógico.
* Muy expresivo para representar conocimiento y relaciones complejas.
* Resolver problemas combinatorios es sencillo gracias a backtracking.
* Pocas líneas de código pueden resolver tareas complejas.
* Alta legibilidad cuando las reglas están bien estructuradas.

### Desventajas de Prolog

* Curva de aprendizaje diferente, cuesta pasar del pensamiento imperativo al declarativo.
* Rendimiento menor en tareas que requieren cálculos numéricos intensivos.
* Difícil de depurar, porque el backtracking puede generar soluciones inesperadas.
* La lógica mal construida puede llevar a búsquedas infinitas o lentas.

## Bases de Conocimiento en Prolog

En Prolog, una base de conocimiento se integra con:

* **Hechos:** afirmaciones sobre el mundo.

``` PL
animal(perro).
animal(gato).
come(perro, carne).
```

* **Reglas:** relaciones lógicas basadas en condiciones.

``` PL
carnivoro(X) :- come(X, carne).
```

* **Consultas:** preguntas a la base de conocimiento.

``` PL
?- carnivoro(perro).
```

## Ejemplos

### **KB1**

``` PL
girl(priya).
girl(natasha).
girl(jasmin).
can_cook(priya).
```

**¿Quiénes son niñas?**

``` PL
?- girl(X).
```

**Resultado:**

``` PL
X = priya ;
X = natasha ;
X = jasmin.
```

**¿Quién sabe cocinar?**

``` PL
?- can_cook(X).
```

**Resultado:**

``` PL
X = priya.
```

### **KB2**

``` PL
sing_a_song(ana).
listens_to_music(rodrigo).

listens_to_music(ana) :- sing_a_song(ana).
happy(ana) :- sing_a_song(ana).
happy(rodrigo) :- listens_to_music(rodrigo).
plays_guitar(rodrigo) :- listens_to_music(rodrigo).
```

**¿Quién puede tocar la guitarra?**

``` PL
?- plays_guitar(X).
```

**Resultado:**

``` PL
X = rodrigo.
```

### **KB3**

``` PL
can_cook(priya).
can_cook(jasmin).
can_cook(timoteo).

likes(priya,jasmin) :- can_cook(jasmin).
likes(priya,timoteo) :- can_cook(timoteo).
```

**¿A quién le gusta Jasmin?**

``` PL
?- likes(X, jasmin).
```

**Resultado:**

``` PL
X = priya.
```

## Conclusión

Prolog es un lenguaje poderoso que se basa en lógica y razonamiento automático. Su enfoque declarativo lo vuelve diferente, pero ideal para representar conocimiento y construir sistemas inteligentes. Aunque requiere un cambio de mentalidad respecto a lenguajes imperativos, su capacidad para resolver problemas complejos con pocas líneas lo convierte en una herramienta fundamental dentro de la inteligencia artificial clásica y el procesamiento lógico.
