# Modelo DARC: Un Marco de Integridad para el Diseño de Sistemas
**Por: Pablo Kaniefsky**

## 1. Introducción
El **Modelo DARC** (Dominio, Abstracción, Responsabilidad, Conexión) surge como una síntesis evolutiva de las mejores prácticas de la ingeniería de software de los últimos 50 años. Su objetivo es proporcionar un marco de pensamiento claro para la construcción de soluciones tecnológicas, priorizando la comprensión del problema real por sobre la implementación técnica.

DARC no es solo una sigla; es un modelo de **integridad sistémica** que organiza las decisiones de diseño en dos grandes estratos: la **Arquitectura** (el qué y el porqué) y la **Ingeniería** (el cómo).

---

## 2. Estrato I: Arquitectura (El "Qué" y el "Porqué")
La arquitectura en DARC se ocupa de las decisiones de alto nivel, aquellas que definen la morfología del sistema y son costosas de revertir.

### D - Dominio (Dominiocentrismo)
Es el núcleo soberano del sistema. El Dominio es el sistema preexistente (manual o analógico) y el problema a resolver.
* **La Doble Dimensión:** Reconoce la ontología del negocio (actores, entidades, reglas) y las fricciones del sistema actual.
* **Las 4 Dimensiones del Problema:** Todo desarrollo DARC debe atacar al menos una de estas áreas:
    1. **Dinero:** Eficiencia de costos y recursos.
    2. **Tiempo:** Reducción de latencia y burocracia.
    3. **Servicios:** Calidad y experiencia del usuario.
    4. **Observabilidad:** Eliminación de la ceguera institucional y gestión del riesgo.
* **Aporte Teórico:** Hereda la centralidad del **Domain-Driven Design (DDD)** de Eric Evans, implementando un **Lenguaje Ubicuo** donde el código habla el idioma del experto del negocio.

### A - Abstracción
Es el proceso de separación conceptual que protege al Dominio de la volatilidad técnica. 
* **Función:** Define los límites (boundaries) y las capas de aislamiento. Es el filtro que decide qué detalles técnicos son irrelevantes para la lógica de negocio.
* **Aporte Teórico:** Basado en la **Separation of Concerns (SoC)** de Dijkstra y la **Inversión de Dependencias (D)** de SOLID. En DARC, la Abstracción garantiza que el Dominio no dependa de la tecnología (la base de datos o la UI son "detalles").

---

## 3. Estrato II: Ingeniería (El "Cómo")
La ingeniería en DARC representa la ejecución táctica, la artesanía del código y la construcción de componentes robustos.

### R - Responsabilidad
Representa la identidad y misión de cada componente. 
* **Principios:** Es el destilado de la **S (Single Responsibility)** de SOLID y la **U (Unix Philosophy)** de CUPID: "Hacer una sola cosa y hacerla bien".
* **Impacto:** Una Responsabilidad clara reduce el radio de explosión de los errores y facilita la testabilidad. Es la unidad mínima de profesionalismo en el código.

### C - Conexión
Define el ensamble y la comunicación entre las partes y el mundo exterior.
* **Principios:** Basado en la **C (Composable)** de CUPID. Se enfoca en el desacoplamiento mediante interfaces y contratos claros.
* **Mecánica:** Es la capa de infraestructura que implementa los "adaptadores" (siguiendo la Arquitectura Hexagonal de Cockburn) para conectar el núcleo con APIs, bases de datos o interfaces de usuario sin contaminar la Responsabilidad.

---

## 4. Herencia y Síntesis Teórica
DARC actúa como un "unificador de principios", descartando el ruido burocrático para quedarse con la esencia operativa:

| Modelo Original | Elementos Subsumidos en DARC |
| :--- | :--- |
| **SOLID** | **S** (en R), **D** (en A y D). (O, L, I se consideran detalles de implementación OOP). |
| **CUPID** | **C** (en C), **U** (en R), **D** (en D). (P e I se consideran requisitos básicos de calidad). |
| **DDD** | Lenguaje Ubicuo y Centralidad del Dominio (en D). |
| **Clean Arch.** | Independencia de infraestructura y reglas de dependencia (en A y C). |

---

## 5. El Modelo en la Era de la IA
DARC posiciona al profesional como un **Arquitecto de Soluciones**. En un contexto donde la IA genera el código, el valor del humano reside en:
1. Realizar un relevamiento profundo del **Dominio** y sus dimensiones de dolor.
2. Diseñar la **Abstracción** correcta para que la IA no genere sistemas rígidos.
3. Auditar que cada pieza generada cumpla su **Responsabilidad** única y posea **Conexiones** desacopladas.

> "En DARC, el código es efímero; el diseño del Dominio y su Abstracción son permanentes."