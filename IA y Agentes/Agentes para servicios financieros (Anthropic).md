---
tipo: articulo
tema: Agentes de IA para finanzas
titulo: "Agents for financial services (Agentes para servicios financieros)"
autor: Anthropic
fuente: https://www.anthropic.com/news/finance-agents
publicado: 2026-05-05
guardado: 2026-07-16
tags: [ia, agentes, anthropic, claude, finanzas, automatizacion]
---

# Agentes para servicios financieros (Anthropic)

> [!abstract] Resumen
> Anthropic lanzó **10 plantillas de agentes listas para usar** para el trabajo más laborioso de servicios financieros (armar pitchbooks, revisar KYC, cierre contable mensual). Cada una viene como **plugin** en Claude Cowork y Claude Code, y como **cookbook** para Claude Managed Agents. Además, Claude ahora trabaja dentro de **Excel, PowerPoint, Word y Outlook** vía add-ins de Microsoft 365.

---

## Qué es cada plantilla de agente

Cada plantilla es una **arquitectura de referencia** que empaqueta 3 cosas:
- **Skills** — instrucciones y conocimiento de dominio para la tarea.
- **Connectors** — acceso gobernado a los datos que la tarea necesita.
- **Subagents** — modelos Claude adicionales para subtareas (ej. selección de comparables, chequeos de metodología).

Las firmas las adaptan a sus convenciones de modelado, políticas de riesgo y flujos de aprobación.

---

## Las 10 plantillas

### 📊 Research y cobertura de clientes
| Agente | Qué hace |
|--------|----------|
| **Pitch builder** | Crea listas objetivo, corre comparables, redacta pitchbooks |
| **Meeting preparer** | Arma briefs de clientes y contrapartes antes de llamadas |
| **Earnings reviewer** | Lee transcripts y filings, actualiza modelos, marca cambios relevantes |
| **Model builder** | Crea y mantiene modelos financieros desde filings, feeds y analistas |
| **Market researcher** | Sigue sectores/emisores, sintetiza noticias, filings y research, marca para revisión de crédito/riesgo |

### 🧾 Finanzas y operaciones
| Agente | Qué hace |
|--------|----------|
| **Valuation reviewer** | Verifica valuaciones vs comparables, metodología y estándares de la firma |
| **General ledger reconciler** | Reconcilia cuentas del libro mayor, corre cálculos de NAV |
| **Month-end closer** | Corre el checklist de cierre, prepara asientos, produce reportes |
| **Statement auditor** | Revisa estados financieros: consistencia, completitud, listo para auditoría |
| **KYC screener** | Arma expedientes de entidades, revisa documentos fuente, empaqueta escalaciones para compliance |

---

## Dos formas de usarlos

1. **Como plugin** (Claude Cowork / Claude Code) — corre junto al analista usando el software de su escritorio. Ej: le das al Pitch agent una lista → recibes modelo de comps en Excel, pitchbook en PowerPoint y nota de portada en Outlook.
2. **Como Claude Managed Agent** — corre autónomo en la plataforma Claude, para trabajo que abarca un libro completo de deals o un cronograma nocturno. Incluye: sesiones de larga duración, permisos por herramienta, bóvedas de credenciales gestionadas y **audit log completo** en la consola.

> [!note] Humano siempre en el loop
> En ambos casos el usuario **revisa, itera y aprueba** el trabajo de Claude antes de que llegue a un cliente, se archive o se ejecute.

---

## Claude dentro de Microsoft 365

| App | Qué hace |
|-----|----------|
| **Outlook** | Chief of staff: tría el inbox, agenda reuniones, redacta respuestas en tu voz |
| **Excel** | Construye modelos desde filings/feeds, audita fórmulas entre libros vinculados, corre análisis de sensibilidad |
| **PowerPoint** | Redacta decks que se actualizan solos cuando cambian los números |
| **Word** | Edita memos de crédito contra las plantillas de la firma |

El **contexto se traslada automáticamente** entre apps: un modelo empezado en Excel no hay que re-explicarlo al pasarlo a PowerPoint.

También existe **Dispatch**: asignar tareas a Claude desde cualquier lugar (texto o voz); sigue trabajando en tus archivos locales mientras estás fuera.

---

## Ecosistema de datos

Claude conecta con decenas de plataformas de datos de mercado y sistemas internos, bajo acceso gobernado:
- FactSet, S&P Capital IQ, MSCI, PitchBook, Morningstar, Chronograph, LSEG, Daloopa.

**Nuevos connectors:** Dun & Bradstreet, Fiscal AI, Financial Modeling Prep, Guidepoint, IBISWorld, SS&C Intralinks, Third Bridge, Verisk.
**Nueva MCP app:** Moody's (ratings de crédito y datos propietarios).

---

## Dato de rendimiento

> Estas actualizaciones funcionan mejor con **Claude Opus 4.7**, líder en el benchmark **Finance Agent de Vals AI** con **64.37%**.

---

## Conexión con mi propio proyecto

> [!tip] Relevancia para Enrique / negocio
> Aunque es un artículo enfocado en finanzas corporativas, el **patrón** es directamente aplicable: **plantillas de agente = skills + connectors + subagentes**, con el humano aprobando al final. Es el mismo modelo que ya uso aquí en Hermes (skills, memoria, subagentes). La idea de "agente que trabaja mientras no estás y deja el trabajo listo para revisar" es exactamente lo que aplicamos con los cron jobs y el flujo Obsidian.

---

## Enlaces relacionados

- [[Hermes Agent - Guía Completa (Arquitectura, Setup y Bucle de Auto-Mejora)]] — mismo concepto de agentes con skills + subagentes + memoria
- Fuente original: https://www.anthropic.com/news/finance-agents
