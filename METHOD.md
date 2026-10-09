# Context Sprint: Method Definition

Version 1.2.0, October 2026. Author: Maike Robert.

## 1. Definition

**Context Sprint** is a product development method in which a business need goes from a meeting to production-ready interfaces, built in the company's own design system and technical stack, through four steps separated by human approval gates. An AI agent carries the company's full context and produces each artifact; people decide at every gate.

Short form: *AI with the company's full context, and people approving at every step.*

## 2. Premise

Earlier methods compressed the time between an idea and a validated answer. The Design Sprint brought it to five days; Lean Inception brought alignment to about a week. Both still depend on people producing every artifact by hand.

With AI agents, producing an artifact is no longer the slow part. The slow part became everything around it: waiting for a slot in the schedule, drawing a low-fidelity wireframe, adapting the screen to the design system, approving it again, and handing it from designer to front-end developer. Most of that work exists because the person producing the screen does not hold the company's standards in their head at the moment of producing it.

Context Sprint removes that gap by giving the AI the company's standards before it produces anything. The central rule of the method is:

> **Speed and quality come from context, far more than from the model.**

An agent with no context produces generic screens that have to be redone. An agent with the Context Layer produces screens that are born inside the standard, so the steps that existed only to bring them into the standard disappear. What remains is human judgment, concentrated at the gates. This is why the method does not depend on which AI the company uses: change the tool and the Context Layer still holds; remove the Context Layer and the best tool in the world will produce solutions that look just like the company next door's.

The second premise is that **producing is cheap, validating is expensive**. With AI, generating one screen or a hundred takes about the same time. The real limit is how much people can validate well. So Context Sprint produces only what the next approval can evaluate.

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
| Governance | What may go into the briefing, what may enter the Context Layer and what stays in the meeting (see 3.6) |

Building the Context Layer is **step zero** of the method. A company without a defined design system starts there, even if the first version is minimal. The Context Layer is never finished: every Sprint adds to it.

### 3.2 Sprint

Four steps, each closed by a gate.

1. **Briefing.** The meeting with whoever brought the need is recorded and transcribed. The agent that reads the transcript, together with the Context Layer, writes the first version of the briefing by answering three questions: who suffers from the problem, and when; how it is done today, and what it costs; how we will know it is solved. The conductor separates the problem from the solution the requester brought. The requester fills in nothing: they confirm, correct or complete that first version at Gate 1. From the third question come the success metric (what must change, how it will be measured, from which starting point and when we will check) and the success criteria, which become the test script. At the same gate, requester and conductor set the scale of validation (see 3.5). The conductor leads the meeting already knowing the Context Layer, so the questions asked target the possible paths and the gaps of the request.
2. **Prototype.** Minutes after the meeting, the agent produces a clickable prototype inside the design system, with real copy and the states that matter (empty, loading, error, success). When the problem admits more than one path, the conductor brings two or three alternatives to Gate 2, differing in something that matters: the structure of the flow, the number of steps, what appears first on the screen. Variations of color or button position do not count as alternatives. The user compares by navigating and chooses, or combines parts. When only one reasonable path exists, the conductor brings a single prototype. The goal is to keep the first idea from being approved just because it arrived first. At most three alternatives; only at the Feature scale and, at the Product scale, in the critical journeys. Discarded alternatives go into the decision log of the Context Layer, with the reason.
3. **Build.** Once the prototype is approved, the agent rebuilds it in the product's stack, following the project's conventions, tested on the devices that matter, and versioned in the repository. The build ships with a test script by role (see 3.4), which the conductor runs before asking for approval.
4. **Handoff.** The approved interface is delivered to engineering for integration with the back-end, or published directly when no integration is needed. The test script goes with it, in the repository and in the pull request.

### 3.3 Gates

Mandatory human approvals between steps.

| Gate | What is approved | Who approves |
|---|---|---|
| Gate 1, Briefing | The problem, the success metric and the scale of validation | Requester |
| Gate 2, Prototype | The solution, navigated as a real screen, chosen among the alternatives when there are any | User (the person who will use it every day) |
| Gate 3, Build | The interface running in the real stack, validated by following the test script | User, with the conductor |
| Gate 4, Handoff | Readiness for integration or launch | Engineering |

No step starts before the previous gate is passed. Gate 2 is where the most valuable input appears: ideas that only show up when people see and click the screen, which the AI does not capture on its own. They are incorporated before moving on.

### 3.4 Test script by role

