# Proyecto Skill

Repositorio de ejemplo con skills personalizadas para [Claude Code](https://claude.com/claude-code).

## ¿Qué es una skill?

Una skill es un conjunto de instrucciones (archivo `SKILL.md`) que Claude Code carga bajo demanda cuando detecta que es relevante para tu petición. Las skills permiten extender el comportamiento del asistente con conocimiento especializado, plantillas y flujos repetibles.

## Estructura

```
.
├── README.md
└── skills/
    └── hello-world/
        └── SKILL.md   ← skill de ejemplo "Hello World"
```

## Cómo usar las skills de este repo

1. Clona el repo en tu máquina:
   ```bash
   git clone https://github.com/jpmartinescolar/proyecto-skill.git
   ```
2. Copia la carpeta de la skill que te interese dentro del directorio de skills de Claude Code:
   - Skills de usuario: `~/.claude/skills/`
   - Skills de proyecto: `<tu-proyecto>/.claude/skills/`
3. Abre Claude Code en el proyecto y escribe `/hello-world` (o el nombre de la skill).

## Skills incluidas

| Skill | Descripción |
|-------|-------------|
| [hello-world](skills/hello-world/SKILL.md) | Skill mínima que saluda al usuario. Útil como plantilla. |

## Crear tu propia skill

1. Crea una carpeta `skills/<nombre-skill>/`.
2. Dentro, crea un `SKILL.md` con frontmatter YAML:
   ```yaml
   ---
   name: nombre-skill
   description: Qué hace la skill y cuándo Claude debe activarla.
   ---
   ```
3. Escribe en el cuerpo Markdown las instrucciones que Claude debe seguir.

## Licencia

MIT
