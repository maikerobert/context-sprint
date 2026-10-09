# Gates checklist

> No step starts before the previous gate is passed. Record every gate in the gate log: date, who approved, what changed.

## Gate 1, Briefing
**Approved by:** requester

- [ ] The briefing answers who suffers and when, how it is done today and what it costs, and how we will know it is solved
- [ ] The success metric has a current value, a target and a date to check
- [ ] The scale of validation is set (and, if Product, the journeys and their order)
- [ ] Scope in and out is explicit
- [ ] Business rules are complete and numbered
- [ ] Every assumption was confirmed or corrected
- [ ] Open questions were answered or consciously deferred
- [ ] Success criteria are written so that each one can become a step of the test script
- [ ] The transcript was classified by the governance rule, and nothing that should stay in the meeting is in the briefing

## Gate 2, Prototype
**Approved by:** the user who will use the solution every day

- [ ] The user navigated the prototype, not a screenshot
- [ ] When there were alternatives, the user compared them by navigating, and the choice was recorded with the reason
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
- [ ] A test script by role exists, covering every success criterion of the briefing (`templates/test-script.md`)
- [ ] The conductor ran the full script before asking for the gate, and what failed was fixed first
- [ ] The user validated the real interface by following the script, in fifteen minutes or less

## Gate 4, Handoff
**Approved by:** engineering

- [ ] Code is in the agreed branch, with a pull request describing the briefing, the changes and how to test
- [ ] The test script is in the repository and linked from the pull request
- [ ] Integration points with the back-end are documented
- [ ] Nothing secret is in the repository
- [ ] The Context Layer was updated: new screens in the screen history, new decisions in the decision log (including discarded alternatives, with the reason)

## Gate log

| Gate | Date | Approved by | Changes requested |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
