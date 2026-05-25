---
name: hello-world
description: Skill de ejemplo que saluda al usuario por su nombre. Úsala cuando el usuario quiera ver un ejemplo mínimo de skill, probar la estructura básica, o como plantilla para crear nuevas skills.
---

# Hello World Skill

Esta es una skill de ejemplo que muestra la estructura mínima necesaria para crear una skill personalizada para Claude Code.

## Cuándo usar esta skill

Invoca esta skill cuando:
- El usuario pida un "hola" o saludo de ejemplo
- El usuario quiera probar que las skills funcionan correctamente
- Se necesite una plantilla mínima para crear otras skills

## Cómo funciona

1. Pregunta al usuario su nombre si no lo conoce todavía
2. Devuelve un saludo personalizado en español
3. Ofrece una breve explicación de qué es una skill

## Ejemplo de uso

**Usuario:** /demo-plugin:hello-world

**Claude:**
> ¡Hola! Soy una skill de ejemplo. ¿Cuál es tu nombre?

**Usuario:** José

**Claude:**
> ¡Hola, José! 👋 Acabas de invocar tu primera skill personalizada.
>
> Una skill es un conjunto de instrucciones (este archivo `SKILL.md`) que Claude
> carga bajo demanda cuando detecta que es relevante para tu petición. La cabecera
> YAML (`name` y `description`) define cuándo se activa, y el cuerpo Markdown
> contiene las instrucciones que sigo.

## Estructura dentro del plugin

```
demo-plugin/
├── .claude-plugin/plugin.json
└── skills/
    └── hello-world/
        └── SKILL.md   ← este archivo
```

## Notas

- El `name` debe coincidir con el nombre de la carpeta.
- El `description` es lo que Claude lee para decidir si activar la skill — sé específico.
- Puedes añadir scripts auxiliares en la misma carpeta y referenciarlos desde aquí.
