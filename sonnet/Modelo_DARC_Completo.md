# Modelo DARC
## Un Marco para la Construcción de Soluciones de Software

---

## Presentación

El **Modelo DARC** (Dominio, Abstracción, Responsabilidad, Conexión) es un marco conceptual para la construcción de soluciones de software. No es una metodología nueva que compite con las existentes, sino una síntesis práctica de principios ya establecidos, reorganizados bajo una lógica que los hace operables en el contexto actual: un contexto donde las Inteligencias Artificiales participan activamente en el ciclo de desarrollo.

DARC propone que la calidad de una solución de software no reside en la tecnología que la implementa, sino en la claridad con que se articulan cuatro dimensiones fundamentales: la centralidad del dominio que se modela, la estructura que lo sostiene, la precisión de propósito de cada pieza, y la transparencia de sus interacciones.

Sus antecedentes principales son:

- **SoC** — *Separation of Concerns*, Dijkstra (1974)
- **SOLID** — Principios de Diseño Orientado a Objetos, Martin (2000)
- **DDD** — *Domain-Driven Design*, Evans (2003)
- **CUPID** — Propiedades para el Desarrollo, North (2022)

Cada pilar de DARC es un destilado de uno o más de estos antecedentes, sin duplicarlos ni reemplazarlos, sino integrándolos en un esquema unificado.

---

## Los Cuatro Pilares

### D — Dominio
*La centralidad de la realidad*

El Dominio es el sistema preexistente al software: el área de conocimiento, actividad o realidad organizacional que el sistema intenta modelar, organizar o automatizar. Antes de que se escriba una sola línea de código, ese dominio existe con su propia estructura (entidades y relaciones), su propio comportamiento (procesos y reglas) y sus propios datos (estados y condiciones). El trabajo del desarrollador no es inventar ese sistema, sino traducirlo con fidelidad.

En DARC, el Dominio es soberano. Esto significa que ninguna decisión tecnológica —la elección de un framework, un motor de base de datos, una arquitectura de red— debe deformar la lógica del dominio para acomodarse a sus limitaciones. El código se adapta al dominio, no al revés.

Esta centralidad tiene una consecuencia directa en la nomenclatura: las clases, funciones y variables deben hablar el idioma del dominio. Si el experto del negocio dice "Legajo", el código dice `Legajo`. Si el proceso se llama "Liquidación de Haberes", el método se llama `liquidar_haberes()`. Esta práctica, que DDD denomina **Lenguaje Ubicuo**, elimina la brecha cognitiva entre quienes conocen el problema y quienes construyen la solución.

El Dominio como pilar hereda directamente del enfoque dominiocéntrico del *Domain-Driven Design* y del principio de que la lógica del negocio debe estar aislada de los detalles de implementación.

---

### A — Abstracción
*La separación de incumbencias*

La Abstracción es el plano estructural que organiza el sistema. Responde a la pregunta de cómo se divide y organiza el software para que cada parte pueda evolucionar sin contaminar a las demás.

El principio fundacional aquí es la **Separación de Incumbencias (SoC)**: cada módulo, capa o componente debe ocuparse de un solo tipo de problema. Una capa no debería saber, al mismo tiempo, cómo se representa una pantalla, cómo se persisten los datos y cómo se calcula un descuento. Cuando esas responsabilidades se mezclan, el sistema se vuelve frágil: un cambio en la base de datos rompe la interfaz, una nueva regla de negocio exige reescribir el acceso a datos.

Una abstracción bien diseñada bajo DARC presenta fronteras claras entre el Dominio y su infraestructura de soporte. El núcleo del sistema —sus reglas, sus entidades, su comportamiento esencial— queda protegido de los detalles técnicos que lo rodean. Cambiar el motor de persistencia, migrar a otra plataforma o reemplazar una librería externa no debería requerir tocar la lógica que le da valor al sistema.

Este pilar recoge la esencia de SoC, los patrones de arquitectura limpia y el diseño estratégico de DDD (Bounded Contexts, capas de dominio aisladas), y orienta las decisiones estructurales grandes: cómo se organizan los módulos, qué conoce cada capa de las demás, dónde residen los distintos tipos de lógica.

---

### R — Responsabilidad
*El propósito atómico de cada pieza*

La Responsabilidad define la granularidad del software a nivel de componente: cada clase, función o módulo debe tener un único propósito, claro y bien delimitado. Debe existir exactamente una razón para que esa pieza cambie.

Este principio proviene directamente del **Principio de Responsabilidad Única (SRP)** de SOLID, pero DARC lo extiende hacia una idea más amplia: no se trata solo de evitar que una clase haga demasiado, sino de que cada pieza de software sea *atómica* en su propósito. Una función que calcula, persiste y notifica al mismo tiempo viola la Responsabilidad aunque esté en una sola clase. Una función de pocas líneas, con pocos parámetros y un nombre que describe exactamente lo que hace, la cumple.

Las consecuencias prácticas son concretas:

- Las funciones deben ser breves y enfocadas. Si necesitan explicación para entenderse, el nombre falló o la función hace demasiado.
- Los parámetros deben ser mínimos. Más de dos o tres parámetros suele ser una señal de que esos datos pertenecen a un objeto propio.
- El código debe poder testearse unitariamente con facilidad. Si para probar una función hay que preparar cinco dependencias, la responsabilidad está mal distribuida.

