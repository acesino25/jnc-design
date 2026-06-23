# JNC Design Compass — Skills

Prompts estructurados como skills instalables en cualquier IA.
Cada skill activa un rol experto especializado en un dominio de diseño.

## Skills disponibles

| Skill | Trigger | Dominio |
|---|---|---|
| `jnc-compass` | `/jnc-compass` | Brújula completa — activa los 10 sub-tools |
| `jnc-foundations` | `/jnc-foundations` | Tokens, grid, color, tipografía, íconos |
| `jnc-components` | `/jnc-components` | Arquitectura de componentes, estados, API |
| `jnc-accessibility` | `/jnc-accessibility` | WCAG, ARIA, teclado, screen readers |
| `jnc-voice-tone` | `/jnc-voice-tone` | UX copy, errores, empty states, botones |
| `jnc-motion` | `/jnc-motion` | Animaciones, transiciones, micro-interactions |
| `jnc-cross-platform` | `/jnc-cross-platform` | Web, iOS, Android, React Native |
| `jnc-context` | `/jnc-context` | Enterprise, consumer, gov, fintech, devtools, media |
| `jnc-governance` | `/jnc-governance` | Operar un design system como producto |
| `jnc-visual-craft` | `/jnc-visual-craft` | Affordances, jerarquía, sombras, dark mode |
| `jnc-emotional-design` | `/jnc-emotional-design` | Modelo Norman (visceral/conductual/reflexivo) |

---

## Instalación en Claude Code

```bash
# Copia cualquier skill a tu directorio global de skills
cp -r skills/jnc-compass ~/.claude/skills/
cp -r skills/jnc-foundations ~/.claude/skills/
# ... repite por cada skill que quieras instalar
```

Luego invoca con el comando slash en cualquier conversación:

```
/jnc-compass ¿Cómo diseño un sistema de tokens para dark mode?
/jnc-accessibility ¿Cómo implemento focus management en un modal?
/jnc-voice-tone Escríbeme el mensaje de error para cuando falla el pago
```

### Instalar todos los skills de una vez

```bash
cp -r skills/jnc-* ~/.claude/skills/
```

---

## Instalación en Cursor / Windsurf / Zed

Cada `SKILL.md` contiene el system prompt completo.
Copia el contenido del archivo en:
- **Cursor**: `.cursor/rules/` como archivo `.mdc`
- **Windsurf**: `.windsurf/rules/` como archivo `.md`
- **Zed**: Settings → Assistant → System Prompt

---

## Uso en cualquier otra IA (GPT-4, Gemini, Mistral, etc.)

1. Abre el `SKILL.md` de la sub-herramienta que necesitas
2. Copia todo el contenido (desde `You are a...` hasta el final)
3. Pégalo como **system prompt** o primer mensaje en tu chat de IA
4. Haz tu pregunta de diseño

Para la brújula completa usa `jnc-compass/SKILL.md`.
Para una tarea específica usa el skill individual.

---

## Cuándo usar cada skill

| Pregunta / Tarea | Skill recomendado |
|---|---|
| ¿Cómo nombro mis tokens de color? | `jnc-foundations` |
| ¿Cómo diseño los estados de un botón? | `jnc-components` |
| ¿El contraste de este color es accesible? | `jnc-accessibility` |
| ¿Cómo redacto este mensaje de error? | `jnc-voice-tone` |
| ¿Qué easing uso para esta animación? | `jnc-motion` |
| ¿Cómo adapto este patrón para iOS? | `jnc-cross-platform` |
| Estoy diseñando para banca/fintech | `jnc-context` |
| ¿Cómo versiono mi design system? | `jnc-governance` |
| ¿Cómo comunico interactividad sin texto? | `jnc-visual-craft` |
| ¿Por qué los usuarios confían (o no) en mi producto? | `jnc-emotional-design` |
| Cualquier pregunta de diseño | `jnc-compass` |
