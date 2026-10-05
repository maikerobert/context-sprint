---
name: context-sprint
description: Runs a Context Sprint, taking a business need from a meeting to production-ready interfaces in the company's own design system and stack, with a human approval gate between every step. Use when the user shares a meeting transcript or a business need for a feature, an internal tool or a screen in an existing product.
---

# Context Sprint

By Maike Robert. Method: [Context Sprint, v1.1](https://github.com/maikerobert/context-sprint/blob/main/METHOD.md) (CC BY 4.0). This skill: MIT License.

Context Sprint: AI with the company's full context, and people approving at every step.

Your job is to carry the company's context and produce each artifact. The people's job is to decide at every gate. Speed comes from context, not from the model, so never start producing before the context is loaded.

## Step zero: the Context Layer

Before anything else, find the company's Context Layer: a set of files covering the company, design system, brand playbook, screen history, decision log and stack. Look in the connected knowledge base, the repository and any folder the user points to.

- **If it exists,** read it. List in one short paragraph what you will rely on (design system source, related screens, decisions that constrain this work) and what is missing.
- **If it is missing or incomplete,** say so and offer to build it now, starting from the templates in `templates/context-layer/` of the method repository. A missing design system blocks the Sprint: create a minimum one with the user before step 2.
- Do not invent context. Anything you could not find is an open question.

## The Sprint

Four steps. Each ends at a gate. At every gate: show the result, list the decisions needed as numbered questions with a recommended answer for each, and stop. Move on only after explicit approval. A change request means edit, show again and wait again. Never deliver two steps in one turn.

### 1. Briefing → Gate 1 (requester)

Input: the meeting transcript and any notes. Output: a one-screen briefing following `templates/briefing.md` (problem, users, goal, scope in and out, business rules, context used, assumptions, open questions, target).

Ask only what changes the result. Look up everything that can be looked up first.

### 2. Prototype → Gate 2 (the user who will use it every day)

Build a clickable prototype inside the design system, with real copy and the states the flow needs. Publish it somewhere the user can open from any device. The user should navigate it, not look at a screenshot.

When ideas appear while the user navigates, list them and ask which to incorporate before passing the gate.

For the detailed rules of this step, use the `brief-to-production-standard` skill (stage 3).

### 3. Build → Gate 3 (the user, with the conductor)

Rebuild the approved prototype in the product's stack, following the project's conventions and reusing existing components. Flag any difference from the prototype. Test on phone and desktop. Use the `brief-to-production-standard` skill (stages 4 and 5) for the build and the pull request.

### 4. Handoff → Gate 4 (engineering)

Deliver for integration or launch: pull request with the briefing, the changes, how to test, the integration points with the back-end and what is pending. Use `templates/gates-checklist.md` to confirm the gate.

## After the Sprint

Update the Context Layer: add the new screens to the screen history and the new decisions to the decision log. Then fill the gate log (date, who approved, what changed) and show it to the user. Each Sprint is one cycle of a continuous practice: what you add to the Context Layer now is what makes the next Sprint faster.

## Never

- Produce a screen before the Context Layer is loaded or the design system is settled.
- Skip a gate or approve on the user's behalf.
- Invent business rules, data, copy or claims.
- Name or depend on a specific AI model in the deliverables. The method is tool-agnostic.
