# AI for Friends — Contenido en Español (Módulos 1 y 2)

Generado a partir de los 9 archivos HTML de Módulo 1 y Módulo 2 en `es/ai-for-friends/`. Incluye únicamente el contenido de cada página (títulos, texto, tablas, listas, callouts) — se omite la barra de navegación, el menú del curso, el pie de página y los scripts, ya que son iguales en todas las páginas.

## Índice

- [Módulo 1: Fundamentos de IA — AI for Friends](#mdulo-1-fundamentos-de-ia-ai-for-friends)
  - [Lección 1.1: Cómo Funcionan los Modelos de IA — AI for Friends](#leccin-11-cmo-funcionan-los-modelos-de-ia-ai-for-friends)
  - [Lección 1.2: Ingeniería de Prompts vs. Ingeniería de Contexto — AI for Friends](#leccin-12-ingeniera-de-prompts-vs-ingeniera-de-contexto-ai-for-friends)
  - [Lección 1.3: Técnicas Prácticas de Prompting — AI for Friends](#leccin-13-tcnicas-prcticas-de-prompting-ai-for-friends)
  - [Lección 1.4: Cómo Elegir el Modelo de IA Correcto — AI for Friends](#leccin-14-cmo-elegir-el-modelo-de-ia-correcto-ai-for-friends)
- [Módulo 2: Configura tu Computadora — AI for Friends](#mdulo-2-configura-tu-computadora-ai-for-friends)
  - [Lección 2.1: Instalando la Terminal de Windows — AI for Friends](#leccin-21-instalando-la-terminal-de-windows-ai-for-friends)
  - [Lección 2.2: Instalando Visual Studio Code — AI for Friends](#leccin-22-instalando-visual-studio-code-ai-for-friends)
  - [Lección 2.3: Navegando en la Terminal — AI for Friends](#leccin-23-navegando-en-la-terminal-ai-for-friends)


---

## Módulo 1: Fundamentos de IA — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-1/index.html`*

[← AI for Friends](../index.html) 01 OBLIGATORIO

# Fundamentos de IA

La fluidez en IA necesaria para usar Claude con confianza y precisión en
el trabajo diario — cómo procesan información los modelos de IA, cómo
escribir prompts que funcionen al primer intento, y qué modelo usar.

55–70 min 4 lecciones RR. HH. · Ingeniería Industrial · Legal ·
Marketing

Al terminar, podrás

- › Entender cómo funcionan los modelos de IA a nivel conceptual, sin
  código de por medio
- › Escribir prompts que produzcan resultados precisos y útiles al
  primer intento
- › Elegir el modelo de IA correcto para cada tarea según velocidad,
  costo y capacidad
- › Aplicar un hábito de validación a cada salida de IA antes de actuar
  sobre ella

Lecciones de este módulo

1.1

### Cómo Funcionan los Modelos de IA

Qué hace realmente la IA, los términos que verás a diario, y cómo
funciona el ciclo del agente.

10 min 1.2

### Ingeniería de Prompts vs. Ingeniería de Contexto

CÓMO le preguntas vs. QUÉ le das a la IA para trabajar, cinco patrones,
y la fórmula completa de un prompt.

15–20 min 1.3

### Técnicas Prácticas de Prompting

Cuatro técnicas fundamentales, el framework COSTARS, prompting estilo
entrevista, y hábitos de validación.

20–30 min 1.4

### Cómo Elegir el Modelo de IA Correcto

Haiku, Sonnet y Opus — una guía de selección según la tarea y
comparaciones reales de costo.

10 min

Conceptos Clave

Términos centrales presentados en este módulo. Se indica la lección
donde cada término se define por primera vez, para que puedas volver a
la explicación de origen.

| Término | Definido En | Significado en Lenguaje Sencillo |
|----|----|----|
| **Prompt** | Lección 1.1 | La instrucción o pregunta que le escribes a la IA. |
| **Ventana de Contexto** | Lección 1.1 | La memoria de trabajo de la IA. Cuánto texto puede contener y procesar a la vez. |
| **Token** | Lección 1.1 | Un fragmento de texto, aproximadamente tres cuartas partes de una palabra. Los modelos miden su capacidad en tokens. |
| **Agente** | Lección 1.1 | Un asistente de IA preconfigurado con instrucciones específicas y, a veces, conexiones en vivo con otras apps. |
| **Servidor MCP** | Lección 1.1 | Una conexión en vivo entre tu asistente de IA y otra app o sistema, como tu correo o un rastreador de proyectos. |
| **Base de Conocimiento** | Lección 1.1 | Una colección de documentos que le proporcionas a la IA. Los consulta para responder tus preguntas. |
| **Alucinación** | Lección 1.2 | Cuando la IA genera información falsa presentada como hecho — ocurre cuando le faltan datos reales y predice en su lugar. |

**Referencia completa de Conceptos Clave**

|  |  |  |
|----|----|----|
| **LLM** | Lección 1.1 | Modelo de Lenguaje Extenso. El nombre técnico para los modelos de IA que generan texto. |
| **Ciclo del Agente** | Lección 1.1 | El ciclo en el que un agente razona, selecciona herramientas, ejecuta acciones, y repite hasta completar la tarea. |
| **Ingeniería de Prompts** | Lección 1.2 | Estructurar CÓMO preguntas — la redacción, especificidad y formato de tu instrucción. |
| **Ingeniería de Contexto** | Lección 1.2 | Controlar QUÉ información le das a la IA para trabajar antes de que genere una respuesta. |
| **Zero-Shot Prompting** | Lecciones 1.2, 1.3 | Preguntar una sola vez con instrucciones claras y sin ejemplos. Funciona para tareas bien definidas. |
| **Few-Shot Prompting** | Lecciones 1.2, 1.3 | Proveer ejemplos del resultado deseado antes de pedirle a la IA que produzca uno nuevo. Mejora la consistencia. |
| **Role Prompting** | Lecciones 1.2, 1.3 | Asignarle a la IA una identidad (p. ej. "Eres un especialista de RR. HH.") para moldear su tono, vocabulario y prioridades. |
| **Chain-of-Thought** | Lecciones 1.2, 1.3 | Pedirle a la IA que razone paso a paso antes de dar una respuesta final. Reduce errores en tareas complejas. |
| **Prompting Estilo Entrevista** | Lección 1.3 | Pedirle a la IA que te entreviste para reunir contexto antes de producir un resultado. Útil para tareas complejas o poco claras. |
| **Meta Prompting** | Lección 1.3 | Pedirle a la IA que escriba un prompt por ti. Útil cuando conoces el objetivo pero no cómo formular la instrucción. |
| **COSTARS** | Lección 1.3 | Un framework para construir prompts complejos: Contexto, Objetivo, Estilo, Tono, Audiencia, Respuesta, Alcance. |
| **Claude (Haiku/Sonnet/Opus)** | Lección 1.4 | La familia de modelos de Anthropic, y tu opción predeterminada para casi todo. Haiku es rápido y económico. Sonnet es el equilibrio predeterminado. Opus maneja el razonamiento más complejo. |
| **Gemini** | Lección 1.4 | La familia de modelos de Google. La única excepción de nicho que vale la pena conocer: Gemini maneja video y audio de forma nativa, algo que ningún modelo de Claude hace. |

Recursos de Soporte

| Recurso | Enlace | Propósito |
|----|----|----|
| Claude | [claude.ai](https://claude.ai) | Regístrate y usa Claude en tu navegador |
| Documentación de Claude | [code.claude.com/docs](https://code.claude.com/docs) | Documentación oficial |
| Soporte de Claude | [support.claude.com](https://support.claude.com) | Centro de ayuda y soporte de cuenta |

A continuación

Módulo 2: Configura tu Computadora (opcional)

[Ver Módulo 2](../module-2/index.html)


---

## Lección 1.1: Cómo Funcionan los Modelos de IA — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-1/lesson-1.html`*

# Cómo Funcionan los Modelos de IA

Aprende qué hace realmente la IA, cómo actúan los agentes, y por qué las
instrucciones claras marcan toda la diferencia.

## 1. Qué Es Realmente un Modelo de IA

La IA no piensa. Predice patrones a una velocidad sobrehumana. Esa
distinción cambia cómo la usas — una vez que entiendes qué está pasando
realmente, puedes darle a la IA las entradas correctas para obtener las
salidas correctas. Elige la analogía de estas tres que más te haga
sentido, y tenla en mente durante todas las lecciones que siguen.

| Analogía | Qué Significa | Qué Te Dice |
|----|----|----|
| **El pasante muy leído** | Procesó miles de millones de documentos, pero predice texto en lugar de entenderlo | Instrucciones vagas producen resultados vagos |
| **El escritorio limitado** | La "ventana de contexto" es su memoria de trabajo — cuando se llena, la información más antigua se descarta | Pega solo lo que la IA necesita, no todo lo que tienes |
| **El ejecutor literal** | Sigue las instrucciones exactamente como están escritas; no infiere lo que quisiste decir | Sé específico — no llenará los vacíos como lo haría un colega |

> **La Idea Central:**
>
> La IA no piensa. Predice qué texto debería venir después según
> patrones. Tu trabajo es darle patrones claros con los cuales trabajar
> — la calidad de la salida es directamente proporcional a la calidad de
> la entrada.

> **La Regla de la Oración Única:**
>
> Si puedes decir exactamente lo que quieres en una sola oración
> específica, el resultado de tu IA será el doble de bueno. Los prompts
> vagos producen respuestas vagas.

## 2. Los Términos Que Debes Conocer

Verás estas palabras constantemente — en Claude, en este curso, y en
conversaciones sobre IA. No necesitas memorizarlas; necesitas
reconocerlas. Empieza por las cuatro marcadas abajo — las usarás todos
los días.

| Término | Qué Significa | Por Qué Te Importa |
|----|----|----|
| **Prompt \*** | La instrucción o pregunta que le escribes a la IA | La calidad de tu prompt determina la calidad de tu respuesta |
| **Ventana de contexto \*** | La memoria de trabajo de la IA — cuánto texto puede procesar en una conversación | Si pegas demasiado, olvida partes anteriores de la conversación |
| **Token** | Un fragmento de texto, aproximadamente tres cuartas partes de una palabra | Los archivos grandes consumen más tokens y pueden desbordar la ventana de contexto |
| **Modelo** | La IA específica con la que estás hablando | Distintos modelos tienen distinta velocidad, costo y capacidades |
| **LLM** | Modelo de lenguaje extenso — el nombre técnico para una IA como Claude | La tecnología que corre detrás de Claude y herramientas similares |
| **IA generativa** | IA que crea contenido nuevo en lugar de clasificar datos existentes | Claude es una herramienta de IA generativa |
| **Servidor MCP \*** | Una conexión en vivo entre tu asistente de IA y otro sistema | Permite que tu agente consulte datos reales en lugar de adivinar |
| **Agente \*** | Un asistente de IA preconfigurado con instrucciones y conexiones específicas | La pieza fundamental detrás de la mayoría de los flujos de trabajo reales con IA |
| **Base de conocimiento** | Una colección de documentos que la IA puede consultar para responder preguntas | Sube los procedimientos operativos estándar (SOP) de tu equipo para que la IA pueda responder con base en ellos |
| **RAG** | Generación aumentada por recuperación — primero busca documentos relevantes, luego responde | Así es como funcionan las bases de conocimiento por dentro |

> **No Es un Examen:**
>
> Esta tabla es una referencia, no algo para memorizar. Guarda esta
> lección en tus marcadores — los cuatro términos con asterisco aparecen
> en todas las lecciones que siguen.

## 3. Tres Etapas de Capacidad de la IA

No todas las herramientas de IA se comportan igual — hay un espectro que
va desde la generación simple de texto hasta sistemas multiagente
totalmente autónomos. Saber dónde se ubica una herramienta te dice qué
puedes pedirle que haga, y qué todavía tienes que hacer tú.

| Etapa 1: Asistente de IA | Etapa 2: Agente de IA | Etapa 3: Sistema de IA Agencial |
|----|----|----|
| Sigue reglas. Automatiza tareas simples. Tú das todo el contexto. | Logra objetivos. Maneja flujos de trabajo de varios pasos. Extrae datos en vivo de sistemas conectados. | Totalmente autónomo. Varios agentes especializados trabajan juntos y consolidan resultados. |
| *Ejemplo:* pega una transcripción en Claude y pídele que la resuma. Hace exactamente eso y se detiene. | *Ejemplo:* pídele a un agente que revise 40 currículums contra una descripción de puesto y clasifique a los mejores candidatos. Lee cada uno, compara, y devuelve una lista clasificada. | *Ejemplo:* un agente coordinador delega en agentes independientes de selección, programación y redacción, y luego entrega una sola actualización consolidada. |

> **Dónde Están las Herramientas Hoy:**
>
> Las etapas 1 y 2 están ampliamente disponibles hoy. Los sistemas
> multiagente de la etapa 3 todavía son incipientes y están surgiendo.
> Usa la etapa 1 para redacción simple, la etapa 2 cuando necesites
> datos en vivo — no construyas un agente complejo para una tarea que un
> solo prompt claro podría resolver.

## 4. Cómo Funcionan Realmente los Agentes

Cuando le envías un mensaje a un agente de IA, pasa más de lo que ves.
Razona, selecciona herramientas, consulta sistemas en vivo, y vuelve a
revisar su propio trabajo antes de responder. Este ciclo es lo que hace
poderosos a los agentes — y es cómo depuras una respuesta equivocada.

1.  **Escribes un prompt.** "¿Qué candidatos han estado en 'Entrevista
    Programada' por más de 10 días?"
2.  **El agente lo recibe** y lee sus propias instrucciones permanentes.
3.  **El agente invoca al modelo,** que razona sobre qué hacer a
    continuación.
4.  **El modelo selecciona una herramienta** — la fuente correcta y la
    consulta correcta.
5.  **La herramienta se ejecuta** contra datos en vivo y devuelve
    resultados.
6.  **El agente razona sobre los resultados,** repitiendo el ciclo si
    necesita más.
7.  **El agente devuelve la respuesta final** — una respuesta
    consolidada y fácil de leer.

**Solución de problemas: ¿qué pasa si el agente da una respuesta
equivocada?**

**El agente devuelve datos desactualizados o incorrectos.** Causa: una
herramienta conectada devolvió datos obsoletos, o el agente eligió la
incorrecta. Solución: pregunta "Explícame paso a paso cómo llegaste a
esa respuesta" — esto revela qué herramienta usó.

**El agente dice que no puede responder.** Causa: la conexión necesaria
no está habilitada, o no tienes permiso en ese sistema. Solución: revisa
primero la configuración de tu herramienta de IA para esa conexión.

## 5. Qué Significa Esto para tu Trabajo

Entender cómo funciona la IA cambia cómo la usas. Tres principios
separan a los usuarios efectivos de IA de los frustrados:

> **Los Tres Principios:**
>
> **1. Tú eres el piloto, no el pasajero.** La IA ejecuta. Tú diriges,
> validas y decides.\
> **2. La especificidad gana.** Campos nombrados, rangos de fechas y
> orden de clasificación producen resultados utilizables.\
> **3. La IA acelera el juicio. No lo reemplaza.** La decisión es tuya.

> **Empieza con una Tarea Real:**
>
> Abre Claude hoy y aplica el Principio 2 a algo que realmente
> necesites. La diferencia en la calidad del resultado será inmediata.

## Verificación

Puedes explicar qué es una ventana de contexto sin usar jerga técnica
Puedes nombrar los cuatro términos más importantes para el trabajo
diario: Prompt, Ventana de contexto, Agente, Servidor MCP

## Recursos Relacionados

- [claude.ai](https://claude.ai) — La plataforma
  de IA de Claude
- [Documentación de Claude](https://code.claude.com/docs) —
  Documentación oficial
- [Soporte de Claude](https://support.claude.com) —
  Centro de ayuda y solución de problemas

Lección completada

Ahora entiendes qué son los modelos de IA, cómo actúan los agentes
usando datos en vivo, y cómo aplicar esto para obtener mejores
resultados en tu trabajo.


---

## Lección 1.2: Ingeniería de Prompts vs. Ingeniería de Contexto — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-1/lesson-2.html`*

# Ingeniería de Prompts vs. Ingeniería de Contexto

Domina las dos palancas que determinan la calidad de las respuestas de
la IA — y aprende cuándo usar cada una.

## 1. La Distinción Central

Dos conceptos controlan la calidad de las respuestas de la IA. La
**ingeniería de prompts** controla cómo preguntas. La **ingeniería de
contexto** controla qué información le das a la IA para trabajar. La
mayoría de la gente dedica todo su tiempo a lo primero e ignora lo
segundo — pero lo segundo importa más.

| Dimensión | Ingeniería de Prompts | Ingeniería de Contexto |
|----|----|----|
| **Enfoque** | Texto orientado al usuario (cómo preguntas) | Datos orientados al sistema (qué proporcionas) |
| **Naturaleza** | Transitoria, de un solo turno | Persistente, gestionada como memoria |
| **Método** | Iteración por prueba y error | Pipelines deterministas y estructurados |
| **Entrada** | Una sola instrucción de texto | Un paquete de información organizado |
| **Analogía** | Escribir un asunto de correo claro | Adjuntar los documentos correctos al correo |

**Tres reglas para aplicar ambas:** antepón la información relevante en
lugar de pedirle al modelo que adivine desde cero; delimita el alcance
siendo explícito sobre qué fuentes son autoritativas; persiste y refina
reutilizando una conversación con contexto acumulado para una sola línea
de trabajo.

> **El Principio Clave:**
>
> Los buenos resultados dependen al menos tanto del contexto como de la
> redacción de un solo prompt. Deja de optimizar tu prompt. Empieza a
> optimizar tu contexto.

> **Diagnostica Antes de Corregir:**
>
> Cuando la IA da una respuesta incorrecta o débil, pregúntate "¿Le di
> la información correcta?" antes de "¿Formulé mi pregunta
> correctamente?". Los problemas de contexto causan la mayoría de las
> fallas de IA.

## 2. Mejores Prompts en la Práctica

Un prompt vago obliga a la IA a adivinar, y cada suposición introduce
error. La solución no es escribir mejor — es ser más específico.

### RR. HH.

    ❌ Antes: "Resume esto."

*Vago. ¿Para quién? ¿Qué tan largo? ¿Qué formato?*

    ✅ Después: "Resume esta transcripción de entrevista en 5 viñetas para el gerente de contratación. Enfócate en las fortalezas del candidato y cualquier preocupación planteada."

### Marketing

    ❌ Antes: "¿Qué está atrasado?"

*¿Atrasado respecto a qué? ¿Qué campaña?*

    ✅ Después: "¿Qué publicaciones de redes sociales de esta campaña de lanzamiento tienen más de 2 días de retraso respecto a su fecha programada? Muéstralo como tabla: plataforma, fecha programada, días de retraso. Ordena por días de retraso descendente."

**Más ejemplos — RR. HH., Ingeniería Industrial y Legal**

### RR. HH.

    ✅ "Escribe una descripción de puesto para un Gerente de Cuentas Senior en el equipo de éxito del cliente. Requisitos: 5+ años en gestión de cuentas B2B, experiencia con CRM, historial de retención de clientes. Usa nuestro formato estándar: resumen, responsabilidades, requisitos, beneficios. Tono: profesional pero cálido."

### Ingeniería Industrial

    ❌ Antes: "Revisa el reporte de tiempo muerto."

*¿Qué línea? ¿Qué turno? ¿Qué cuenta como tiempo muerto?*

    ✅ Después: "¿Qué líneas de producción en el reporte de tiempo muerto de esta semana superaron 30 minutos de tiempo muerto no planificado? Muéstralo como tabla: línea, fecha, duración, causa señalada. Ordena por duración descendente."

### Legal

    ✅ "Revisa este NDA en busca de cláusulas estándar faltantes. Verifica: definición de información confidencial, duración del acuerdo, devolución de materiales, ley aplicable. Enumera cada cláusula faltante o débil con una nota de una línea sobre el riesgo que genera."

> **La Regla de la Especificidad:**
>
> Cada palabra vaga en tu prompt obliga a una suposición. Un prompt con
> cinco elementos vagos tiene aproximadamente un 3% de probabilidad de
> producir exactamente lo que quieres. Cinco elementos específicos
> producen resultados precisos casi siempre.

## 3. Cinco Patrones de Prompting Que Cubren el 90% de tu Trabajo

No necesitas decenas de técnicas — cinco patrones cubren casi todo lo
que harás en Claude.

| Patrón | Qué Es | Cuándo Usarlo |
|----|----|----|
| **1. Zero-Shot** | Pregunta una vez con instrucciones claras, sin ejemplos | Tareas simples y bien definidas con un formato obvio |
| **2. Few-Shot** | Provee 1–3 ejemplos antes de pedirle al modelo que continúe el patrón | Transformar notas, clasificar elementos, formato consistente |
| **3. Role Prompting** | Asígnale explícitamente un rol a la IA para alinear tono y profundidad | Cuando necesitas un nivel de experiencia o estilo específico |
| **4. Chain-of-Thought** | Pídele al modelo que razone paso a paso antes de responder | Análisis, decisiones relevantes para la seguridad, tradeoffs complejos |
| **5. Estilo Entrevista** | Pídele al modelo que TE haga preguntas aclaratorias primero | Cuando no estás seguro de lo que necesitas, o la tarea es ambigua |

### Ejemplo del Patrón 2 (Few-Shot)

    Convierte estas notas sin procesar de nuestro retro de campaña en elementos de acción con formato:

    Entrada: "el tiempo de carga de la landing page afectó las conversiones, se necesita que desarrollo lo arregle antes del próximo lanzamiento"
    Salida: Elemento de Acción: Arreglar el tiempo de carga de la landing page antes del próximo lanzamiento. Responsable: [Tu Nombre]. Fuente: Retro de campaña. Fecha límite: Antes del próximo lanzamiento.

    Entrada: "las tasas de apertura de correo bajaron, los asuntos se sintieron genéricos"
    Salida: Elemento de Acción: Hacer pruebas A/B con asuntos de correo más específicos. Responsable: [Tu Nombre]. Fuente: Retro de campaña. Fecha límite: Próximo envío de correo.

    Ahora convierte esto:
    Entrada: "el gasto en redes pagadas se pasó del presupuesto, nadie estaba vigilando los topes diarios"

**Ejemplo del Patrón 4 — Chain-of-Thought**

    Necesito decidir si escalar la renovación de un contrato con un proveedor que vence en 30 días. Guíame por la decisión paso a paso:
    (1) ¿Cuál es la fecha de vencimiento actual?
    (2) ¿Cuándo debe tomarse la decisión de renovar?
    (3) ¿Cuál es el costo de renovar frente a cambiar de proveedor?
    (4) ¿Cuál es el riesgo de dejar que se renueve automáticamente?
    (5) Con base en estos factores, recomienda escalar o esperar.

**Ejemplo del Patrón 5 — Estilo Entrevista**

    Necesito escribir un caso de negocio para una nueva herramienta de onboarding de empleados.
    Antes de redactar nada, hazme 5 preguntas aclaratorias sobre el problema, la audiencia, el presupuesto y el cronograma.

> **Combina Patrones para Mejores Resultados:**
>
> Empieza con Role Prompting ("Eres un reclutador senior..."), agrega
> ejemplos Few-Shot, y luego solicita razonamiento Chain-of-Thought.
> Combinar patrones produce los resultados de mayor calidad.

## 4. Ingeniería de Contexto en la Práctica

Un modelo es tan inteligente como su contexto. Sin él, los sistemas de
IA alucinan — inventan hechos. El contexto bien diseñado corrige esto.

| Rol | Contexto Deficiente | Buen Contexto |
|----|----|----|
| **RR. HH.** | Pegar 40 currículums y preguntar "ayúdame a filtrarlos" | Pegar primero los requisitos del puesto, luego 3 currículums a la vez: "Califica cada uno del 1 al 5 en experiencia relevante, años, indicadores de liderazgo. Muéstralo como tabla." |
| **Ingeniería Industrial** | Pegar un mes completo de bitácoras de mantenimiento y preguntar "¿qué está mal con la línea?" | Extraer solo las entradas de esta semana: "¿Qué códigos de falla aparecen más de dos veces? Enumera código, frecuencia y línea afectada." |
| **Legal** | Pegar un acuerdo de fusión de 40 páginas y preguntar "¿hay riesgos?" | Extraer solo Indemnización y Terminación: "¿Qué cláusulas se desvían de nuestra plantilla estándar? Enumera número de cláusula, desviación, nivel de riesgo." |
| **Marketing** | Preguntar "¿cómo le fue a la campaña?" sin datos adjuntos | Pegar el CSV de la campaña filtrado a los últimos 30 días: "¿Qué canales tuvieron un desempeño inferior al CPA objetivo? Muestra canal, objetivo, real, diferencia." |

| Calidad del Contexto | Qué Sucede |
|----|----|
| **Sin contexto** | La IA adivina. Alta tasa de alucinación. El resultado es inútil. |
| **Contexto parcial** | La IA acierta en algunas cosas e inventa otras — peligroso porque parece verosímil. |
| **Contexto completo y estructurado** | La IA entrega respuestas precisas y fundamentadas. Alucinación mínima. |

> **El Contexto Parcial Es el Estado Más Peligroso:**
>
> Produce resultados que parecen correctos pero contienen detalles
> inventados. Siempre verifica la salida de la IA contra los datos
> fuente cuando sospeches que tu contexto estaba incompleto.

## 5. Gestiona tu Ventana de Contexto

Cada conversación tiene un límite. A medida que crece, la IA puede
olvidar instrucciones anteriores o mezclar tareas viejas y nuevas. Saber
cuándo continuar y cuándo empezar de cero es una habilidad diaria.

### Reutiliza la misma conversación cuando

- Es la misma línea de trabajo — el mismo documento, decisión o
  preparación de reunión
- Los turnos anteriores siguen siendo relevantes ("acordamos que riesgo
  alto significa X")
- La conversación aún no está saturada ni mezcla varios proyectos

### Empieza de cero cuando

- El tema realmente cambió
- El hilo es largo, desordenado y lleno de callejones sin salida
- La IA empieza a reutilizar suposiciones desactualizadas de hace 20
  turnos

### La técnica de resumir y reiniciar

Pregunta: *"Resume las decisiones clave y las restricciones de esta
conversación en 5 viñetas."* Copia ese resumen, inicia una nueva
conversación, y pégalo en un bloque de CONTEXTO al inicio de tu primer
prompt nuevo:

    CONTEXTO (de la conversación anterior):
    - Decisión 1: [viñeta generada por la IA]
    - Decisión 2: [viñeta generada por la IA]
    - Decisión 3: [viñeta generada por la IA]

    TAREA: [Tu nueva pregunta o solicitud]

> **Cuidado con la Señal de Contaminación:**
>
> Si la IA menciona algo de hace 20 turnos que ya no es relevante, tu
> ventana de contexto está contaminada. Empieza de cero y lleva contigo
> solo lo que importa.

## 6. Uniendo Todo

**Gran Resultado de IA = Prompt Claro + Contexto Correcto + Patrón
Apropiado.** Este es un prompt completo y listo para producción que
combina contexto, rol, tarea, formato y restricciones:

    CONTEXTO:
    [Pega aquí los datos relevantes — p. ej. la actualización de esta semana del sistema de seguimiento de candidatos]

    ROL:
    Eres un coordinador senior de RR. HH. escribiendo una actualización semanal del pipeline de contratación.

    TAREA:
    Con base en los datos del pipeline de arriba, redacta una actualización de estatus semanal para el gerente de contratación.

    FORMATO:
    - Agrupa por: Ofertas Extendidas, En Entrevista, Nuevos Candidatos, Estancados
    - Incluye nombre del candidato, puesto, y estatus de una línea para cada elemento
    - Agrega una sección de "Decisiones Necesarias" al final
    - Mantén la longitud total bajo 1 página

    RESTRICCIONES:
    - Solo incluye candidatos con actividad en los últimos 7 días
    - Marca a cualquiera estancado en una etapa por más de 10 días
    - No incluyas candidatos ya rechazados

| Sección | Qué Controla | Sin Ella |
|----|----|----|
| **CONTEXTO** | Los datos y la verdad base desde la cual razonar | La IA inventa hechos o da respuestas genéricas |
| **ROL** | Tono, profundidad, vocabulario, nivel de experiencia | La IA usa un estilo genérico por defecto |
| **TAREA** | La instrucción central y el entregable | La IA malinterpreta lo que quieres |
| **FORMATO** | Estructura, longitud, agrupación, diseño | La IA elige su propio formato — tienes que reformatear después |
| **RESTRICCIONES** | Qué excluir, marcar o seguir | La IA incluye contenido irrelevante, pasa por alto casos límite |

> **No Necesitas las Cinco Secciones Siempre:**
>
> Las tareas simples solo necesitan TAREA y FORMATO. Usa CONTEXTO, ROL y
> RESTRICCIONES cuando la tarea sea compleja, cuando la precisión
> importe, o cuando el resultado se vaya a compartir con otros.

## Verificación

Puedes explicar la diferencia entre ingeniería de prompts e ingeniería
de contexto en una sola oración Puedes nombrar al menos tres de los
cinco patrones de prompting y cuándo usar cada uno Conoces los tres
niveles de calidad de contexto y cuál produce alucinaciones convincentes
Sabes cuándo reutilizar una conversación y cuándo empezar de cero

## Recursos Relacionados

- [claude.ai](https://claude.ai) — Inicia una
  conversación y aplica estos patrones
- [Documentación de Claude](https://code.claude.com/docs) —
  Documentación oficial
- [Soporte de Claude](https://support.claude.com) —
  Artículos de ayuda y respuestas a preguntas frecuentes

Lección completada

Ahora conoces las dos palancas que controlan la calidad de las
respuestas de la IA, cinco patrones que cubren el 90% de tu trabajo, y
una fórmula para cualquier solicitud compleja.


---

## Lección 1.3: Técnicas Prácticas de Prompting — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-1/lesson-3.html`*

# Técnicas Prácticas de Prompting

Construye tu caja de herramientas diaria de IA — cuatro técnicas
fundamentales, un framework estructurado, y los hábitos de validación
que mantienen confiables tus resultados.

## 1. Cuatro Técnicas Fundamentales de Prompting

Cuatro técnicas cubren el 90% de lo que harás con Claude. Cada una
resuelve un problema distinto — saber cuál usar es la habilidad.

| Técnica | Qué Es | Cuándo Usarla |
|----|----|----|
| **Few-Shot** | Muestra 1–3 ejemplos de entrada/salida correctos; la IA imita el patrón | Extracción de datos, formato, clasificación — donde sea que necesites estructura consistente |
| **Role Prompting** | Asígnale a la IA un rol específico para moldear tono, vocabulario, profundidad | Cuando necesitas experiencia de dominio o un estilo apropiado para la audiencia |
| **Chain-of-Thought** | Pídele a la IA que razone paso a paso antes de la respuesta final | Análisis complejo, decisiones de varios factores, trabajo relevante para la seguridad |
| **Meta Prompting** | Pídele a la IA que escriba el prompt por ti | Cuando sabes lo que quieres pero no cómo pedirlo |

### Ejemplo de few-shot (RR. HH.)

    Necesito que extraigas información de candidatos a partir de notas de entrevista.

    Entrada de Ejemplo: "Hablé con María el martes. Tiene 8 años en gestión de operaciones. Buena comunicación. Quiere $145K. Disponible en 2 semanas."
    Salida de Ejemplo:
    | Campo | Valor |
    | Nombre | María |
    | Experiencia | 8 años, gestión de operaciones |
    | Fortalezas | Comunicación |
    | Salario | $145K |
    | Disponibilidad | 2 semanas |

    Ahora procesa esta entrada:
    "Llamé a James el viernes. 12 años en cadena de suministro, los últimos 4 liderando un equipo de logística. Busca un rango de $160K. Puede empezar el 1 de marzo. Gran pensamiento sistémico."

**Ejemplo de few-shot — Legal (riesgo de cláusulas contractuales)**

    Necesito que clasifiques cláusulas contractuales por nivel de riesgo.

    Entrada de Ejemplo: "Cualquiera de las partes puede terminar este acuerdo por cualquier motivo con 15 días de aviso por escrito."
    Salida de Ejemplo: RIESGO ALTO — La ventana corta de terminación por conveniencia genera inestabilidad de ingresos. Acción: Negociar a 90 días y agregar una cuota por terminación anticipada.

    Entrada de Ejemplo: "Este acuerdo se renueva automáticamente por periodos sucesivos de un año a menos que cualquiera de las partes dé aviso con 60 días de anticipación."
    Salida de Ejemplo: RIESGO MEDIO — La renovación automática es estándar, y 60 días de aviso es razonable. Acción: Agendar la fecha límite de aviso; no se necesita redline.

    Ahora clasifica esto:
    "La responsabilidad total del Proveedor bajo este acuerdo no excederá $10,000 en ninguna circunstancia, incluyendo negligencia grave."

**Ejemplo de few-shot — Ingeniería Industrial (clasificación de causas
de tiempo muerto)**

    Necesito que clasifiques eventos de tiempo muerto no planificado por categoría de causa raíz.

    Entrada de Ejemplo: "La Línea 3 se detuvo 45 min, el cambio de formato tardó más de lo estándar por falta de un accesorio."
    Salida de Ejemplo: DESPERDICIO DE PREPARACIÓN/CAMBIO — Causa raíz: accesorio no preparado con anticipación. Acción: preparar accesorios 15 minutos antes del cambio programado.

    Entrada de Ejemplo: "La Línea 1 estuvo 20 min parada, el sensor de la banda transportadora se desalineó de nuevo tras el último mantenimiento preventivo."
    Salida de Ejemplo: EQUIPO/MANTENIMIENTO — Causa raíz: alineación del sensor no verificada durante el mantenimiento preventivo. Acción: agregar verificación de alineación a la lista de mantenimiento preventivo.

    Ahora clasifica esto:
    "La Línea 2 estuvo inactiva 30 min esperando la entrega de un componente desde recepción."

### Role prompting por puesto

    RR. HH.: "Eres un reclutador senior con 10 años de experiencia contratando en roles técnicos y profesionales. Entiendes cómo distinguir habilidades transferibles de las específicas de un rol, y cómo escribir descripciones de puesto inclusivas y precisas. Comunícate en un lenguaje claro y amigable para el candidato."

    Ingeniería Industrial: "Eres un ingeniero industrial senior con 10 años de experiencia en optimización de procesos y Lean Six Sigma. Entiendes el takt time, el OEE, el análisis de causa raíz, y los ocho desperdicios. Comunícate en un lenguaje preciso y basado en datos, apropiado para las partes interesadas de operaciones."

    Legal: "Eres un abogado senior de contratos comerciales con 12 años de experiencia. Entiendes indemnización, límites de responsabilidad, derechos de terminación, y términos de renovación automática. Señala el riesgo con precisión, cita el lenguaje exacto en cuestión, y comunícate en inglés sencillo para una audiencia de negocios."

    Marketing: "Eres un gerente senior de marketing de marca con 10 años de experiencia en redes pagadas, correo electrónico y contenido. Entiendes segmentación de audiencia, métricas de campaña, y voz de marca consistente. Escribe de forma concisa y persuasiva para la audiencia de cada canal."

**Ejemplos de chain-of-thought — Legal y Marketing**

**Legal — escalar el incumplimiento de un proveedor:**

    Eres un abogado de contratos comerciales. Necesito decidir si escalar formalmente el incumplimiento de contrato de un proveedor.

    Piénsalo paso a paso:
    1. El contrato exigía entrega para el 15 de agosto. El proveedor entregó el 10 de septiembre.
    2. El retraso nos costó un estimado de $40,000 en compromisos posteriores incumplidos.
    3. El contrato incluye un periodo de subsanación de 30 días y una cláusula de daños liquidados de $500/día.
    4. Dependemos de este proveedor para otros dos proyectos activos.

    Recomienda: ¿enviar un aviso formal de incumplimiento ahora, o abrir primero una resolución informal? Muestra tu razonamiento.

**Marketing — asignar un presupuesto publicitario limitado:**

    Tengo un conflicto de calendario. Dos campañas necesitan el mismo presupuesto publicitario limitado esta semana, y solo puedo financiar una por completo.

    Campaña A: Lanzamiento de producto, fecha límite estricta el viernes, ligada a un anuncio de prensa que no se puede mover.
    Campaña B: Promoción de temporada, fecha límite estricta el domingo, históricamente nuestro correo de mayor ingreso del trimestre.

    Piénsalo paso a paso: ¿Qué campaña recibe el presupuesto? ¿Qué hago con la otra? ¿Qué debo comunicarle a mi director?

**Meta prompting — pídele a la IA que escriba tu prompt**

Úsalo cuando sepas QUÉ quieres pero no CÓMO pedirlo:

    Eres un experto en escribir prompts de IA.
    Necesito un prompt que haga [describe tu objetivo].
    El resultado debe [describe el formato/estructura].
    La audiencia es [describe quién lo leerá].
    Escribe ese prompt por mí.

Ejemplo:

    Eres un experto en escribir prompts de IA.
    Necesito un prompt que haga que una IA extraiga elementos de acción de notas de reunión y los formatee como una lista de verificación con responsables y fechas límite.
    El resultado debe ser una tabla en markdown.
    La audiencia es mi líder de equipo, que necesita revisar rápidamente los compromisos.
    Escribe ese prompt por mí.

No hay penalización por pedirle a la IA que te ayude a hablar con la IA
— úsalo con confianza.

> **Combina Técnicas para Mejores Resultados:**
>
> Empieza cada prompt complejo con Role Prompting para sentar las bases.
> Agrega ejemplos Few-Shot para el formato. Agrega Chain-of-Thought para
> el análisis.

## 2. El Framework COSTARS

Cuando una tarea es compleja y multidimensional, una sola oración no
basta. COSTARS te da una estructura de siete componentes que elimina las
suposiciones en cada dimensión de un prompt.

| Letra | Componente | Qué Controla |
|----|----|----|
| **C** | Contexto | Trasfondo — quién eres, la situación, qué ha pasado hasta ahora |
| **O** | Objetivo | Lo que quieres que la IA logre |
| **S** | Estilo | Cómo se lee el resultado: profesional, técnico, basado en datos |
| **T** | Tono | El registro emocional: confiado, empático, urgente |
| **A** | Audiencia | Quién lo leerá — tu director, un nuevo empleado, un cliente |
| **R** | Respuesta | Formato: tabla, viñetas, borrador de correo, lista numerada |
| **S** | Alcance | Lo que la IA NO debe hacer — límites, exclusiones, supuestos |

### El prompt de Lanzamiento de IA (copia y completa)

    Contexto: Soy miembro del equipo de [nombre del equipo], enfocado en [áreas clave de tu responsabilidad individual], y me gustaría identificar formas concretas en que la IA puede ayudar a reducir o eliminar tareas mundanas o repetitivas en mi flujo de trabajo, manteniéndome en el asiento estratégico del conductor como validador y dueño de todos los resultados.

    Objetivo: Eres un consultor de clase mundial en transformación con IA y mejora de procesos, especializado en ayudar a profesionales de distintas industrias a usar la IA como su socio de pensamiento. Identifica 2-3 oportunidades concretas donde la IA pueda amplificar mis capacidades mientras mantengo total propiedad estratégica.

    Estilo: Profesional y técnico, respaldado por ejemplos e indicadores de datos reales de la industria.

    Tono: Confiado y pragmático, abordando tanto oportunidades como desafíos de implementación.

    Audiencia: Mi gerente y las partes interesadas clave, que necesitan entender tanto las capacidades técnicas que voy a aprovechar, el retorno de inversión práctico, y cómo mantendré la propiedad y supervisión de mi trabajo.

    Respuesta: Provee una tabla con una lista priorizada de oportunidades concretas donde la IA pueda amplificar mis capacidades. Para cada una: 1) cómo se ve el apoyo de la IA (entradas, salidas, mi rol de validación), 2) cómo esto cambia mi trabajo y el ahorro de tiempo semanal estimado, 3) un consejo práctico para evitar errores comunes, 4) un primer paso recomendado inmediato, 5) qué seguiría siendo completamente mío.

    Alcance: Enfócate en mi rol específico. No recomiendes herramientas que requieran instalación de TI o acceso de administrador. Mantén los ejemplos anclados en mi trabajo profesional del día a día.

**Reemplaza antes de enviar:** `[nombre del equipo]` — p. ej.
"Marketing" o "Legal" — y
`[áreas clave de tu responsabilidad individual]` — p. ej. "gestionar
campañas de marca" o "revisar contratos con proveedores".

> **Este Es tu Lanzamiento de IA:**
>
> Ejecuta este prompt con los detalles de tu propio rol — produce una
> hoja de ruta personalizada de adopción de IA en menos de 2 minutos.
> Guarda el resultado.

## 3. Prompting Estilo Entrevista para Tareas Exploratorias

A veces no sabes exactamente qué necesitas. El prompting estilo
entrevista invierte la dinámica: en lugar de redactar el prompt
perfecto, le pides a la IA que te entreviste.

    Eres un consultor experimentado en transformación con IA, especializado en ayudar a profesionales de distintas industrias a identificar problemas que pueden resolver usando IA. Tienes experiencia profunda en colaboración humano-IA, mejora de procesos, y en entender dónde la IA aporta un valor enorme frente a dónde el juicio humano sigue siendo crítico.

    Soy un [TU ROL Y EQUIPO] buscando identificar formas concretas en que la IA puede ayudar a reducir o eliminar tareas mundanas o repetitivas, manteniéndome en el asiento estratégico del conductor como validador y dueño de todos los resultados.

    Ayúdame con una evaluación haciéndome preguntas específicas sobre mi trabajo. Empieza haciendo hasta tres preguntas enfocadas (una a la vez) sobre mis roles, responsabilidades y puntos de dolor. Luego haz hasta tres más sobre trabajo repetitivo, sobrecarga de información, y dónde desearía tener mejores conocimientos.

    Mi objetivo: identificar 2-3 oportunidades concretas donde la IA pueda amplificar mis capacidades mientras mantengo total propiedad estratégica. Una vez que tengas mis respuestas, produce una tabla con: 1) cómo se vería el apoyo de la IA, 2) ahorro de tiempo, 3) un consejo práctico, 4) un primer paso inmediato, 5) qué seguiría siendo completamente mío.

| Dimensión | Prompt COSTARS | Prompt Estilo Entrevista |
|----|----|----|
| **Esfuerzo inicial** | Alto — tú completas todos los detalles | Bajo — la IA te pregunta a ti |
| **Velocidad** | Rápido — un prompt, una respuesta | Más lento — conversación de 5–10 min |
| **Profundidad** | Buena, según lo que proporcionaste | Excelente — saca a la luz lo que no se te ocurrió mencionar |
| **Ideal para** | Tareas donde sabes exactamente qué necesitas | Tareas exploratorias donde aún estás definiendo el problema |

> **Empieza Aquí Si Es tu Primera Sesión:**
>
> El prompting estilo entrevista requiere menos esfuerzo inicial y
> produce resultados más personalizados. Ejecútalo antes del prompt
> COSTARS si no estás seguro de qué pedir.

## 4. Hábitos de Validación Responsable

La IA es poderosa, no infalible — genera texto que suena confiado
incluso cuando está equivocado. Cada resultado requiere validación
humana antes de convertirse en una decisión, una comunicación, o un
entregable.

| Hábito | Qué Significa | Cómo Aplicarlo |
|----|----|----|
| **1. Verificación de Fuente** | ¿De dónde salió esto? ¿Puedes verificarlo? | ¿Puedes rastrearlo a un sistema fuente o dato verificado? Si no, trátalo como no verificado. |
| **2. Escaneo de Plausibilidad** | ¿Algo contradice lo que ya sabes? | Lee con tu experiencia de dominio activa — investiga cualquier cosa que se sienta rara. |
| **3. Autocrítica** | Haz que la IA cuestione su propio resultado | Pregunta "Enumera 3 formas en que esto podría estar equivocado o incompleto." |
| **4. Etiqueta Borradores** | Marca el estatus del resultado de IA antes de compartirlo | Siempre etiqueta "borrador", "necesita revisión", o "solo para lluvia de ideas". |
| **5. Descompón Tareas Riesgosas** | Divide el trabajo de alto riesgo en subtareas seguras | Usa Claude para resumir o generar opciones; los humanos son dueños de las conclusiones. |
| **6. Escala Casos Límite** | Sabe cuándo detenerte y preguntarle a un experto humano | ¿No estás seguro sobre cumplimiento o implicaciones legales? Pregúntale a tu gerente. |

### Autocrítica en la práctica

    Tú: "Enumera 3 formas en que este análisis podría estar equivocado o incompleto."

    Claude: "1. Clasifiqué a los candidatos solo por años de experiencia. Las habilidades relevantes y el alcance reciente del rol pueden importar más que la antigüedad bruta.
    2. Asumí que cada currículum enumeraba toda la experiencia relevante. Algunos candidatos subestiman roles anteriores, así que puedo haber subestimado su idoneidad.
    3. No consideré las certificaciones requeridas por la descripción del puesto, que podrían descalificar a un candidato mejor clasificado."

| Seguro para IA | Mantén Solo Humano |
|----|----|
| Resumir notas de reunión | Tomar decisiones de contratación o despido |
| Redactar correos (revisas antes de enviar) | Aprobar procedimientos críticos de seguridad |
| Dar formato a datos en tablas | Hacer representaciones legalmente vinculantes |
| Generar opciones para tu consideración | Comprometerse a fechas límite en nombre de tu equipo |
| Extraer elementos de acción de transcripciones | Finalizar decisiones de riesgo de marca o legal |
| Clasificar y priorizar según criterios que tú definas | Aprobar determinaciones de cumplimiento |

> **La Validación Parcial No Es Validación:**
>
> "Se ve bien" no es un método de validación. Aplica la Verificación de
> Fuente y el Escaneo de Plausibilidad a cada resultado de IA antes de
> compartirlo.

## 5. Tu Plan de Acción

Las técnicas solo se vuelven habilidades a través de la práctica.

| Situación | Usa Esto | Por Qué |
|----|----|----|
| Sabes lo que quieres y el formato es claro | Zero-Shot + COSTARS | Ejecución rápida y de un solo intento con cobertura completa |
| Necesitas formato consistente entre elementos | Few-Shot | La coincidencia de patrones elimina la variación |
| Necesitas experiencia de dominio o un tono específico | Role Prompting | Define vocabulario, profundidad, prioridades |
| Una decisión compleja con varios factores | Chain-of-Thought | Obliga a un razonamiento visible y auditable |
| No estás seguro de lo que necesitas | Estilo Entrevista | La IA reúne contexto mediante preguntas |
| Sabes el objetivo pero no cómo formularlo | Meta Prompting | La IA escribe el prompt por ti |

**Para el viernes:** ejecuta hoy el prompt COSTARS del Paso 2, el prompt
Estilo Entrevista del Paso 3 mañana, y luego elige la única oportunidad
de mayor valor de cualquiera de los dos resultados y dedícale 15 minutos
con Claude.

> **Construye tu Biblioteca de Prompts:**
>
> Guarda los resultados y los prompts que los generaron. En un mes
> tendrás una biblioteca personal que cubre tu trabajo más común.

## Verificación

Puedes nombrar las cuatro técnicas fundamentales y cuándo usar cada una
Puedes explicar qué representa cada letra en COSTARS Puedes aplicar la
autocrítica y nombrar al menos tres hábitos de validación

## Recursos Relacionados

- [claude.ai](https://claude.ai) — Ejecuta cada
  prompt de esta lección
- [Documentación de Claude](https://code.claude.com/docs) —
  Documentación oficial del producto y sus funciones
- [Soporte de Claude](https://support.claude.com) —
  Centro de ayuda y soporte de cuenta

Lección completada

Cuatro técnicas, un framework, un método exploratorio, y seis hábitos de
validación — todo lo que necesitas para usar Claude efectivamente desde
hoy.


---

## Lección 1.4: Cómo Elegir el Modelo de IA Correcto — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-1/lesson-4.html`*

# Cómo Elegir el Modelo de IA Correcto

Claude te da acceso a varios modelos. Aprende cuál usar, cuándo cambiar,
y cómo obtener el mejor resultado sin gastar de más.

## 1. Por Qué Existen Varios Modelos

Piensa en los modelos de IA como contrataciones para distintos roles —
no le asignarías a un director senior responder correos rutinarios, ni
le pedirías a un becario que desarrolle tu estrategia de programa. Cada
modelo está optimizado para un balance distinto de inteligencia,
velocidad y costo, y esas dimensiones compiten entre sí.

> **La Regla de Oro:**
>
> Usa el modelo más pequeño y económico que pueda hacer bien el trabajo.
> Sube de nivel solo cuando la tarea lo exija — esta sola regla puede
> reducir tus costos de IA a la mitad.

## 2. La Familia de Modelos

Claude viene en tres modelos — Haiku, Sonnet y Opus. Comparten las
mismas fortalezas (escritura, análisis, razonamiento, instrucciones de
varias partes) y difieren solo en el balance de velocidad, inteligencia
y costo.

| Modelo | Ideal Para | Especificaciones Clave |
|----|----|----|
| **Claude Haiku 4.5** | Preguntas rápidas, formato de datos, clasificación simple, tareas repetitivas en volumen | El más rápido. El de menor costo. |
| **Claude Sonnet 4.5** | Reportes, análisis de datos, resúmenes de reunión, redacción de correos, la mayoría del trabajo diario | Velocidad y calidad balanceadas. Tu opción predeterminada. |
| **Claude Opus 4.7** | Estrategia compleja, análisis profundo de varios pasos, entregables importantes | El razonamiento más profundo. Más lento. Premium. |

Claude no procesa video ni audio de forma nativa, y no genera imágenes.
Para esas tareas de nicho, una herramienta especializada de otro
proveedor es la opción correcta — no necesitas aprenderlas a fondo, solo
saber que existen.

| Tarea | Herramienta a Usar |
|----|----|
| Analizar una grabación de video o audio | Google Gemini (video/audio nativo) |
| Generar una imagen a partir de texto | Un modelo de imagen dedicado (p. ej. GPT Image 1 Mini) |
| Transcribir audio a texto solamente | Un modelo de transcripción dedicado (p. ej. Whisper) |

> **Video y Audio Son la Excepción Principal:**
>
> ¿Necesitas resumir una sesión de capacitación o reunión grabada?
> Claude no puede procesar video o audio directamente. Google Gemini
> maneja ambos de forma nativa y es la mejor opción para esa tarea
> específica.

> **Ante la Duda, Empieza con Sonnet:**
>
> Sonnet es tu opción predeterminada para el 80% de las tareas. Cambia a
> Haiku para tareas simples, a Opus para razonamiento de alto riesgo.

## 3. Elegir Según la Tarea

La forma más rápida de elegir un modelo es hacer coincidir tu tarea con
una categoría.

| Tu Tarea | Usa Este Modelo | Por Qué |
|----|----|----|
| Consulta rápida o pregunta corta | Haiku 4.5 | Rápido y económico, no requiere razonamiento |
| Reformatear datos en una tabla | Haiku 4.5 | Coincidencia de patrones — Haiku lo maneja perfectamente |
| Resumir notas de reunión (1–2 páginas) | Sonnet 4.5 | Calidad y velocidad equilibradas |
| Redactar un correo a tu director | Sonnet 4.5 | Buen control de tono, sigue instrucciones complejas |
| Analizar una hoja de cálculo o reporte | Sonnet 4.5 | Fuerte capacidad analítica a costo moderado |
| Análisis de decisión compleja con varios factores | Opus 4.7 | Requiere razonamiento profundo, vale la pena el costo premium |
| Procesar un documento muy extenso (300+ páginas) | Sonnet 4.5 | Su amplia ventana de contexto lo maneja en una sola pasada |
| Procesar una grabación de video o audio | Google Gemini | Claude no lee video ni audio |

**Tabla de referencia completa por tarea**

|  |  |  |
|----|----|----|
| Escribir una evaluación de desempeño | Sonnet 4.5 | Escritura matizada con buena estructura |
| Escribir un caso de negocio o documento de estrategia | Opus 4.7 | Necesita coherencia sostenida en resultados largos |
| Analizar imágenes, capturas de pantalla, diagramas | Sonnet 4.5 | Maneja imágenes y texto en conjunto |
| Extraer datos de muchos documentos cortos | Haiku 4.5 | Rápido y económico para extracción repetitiva |
| Transcribir audio a texto solamente | Una herramienta de transcripción dedicada | Diseñada específicamente para audio a texto |
| Generar una imagen a partir de texto | Una herramienta de imagen dedicada | Diseñada específicamente para generación de imágenes |

### El flujo de decisión de cinco preguntas

    1. ¿La tarea es simple y está bien definida? (formato, consulta, clasificación)
       -> Usa Haiku 4.5

    2. ¿Es trabajo de conocimiento estándar? (escritura, resumen, redacción)
       -> Usa Sonnet 4.5 — TU OPCIÓN PREDETERMINADA

    3. ¿La tarea requiere razonamiento profundo? (estrategia, decisiones complejas)
       -> Usa Opus 4.7

    4. ¿La tarea involucra video o audio?
       -> Análisis de video/audio: Google Gemini
       -> Solo transcripción: una herramienta de transcripción dedicada

    5. ¿La tarea involucra generar imágenes?
       -> Usa una herramienta de imagen dedicada

> **El 80% de las Tareas Caen en Sonnet:**
>
> Si no puedes responder claramente sí a la pregunta 1 o 3–5, usa
> Sonnet. Es la elección correcta para la gran mayoría del trabajo de
> conocimiento diario.

## 4. Velocidad, Costo y Errores Comunes

| Modelo | Costo Relativo | Mejor Valor Para |
|----|----|----|
| **Haiku 4.5** | 1x (referencia) | Tareas simples, repetitivas, de alto volumen |
| **Sonnet 4.5** | ~3x Haiku | Trabajo de conocimiento diario estándar (tu opción predeterminada) |
| **Opus 4.7** | ~5x Haiku | Solo razonamiento de alto riesgo |

    1 token = ¾ de palabra (unos 4 caracteres)
    1 página = 500 tokens
    10 páginas = 5,000 tokens
    Transcripción de 1 hora de reunión = 10,000–20,000 tokens
    1M tokens = 750,000 palabras = 1,500 páginas

### Haz esto

- Empieza con Sonnet para todo; cambia solo con una razón específica
- Baja a Haiku para tareas repetitivas — aproximadamente 3x más
  económico, igual de preciso
- Recurre a Gemini solo cuando necesites video o audio
- Revisa tu selector de modelo con regularidad — Anthropic lanza nuevos
  modelos periódicamente

### Evita esto

- Usar Opus para preguntas simples — 5x el costo, sin mejora notable de
  calidad
- Pasar un documento muy largo por Haiku — su ventana de contexto más
  pequeña puede truncarlo
- Asumir que el modelo más pesado siempre es el mejor
- Ejecutar todo con un solo modelo por costumbre

> **Haiku Tiene una Ventana de Contexto Más Pequeña:**
>
> Para un documento muy largo (más de unas 30 páginas), usa Sonnet para
> evitar truncar tu contenido.

## Verificación

Puedes nombrar las tres dimensiones que diferencian a los modelos de IA:
inteligencia, velocidad, costo Sabes qué modelo de Claude usar para
tareas simples, trabajo estándar, y razonamiento complejo Sabes qué
modelo usar para contenido de video y audio Puedes aplicar el flujo de
decisión de cinco preguntas a cualquier tarea nueva en menos de 10
segundos

## Recursos Relacionados

- [claude.ai](https://claude.ai) — Abre el
  selector de modelo para ver los modelos disponibles en tu plan
- [docs.claude.com/docs](https://docs.claude.com/docs) —
  Documentación oficial
- [support.claude.com](https://support.claude.com) —
  Centro de ayuda y soporte de cuenta

Módulo 1 completado

Ahora entiendes cómo funcionan los modelos de IA, cómo darles buenas
instrucciones, y cómo elegir el correcto para cualquier tarea. Abre
claude.ai, configura Sonnet como tu opción predeterminada, y ejecuta tu
próxima tarea real a través del flujo de decisión.


---

## Módulo 2: Configura tu Computadora — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-2/index.html`*

[← AI for Friends](../index.html) 02 CALENTAMIENTO OPCIONAL

# Configura tu Computadora

Un espacio de práctica para cualquiera que nunca haya abierto una
terminal o un editor de código. Nada aquí es un requisito previo para el
Módulo 3 — si una terminal y VS Code ya te resultan familiares, ve
directamente ahí.

25 min 3 lecciones Windows y Mac RR. HH. · Ingeniería Industrial · Legal
· Marketing

> **Este Módulo Completo Es Opcional:**
>
> El Módulo 3 cubre todo lo que necesitas, incluida la terminal, y no
> depende de nada de esto. Si te sientes cómodo saltando directo a la
> guía de instalación del Módulo 3, sáltate este módulo por completo.

Lecciones de este módulo

2.1

### Instalando la Terminal de Windows

Una terminal independiente de Microsoft Store, con PowerShell
configurado como su opción predeterminada. Solo para Windows — Mac ya
trae Terminal integrada.

5 min 2.2

### Instalando Visual Studio Code

Descarga, instala, y encuentra el panel de Extensions — un vistazo más
ligero y anticipado a la configuración del Módulo 3.

5 min 2.3

### Navegando en la Terminal

Cuatro comandos, un ejercicio de práctica, y la única lección que vale
la pena si solo haces una.

15 min

Conceptos Clave

Términos centrales introducidos a lo largo de las tres lecciones de este
módulo. Se indica la lección donde aparece cada término por primera vez
para que puedas volver a la explicación original.

| Término | Definido En | Significado en Lenguaje Sencillo |
|----|----|----|
| **Terminal** | Lección 2.1 | Una ventana donde escribes comandos de texto para tu computadora en lugar de hacer clic. |
| **PowerShell** | Lección 2.1 | El lenguaje de comandos de Windows, usado en todos los pasos de Windows de este módulo. La "PS" en el prompt significa PowerShell. (La Terminal integrada de Mac usa zsh en su lugar — no necesita instalación aparte.) |
| **Perfil Predeterminado** | Lección 2.1 | El shell que una terminal abre por defecto. En Windows, este módulo lo configura como PowerShell. |
| **VS Code** | Lección 2.2 | Visual Studio Code, el editor de texto gratuito de Microsoft que este curso usa para ver y editar archivos. |
| **Extensión** | Lección 2.2 | Un complemento que le da a VS Code nuevas capacidades. El Módulo 3 te dice cuáles instalar. |
| **pwd** | Lección 2.3 | Print working directory. Muestra en qué carpeta estás actualmente. |
| **cd** | Lección 2.3 | Change directory. Te mueve dentro de una carpeta, o un nivel hacia arriba con cd ... |

**Referencia completa de Conceptos Clave**

|  |  |  |
|----|----|----|
| **Microsoft Store** | Lección 2.1 | La tienda oficial de aplicaciones de Windows. El lugar seguro para instalar la Terminal de Windows. (No hace falta equivalente en Mac — Terminal.app viene preinstalada.) |
| **Terminal de Windows** | Lección 2.1 | Una aplicación de terminal independiente que abres por su cuenta, separada de cualquier editor. Solo para Windows. |
| **Terminal Integrada** | Lección 2.1 | La terminal integrada en VS Code, que se abre con Ctrl + acento grave (el mismo atajo en Mac). La opción predeterminada del Módulo 3, en ambas plataformas. |
| **Prompt** | Lección 2.1 | El texto donde escribes, por ejemplo PS C:\Users\YourName\> en Windows o yourname@Mac ~ % en Mac. Espera hasta que presiones Enter. |
| **Atajo de Extensions** | Lección 2.2 | Ctrl + Shift + X en Windows, Cmd + Shift + X en Mac — abre el panel de Extensions en VS Code. |
| **ls** | Lección 2.3 | List. Muestra todos los archivos y carpetas en tu ubicación actual. Idéntico en Windows (Git Bash/PowerShell) y en la Terminal de Mac. |
| **mkdir** | Lección 2.3 | Make directory. Crea una nueva carpeta donde estás actualmente. Idéntico en Windows y Mac. |
| **Carpeta de Inicio** | Lección 2.3 | Tu carpeta personal de nivel superior, a la que llegas con cd ~ en ambas plataformas — C:\Users\YourName en Windows, /Users/yourname en Mac. |

Recursos de Soporte

| Recurso | Enlace | Propósito |
|----|----|----|
| Claude | [claude.ai](https://claude.ai) | Regístrate y usa Claude en tu navegador |
| Documentación de Claude | [docs.claude.com/docs](https://docs.claude.com/docs) | Documentación oficial |
| Soporte de Claude | [support.claude.com](https://support.claude.com) | Centro de ayuda y soporte de cuenta |

A continuación

Módulo 3: Claude Code — IA en tus Propios Archivos

[Ver el Módulo 3](../module-3/index.html)


---

## Lección 2.1: Instalando la Terminal de Windows — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-2/lesson-1.html`*

# Instalando la Terminal de Windows

Una aplicación de terminal independiente, instalada desde Microsoft
Store, con PowerShell configurado como su opción predeterminada.

5 MIN OPCIONAL SOLO WINDOWS ¿Tienes Mac? Sáltate Esta Lección

Esta lección es solo para Windows. Mac viene con Terminal.app ya
instalada — no hay nada que instalar aquí. Ve directamente a la
[Lección 2.2](lesson-2.html).

Opcional

El Módulo 3 usa en su lugar la terminal integrada en VS Code, así que
esta instalación no es necesaria para nada más adelante en el curso. Haz
esto solo si también te gustaría tener una terminal independiente fuera
de VS Code.

## 1. Instala la Terminal de Windows

La Terminal de Windows es la propia aplicación de terminal con pestañas
de Microsoft — una ventana independiente que abres por su cuenta,
separada de cualquier editor. Viene directamente de Microsoft Store, el
lugar seguro y oficial para instalarla.

1.  Abre **Microsoft Store** desde el menú Inicio.
2.  Busca **"Windows Terminal."**
3.  Haz clic en **Install**, y ábrela una vez que termine la
    instalación.
4.  Verás una ventana con pestañas y un **prompt** de comandos — el
    texto PS C:\Users\YourName\> donde escribes. Espera hasta que
    presiones Enter.

## 2. Configura PowerShell como el Perfil Predeterminado

La Terminal de Windows puede abrir varios shells distintos. Este curso
usa PowerShell en todo momento, así que configúralo como el **perfil
predeterminado** — el shell que la terminal abre automáticamente.

1.  Haz clic en la pequeña flecha desplegable junto al botón **+**
    (nueva pestaña).
2.  Selecciona **Settings.**
3.  En **Startup**, configura **Default profile** en **Windows
    PowerShell.**
4.  Cierra Settings y abre una nueva pestaña para confirmar — debería
    abrir directamente en un prompt de PowerShell.

> **La "PS" en el Prompt:**
>
> Una vez que PowerShell sea tu opción predeterminada, cada pestaña
> nueva comenzará con PS en el prompt. Esa es tu confirmación de que
> quedó bien configurado.

## Verificación

La Terminal de Windows está instalada y abre sin problemas Una nueva
pestaña abre directamente en un prompt de PowerShell (comienza con "PS")

## Recursos Relacionados

- [claude.ai](https://claude.ai) — Regístrate y
  usa Claude en tu navegador
- [Documentación de Claude](https://docs.claude.com/docs) —
  Documentación oficial
- [Soporte de Claude](https://support.claude.com) —
  Centro de ayuda y soporte de cuenta

Lección completada

Tienes una terminal independiente instalada y configurada con PowerShell
— una cosa menos desconocida cuando llegues a la guía de instalación del
Módulo 3.


---

## Lección 2.2: Instalando Visual Studio Code — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-2/lesson-2.html`*

# Instalando Visual Studio Code

Un repaso más ligero y anticipado de una instalación que el Módulo 3
cubre a fondo — para que la guía real te resulte familiar cuando llegues
ahí.

5 MIN OPCIONAL El Módulo 3 Cubre Esto a Fondo

El Módulo 3 recorre esta instalación con más detalle. Este es un vistazo
más ligero y anticipado — sáltatelo si prefieres hacerlo una sola vez,
bien hecho, en el Módulo 3.

## 1. Descarga e Instala VS Code

VS Code viene directamente del sitio oficial de Microsoft. Descargas un
instalador, lo ejecutas, y aceptas las opciones predeterminadas — no hay
nada que configurar en esta etapa.

### Windows

1.  Ve a code.visualstudio.com.
2.  Haz clic en el botón de descarga para Windows.
3.  Ejecuta el instalador y acepta todas las opciones predeterminadas.
4.  Abre Visual Studio Code una vez que termine.

### Mac

1.  Ve a code.visualstudio.com.
2.  Haz clic en el botón de descarga para Mac.
3.  Abre el archivo descargado y arrastra **Visual Studio Code** a tu
    carpeta **Applications**.
4.  Ábrela desde Applications (o Spotlight — Cmd + Space, y luego
    escribe "Visual Studio Code"). La primera vez, macOS podría pedirte
    que confirmes que confías en ella — haz clic en **Open**.

<!-- -->

    +-----------------------------------------+
    | (icons) | Welcome                       |
    | []      |                               |
    | *       | Start                         |
    | v       | New File...                   |
    | |>      | Open Folder...                |
    | []      |                               |
    |         | (empty editor area)           |
    +-----------------------------------------+

Una ventana con una pestaña Welcome, una fila de íconos en la barra
lateral izquierda, y un área de editor vacía en el medio — idéntica en
Windows y Mac.

> **Solo el Sitio Oficial:**
>
> Descarga únicamente desde code.visualstudio.com — no desde un sitio de
> descargas de terceros. El instalador oficial es seguro y gratuito.

> **Las Opciones Predeterminadas Están Bien Aquí:**
>
> No necesitas cambiar ninguna opción del instalador. Avanza con las
> opciones predeterminadas. El Módulo 3 cubre más adelante cualquier
> configuración que importe.

## 2. Encuentra el Panel de Extensions

Las extensiones son complementos que le dan a VS Code nuevas
capacidades. No instales ninguna todavía — el objetivo aquí es solo
encontrar el panel para que te resulte familiar en el Módulo 3.

1.  Busca en la barra lateral izquierda el ícono de **Extensions**
    (cuatro cuadrados).
2.  Haz clic en él, o presiona Ctrl + Shift + X (Windows) / Cmd +
    Shift + X (Mac) para abrir el panel.
3.  Escribe un nombre en el cuadro de búsqueda para ver cómo aparecen
    los resultados.
4.  Explora la lista. No hagas clic en Install en nada todavía.

> **No Instales Nada Todavía:**
>
> El Módulo 3 te dice exactamente qué extensiones agregar. Instalarlas
> ahora, fuera de orden, solo genera confusión — por ahora solo observa.

## Verificación

VS Code abre sin problemas en la pestaña Welcome Puedes abrir el panel
de Extensions y buscar en él

> **Déjalo Instalado:**
>
> Mantén VS Code instalado después de esta lección. El Módulo 3 retoma
> justo donde lo dejaste e instala las extensiones que realmente
> necesitas.

## Recursos Relacionados

- [claude.ai](https://claude.ai) — La plataforma
  de IA de Claude
- [Documentación de Claude](https://code.claude.com/docs) —
  Documentación oficial
- [Soporte de Claude](https://support.claude.com) —
  Centro de ayuda y solución de problemas

Lección completada

Tienes VS Code instalado y sabes dónde vive el panel de Extensions — las
dos cosas que hacen que la configuración del editor en el Módulo 3 te
resulte familiar.


---

## Lección 2.3: Navegando en la Terminal — AI for Friends

*Archivo fuente: `es/ai-for-friends/module-2/lesson-3.html`*

# Navegando en la Terminal

Cuatro comandos. Esa es toda la habilidad — y la verdadera razón por la
que existe este módulo.

~10 MIN HAZ ESTA LECCIÓN La Única Lección que Vale la Pena Hacer

Si solo vas a hacer una lección de este módulo opcional, que sea esta.
El Módulo 3 asume que puedes escribir un comando y leer el resultado.

## 1. Aprende los Cuatro Comandos

Una terminal es simplemente un lugar donde escribes instrucciones para
tu computadora. Solo necesitas cuatro comandos para moverte y ver qué
hay ahí — todo lo demás en el Módulo 3 se construye sobre estos. Léelos
una vez antes de escribir nada.

| Comando | Qué Hace | Ejemplo |
|----|----|----|
| pwd | Muestra en qué carpeta estás actualmente | Escribe pwd, presiona Enter |
| ls | Muestra todos los archivos y carpetas en tu ubicación actual | Escribe ls, presiona Enter |
| cd NombreDeCarpeta | Te mueve DENTRO de una carpeta | cd Documents |
| cd .. | Te mueve HACIA ARRIBA un nivel de carpeta | cd .. |

> **Igual en Mac:**
>
> Estos cuatro comandos funcionan igual en la aplicación Terminal
> integrada de Mac — sin cambios necesarios. Cada ejemplo de abajo usa
> la misma sintaxis en Windows y Mac.

> **Nada se Ejecuta Hasta que Presionas Enter:**
>
> Escribir un comando no hace nada por sí solo — la terminal espera a
> que presiones Enter. Siempre puedes corregir un error de escritura
> antes de ejecutarlo, y un error de escritura solo produce un mensaje
> de error. No puedes romper nada de esta manera.

## 2. Realiza el Ejercicio de Práctica

Ahora te toca escribir. Esto te mueve a tu carpeta de inicio, crea una
carpeta de práctica con dos subcarpetas, y las lista. Escribe una línea,
presiona Enter, lee el resultado, y luego pasa a la siguiente.

    cd ~
    pwd
    mkdir ai-practice
    cd ai-practice
    mkdir shared
    mkdir candidate-review
    ls

## 3. Confirma lo que Construiste

Leer el resultado te confirma que cada comando funcionó. Esto es lo que
hizo cada línea:

| Comando                | Qué Hizo                                       |
|------------------------|------------------------------------------------|
| cd ~                   | Te movió a tu carpeta de inicio                |
| pwd                    | Te mostró dónde estás                          |
| mkdir ai-practice      | Creó una nueva carpeta llamada "ai-practice"   |
| cd ai-practice         | Te movió dentro de esa carpeta                 |
| mkdir shared           | Creó una subcarpeta llamada "shared"           |
| mkdir candidate-review | Creó una subcarpeta llamada "candidate-review" |
| ls                     | Te mostró las carpetas que acabas de crear     |

Ahora tienes esta estructura bajo tu carpeta de inicio:

    ai-practice/
    ├── shared/
    └── candidate-review/

> **Verifica con el Explorador de Archivos:**
>
> Abre File Explorer (Finder en Mac), ve a tu carpeta de inicio, y busca
> ai-practice. Ver las mismas carpetas que creaste en la terminal
> confirma que los comandos hicieron exactamente lo que escribiste.

> **Esa es Toda la Habilidad:**
>
> Esto es todo lo que necesitas. Cuando llegues al Módulo 3, escribir
> comandos en una terminal ya te resultará rutinario.

## Verificación

Puedes decir en qué carpeta estás usando pwd ls lista shared y
candidate-review dentro de ai-practice Puedes moverte dentro de una
carpeta y volver un nivel hacia arriba sin mirar la tabla

> **Practica una Vez Más:**
>
> Abre una terminal, ejecuta pwd y ls, luego usa cd para entrar a una
> carpeta y sal con cd ... Repetir este ciclo una vez más fija la
> memoria muscular antes del Módulo 3.

## Recursos Relacionados

- [claude.ai](https://claude.ai) — La plataforma
  de IA de Claude
- [Documentación de Claude](https://code.claude.com/docs) —
  Documentación oficial
- [Soporte de Claude](https://support.claude.com) —
  Centro de ayuda y solución de problemas

Módulo 2 completado

Escribir comandos en una terminal y explorar un editor ya te resultará
rutinario cuando llegues al Módulo 3 — la configuración real comienza
ahí.
