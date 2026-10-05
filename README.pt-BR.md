# Context Sprint

**Context Sprint: a IA com o contexto inteiro da empresa, e pessoas aprovando em cada etapa.**

Context Sprint é um método de desenvolvimento de produto que leva uma necessidade de negócio da reunião até interfaces prontas para publicar ou integrar ao sistema, construídas no design system e na stack da própria empresa, com uma aprovação humana entre cada etapa. Na prática, o protótipo navegável existe minutos depois do fim da reunião, e as telas ficam prontas no dia seguinte.

O método se apoia em uma regra: **a velocidade vem do contexto, não do modelo.** Uma IA que não conhece a empresa produz telas genéricas, que precisam ser refeitas. Uma IA que carrega o design system, o playbook da marca, o histórico de telas e o jeito de a empresa funcionar produz telas que já nascem no padrão. O método não depende do modelo ou da ferramenta de IA que o time usa.

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

## Quando usar

O Context Sprint foi pensado para a **evolução** de produtos e sistemas que já existem: novas funcionalidades, ferramentas internas, telas que seguem um padrão já definido. Ele não serve para criar um produto do zero, quando ainda não existe padrão e o trabalho é justamente criá-lo. Nesse caso o design exploratório vem primeiro, e o Context Sprint entra quando o padrão existe e passa a fazer parte do Context Layer.

## O que tem neste repositório

| Caminho | Conteúdo |
|---|---|
| [`METHOD.md`](METHOD.md) | A especificação completa do método, versão 1.0 (em inglês) |
| [`templates/context-layer/`](templates/context-layer/) | Estrutura inicial do Context Layer de uma empresa |
| [`templates/briefing.md`](templates/briefing.md) | Modelo de briefing, preenchido a partir da transcrição da reunião |
| [`templates/gates-checklist.md`](templates/gates-checklist.md) | O que cada Gate aprova e quem aprova |
| [`skills/`](skills/) | Implementação de referência em skills para agentes de IA |

## Autoria e citação

O Context Sprint foi descrito por **Maike Robert** em outubro de 2026 (São Paulo, Brasil), a partir da prática em empresas de tecnologia.

Se você usar ou adaptar o método, cite assim:

> Robert, M. (2026). *Context Sprint: Method Definition* (Versão 1.0.0). https://github.com/maikerobert/context-sprint

## Licença

- Texto do método e templates: [CC BY 4.0](LICENSE). Você pode usar, adaptar e compartilhar, inclusive comercialmente, desde que dê o crédito ao autor.
- Skills: [MIT](skills/LICENSE).
