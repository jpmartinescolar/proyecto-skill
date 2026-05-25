# proyecto-skill — marketplace de plugins

Marketplace de ejemplo para [Claude Code](https://claude.com/claude-code). Contiene un plugin demo (`demo-plugin`) con una skill y un sub-agente.

## ¿Qué es un marketplace y qué es un plugin?

- **Marketplace**: catálogo (`.claude-plugin/marketplace.json`) que lista uno o varios plugins. Es lo que se añade a Claude Code con `/plugin marketplace add`.
- **Plugin**: paquete con su propio manifiesto (`.claude-plugin/plugin.json`) que agrupa skills, sub-agentes, slash commands, hooks y/o servidores MCP bajo un namespace único.

📚 Docs oficiales: https://code.claude.com/docs/en/plugin-marketplaces.md

## Estructura del repo

```
proyecto-skill/
├── .claude-plugin/
│   └── marketplace.json                       ← catálogo del marketplace
└── plugins/
    └── demo-plugin/
        ├── .claude-plugin/
        │   └── plugin.json                    ← manifiesto del plugin
        ├── skills/
        │   └── hello-world/SKILL.md           ← skill de saludo
        └── agents/
            └── markdown-reviewer.md           ← sub-agente revisor
```

## Cómo instalarlo en Claude Code

1. **Añade el marketplace** (en Claude Code):
   ```
   /plugin marketplace add jpmartinescolar/proyecto-skill
   ```
2. **Instala el plugin** del catálogo:
   ```
   /plugin install demo-plugin@proyecto-skill
   ```

## Contenido del plugin `demo-plugin`

| Pieza | Tipo | Invocación |
|------|------|------------|
| [hello-world](plugins/demo-plugin/skills/hello-world/SKILL.md) | Skill | `/demo-plugin:hello-world` |
| [markdown-reviewer](plugins/demo-plugin/agents/markdown-reviewer.md) | Sub-agente | Vía `Agent` con `subagent_type: markdown-reviewer` |

## Crear tu propio marketplace a partir de este

1. Haz fork o clona el repo.
2. Edita [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) con tu nombre y la lista de plugins.
3. Añade más plugins en `plugins/<nombre>/` (cada uno con su propio `.claude-plugin/plugin.json`).
4. Sube el repo a GitHub y compártelo.

## Licencia

MIT
