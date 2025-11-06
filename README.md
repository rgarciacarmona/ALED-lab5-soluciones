# ALED (Algorithms and Data Structures) Lab Session 5 - Solution

This repository contains the code for a Java application that simulates an ER of a hospital using threads. It also uses monitors to manage shared resources (the areas of the ER).

This code is the solution for this lab session: https://github.com/rgarciacarmona/ALED-lab5

## Respuestas a las preguntas

### Sección 1.2

- **¿Puede el atributo `capacity` de `Area` cambiar durante la ejecución del programa? Si es así, ¿en qué circunstancias?, ¿cuánto se incrementará o reducirá cada vez?:** No, este atributo se fija cuando se crea el objeto y no varía durante la ejecución.
- **¿Puede el atributo `numPatients` de `Area` cambiar durante la ejecución del programa? Si es así, ¿en qué circunstancias?, ¿cuánto se incrementará o reducirá cada vez?:** Sí. Se incrementará en 1 cuando se empiece a tratar a un paciente. Se reducirá en 1 cuando se termine de tratar a un paciente.
- **¿Puede el atributo `waiting` de `Area` cambiar durante la ejecución del programa? Si es así, ¿en qué circunstancias?, ¿cuánto se incrementará o reducirá cada vez?:** Sí. Se incrementará en 1 cuando un paciente tenga que esperar a ser atendido. Se reducirá en 1 cuando un paciente que estaba esperando empiece a ser atendido.

### Sección 1.2.1

- **¿Qué atributos de `Area` son compartidos?:** `numPatients` y `waiting`, pues ambos pueden ser variar mientras una hebra está accediendo a ellos.
- **¿Qué métodos de Area contienen regiones críticas?:** `enter`, `exit`, `getNumPatients` y `getWaiting`.
- **¿Cómo se indica en Java que un método es sincronizado?:** Con la palabra clave `synchronized` en la cabecera del método, entre la visibilidad y el tipo de retorno.