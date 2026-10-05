# Gates checklist

> No step starts before the previous gate is passed. Record every gate in the gate log: date, who approved, what changed.

## Gate 1, Briefing
**Approved by:** requester

- [ ] The problem and the goal are stated the way the requester would state them
- [ ] Scope in and out is explicit
- [ ] Business rules are complete and numbered
- [ ] Every assumption was confirmed or corrected
- [ ] Open questions were answered or consciously deferred

## Gate 2, Prototype
**Approved by:** the user who will use the solution every day

- [ ] The user navigated the prototype, not a screenshot
- [ ] It follows the design system: no new colors, fonts or components without a stated reason
- [ ] Real copy, no placeholder text, no invented data
- [ ] Empty, loading, error and success states exist where the flow needs them
- [ ] It works on the devices the user actually uses
- [ ] Ideas that appeared while navigating were listed and either incorporated or deferred

## Gate 3, Build
**Approved by:** the user, with the conductor

- [ ] It matches the approved prototype; any difference was flagged, not introduced silently
- [ ] It follows the project's conventions and reuses existing components
- [ ] Build and tests pass
- [ ] Tested on phone and desktop, keyboard and focus work
- [ ] The user navigated the real interface

## Gate 4, Handoff
**Approved by:** engineering

- [ ] Code is in the agreed branch, with a pull request describing the briefing, the changes and how to test
- [ ] Integration points with the back-end are documented
- [ ] Nothing secret is in the repository
- [ ] The Context Layer was updated: new screens in the screen history, new decisions in the decision log

## Gate log

| Gate | Date | Approved by | Changes requested |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
