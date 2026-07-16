
# Hermes Agent recibió una actualización masiva. _Ahora dirige mis cinco negocios._

PT

Prajwal Tomar · @PrajwalTomar_ · publicado el 26 de junio

Contexto del autor

Prajwal dirige cinco operaciones al mismo tiempo: una agencia de MVPs (**@ignytlabs**) con $20K MRR, una comunidad de más de 3,500 builders (**@aimvpbuilders**), un estudio de apps móviles, llamadas de consultoría uno a uno, y una cuenta de Instagram de 50K+ seguidores con contenido patrocinado.

Hace unas semanas escribió un análisis completo de Hermes Agent, el primer agente de IA en el que confió para trabajar en segundo plano en lugar de solo responder preguntas. Este artículo es sobre lo que cambió la semana pasada, cuando Nous Research lanzó una actualización mayor que convirtió a Hermes de "herramienta que estaba probando" a "lo que ahora dirige una parte real de mi día" en sus cinco negocios.

Si no conoces Hermes — repaso rápido

La mayoría de los agentes que usas hoy funcionan por sesión: abres Claude Code o Cursor, le das una tarea, cierras la pestaña, y a la mañana siguiente olvidó todo sobre ti y tu trabajo.

Hermes funciona al revés. Vive en un servidor, corre todo el día, recuerda cada conversación y escribe sus propios archivos de habilidades ("skills") sobre la marcha. Mientras más tiempo lo usas, menos tienes que explicarte.

## Lo que cambió con esta actualización

Ocho cambios concretos, organizados como los vería el propio Prajwal: cada uno con su nivel de madurez.

hermes connect --imessageEstable

### Ahora vive en tu iMessage

Este es el cambio que más modificó su rutina diaria. Hermes ahora se conecta de forma nativa a iMessage, gratis, y aparece en la misma app donde le escribe a su equipo y a su familia. Sin dashboard, sin app aparte: simplemente le escribe como a una persona.

Su flujo: iMessage para tareas rápidas cuando está fuera de su escritorio, la app de escritorio cuando está enfocado trabajando. Mismo agente, misma memoria.

- Ejecutar hermes photon setup --phone +1... en la terminal
- Aprobar el inicio de sesión del dispositivo en el navegador
- Recibir el número que se usará para escribirle al agente

La opción más simple es **Photon** (línea de iMessage gestionada, sin necesidad de tener una Mac encendida). También existe la alternativa **BlueBubbles** si prefieres usar tu propia Mac.

hermes config --background-agents=onEstable · núcleo

### Los agentes en segundo plano vienen activados por defecto

El cambio más importante, aunque el menos vistoso. Al darle una tarea compleja, Hermes crea sub-agentes y trabaja en segundo plano: no te quedas viendo un spinner, puedes seguir hablándole de otra cosa mientras el trabajo pesado ocurre por detrás.

El cuello de botella dejó de ser "cuánto tengo que esperar" y se convirtió en "cuántas tareas puedo correr antes de perder el hilo".

Para su agencia, esto marca la diferencia entre un asistente y un empleado real: alguien que no congela la conversación cada vez que le delegas algo.

hermes desktop --openEstable

### La app de escritorio ahora se siente como un cockpit

- Chats que se pueden desprender en ventanas propias, para vigilar un agente mientras trabajas en otro
- Selector de modelo reubicado donde realmente se usa
- Panel en vivo de sub-agentes: ves exactamente qué está haciendo cada uno en tiempo real
- Terminal integrada, sin tener que alternar con una ventana aparte

El panel de sub-agentes en vivo es el que mantiene abierto todo el día: ver el trabajo real en lugar de adivinar es lo que le da la confianza para alejarse y tomar una llamada de consultoría.

hermes dashboard → profiles → newEstable

### Crear nuevos "perfiles" toma dos minutos

Un perfil es esencialmente un agente independiente que corre junto a los demás, con su propia memoria y sus propias habilidades. Antes era tedioso de configurar; ahora se arma desde el navegador en minutos. Así es como reparte el trabajo de sus cinco negocios:

- **Chief of staff** — conoce las prioridades de los cinco negocios y arma el resumen matutino
- **Agencia** — investigación de clientes y primeros borradores de especificaciones para los MVPs
- **Contenido** — artículos en X, tweets y guiones para los posts patrocinados de Instagram
- **Comunidad** — monitorea qué pregunta la comunidad y detecta temas recurrentes

Su recomendación: correr al menos dos perfiles aunque solo necesites uno, por redundancia. Un perfil solo es un punto único de falla; dos se cubren entre sí.

hermes skills hub --browseEstable

### Llegó un Skills Hub

Hermes ya escribía sus propias habilidades mientras trabajaba, pero hasta ahora no había forma fácil de tomar habilidades que otros ya habían construido. El nuevo Skills Hub vive en el dashboard y permite explorar e instalar habilidades populares con un clic.

