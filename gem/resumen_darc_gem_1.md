# Resumen Ejecutivo: Modelo DARC

El **Modelo DARC** es una metodología de diseño sistémico que organiza la creación de software en cuatro pilares fundamentales, divididos en dos áreas de competencia profesional:

## 🏛️ ARQUITECTURA (Estratégico: El "Qué")
* **D - Dominio:** El centro de todo. Es entender el sistema manual preexistente y resolver problemas de **Dinero, Tiempo, Servicio u Observabilidad**. El código debe reflejar el lenguaje real del negocio (Lenguaje Ubicuo).
* **A - Abstracción:** El diseño del mapa. Es separar los conceptos de la tecnología. Decide qué se oculta y qué se muestra para que el sistema sea fácil de entender y costoso de romper.

## 🛠️ INGENIERÍA (Táctico: El "Cómo")
* **R - Responsabilidad:** La calidad de la pieza. Cada función o módulo debe hacer una sola cosa y hacerla bien (Single Responsibility). Es el núcleo de la lógica interna.
* **C - Conexión:** El ensamble. Es cómo las piezas se hablan entre sí y con el exterior (Bases de datos, Web, APIs) sin quedar "pegadas" (Bajo acoplamiento).

---

### ¿Para qué sirve DARC?
1. **Evitar la sobreingeniería:** Solo se construye lo que el Dominio necesita.
2. **Priorizar el Valor:** Ataca directamente los dolores de la organización (ej. falta de visibilidad o pérdida de tiempo).
3. **Optimizar el uso de IA:** Proporciona el contexto necesario para que las IAs generen código útil y organizado, no "código espagueti".

**En resumen:** DARC nos enseña a pensar el problema (**Dominio**), diseñar el plano (**Abstracción**), pulir la pieza (**Responsabilidad**) y asegurar el encastre (**Conexión**).