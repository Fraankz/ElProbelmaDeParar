# Práctica: Simulación del Problema de Parada (Halting Problem)

## 1. Introducción

El Problema de Parada (Halting Problem) fue formulado por **Alan Turing en 1936** y plantea la siguiente pregunta:  
> ¿Existe un algoritmo que, dado cualquier programa y cualquier entrada, pueda determinar si dicho programa se detendrá o continuará ejecutándose para siempre?

Turing demostró que este problema es **indecidible**, es decir, que **no existe ningún algoritmo general** que pueda resolverlo en todos los casos posibles.  
Esta práctica tiene como objetivo simular este concepto en Java, comprendiendo tanto su funcionamiento como sus implicaciones teóricas.

---

## 2. Programas de ejemplo

Se han implementado dos programas sencillos que permiten visualizar el problema:

- **`programStops`**: cuenta hacia abajo desde un número dado hasta 0. Este programa **siempre se detiene**.
- **`programLoops`**: cuenta hacia arriba indefinidamente sin condición de parada. Este programa **nunca se detiene**.

Estos ejemplos sirven como base para que nuestro sistema simulado (`HaltChecker`) pueda analizarlos y emitir predicciones controladas.

---

## 3. Simulación de `HaltChecker`

`HaltChecker` representa una **simulación conceptual** de un programa que intenta decidir si otro programa se detiene o no, basándose en su nombre o estructura.  
Por supuesto, como sabemos que el problema real es indecidible, este `HaltChecker` no es un verificador universal, sino un modelo que **devuelve respuestas controladas** para los casos conocidos (`programStops`, `programLoops`, etc.).

Esto permite simular cómo **se comportaría un verificador si existiera**, y así reproducir la lógica del razonamiento de Turing.

---

## 4. El programa `Reverser`

`Reverser` es un programa diseñado para crear una **contradicción lógica**. Su comportamiento depende del resultado que le da `HaltChecker`:

- Si `HaltChecker` indica que el programa se detendrá, entonces `Reverser` **entra en un bucle infinito**.
- Si `HaltChecker` indica que no se detendrá, entonces `Reverser` **termina inmediatamente**.

Es decir, hace exactamente lo **opuesto** a lo que predice el verificador.

---

## 5. Paradoja de `Reverser(Reverser)`

Aquí se encuentra el núcleo de la paradoja. Ejecutamos `Reverser` pasando **su propio código como entrada**:
```java
Reverser.execute("Reverser");
```

Esto lleva a dos posibilidades, ambas contradictorias:

Si HaltChecker dice que Reverser se detiene con su propia entrada -> entonces Reverser entra en bucle -> no se detiene.
Si HaltChecker dice que Reverser no se detiene con su propia entrada -> entonces Reverser termina -> sí se detiene.
Por tanto, no importa qué responda HaltChecker, siempre se equivoca. Esta paradoja demuestra de forma práctica la indecidibilidad del problema.

## 6. Conclusión
Esta simulación permite visualizar una de las ideas más importantes de la teoría de la computación:

Existen límites fundamentales a lo que los algoritmos pueden resolver.

El Problema de Parada es indecidible, lo que significa que no hay ninguna forma general y segura de determinar si un programa se detendrá con una entrada dada.
Esta conclusión no solo tiene valor teórico, sino que también impacta el diseño de compiladores, verificadores de código y sistemas automáticos de prueba.

Gracias a esta práctica, se comprende no solo el razonamiento lógico detrás del problema, sino también su impacto real en el pensamiento algorítmico y los límites de la computación.