Every build is delivered with a short test script, written by role, that turns the success criteria of the briefing into concrete steps. The conductor runs the script before asking for Gate 3; the user validates in a few minutes by following the same steps. Since the criteria are written at Gate 1, everyone knows from the start how the delivery will be judged.

The script has four parts:

1. **Before starting.** How to run it, with which user or permission, and how to switch roles.
2. **Main path.** One numbered step per role, in the order the work really happens. Each step says who tests, what they do (with concrete values) and what must appear, with the exact texts and numbers of the screen. Example: marketing releases the budget, the manager requests it, the director sees the balance and approves, the manager sees it approved and reports, marketing sees everything.
3. **Cases that must not break.** Rejection, required fields, what each role must not see, empty states, value and date formats, phone.
4. **With the back-end ready.** The same path with real users and what changes (notifications, integrations).

Two rules. The script tests what was built; it does not ask for changes in the code. And it travels with the delivery: in the repository and in the pull request. It worked when the requester validates in fifteen minutes or less and the team finds the errors before the validation, not during it.

### 3.5 Scale of validation

At Gate 1, the requester and the conductor define the size of the validation the need requires. Production time does not enter this account, because with AI it is short in every case.

| Scale | What it is | How validation happens |
|---|---|---|
| Adjustment | A change to a screen or flow that already exists | One cycle, usually the same day. One prototype is enough |
| Feature | A new screen or flow inside an existing product | The everyday user validates, in one or a few cycles |
| Product | A new application or system, with dozens or hundreds of screens | Validation is split into journeys. Each journey goes through its own Gate 2, with the users of that journey, in a sequence agreed at Gate 1 |

At the Product scale, the AI can generate every screen at once, but they are validated journey by journey. So nobody receives a hundred screens to approve in one go, and every approval remains a real one. The rule is to produce no more than the next approval can evaluate.

### 3.6 Governance

Not everything said in a meeting may reach the people who validate the screen. Before the first Sprint, the company sets the macro rule: which information may go into the briefing, which may enter the Context Layer and which stays in the meeting (for example: names of people under evaluation, compensation figures, decisions not yet announced). The agent that reads the transcript applies this rule when classifying each piece of information, and the conductor checks it at Gate 1. The rule is set once and reviewed at the same cadence as the Context Layer, not at every meeting.

## 4. Roles

| Role | Responsibility |
|---|---|
| Conductor | A product person who joins the meeting, operates the agent and takes the work through the gates. Runs the test script before asking for Gate 3. One conductor covers what used to require an analyst, a UX designer and a front-end developer. |
| Requester | The person or area that brought the need. Confirms the briefing and the success metric at Gate 1. |
| User | The person who will use the solution every day. Approves gates 2 and 3, at gate 3 by following the test script. |
| Engineering | Receives the handoff and integrates it with the system. |
| Context keeper | Keeps the Context Layer current after every Sprint: new screens enter the screen history, new decisions enter the decision log, and the governance rule is reviewed at the same cadence. |

## 5. Artifacts

1. Meeting transcript.
2. Briefing (one screen), with success metric, scale and success criteria.
3. Clickable prototype, or two to three alternatives when the problem admits more than one path.
4. Gate log: what was approved, by whom, when, and what changed.
5. Test script by role, derived from the success criteria of the briefing.
6. Interface in the repository.
7. Context Layer update.

## 6. Continuous practice

Context Sprint is meant to be used every day, all year, the same way a team uses Scrum or Kanban. A single Sprint takes one need from a meeting to production-ready interfaces; the practice is running a Sprint for every need that comes up and keeping the Context Layer current between them.

### 6.1 Two rhythms

| Part | Rhythm | What happens |
|---|---|---|
| Sprint | Once per need, often several in parallel | Briefing, prototype, build and handoff, each closed by its gate |
| Context Layer | Continuous | Every Sprint adds screens, decisions and patterns, and the context keeper reviews it on a fixed cadence |

The Sprints are where the work is delivered, and the Context Layer is where it accumulates. Each new screen enters the screen history, each decision taken at a gate enters the decision log, so the next Sprint starts from a richer context than the one before. The effect the method aims for is that each Sprint needs fewer changes at the gates than the previous one, because the agent already knows how the company solved similar problems.

### 6.2 Recommended cadence

