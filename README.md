# Clean Vibe Coding
Curso: Clean Vibe Coding - De la Arquitectura al Código con IA

---

## Introducción del Curso

"Basta de Código Caótico: Bienvenido a Clean Vibe Coding"

> El Clean Vibe Coding no es magia, es una metodología. La velocidad de la IA es inútil sin una base sólida. En este curso, aprenderás a ser el arquitecto que guía a la IA para construir software robusto, escalable y de alta calidad. Olvídate del código espagueti generado por IA; vamos a construir y generar código con sentido para tu modelo de negocio.

---

## Módulo 1: El Fundamento - Importancia de una Arquitectura Limpia en los primeros pasos

*Capítulo 1: "No Escribas una Línea de Código sin un Plano"*

**Objetivo:** Entender que la arquitectura no es una ocurrencia tardía, sino el prerrequisito para que la IA sea efectiva.

### Temas a tratar:

1.  **La Importancia Crítica de la Arquitectura:**
    * ¿Por qué la IA falla en proyectos sin una estructura clara? (Falta de contexto, decisiones inconsistentes).
    * Demostración: Pide a la IA que añada una feature en un proyecto desordenado vs. uno bien estructurado.

2.  **Construyendo Nuestro Esqueleto desde Cero:**
    * **Proyecto práctico:** Iniciar un proyecto en **Spring Boot o Nest JS**.
    * Explicar la decisión de no usar generadores automáticos al principio para entender el "core" de la aplicación.

3.  **La Arquitectura Hexagonal y el "Vertical Slicing":**
    * **Teoría:** Explicar de forma sencilla qué es la Arquitectura Hexagonal (Puertos y Adaptadores) y por qué es ideal para aislar la lógica de negocio.
    * **Práctica:** Estructurar los paquetes y módulos del proyecto siguiendo este patrón. Introducir el concepto de "Vertical Slicing" para organizar las funcionalidades de forma cohesiva.

4.  **Nociones de DDD (Domain-Driven Design):**
    * Introducir conceptos básicos y prácticos: Entidades, Agregados, Repositorios. No es necesario profundizar en toda la teoría, solo lo esencial para que el código tenga sentido de negocio.

5.  **Configurando la Persistencia:**
    * Crear las interfaces de los repositorios en el dominio.
    * Implementar los adaptadores de persistencia para **PostgreSQL** y/o **MongoDB**.

---

## Módulo 2: Las Herramientas del Oficio - Tu Agente de IA

*Capítulo 2: "Elige tu Copiloto, No tu Piloto Automático"*

**Objetivo:** Desmitificar la elección de la herramienta y centrarse en la habilidad del desarrollador.

### Temas a tratar:

1.  **El Agente y el Modelo No Son lo Más Importante (Al Principio):**
    * Detalles que el factor clave es la calidad de las instrucciones (prompting) y el contexto (código y documentación), no si usas el modelo de LLM X o Y.
    * El refinamiento de LLMs es para optimización avanzada, no para empezar.

2.  **Análisis de las Herramientas Iniciales: Cursor vs. Junie:**
    * **Cursor:** Mostrar su interfaz. Destacar su velocidad y su naturaleza como un editor de texto "vitaminado".
    * **Junie:** Mostrar su integración directa en el IDE de JetBrains (IntelliJ, WebStorm). Explicar la ventaja de no tener que salir de tu entorno de trabajo.

3.  **Mi Recomendación y Por Qué:**
    * Explica tu experiencia personal: "En mi caso, Junie me ha resultado muy cómodo por su integración, y aunque antes era más lento, las últimas actualizaciones han reducido mucho la diferencia con Cursor, especialmente si aplicamos las técnicas de prompting que veremos".

---

## Módulo 3: El Mapa - Documentación que Guía a la IA

*Capítulo 3: "Escribe Documentación para tu IA como si Fuera un Junior Dev", aunque veremos que este junior está MUY VITAMINADO*

**Objetivo:** Crear una base de conocimiento que la IA pueda usar para entender la estructura y las reglas del proyecto.

### Temas a tratar:

1.  **El README.md como "Cerebro" del Proyecto:**
    * Generar un README principal que explique la arquitectura elegida, la estructura de los directorios y las decisiones clave.

2.  **Documentación Estructural con IA:**
    * Usar un agente de IA para generar borradores de la documentación. **Prompt de ejemplo:** *"Analiza esta estructura de directorios y genera una sección de README en formato Markdown que describa el propósito de cada módulo, siguiendo los principios de la Arquitectura Hexagonal."*

3.  **LA REGLA DE ORO: Revisión Humana Obligatoria:**
    * Enfatizar que la IA alucina. Es **CRUCIAL** revisar cada línea de la documentación generada y contrastarla con el código fuente real para asegurar que es precisa.

4.  **Nota sobre MCP (Multi-Code-Project) Servers:**
    * Mencionaré brevemente qué son y por qué no los recomiendo usar para esta fase inicial. "Son para proyectos maduros que ya tienen una base de código grande y bien establecida. Empezar con ellos es matar moscas a cañonazos".

---

## Módulo 4 y 5: La Conversación - El Arte y la Ciencia del Prompting

*Capítulo 4: "De Peticiones Vagas a Instrucciones de Precisión"*

**Objetivo:** Proporcionar un sistema de prompting que sea repetible, efectivo y fácil de adaptar.

### Temas a tratar:

1.  **Las Bases del Prompting para Código:**
    * Explicaciones sobre los componentes de un buen prompt: Contexto, Rol, Tarea, Reglas y el **Goal**.

2.  **La Plantilla Maestra de Prompting:**
    * Proporcionaré una guía o plantilla de prompt lista para copiar y pegar, donde el único elemento variable sea el "Goal".
    * **Ejemplo de plantilla:**
        ```
        # ROL: Eres un desarrollador experto en Spring Boot, Arquitectura Hexagonal y DDD.

        # CONTEXTO: Estoy trabajando en este proyecto con la siguiente estructura [...]. El código relevante es [...].

        # TAREA: Implementa la siguiente funcionalidad siguiendo las reglas establecidas.

        # REGLAS:
        - No modifiques la firma de los métodos existentes en las interfaces del dominio.
        - Coloca cada clase en su paquete correspondiente según la arquitectura.
        - Usa el logger para los mensajes de error.

        # GOAL:
        {Aquí es donde irá nuestro objetivo detallado}
        ```
    * **SPOIL: EL PROMPT QUE VEREMOS EN EL CURSO ESTÁ MÁS CURRADO**

3.  **Generando el "Goal" Perfecto con Ayuda de la IA:**
    * Este es el truco final. Enseñar a usar la IA para refinar una idea simple en un "Goal" detallado y sin ambigüedades.
    * **Prompt de ejemplo a mejorar para generar el Goal:** *"Tengo que implementar una funcionalidad para registrar un nuevo usuario. El usuario debe tener un email único y una contraseña encriptada. Genera un texto detallado para la sección 'GOAL' de mi prompt que incluya los pasos a seguir: crear la entidad, validar el email, encriptar la contraseña y guardar en el repositorio."*

4.  **Pruebas en Vivo:**
    * Usar la plantilla y el Goal generado para crear una nueva funcionalidad completa en el proyecto práctico, demostrando el poder del flujo de trabajo.
