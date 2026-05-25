# demo-plugin

Plugin de ejemplo para [Claude Code](https://claude.com/claude-code). Sirve como plantilla mínima para entender la estructura de un plugin con **skills** y **sub-agentes**.

## ¿Qué es un plugin de Claude Code?

Un plugin es un paquete reutilizable bajo un namespace único que puede contener skills, sub-agentes, slash commands, hooks y servidores MCP. Se instala desde un repo Git o un marketplace y queda disponible en todos tus proyectos.

📚 Docs oficiales: https://code.claude.com/docs/en/plugins.md

## Estructura del plugin

```
proyecto-skill/
├── .claude-plugin/
│   └── plugin.json              ← manifiesto del plugin
├── skills/
│   └── hello-world/
│       └── SKILL.md             ← skill de saludo
├── agents/
│   └── markdown-reviewer.md     ← sub-agente revisor de Markdown
├── README.md
└── .gitignore
```

## Contenido

| Pieza | Tipo | Invocación |
|------|------|------------|
| [hello-world](skills/hello-world/SKILL.md) | Skill | `/demo-plugin:hello-world` |
| [markdown-reviewer](agents/markdown-reviewer.md) | Sub-agente | Vía `Agent` con `subagent_type: markdown-reviewer` |

## Instalación

### Opción 1 — desde GitHub
En Claude Code:
```
/plugin install jpmartinescolar/proyecto-skill
```

### Opción 2 — desarrollo local
Clona el repo y arranca Claude Code apuntando al directorio:
```bash
git clone https://github.com/jpmartinescolar/proyecto-skill.git
cd proyecto-skill
claude --plugin-dir .
```

Durante el desarrollo, recarga cambios con `/reload-plugins`.

## Crear tu propio plugin a partir de este

1. Haz fork o clona este repo.
2. Edita [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json) con tu nombre, autor y descripción.
3. Añade tus propias skills en `skills/<nombre>/SKILL.md` y sub-agentes en `agents/<nombre>.md`.
4. Sube tu repo a GitHub y compártelo.

## Licencia

MIT