1. **Intake.** Every new need becomes a Sprint candidate and is prioritized in the backlog the team already keeps.
2. **Sprints.** One conductor can run more than one Sprint at a time, since most of the waiting happens at the gates. Limit the work in progress to what the approvers can actually review.
3. **Context review.** Weekly, or at the end of each team iteration, the context keeper checks the Context Layer for outdated screens, decisions that changed and gaps found during the Sprints.
4. **Retrospective.** At the same cadence, the team reads the gate log: which gates needed the most changes, and which missing context caused them. That context goes into the Context Layer.

### 6.3 With Scrum and Kanban

Context Sprint fits inside the delivery framework the team already uses.

- **Scrum.** A Context Sprint can start and finish inside a single Scrum sprint. The need enters the backlog as an item; Briefing, Prototype and Build take the place of the wireframe, design and front-end tasks; Handoff delivers to the back-end tasks of the same or the next Scrum sprint. The word means different things in each: in Scrum a sprint is a fixed time box for the whole team, in Context Sprint it is the cycle of one need.
- **Kanban.** Each step can be a column and each gate a column policy: an item moves on only after the named approver signs off.

Back-end, data and infrastructure work keep the engineering team's own process. Context Sprint ends at the handoff.

## 7. Scope

**Use Context Sprint for evolution:** new features in existing products, internal tools, screens and flows that follow an established standard. In these cases the company wants speed inside its own standard, and the creativity that matters is solving the problem well, not inventing a new visual language.

**Do not use Context Sprint for creation from scratch:** a new product, a new brand, a new design language. When no standard exists, exploratory design is the work itself. Context Sprint comes in afterwards, once the new standard exists and becomes part of the Context Layer.

The Product scale (a new system or application with dozens of screens) fits the method when the standard already exists: design system, playbook and stack defined. What is new is the system, not the standard. In that case validation is split into journeys, as described in the scale of validation. When the standard also has to be invented, it remains design work, and the method comes in afterwards.

This boundary also answers the most common objection, that the method replaces design. It replaces the repeated adaptation of screens to a standard that already exists. It depends on the people who create and maintain that standard.

## 8. Comparison

| | Design Sprint | Typical Agile cycle | Context Sprint |
|---|---|---|---|
| Time unit | 5 days | 1 to 4 weeks | One meeting plus about one day |
| Input | A problem to explore | A prioritized backlog | A transcribed meeting plus the Context Layer |
| Output | A tested prototype | A software increment | Interfaces ready to integrate or publish |
| Who produces screens | Designers | Designer and developer | Conductor with an AI agent |
| Role of people | Create and decide | Create and decide | Decide at the gates |
| Prerequisite | A team available for a week | A team | An existing Context Layer |

## 9. Related work

Context Sprint builds on and differs from:

- **Design Sprint** (Jake Knapp, Google Ventures): five days from problem to tested prototype. Context Sprint keeps the idea of a short, gated cycle and extends it to production-ready code.
- **Lean Inception** (Paulo Caroli): alignment on an MVP in about a week. Context Sprint assumes the product already exists and focuses on its evolution.
- **AI-Driven Development Lifecycle, AI-DLC** (AWS, 2025): an engineering lifecycle in which AI participates in every phase. Context Sprint is narrower and product-facing: it starts at a business meeting and ends at an interface.
- **Context engineering** and **spec-driven development**: practices for feeding AI agents the right information. The Context Layer applies the same idea at the level of a whole company.
- Practitioners have also described one-hour team exercises to write context documents with AI (for example, Allie K. Miller's "context engineering sprint", 2026). Exercises like these are a good way to run step zero, building the Context Layer.

## 10. Origin

The method was formalized from a real case in a Brazilian technology company in 2026. Leadership needed a way to control expenses of directors and managers. The need was discussed in a meeting of less than one hour. Fifteen minutes after the meeting, a clickable prototype existed in the company's design system. The next day, the interfaces were in the product's stack, tested across devices, validated with users navigating them, and ready for back-end integration.

Before, the same path took weeks: scheduling the wireframe in a sprint, validating it, handing it to UX to adapt to the design system, validating again, testing with users, then the front-end developer, and only then the back-end.

## 11. Versioning

This document follows semantic versioning. Changes are recorded in [CHANGELOG.md](CHANGELOG.md). Version 1.0.0 was the first public definition of the method; 1.1.0 adds its use as a continuous practice; 1.2.0 adds the success metric, the scale of validation, prototype alternatives, the test script by role and governance.

## Citation

> Robert, M. (2026). *Context Sprint: Method Definition* (Version 1.2.0). Zenodo. https://doi.org/10.5281/zenodo.23252178

Licensed under [CC BY 4.0](LICENSE).
