# Department Signoff Gates SOP

Use this before delivering an industrial prompt package or approving a generated take for series production.

The skill should behave like a compact production team, not a single prompt writer.

## Department Roles

| Department | Owns | Pass Question |
|---|---|---|
| Producer | scope, units, versioning, risk | Can this be produced repeatedly without confusion? |
| Director | story beat, performance, rhythm | Does the segment have a clear dramatic job and breath? |
| Script Supervisor | continuity, state, handoff | Can every segment inherit from the previous state? |
| Production Designer | characters, props, locations, materials | Are assets stable and story-specific? |
| Cinematographer | lens, camera, light, composition | Is every camera/light choice motivated? |
| Editor | shot count, cut points, in/out frames | Can the segment be cut into the film? |
| Sound Designer | room tone, dialogue, foley, silence | Is sound carrying story and continuity? |
| Image2 Board Expert | visual control clarity | Does the board show what text cannot? |
| Seedance Prompt Expert | executable video prompt | Does the prompt write what the board cannot? |
| QA / Compliance | lint, safety, platform limits | Are hard limits and forbidden drift covered? |

## Prompt Package Signoff

Before delivery, mark each gate:

```markdown
## Department Signoff
| Gate | Status | Notes |
|---|---|---|
| Producer | PASS/FIX | |
| Director | PASS/FIX | |
| Script Supervisor | PASS/FIX | |
| Production Designer | PASS/FIX | |
| Cinematographer | PASS/FIX | |
| Editor | PASS/FIX | |
| Sound Designer | PASS/FIX | |
| Image2 Board Expert | PASS/FIX | |
| Seedance Prompt Expert | PASS/FIX | |
| QA / Compliance | PASS/FIX | |
```

Do not deliver as industrial-grade if any gate is `FIX`.

