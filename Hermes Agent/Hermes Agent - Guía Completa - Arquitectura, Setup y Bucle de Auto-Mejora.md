---
tipo: articulo
tema: Hermes Agent
titulo: "Hermes Agent FULL GUIDE: Architecture, Setup, and the Self-Improving Loop"
autor: SCOTTY BEAM (@ScottyBeamIO)
fuente: https://x.com/ScottyBeamIO/status/2066885278451519590
publicado: 2026-06-16
guardado: 2026-07-16
vistas: 843.5K
verificado_con: https://hermes-agent.nousresearch.com/docs
tags: [hermes-agent, ia, agentes, arquitectura, self-improving]
---

# Hermes Agent — Guía Completa: Arquitectura, Setup y el Bucle de Auto-Mejora

> [!info] Nota sobre esta ficha
> El artículo original de X ("Article" largo de @ScottyBeamIO) requiere iniciar sesión para leerse completo. Esta nota reconstruye y **verifica** sus temas centrales —arquitectura, setup y el bucle de auto-mejora— contra la **documentación oficial** de Hermes Agent, para que el contenido sea preciso y no solo un extracto.

## De qué trata

Está surgiendo una nueva categoría de herramientas de IA: **agentes que no viven en una ventana de chat que abres y cierras**, sino que corren de forma continua en la nube y te hablan a través de un mensajero (como Telegram, iMessage, etc.). Hermes Agent, de **Nous Research**, es el ejemplo central: un agente autónomo *terminal-native* con **memoria persistente**, **habilidades que él mismo crea** y un **gateway de mensajería** en 21+ plataformas.

---

## 1. Arquitectura

Hermes se organiza en capas. De arriba hacia abajo:

| Capa | Qué hace |
|------|----------|
| **Entry Points** | CLI, Gateway (mensajería), ACP, Batch Runner, API Server, librería de Python |
| **AIAgent** (`run_agent.py`) | El núcleo. Coordina todo el ciclo del agente |
| **Prompt Builder** | Construye el prompt, con compresión y caché de contexto |
| **Provider Resolution** | Resuelve el proveedor y opera en 3 modos de API: `chat_completions`, `codex_responses`, `anthropic` |
| **Tool Dispatch** | Despacha llamadas a herramientas — 70+ tools organizadas en 28 toolsets |

Puntos clave:
- **Multi-backend de ejecución**: local, Docker, SSH, Daytona, Modal o Singularity.
- **Multi-proveedor de modelos**: Nous Portal, OpenRouter, OpenAI, Anthropic, Google o cualquier endpoint compatible con OpenAI.
- El **gateway** arranca, autoriza usuarios, enruta sesiones y entrega mensajes en cada plataforma.

---

## 2. Setup (instalación)

Instalación en una línea (Linux, macOS, WSL2, Termux/Android):

```bash
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
```

Flujo típico después de instalar:
1. Configurar proveedor y modelo (`hermes config …`).
2. Conectar un canal de mensajería (Telegram, iMessage, Discord, Slack, WhatsApp…).
3. Empezar a chatear — el agente recuerda de una sesión a otra.

> [!tip] Perfiles
> Cada **perfil** es un agente independiente con su propia memoria, habilidades, cron y plugins. Útil para separar negocios o contextos (ej. uno para inventario, otro para contenido).

---

## 3. El Bucle de Auto-Mejora (Self-Improving Loop)

Esto es lo que distingue a Hermes de un chatbot normal. Tres piezas trabajan juntas:

### 🧠 Memoria persistente
Dos archivos, inyectados en el system prompt al inicio de cada sesión:

| Archivo | Propósito | Límite |
|---------|-----------|--------|
| `MEMORY.md` | Notas del agente: entorno, convenciones, aprendizajes | 2,200 chars |
| `USER.md` | Perfil del usuario: preferencias, estilo, expectativas | 1,375 chars |

Los límites mantienen la memoria **enfocada**: si una escritura excede el tope, el agente consolida o borra entradas para hacer espacio. No hay auto-compactado silencioso.

### 📚 Habilidades (Skills)
- Documentos de conocimiento **bajo demanda** con *progressive disclosure* (se cargan solo cuando se necesitan → ahorran tokens).
- Viven en `~/.hermes/skills/`.
- El agente **escribe y actualiza sus propias skills** mientras trabaja.
- Hay un **Skills Hub** para instalar habilidades ya probadas por la comunidad.
- Compatible con el estándar abierto `agentskills.io`.

### 🔁 Persistent Goals (`/goal`) — el "loop" propiamente dicho
Le das un objetivo permanente y Hermes **sigue trabajando turno tras turno solo**, sin que tengas que decirle "continúa". Un modelo juez revisa después de cada turno si el objetivo se cumplió; si no, se auto-alimenta un prompt de continuación hasta lograrlo (o hasta agotar el presupuesto de turnos). Es la versión de Hermes del *Ralph loop*.

Ejemplos de uso:
- "Arregla todos los errores de lint en `src/` y verifica que `ruff check` pase"
- "Porta la feature X del repo Y, con pruebas, y deja el CI en verde"

---

## Por qué importa

> La mayoría de las herramientas de IA son **igual de buenas en el día 90 que en el día 1**. Hermes se supone que **mejora de forma medible**, porque ha estado escribiendo su propio manual todo el tiempo.

La brecha entre agentes *basados en sesión* (abrir pestaña → tarea → cerrar) y agentes *persistentes* (corren todo el día, recuerdan todo, te responden por mensaje y mejoran solos) se hace cada vez más amplia.

---

## Enlaces relacionados

- [[Hermes Agent Actualización]] — el otro análisis (actualización masiva, por Prajwal Tomar)
- Documentación oficial: https://hermes-agent.nousresearch.com/docs
- Repositorio: https://github.com/NousResearch/hermes-agent
