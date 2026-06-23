<div align="center">

![JNC Design Compass](portada.jpg)

# JNC Design Compass

**Una brújula de diseño universal — kit de herramientas y prompts de IA**

Sintetizado a partir de más de 20 sistemas de diseño de clase mundial, dos libros de teoría aplicada y más de 100 fuentes adicionales. Úsalo como referencia, pégalo en cualquier IA como system prompt o activa sub-herramientas individuales para tareas específicas de diseño.

</div>

---

## ¿Qué es esto?

Este repositorio contiene **10 sub-herramientas de diseño** estructuradas como prompts listos para usar con cualquier IA (Claude, GPT-4, Gemini, etc.). Cada sub-herramienta cubre un dominio específico del diseño de interfaces y sistemas, con principios extraídos directamente de las mejores fuentes del mundo.

No es un framework de código. Es una **brújula de criterio de diseño** — principios que guían decisiones visuales, estructurales, emocionales y estratégicas en cualquier contexto.

---

## Estructura del repositorio

```
jnc-design/
├── README.md                        ← Estás aquí
├── DESIGN_COMPASS.md                ← Guía de referencia completa (todos los principios)
└── prompts/
    ├── MASTER_SYSTEM_PROMPT.md      ← Pega en cualquier IA para activar la Brújula completa
    ├── 01-foundations.md            ← Tokens, grid, color, tipografía, íconos, jerarquía
    ├── 02-components.md             ← Arquitectura de componentes, affordances, estados
    ├── 03-accessibility.md          ← Diseño inclusivo y cumplimiento WCAG
    ├── 04-voice-tone.md             ← Copy de UX, mensajes de error, estados vacíos
    ├── 05-motion.md                 ← Animación, micro interacciones, diseño emocional
    ├── 06-cross-platform.md         ← Web, iOS, Android, React Native
    ├── 07-context-adapters.md       ← Guía por industria (enterprise, consumer, gov...)
    ├── 08-governance.md             ← Operar un design system como producto
    ├── 09-visual-craft.md           ← Affordances, jerarquía, sombras, overlays, dark mode
    └── 10-emotional-design-norman.md ← Modelo de tres niveles, confianza, personalidad
```

---

## Cómo usarlo con una IA

### Opción A — Brújula completa

1. Abre `prompts/MASTER_SYSTEM_PROMPT.md`
2. Copia todo el contenido
3. Pégalo como **system prompt** (o primer mensaje) en cualquier chat de IA
4. Haz tu pregunta de diseño con naturalidad

La IA usará los 10 sub-tools y 20 principios universales para responder.

### Opción B — Sub-herramienta específica

1. Elige el archivo que corresponde a tu tarea (ej. `03-accessibility.md`)
2. Copia su contenido
3. Pégalo como contexto antes de tu pregunta

Útil cuando trabajas en un problema acotado y no quieres cargar toda la brújula.

### Opción C — Referencia sin IA

Lee `DESIGN_COMPASS.md` directamente como manual de diseño. Tiene los principios desarrollados con ejemplos y tablas de decisión.

---

## Las 10 Sub-Herramientas

| Archivo | Sub-herramienta | Para qué usarla |
|---|---|---|
| `01-foundations.md` | Foundations Forge | Tokens de diseño, grid, color, tipografía, íconos, jerarquía visual |
| `02-components.md` | Component Architect | Arquitectura de componentes, affordances, estados, diseño de API |
| `03-accessibility.md` | Accessibility Blueprint | WCAG, ARIA, navegación por teclado, lectores de pantalla |
| `04-voice-tone.md` | Voice & Tone Studio | Copy de UX, mensajes de error, estados vacíos, formateo |
| `05-motion.md` | Motion Playbook | Animaciones, micro interacciones, diseño emocional conductual |
| `06-cross-platform.md` | Cross-Platform Mapper | Decisiones web + mobile + nativo simultáneamente |
| `07-context-adapters.md` | Context Adapters | Enterprise, consumer, gobierno, fintech, herramientas dev, media |
| `08-governance.md` | Governance Engine | Operar un design system: versionado, contribuciones, métricas |
| `09-visual-craft.md` | Visual Craft | Affordances, jerarquía, sombras, overlays, dark mode, micro interacciones |
| `10-emotional-design-norman.md` | Emotional Design | Modelo visceral/conductual/reflexivo, confianza, personalidad, seducción |

