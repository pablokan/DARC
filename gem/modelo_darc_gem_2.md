# Modelo DARC: Un Marco de Integridad para la Construcción de Software en la Era de la IA
**Autor: Pablo Kaniefsky**

## 1. Introducción y Contexto
[cite_start]El **Modelo DARC** surge como una respuesta a la irrupción masiva de las Inteligencias Artificiales (IAs) en el flujo de trabajo del desarrollo de software[cite: 9]. [cite_start]En un escenario donde la IA asume gran parte de la escritura de código, el rol del profesional se desplaza hacia la definición estratégica, la delimitación de tareas y la supervisión crítica de los productos generados[cite: 21, 22].

[cite_start]DARC es un marco de integridad diseñado para evitar la deuda técnica y garantizar la escalabilidad y legibilidad, redefiniendo el perfil profesional desde el "hacer" hacia el "arquitectar y supervisar"[cite: 23, 24].

## 2. Antecedentes Teóricos
[cite_start]DARC no reinventa la rueda, sino que destila y simplifica aportaciones fundamentales de la ingeniería de sistemas[cite: 3, 15]:
* **SoC (Separation of Concerns):** Edsger Dijkstra (1974). [cite_start]El cimiento de la limpieza mental y técnica[cite: 5].
* **SOLID:** Robert Martin (2000). [cite_start]El estándar de la orientación a objetos, del cual DARC rescata la Responsabilidad Única y la Inversión de Dependencias[cite: 5].
* **DDD (Domain-Driven Design):** Eric Evans (2003). [cite_start]La soberanía del negocio sobre la tecnología[cite: 6].
* **CUPID:** Dan North (2022). [cite_start]Propiedades modernas que priorizan la "componibilidad" y el gozo del desarrollo[cite: 6, 8].

## 3. Estructura del Modelo: Los Dos Estratos
El modelo organiza las decisiones de diseño en dos estratos jerárquicos: la **Arquitectura** (el "Qué" y el "Porqué") y la **Ingeniería** (el "Cómo").

### I. Estrato de Arquitectura (Estratégico)
[cite_start]Se enfoca en las decisiones de alto nivel que delimitan el problema y la estructura de la solución[cite: 13].

#### D - Dominio / Datos (Centralidad de la Realidad)
[cite_start]Es el punto de partida absoluto: entender el sistema preexistente y el problema a resolver[cite: 13, 16].
* **El Problema:** Se define mediante una combinación de cuatro dimensiones de valor:
    1. **Dinero:** Eficiencia de costos.
    2. **Tiempo:** Agilidad de procesos.
    3. **Servicios:** Calidad de la experiencia.
    4. **Visibilidad (Observabilidad):** Eliminación de la ceguera institucional y gestión de la incertidumbre.
* [cite_start]**Foco:** En desarrollo de software, manda el Dominio; en ciencia de datos, mandan los Datos[cite: 16].

#### A - Abstracción / Arquitectura (Separación de Incumbencias)
[cite_start]Es el proceso de definir las capas y partes del sistema en función de las necesidades reales, evitando el sobre-diseño[cite: 13, 17].
* **Función:** Actúa como el filtro que protege al Dominio de la volatilidad técnica, asegurando que el diseño resuelva los *trade-offs* estructurales necesarios.

### II. Estrato de Ingeniería (Táctico)
[cite_start]Se ocupa de la construcción granular y la conexión de las piezas de software[cite: 14].

#### R - Responsabilidad Única
[cite_start]Se centra en la creación de piezas de propósito atómico[cite: 14, 18].
* **Principio:** Cada componente debe tener una única razón para existir y cambiar, destilando la esencia de SOLID y el estilo Unix (hacer una sola cosa y hacerla bien).

#### C - Conectividad
[cite_start]Define cómo interactúan las piezas entre sí y con el mundo exterior[cite: 14, 18].
* **Principio:** Basado en la componibilidad (CUPID), busca que las conexiones sean fluidas y desacopladas, facilitando el reemplazo o evolución de componentes individuales sin colapsar el todo.

## 4. El Nuevo Rol Profesional frente a la IA
[cite_start]El uso de IAs exige que el profesional se concentre en tareas que aseguren la integridad del producto final[cite: 22]:
* **Delimitación:** Definir los límites del trabajo que realizará la IA mediante un Dominio y una Abstracción claros.
* [cite_start]**Supervisión:** Utilizar DARC como criterio de evaluación para asegurar que el código generado sea legible, responsable y bien conectado[cite: 22, 24].
* [cite_start]**Mantenimiento:** Garantizar que la arquitectura soporte el crecimiento a largo plazo, mitigando la deuda técnica inherente a la generación automática de código[cite: 23, 24].