Antes, cada perfil nuevo arrancaba desde cero y tardaba semanas en formar una librería útil. Ahora se puede sembrar un perfil nuevo con habilidades ya probadas desde el primer día.

hermes self-improve --statusEstable

### Mejora notablemente más rápido a sí mismo

El bucle de auto-mejora se volvió más inteligente: el agente ahora escribe y actualiza sus propias habilidades de forma mucho más agresiva mientras trabaja, y las ediciones a su propia memoria son de mejor calidad.

La mayoría de las herramientas de IA son exactamente igual de buenas en el día 90 que en el día 1. Esta se supone que mejora de forma medible, porque ha estado escribiendo su propio manual todo el tiempo.

hermes mcp install unreal-engine@5.8Experimental

### Ahora puede construir juegos en Unreal Engine

Hermes ahora tiene un MCP para Unreal Engine 5.8, el motor de juegos más potente que existe. Con el MCP instalado, el agente puede construir juegos 3D complejos directamente.

El propio autor es honesto: no va a lanzar un estudio de videojuegos la próxima semana, y para la mayoría esto es más una demostración que una herramienta de uso diario. Pero es una señal de hacia dónde se expande la superficie de MCPs de Hermes: hacia software profesional serio, no solo herramientas web pequeñas.

hermes connect --telegramEstable

### Telegram también se puso más inteligente

Hermes ahora envía mensajes con formato enriquecido en Telegram a través de la Bot API 10.1, con tablas y maquetado limpio en lugar de un muro de texto plano.

Su división actual: iMessage para prompts rápidos en movimiento, Telegram para trabajo más profundo donde quiere que la salida del agente sea realmente legible.

## Lo que esto cambia en la forma de operarlo

Cuando escribió el primer análisis, Hermes era un agente potente que dirigía desde su máquina. Después de esta actualización, es un agente al que accede desde cualquier lugar, que trabaja en segundo plano por defecto, que opera como un pequeño equipo de perfiles en lugar de uno solo, y que mejora en su propio trabajo mientras duerme.

**No es una herramienta nueva. Es la misma herramienta, ya madura.** Y la configuración completa sigue tomando unos 30 minutos.

## Qué vigilar

⚠ Costo de tokens

Que los agentes en segundo plano vengan activados por defecto es excelente, hasta que olvidas que consumen tokens reales. Cada sub-agente que se crea es gasto real. Vigílalo la primera semana antes de que la cuenta te sorprenda.

⚠ No sobre-construyas perfiles

Corre al menos dos perfiles, pero no construyas diez el primer día. Cada uno necesita un trabajo real; los perfiles vacíos solo saturan el dashboard y confunden tu propio flujo.

⚠ Navegador y control de computadora, apagados por defecto

Siguen desactivados por seguridad, y deberían seguir así hasta que un perfil específico realmente los necesite. No le des a cada agente de tu stack las llaves de todo en lo que estás conectado.

⚠ El MCP de Unreal aún es temprano

Es impresionante, pero trátalo como experimento, no como pipeline de producción, hasta que lo veas sostenerse en algo real.

## Lo que esto realmente significa

La brecha entre los agentes basados en sesión y los agentes persistentes se hizo más amplia. La mayoría de los builders sigue viviendo enteramente en el mundo de "abrir pestaña, hacer tarea, cerrar pestaña". Está bien para programar enfocado, pero hay una segunda mitad del stack que corre todo el día, recuerda todo, te responde por mensaje y mejora solo — y casi nadie la tiene configurada todavía.

Para Prajwal, esto vive en el carril de "empleados de IA": una parte real del trabajo de construcción, investigación, borradores, pulso de la comunidad y primeros borradores de contenido patrocinado ya se mueve hacia estos perfiles. Los que configuren esto este año van a verse injustamente adelantados el próximo: dejan de pagar el impuesto diario de re-explicarle contexto a una herramienta que los olvida cada mañana.

"La actualización ya está disponible. La configuración toma 30 minutos. El efecto compuesto es permanente."SOMOS MUY TEMPRANEROS EN ESTO

resumen.txt

Conexión nativa a iMessage: le escribes a tu agente como a una persona, desde el celular.

Agentes en segundo plano activados por defecto: delegas tareas complejas y sigues conversando mientras trabajan.

App de escritorio con panel de sub-agentes en vivo, terminal integrada y chats desprendibles. Se siente un control room.

Crear perfiles toma dos minutos desde el navegador. Un perfil por negocio: chief of staff, agencia, contenido, comunidad.

Skills Hub para explorar e instalar habilidades probadas: perfiles útiles en días, no semanas.

El bucle de auto-mejora escribe y actualiza sus propias habilidades de forma más agresiva.

Nuevo MCP para construir juegos en Unreal Engine 5.8 — señal de hacia dónde va la superficie de integraciones.

Telegram con formato enriquecido (tablas, maquetado limpio) vía Bot API 10.1.