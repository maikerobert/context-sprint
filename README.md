# Context Sprint

**Context Sprint: AI with the company's full context, and people approving at every step.**

Context Sprint is a product development method that takes a business need from a meeting to production-ready interfaces, built in the company's own design system and stack, with a human approval gate between every step. In practice, a clickable prototype exists minutes after the meeting ends and the screens are ready to publish or integrate the next day.

The central rule of the method: **speed comes from context, not from the model.** An AI with no knowledge of the company produces generic screens that have to be redone. An AI that carries the company's design system, brand playbook, screen history and way of working produces screens that are born inside the standard. The method does not depend on which AI model or tool a team uses.

[Leia em português](README.pt-BR.md)

## The three elements

| Element | What it is |
|---|---|
| **Context Layer** | The company's knowledge, written in plain files that people and AI can both read: design system, brand playbook, screen history, how the company works, decisions already made, technical stack. |
| **Sprint** | Four steps: Briefing, Prototype, Build, Handoff. |
| **Gates** | A human approval between every step. The AI never skips a gate. |

## The flow

```
Context Layer (step zero, built once and kept current)
        │
        ▼
Meeting ─► Briefing ─[Gate 1]─► Prototype ─[Gate 2]─► Build ─[Gate 3]─► Handoff ─[Gate 4]─► Integration / launch
```

## Used every day

Context Sprint is a way of working, used continuously like Scrum or Kanban. Every need that comes up becomes a Sprint, several can run in parallel, and each one feeds the Context Layer, so the next Sprint starts with more context than the last. It fits inside the delivery framework the team already uses, including inside a Scrum sprint. See [section 6 of the method](METHOD.md#6-continuous-practice).

## When to use it

Context Sprint is designed for **evolving** existing products and systems: new features, internal tools, screens that follow a standard that already exists. It is not meant for creating a new product from scratch, when there is no standard yet and the work is precisely to create one. In that case exploratory design comes first, and Context Sprint comes in once the standard exists and becomes part of the Context Layer.

## What is in this repository

| Path | Contents |
|---|---|
| [`METHOD.md`](METHOD.md) | The full method specification, version 1.1 |
| [`templates/context-layer/`](templates/context-layer/) | A starting structure for a company's Context Layer |
| [`templates/briefing.md`](templates/briefing.md) | Briefing template, filled from the meeting transcript |
| [`templates/gates-checklist.md`](templates/gates-checklist.md) | What each gate approves and who approves it |
| [`skills/context-sprint/`](skills/context-sprint/) | Reference implementation: an agent skill that runs the method and stops at every gate |
| [`skills/brief-to-production-standard/`](skills/brief-to-production-standard/) | Reference implementation of the Prototype and Build steps |

The skills follow the open Agent Skills format (a folder with a `SKILL.md`). They are a reference implementation; the method itself is tool-agnostic.

## Author and citation

Context Sprint was created and named by **Maike Robert** (São Paulo, Brazil) in October 2026, from the way he runs product development with AI day to day.

If you use or adapt the method, please credit it as:

> Robert, M. (2026). *Context Sprint: Method Definition* (Version 1.1.0). https://github.com/maikerobert/context-sprint

GitHub's "Cite this repository" button provides the same reference in other formats.

## License

- Method text and templates (`README`, `METHOD.md`, `templates/`): [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). You may use, adapt and share them, including commercially, as long as you credit the author.
- Skills (`skills/`): [MIT](skills/LICENSE).