La Responsabilidad bien aplicada produce código predecible, fácil de leer y mantenible a largo plazo. Es el pilar que convierte la intención del Dominio en piezas de software que los desarrolladores —y las IAs que los asisten— pueden verificar, refactorizar y evolucionar con confianza.

---

### C — Conexión
*La transparencia en la interacción*

La Conexión describe cómo se comunican las distintas partes del sistema entre sí y con el mundo exterior. Una buena conexión es explícita, predecible y de bajo acoplamiento: cada componente sabe qué necesita de los demás, pero no cómo están implementados.

Este pilar sintetiza varios principios complementarios. De **SOLID** recoge la Inversión de Dependencias (DIP) y el Principio de Segregación de Interfaces (ISP): los módulos deben depender de abstracciones, no de implementaciones concretas, y las interfaces deben ser específicas y coherentes. De **CUPID**, recoge la idea de código *composable*: piezas que se integran naturalmente porque sus contratos son claros y sus efectos secundarios están controlados.

En la práctica, esto se traduce en el uso de interfaces bien definidas, inyección de dependencias, y APIs internas que comunican intención antes que detalle de implementación. Una conexión bien diseñada permite reemplazar un componente sin que el resto del sistema se entere: se respeta el contrato, se ignora el cómo.

La Conexión también gobierna la relación del sistema con el exterior: servicios externos, bases de datos, interfaces de usuario. Esas integraciones deben ser adaptadores que protegen el núcleo del sistema de los detalles y la volatilidad del mundo externo.

---

## Estructura del Modelo

Los cuatro pilares no son independientes: se organizan en dos pares funcionales.

**D + A forman la Arquitectura del sistema.** El Dominio establece qué es el sistema y cuáles son sus reglas. La Abstracción define cómo se organiza esa realidad en capas, módulos y fronteras. Juntos, responden a la pregunta de *qué construir y cómo estructurarlo*.

**R + C forman la Ingeniería del sistema.** La Responsabilidad define el propósito de cada pieza individual. La Conexión define cómo esas piezas se articulan para formar el todo. Juntos, responden a la pregunta de *cómo construir cada componente y cómo integrarlo*.

Esta distinción es relevante porque opera en niveles de abstracción diferentes: la Arquitectura (D+A) se decide antes de escribir código y define la estructura global; la Ingeniería (R+C) se aplica en cada decisión de implementación.

---

## DARC en el Contexto de las IAs

El Modelo DARC adquiere especial relevancia en el momento actual del desarrollo de software, donde los agentes de IA participan en la escritura, revisión y modificación de código. En este contexto, DARC no es solo un criterio de calidad: es el marco que permite al desarrollador delimitar, supervisar y evaluar el trabajo de la IA.

Un agente que conoce el Dominio del sistema no generará entidades ni lógicas ajenas al contexto del problema. Uno que comprende la Abstracción sabrá en qué capa debe residir cada tipo de código. La Responsabilidad garantiza que el código generado sea verificable y testeable de forma aislada. La Conexión asegura que las interfaces producidas sean coherentes con el resto del sistema.

En entornos de desarrollo agéntico, los pilares de DARC pueden formalizarse como instrucciones de contexto (por ejemplo, en un archivo `AGENTS.md`) que el agente consulta antes de actuar. En entornos más simples —un IDE estándar con asistencia de IA conversacional— DARC funciona como un criterio de revisión: la pregunta de si el código generado respeta el Dominio, separa incumbencias, tiene propósito único y conecta de forma explícita es suficiente para orientar la supervisión.

El objetivo final es que el desarrollador pueda leer, entender y validar el producto de la IA. Un sistema construido bajo DARC es, por definición, un sistema legible.

---

## Aplicación

**Antes de escribir código:** Definir el Dominio. Identificar las entidades, reglas y procesos del área de problema. Construir el vocabulario del sistema antes de elegir tecnologías.

**Al diseñar la estructura:** Aplicar la Abstracción. Decidir cómo se organizan las capas, qué conoce cada módulo de los demás, dónde residen las distintas responsabilidades.

**Al implementar cada componente:** Verificar la Responsabilidad. ¿Esta función tiene un único propósito? ¿Puede nombrarse con claridad? ¿Puede testearse de forma aislada?

**Al integrar componentes:** Diseñar la Conexión. ¿Las interfaces son explícitas? ¿Las dependencias son inyectadas, no hard-codeadas? ¿Reemplazar un componente requiere tocar a sus vecinos?

**Al revisar y refactorizar:** Usar DARC como criterio de evaluación. Si una pieza tiene más de una razón para cambiar, la Responsabilidad está comprometida. Si cambiar una tecnología afecta la lógica de negocio, la Abstracción está rota. Si el código no habla del dominio, el Dominio no es soberano.

---

## Conclusión

DARC es una filosofía de trabajo antes que un conjunto de reglas. Su propósito es que el software produzca sistemas que sean comprensibles para quienes los construyen, para quienes los heredan, y para las herramientas —humanas o artificiales— que los asisten. Un sistema DARC no es solo funcional: es legible, mantenible y honesto con el problema que resuelve.
