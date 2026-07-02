# AllDev Skill 0.1

**Código mínimo · Zero dependências · Zero Trust**

Uma Skill enxuta e independente de linguagem que disciplina assistentes de IA na codificação em qualquer tarefa de desenvolvimento. Ela é ativada sempre que código é escrito, gerado, refatorado ou revisado — em qualquer linguagem, stack ou domínio — e impõe quatro princípios ordenados mais passagens obrigatórias de revisão antes que qualquer coisa seja entregue.

Projetada para ser o menor possível, de forma a permanecer barata em tokens enquanto ativa em todas as tarefas.

[English](README.md) | Português | [Español](README.es.md)

## Por quê

Assistentes de IA tendem a fazer over-engineering, recorrer a dependências por padrão, produzir código genérico e não idiomático, e tratar segurança como algo secundário. AllDev Skill inverte esses padrões:

1. **O melhor código é nenhum código** — toda funcionalidade é desafiada antes de ser escrita. Soluções nativas da plataforma vêm primeiro; YAGNI se aplica sempre; deletar código supera adicionar.
2. **Vanilla-first, zero dependências** — apenas as capacidades nativas da linguagem e plataforma escolhidas. Utilitários abaixo de ~200 linhas são escritos à mão. Cada dependência exige uma justificativa explícita.
3. **Código limpo, legível, idiomático e bem comentado** — as convenções da linguagem e os padrões existentes do projeto vêm primeiro; nomes que revelam intenção, unidades pequenas de responsabilidade única, e comentários que explicam o *porquê*, nunca o *o quê*.
4. **Segurança Zero Trust** — nenhuma entrada é confiada, a saída é escapada por contexto, o acesso é negado por padrão, os padrões são seguros, e falhas fecham em vez de abrir.

Além disso, nenhum primeiro rascunho é entregue. Quatro passagens de revisão são obrigatórias: **simplificação**, **legibilidade**, **segurança** e uma **passagem adversarial** onde o assistente ataca o próprio código — repetidas até que uma passagem completa não encontre nada.

## O que não é

- Não é um guia de stack. Não contém **exemplos de código** e nunca prescreve uma linguagem, framework ou ferramenta.
- Não substitui uma skill de segurança dedicada.

## Instalação

A skill é uma única pasta com um único arquivo:

```
alldev/
└── SKILL.md
```

**Claude Code** — pessoal (todos os projetos):

```bash
git clone https://github.com/gmasson/alldev.git ~/.claude/skills/alldev
```

Ou por projeto:

```bash
git clone https://github.com/gmasson/alldev.git .claude/skills/alldev
```

**Outras ferramentas** — qualquer assistente que suporte o padrão Agent Skills (Claude.ai, Cursor, Windsurf, GitHub Copilot, entre outros): copie a pasta `alldev/` para o diretório de skills da ferramenta. Para ferramentas sem suporte a skills, cole o conteúdo de `SKILL.md` no arquivo de regras ou instruções personalizadas do assistente.

## Quando é ativada

Qualquer tarefa que produza código: aplicações, sites, APIs, scripts, CLIs, bibliotecas, automações, bots, jogos, sistemas embarcados, infraestrutura — incluindo pequenos pedidos como "escreva uma função" ou "crie um script", e também ao planejar projetos, adicionar funcionalidades, escolher bibliotecas ou corrigir bugs.

## Licença

[MIT](LICENSE)

## Autor

Gabriel Masson — [github.com/gmasson](https://github.com/gmasson)