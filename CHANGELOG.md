# Changelog

All notable changes to the Context Sprint method are recorded here. The method follows [semantic versioning](https://semver.org/): major versions change the structure of the method, minor versions add guidance, patches fix wording.

## [1.2.0] - 2026-10-09

- Central rule rewritten: speed and quality come from context, far more than from the model. New premise: producing is cheap, validating is expensive.
- Briefing: the agent writes the first version from three questions (who suffers and when; how it is done today and what it costs; how we will know it is solved); success metric and success criteria; scale of validation (Adjustment, Feature, Product), new section 3.5.
- Prototype: two or three alternatives when the problem admits more than one path; discarded alternatives go into the decision log.
- Test script by role, mandatory with every build: new section 3.4, new artifact, Gate 3 approved by following the script. Learned from a budget-control delivery in October 2026.
- Governance: new section 3.6, new Context Layer area and template `templates/context-layer/07-governance.md`.
- Scope: the Product scale fits the method when the standard already exists.
- Briefing and gates checklist templates rewritten; new template `templates/test-script.md`; skills updated.

## [1.1.0] - 2026-10-05

- New section 6, Continuous practice: the two rhythms (Sprints per need, Context Layer continuously), a recommended cadence (intake, parallel Sprints, context review, retrospective on the gate log) and how Context Sprint fits inside Scrum and Kanban.
- README: new "Used every day" section; authorship line now reads "created and named by".

## [1.0.0] - 2026-10-05

First public definition of the method.

- Definition and central rule: speed comes from context, not from the model.
- Three elements: Context Layer, Sprint (Briefing, Prototype, Build, Handoff) and Gates.
- Roles: conductor, requester, user, engineering, context keeper.
- Scope: evolution of existing products, not creation from scratch.
- Templates: Context Layer, briefing, gates checklist.
- Reference implementation: `context-sprint` and `brief-to-production-standard` agent skills.
