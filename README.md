# Práctica: Simulación del Problema de Parada (Halting Problem)

## 1. Introducción
Esta práctica simula el Problema de Parada propuesto por Alan Turing en 1936, demostrando que no existe un algoritmo que determine si cualquier programa terminará o se ejecutará indefinidamente.

## 2. Programas de ejemplo
- **programStops**: cuenta hacia abajo hasta 0 y se detiene.
- **programLoops**: cuenta hacia arriba indefinidamente y nunca se detiene.

## 3. Simulación de HaltChecker
**HaltChecker** simula un algoritmo hipotético que predice si un programa se detiene, pero solo funciona con programas conocidos.

## 4. Reverser
**Reverser** analiza un programa consigo mismo como entrada.  
- Si HaltChecker dice que se detiene, Reverser entra en bucle.  
- Si dice que no se detiene, Reverser finaliza.

## 5. Paradoja de Reverser(Reverser)
- Si HaltChecker dice que se detiene → Reverser no se detiene (bucle).
- Si dice que no se detiene → Reverser se detiene.

**Ambos casos son contradictorios.**

## 6. Conclusión
La práctica demuestra que el **Problema de Parada es indecidible**. No existe un algoritmo que pueda resolverlo para todos los programas posibles.
