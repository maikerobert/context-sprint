# Context Sprint: Method Definition

Version 1.0.0, October 2026. Author: Maike Robert.

## 1. Definition

**Context Sprint** is a product development method in which a business need goes from a meeting to production-ready interfaces, built in the company's own design system and technical stack, through four steps separated by human approval gates. An AI agent carries the company's full context and produces each artifact; people decide at every gate.

Short form: *AI with the company's full context, and people approving at every step.*

## 2. Premise

Earlier methods compressed the time between an idea and a validated answer. The Design Sprint brought it to five days; Lean Inception brought alignment to about a week. Both still depend on people producing every artifact by hand.

With AI agents, producing an artifact is no longer the slow part. The slow part became everything around it: waiting for a slot in the schedule, drawing a low-fidelity wireframe, adapting the screen to the design system, approving it again, and handing it from designer to front-end developer. Most of that work exists because the person producing the screen does not hold the company's standards in their head at the moment of producing it.

Context Sprint removes that gap by giving the AI the company's standards before it produces anything. The central rule of the method is:

> **Speed comes from context, not from the model.**

An agent with no context produces generic screens that have to be redone. An agent with the Context Layer produces screens that are born inside the standard, so the steps that existed only to bring them into the standard disappear. What remains is human judgment, concentrated at the gates.

## 3. Elements

### 3.1 Context Layer

A structured body of knowledge about the company, written in plain text files that people and AI can both read, and connected to the AI tools the team uses.

Minimum content:

| Area | Content |
|---|---|
| Company | What the company does, departments, roles, who decides what, internal glossary |
| Design system | Colors, typography, spacing, components and their states, interaction patterns |
| Brand playbook | Key visual, tone of voice, writing rules, presentation rules |
| Screen history | Every existing screen, what it does, where it lives in the product |
| Decisions | Product decisions already made and the reasons behind them |
| Stack | Technologies, conventions, repository structure, how to run and test |

Building the Context Layer is **step zero** of the method. A company without a defined design system starts there, even if the first version is minimal. The Context Layer is never finished: every Sprint adds to it.

### 3.2 Sprint

Four steps, each closed by a gate.

1. **Briefing.** The meeting with whoever brought the need is recorded and transcribed. The transcript, together with the Context Layer, becomes a one-screen briefing: problem, users, goal, scope, business rules, assumptions and open questions. The conductor leads the meeting already knowing the Context Layer, so the questions asked target the possible paths and the gaps of the request.
2. **Prototype.** Minutes after the meeting, the agent produces a clickable prototype inside the design system, with real copy and the states that matter (empty, loading, error, success).
3. **Build.** Once the prototype is approved, the agent rebuilds it in the product's stack, following the project's conventions, tested on the devices that matter, and versioned in the repository.
4. **Handoff.** The approved interface is delivered to engineering for integration with the back-end, or published directly when no integration is needed.

### 3.3 Gates

Mandatory human approvals between steps.

| Gate | What is approved | Who approves |
|---|---|---|
| Gate 1, Briefing | The understanding of the need | Requester |
| Gate 2, Prototype | The solution, navigated as a real screen | User (the person who will use it every day) |
| Gate 3, Build | The interface running in the real stack | User, with the conductor |
| Gate 4, Handoff | Readiness for integration or launch | Engineering |

No step starts before the previous gate is passed. Gate 2 is where the most valuable input appears: ideas that only show up when people see and click the screen, which the AI does not capture on its own. They are incorporated before moving on.

## 4. Roles

| Role | Responsibility |
|---|---|
| Conductor | A product person who joins the meeting, operates the agent and takes the work through the gates. One conductor covers what used to require an analyst, a UX designer and a front-end developer. |
| Requester | The person or area that brought the need. |
| User | The person who will use the solution every day. Approves gates 2 and 3. |
| Engineering | Receives the handoff and integrates it with the system. |
| Context keeper | Keeps the Context Layer current after every Sprint: new screens enter the screen history, new decisions enter the decision log. |

## 5. Artifacts

1. Meeting transcript.
2. Briefing (one screen).
3. Clickable prototype.
4. Gate log: what was approved, by whom, when, and what changed.
5. Interface in the repository.
6. Context Layer update.

## 6. Scope

**Use Context Sprint for evolution:** new features in existing products, internal tools, screens and flows that follow an established standard. In these cases the company wants speed inside its own standard, and the creativity that matters is solving the problem well, not inventing a new visual language.

**Do not use Context Sprint for creation from scratch:** a new product, a new brand, a new design language. When no standard exists, exploratory design is the work itself. Context Sprint comes in afterwards, once the new standard exists and becomes part of the Context Layer.

This boundary also answers the most common objection, that the method replaces design. It replaces the repeated adaptation of screens to a standard that already exists. It depends on the people who create and maintain that standard.

## 7. Comparison

| | Design Sprint | Typical Agile cycle | Context Sprint |
|---|---|---|---|
| Time unit | 5 days | 1 to 4 weeks | One meeting plus about one day |
| Input | A problem to explore | A prioritized backlog | A transcribed meeting plus the Context Layer |
| Output | A tested prototype | A software increment | Interfaces ready to integrate or publish |
| Who produces screens | Designers | Designer and developer | Conductor with an AI agent |
| Role of people | Create and decide | Create and decide | Decide at the gates |
| Prerequisite | A team available for a week | A team | An existing Context Layer |

## 8. Related work

Context Sprint builds on and differs from:

- **Design Sprint** (Jake Knapp, Google Ventures): five days from problem to tested prototype. Context Sprint keeps the idea of a short, gated cycle and extends it to production-ready code.
- **Lean Inception** (Paulo Caroli): alignment on an MVP in about a week. Context Sprint assumes the product already exists and focuses on its evolution.
- **AI-Driven Development Lifecycle, AI-DLC** (AWS, 2025): an engineering lifecycle in which AI participates in every phase. Context Sprint is narrower and product-facing: it starts at a business meeting and ends at an interface.
- **Context engineering** and **spec-driven development**: practices for feeding AI agents the right information. The Context Layer applies the same idea at the level of a whole company.
- Practitioners have also described one-hour team exercises to write context documents with AI (for example, Allie K. Miller's "context engineering sprint", 2026). Exercises like these are a good way to run step zero, building the Context Layer.

## 9. Origin

The method was formalized from a real case in a Brazilian technology company in 2026. Leadership needed a way to control expenses of directors and managers. The need was discussed in a meeting of less than one hour. Fifteen minutes after the meeting, a clickable prototype existed in the company's design system. The next day, the interfaces were in the product's stack, tested across devices, validated with users navigating them, and ready for back-end integration.

Before, the same path took weeks: scheduling the wireframe in a sprint, validating it, handing it to UX to adapt to the design system, validating again, testing with users, then the front-end developer, and only then the back-end.

## 10. Versioning

This document follows semantic versioning. Changes are recorded in [CHANGELOG.md](CHANGELOG.md). Version 1.0.0 is the first public definition of the method.

## Citation

> Robert, M. (2026). *Context Sprint: Method Definition* (Version 1.0.0). https://github.com/maikerobert/context-sprint

Licensed under [CC BY 4.0](LICENSE).
