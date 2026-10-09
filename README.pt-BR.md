# Context Sprint

**Context Sprint: a IA com o contexto inteiro da empresa, e pessoas aprovando em cada etapa.**

Context Sprint é um método de desenvolvimento de produto que leva uma necessidade de negócio da reunião até interfaces prontas para publicar ou integrar ao sistema, construídas no design system e na stack da própria empresa, com uma aprovação humana entre cada etapa. Na prática, o protótipo navegável existe minutos depois do fim da reunião, e as telas ficam prontas no dia seguinte.

A regra central do método: **a velocidade e a qualidade vêm do contexto, bem mais do que do modelo.** Uma IA que não conhece a empresa produz telas genéricas, que precisam ser refeitas. Uma IA que carrega o design system, o playbook da marca, o histórico de telas e o jeito de a empresa funcionar produz telas que já nascem no padrão. O método não depende do modelo ou da ferramenta de IA que o time usa.

[Read in English](README.md)

## Os três elementos

| Elemento | O que é |
|---|---|
| **Context Layer** | O conhecimento da empresa, escrito em arquivos simples que pessoas e IA conseguem ler: design system, playbook da marca, histórico de telas, como a empresa funciona, decisões já tomadas, stack técnica. |
| **Sprint** | Quatro etapas: Briefing, Protótipo, Build, Handoff. |
| **Gates** | Uma aprovação humana entre cada etapa. A IA nunca pula um Gate. |

## O fluxo

```
Context Layer (etapa zero, montado uma vez e mantido atualizado)
        │
        ▼
Reunião ─► Briefing ─[Gate 1]─► Protótipo ─[Gate 2]─► Build ─[Gate 3]─► Handoff ─[Gate 4]─► Integração / publicação
```

## Uso no dia a dia

O Context Sprint é um jeito de trabalhar, usado de forma contínua, assim como o Scrum ou o Kanban. Cada necessidade que aparece vira um Sprint, vários podem rodar ao mesmo tempo, e cada um alimenta o Context Layer, então o Sprint seguinte já começa com mais contexto do que o anterior. Ele se encaixa no modelo de entrega que o time já usa, inclusive dentro de uma sprint do Scrum. Os detalhes estão na [seção 6 do método](METHOD.md#6-continuous-practice) (em inglês).

## Quando usar

O Context Sprint foi pensado para a **evolução** de produtos e sistemas que já existem: novas funcionalidades, ferramentas internas, telas que seguem um padrão já definido. Ele não serve para criar um produto do zero, quando ainda não existe padrão e o trabalho é justamente criá-lo. Nesse caso o design exploratório vem primeiro, e o Context Sprint entra quando o padrão existe e passa a fazer parte do Context Layer.

## O que tem neste repositório

| Caminho | Conteúdo |
|---|---|
| [`METHOD.md`](METHOD.md) | A especificação completa do método, versão 1.2 (em inglês) |
| [`templates/context-layer/`](templates/context-layer/) | Estrutura inicial do Context Layer de uma empresa |
| [`templates/briefing.md`](templates/briefing.md) | Modelo de briefing, preenchido a partir da transcrição da reunião |
| [`templates/gates-checklist.md`](templates/gates-checklist.md) | O que cada Gate aprova e quem aprova |
| [`templates/test-script.md`](templates/test-script.md) | Roteiro de teste por papel, entregue com toda construção |
| [`templates/context-layer/07-governance.md`](templates/context-layer/07-governance.md) | Regra de governança: o que vai pro briefing, o que entra no Context Layer, o que não sai da reunião |
| [`skills/`](skills/) | Implementação de referência em skills para agentes de IA |

## Autoria e citação

O Context Sprint foi criado e batizado por **Maike Robert** (São Paulo, Brasil) em outubro de 2026, a partir do jeito como ele conduz o desenvolvimento de produto com IA no dia a dia.

Se você usar ou adaptar o método, cite assim:

> Robert, M. (2026). *Context Sprint: Method Definition* (Versão 1.2.0). https://github.com/maikerobert/context-sprint

## Licença

- Texto do método e templates: [CC BY 4.0](LICENSE). Você pode usar, adaptar e compartilhar, inclusive comercialmente, desde que dê o crédito ao autor.
- Skills: [MIT](skills/LICENSE).
