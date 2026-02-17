# Modelo DARC — Resumen

**DARC** es un marco para construir software. Su nombre es un acrónimo de sus cuatro pilares: **Dominio, Abstracción, Responsabilidad, Conexión**.

---

## Los cuatro pilares en una línea

| Pilar | Pregunta que responde | Núcleo conceptual |
|---|---|---|
| **D — Dominio** | ¿Qué modela el sistema? | La realidad preexistente al software: sus entidades, reglas y procesos. El código habla el idioma del dominio. |
| **A — Abstracción** | ¿Cómo se organiza? | Separación de incumbencias: capas con fronteras claras que protegen el núcleo del sistema de los detalles técnicos. |
| **R — Responsabilidad** | ¿Para qué existe cada pieza? | Propósito atómico: una sola razón para existir, una sola razón para cambiar. Funciones breves, nombres claros. |
| **C — Conexión** | ¿Cómo se comunican las partes? | Interfaces explícitas y bajo acoplamiento. Las dependencias se inyectan; los contratos se respetan. |

---

## La estructura del modelo

**D + A = Arquitectura** → Qué construir y cómo estructurarlo.  
**R + C = Ingeniería** → Cómo construir cada pieza y cómo integrarla.

---

## La regla de oro de cada pilar

- **Dominio:** Si cambias una tecnología y eso obliga a cambiar una regla de negocio, el Dominio no es soberano.
- **Abstracción:** Si una capa sabe demasiado de otra, las incumbencias no están separadas.
- **Responsabilidad:** Si necesitás leer el cuerpo de una función para entender qué hace, el nombre o la función falló.
- **Conexión:** Si reemplazar un componente requiere tocar a sus vecinos, el acoplamiento es demasiado rígido.

---

## Para qué sirve hoy

DARC es el criterio que permite al desarrollador **delimitar y supervisar el trabajo de las IAs**. Un sistema construido bajo DARC es legible por humanos y verificable por herramientas. Evita deuda técnica al mantener la lógica del negocio separada, las piezas enfocadas y las integraciones transparentes.