---

## Los 20 Principios Universales

Estos principios atraviesan todas las sub-herramientas y se aplican en cualquier contexto de diseño:

1. **Semántico sobre visual** — Los elementos se nombran por su rol, no por su apariencia.
2. **La accesibilidad es arquitectura** — Se construye desde el inicio; no se retrofita.
3. **Los tokens son el sistema** — Los componentes cambian; los tokens deben ser estables.
4. **Composición sobre configuración** — Menos props, más composición.
5. **Respeto por la plataforma** — Los patrones nativos existen por buenas razones.
6. **El movimiento sirve a la función** — Cada animación debe ganarse su lugar.
7. **La documentación es el producto** — Lo no documentado no existe para el usuario.
8. **La consistencia habilita velocidad** — Los patrones familiares eliminan fricción cognitiva.
9. **Diseña el error primero** — El camino de recuperación es tan importante como el feliz.
10. **El color es semántico** — Transmite significado, no solo estética.
11. **El dark mode es un sistema** — No es la inversión del light mode.
12. **El sistema sirve al producto** — Cuando el sistema frena una necesidad real, el producto gana.
13. **Cada interacción necesita respuesta** — El silencio de la UI rompe la confianza.
14. **La jerarquía decide antes que el usuario** — Tamaño, posición y color guían el ojo.
15. **Los affordances son instrucciones sin palabras** — La forma visual comunica interactividad.
16. **Investigar → Analizar → Adaptar** — Diseña dentro de las convenciones del mercado, luego mejora.
17. **Las cosas atractivas funcionan mejor** — El afecto positivo amplía el pensamiento y tolera errores menores.
18. **Los tres niveles deben funcionar** — Visceral sin conductual frustra; conductual sin reflexivo es olvidable.
19. **La confianza se construye gota a gota y se pierde de golpe** — Un error silencioso puede destruir meses de experiencia positiva.
20. **Diseña para el contexto de ansiedad** — Usuarios bajo estrés necesitan claridad absoluta; usuarios relajados disfrutan la profundidad.

---

## Fuentes y teoría base

**Sistemas de diseño explorados directamente:**

Material Design 3 · Apple HIG · Atlassian · Shopify Polaris · GitHub Primer · GitLab Pajamas · IBM Carbon · Microsoft Fluent 2 · Elastic UI · Adobe React Aria · Radix UI · Zag.js · Semantic UI · Evergreen · Tamagui · AgnosticUI · Thumbprint · GOV.UK · Gestalt (Pinterest) · BBC GEL · y más de 100 sistemas adicionales catalogados por Adele (UXPin) y Design System Repo.

**Teoría UI/UX aplicada (Sub-Tool 9):**
UI/UX Concept — 11 conceptos visuales fundamentales: Affordances & Signifiers · Jerarquía Visual · Grids & Spacing · Tipografía · Teoría del Color · Dark Mode · Sombras · Íconos & Botones · Feedback & Estados · Micro Interacciones · Overlays.

**Diseño Emocional (Sub-Tool 10):**
Donald A. Norman — *Emotional Design: Why We Love (or Hate) Everyday Things* (2004) — Modelo de tres niveles (Visceral/Conductual/Reflexivo) · Las cosas atractivas funcionan mejor · Confianza y antropomorfismo · Modelo conceptual · Personalidad de producto · Autoimagen · Modelo de seducción · Personalización · Contexto de ansiedad · Diseño de sonido.

**Agregado desde:** [awesome-styleguides](https://github.com/streamich/awesome-styleguides)

---

<div align="center">

**Construido para diseñadores y equipos que trabajan con IA.**

*Cuantos más contextos le des a la IA, mejores decisiones de diseño tomará contigo.*

</div>
