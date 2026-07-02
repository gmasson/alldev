# AllDev Skill 0.1

**Código mínimo · Cero dependencias · Zero Trust**

Una Skill ligera y agnóstica al lenguaje que disciplina a los asistentes de IA en cualquier tarea de desarrollo. Se activa siempre que se escribe, genera, refactoriza o revisa código — en cualquier lenguaje, stack o dominio — y aplica cuatro principios ordenados más pasajes obligatorios de revisión antes de entregar cualquier cosa.

Diseñada para ser lo más pequeña posible, de modo que siga siendo barata en tokens mientras está activa en cada tarea.

[English](README.md) | [Português](README.br.md) | Español

## Por qué

Los asistentes de IA tienden a hacer over-engineering, recurrir a dependencias por defecto, producir código genérico y no idiomático, y tratar la seguridad como algo secundario. AllDev Skill invierte esos patrones:

1. **El mejor código es ningún código** — toda funcionalidad se cuestiona antes de escribirse. Las soluciones nativas de la plataforma van primero; YAGNI siempre aplica; eliminar código supera a añadirlo.
2. **Vanilla-first, cero dependencias** — solo las capacidades nativas del lenguaje y plataforma elegidos. Utilidades de menos de ~200 líneas se escriben a mano. Cada dependencia requiere una justificación explícita.
3. **Código limpio, legible, idiomático y bien comentado** — las convenciones del lenguaje y los patrones existentes del proyecto van primero; nombres que revelan intención, unidades pequeñas de responsabilidad única, y comentarios que explican el *por qué*, nunca el *qué*.
4. **Seguridad Zero Trust** — no se confía en ninguna entrada, la salida se escapa según el contexto, el acceso se niega por defecto, los valores predeterminados son seguros, y los fallos cierran en lugar de abrir.

Además, ningún primer borrador se entrega. Cuatro pasajes de revisión son obligatorios: **simplificación**, **legibilidad**, **seguridad** y un **pasaje adversarial** donde el asistente ataca su propio código — repetidos hasta que un pasaje completo no encuentre nada.

## Lo que no es

- No es una guía de stack. No contiene **ejemplos de código** y nunca prescribe un lenguaje, framework o herramienta.
- No reemplaza una skill de seguridad dedicada.

## Instalación

La skill es una sola carpeta con un solo archivo:

```
alldev/
└── SKILL.md
```

**Claude Code** — personal (todos los proyectos):

```bash
git clone https://github.com/gmasson/alldev.git ~/.claude/skills/alldev
```

O por proyecto:

```bash
git clone https://github.com/gmasson/alldev.git .claude/skills/alldev
```

**Otras herramientas** — cualquier asistente que soporte el estándar Agent Skills (Claude.ai, Cursor, Windsurf, GitHub Copilot, entre otros): copie la carpeta `alldev/` en el directorio de skills de la herramienta. Para herramientas sin soporte de skills, pegue el contenido de `SKILL.md` en el archivo de reglas o instrucciones personalizadas del asistente.

## Cuándo se activa

Cualquier tarea que produzca código: aplicaciones, sitios web, APIs, scripts, CLIs, librerías, automatizaciones, bots, juegos, sistemas embebidos, infraestructura — incluyendo peticiones pequeñas como "escribe una función" o "crea un script", y también al planear proyectos, añadir funcionalidades, elegir librerías o corregir bugs.

## Licencia

[MIT](LICENSE)

## Autor

Gabriel Masson — [github.com/gmasson](https://github.com/gmasson)