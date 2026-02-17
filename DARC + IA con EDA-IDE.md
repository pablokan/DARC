
| User Prompt: |
|-------------|
| Tú dijiste

DARC + IA (Contexto: El Modelo DARC elaborado en una conversación anterior y el documento anexado).

En los proyectos actuales se usan EDAs (en mi caso estoy usando opencode), que permiten crear/revisar/modificar repositorios completos de proyectos. Además se los puede contextualizar con un archivo markdown (por ejemplo AGENTS.md) y darles "skills" (que son recetas para diferentes tareas).

En este marco, cual sería tu propuesta de integración para DARC + IA usando un EDA? Adicionalmente, para no hacer "sobreingeniería", podés mencionar variantes abordadas con herramientas más simples como un IDE estándar (por ejemplo VSCode) |

Esta propuesta de integración combina los principios del modelo **DARC** (Dominio, Arquitectura, Responsabilidad, Conexión) con las capacidades de los **Entornos de Desarrollo Agénticos (EDAs)** como *opencode* o *Cursor*, optimizando la autonomía de los agentes mediante un contexto estructurado.

### Resumen de la Propuesta
La integración se centra en convertir los pilares de **DARC** en el "manual de instrucciones" del EDA. Al definir explícitamente el **Dominio**, la **Arquitectura**, las **Responsabilidades** y las **Conexiones** en archivos de configuración (como `AGENTS.md`), el agente deja de "adivinar" y comienza a operar bajo las reglas de integridad del iTec.

---

### 1. Integración en EDAs (Nivel Avanzado)
Para herramientas como *opencode*, la clave es la **contextualización** y la definición de **skills**:

* **Configuración del `AGENTS.md` (El Corazón DARC):**
    * **Dominio (D):** Define el lenguaje ubicuo y las reglas de negocio centrales. Esto evita que el agente cree entidades fuera de la lógica del dominio del iTec.
    * **Arquitectura (A):** Establece el "qué" y el "por qué" del diseño (ej. Arquitectura Hexagonal o en Capas). Indica al EDA dónde debe residir cada tipo de archivo.
    * **Responsabilidad (R):** Define los límites de cada componente, basándose en el principio de responsabilidad única (S de SOLID).
    * **Conexión (C):** Especifica cómo deben interactuar los módulos (interfaces, inyección de dependencias) para mantener el acoplamiento bajo.

* **Implementación de "Skills" (Recetas DARC):**
    * Crea comandos específicos dentro del EDA para tareas repetitivas. Por ejemplo, una skill llamada `crear-entidad-darc` que, al ejecutarse, genere automáticamente el archivo de dominio, su interfaz de conexión y la implementación de su responsabilidad, respetando la estructura del repositorio.

---

### 2. Variantes en IDEs Estándar (Sin Sobreingeniería)
Si no es necesario gestionar el repositorio completo con agentes, se pueden aplicar variantes de **DARC** en entornos como **VSCode** de forma más sencilla:

* **Snippets Orientados a DARC:** * Configurar fragmentos de código (Snippets) que ya traigan la estructura de carpetas y comentarios basada en DARC. Por ejemplo, un snippet para una nueva clase que incluya secciones obligatorias para "Responsabilidades" y "Conexiones".
* **Prompt Engineering en Chat (Modo "Tía Marta" o Conversacional):** * En lugar de un archivo de configuración complejo, puedes usar una instrucción de sistema persistente en el chat de la IA (como GitHub Copilot o ChatGPT) que diga: *"Toda pieza de código que generes debe seguir el modelo DARC: separa claramente el Dominio de la Arquitectura, asigna una única Responsabilidad y define explícitamente las Conexiones mediante interfaces"*.
* **Linter y Reglas de Estilo:** * Usar herramientas de análisis estático que detecten cuando un componente está mezclando lógica de Dominio con detalles de Arquitectura, forzando la integridad del modelo sin necesidad de un agente autónomo.

---

### Beneficios de la Integración
* **Foco en la Lectura:** Al tener una estructura predecible basada en DARC, los desarrolladores (especialmente los aprendices) pueden leer y entender más rápido el código generado por la IA.
* **Consistencia Académica:** Para el iTec, esto asegura que todos los proyectos sigan el mismo estándar de integridad de software, facilitando la evaluación y la enseñanza de la "gramática" de los lenguajes.
