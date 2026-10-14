# @BR_Legacy — cómo instalarlo

Escribe `@BR_Legacy <lo que necesitas>` y la IA diseña con estilo Blue Roster Legacy. La lógica vive en `skills/BR_Legacy/SKILL.md`; cada herramienta solo apunta ahí.

## Cursor
1. Abre este repo en Cursor (o copia `.cursor/rules/br-legacy.mdc` a tu proyecto, junto con `skills/`).
2. En el chat escribe `@br-legacy` o simplemente "@BR_Legacy …"; la regla se activa sola por su descripción.

## Claude (claude.ai)
1. Descarga `claude/BR_Legacy.zip`: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/claude/BR_Legacy.zip
2. Settings → Capabilities → Skills → **Upload skill** y sube el zip.
3. En el chat: "@BR_Legacy …". En Claude Code, copia `claude/BR_Legacy/` a `~/.claude/skills/`.

## ChatGPT (GPT personalizado o Proyecto)
1. Crea un GPT (Explore GPTs → Create) o un Proyecto.
2. Pega el bloque de `gpt/instructions.md` en Instructions.
3. Sube a Knowledge los archivos que lista ese mismo documento.

## Gemini (Gem)
1. Gemini → Gems → **New Gem**, nómbralo BR_Legacy.
2. Pega el bloque de `gemini/gem-instructions.md` en Instructions.
3. Agrega los archivos de Knowledge que lista el documento y guarda.

## Codex
1. Clona el repo; Codex lee `AGENTS.md` automáticamente.
2. Pide "@BR_Legacy …" y seguirá `skills/BR_Legacy/SKILL.md`.

## Enlace único
Si una herramienta no permite instalar nada, pega este enlace: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/llms-full.txt
