# Segment Complexity Budget SOP

Use this before writing each storyboard + Seedance prompt pair.

Seedance stability depends on whether the segment asks the model to do a reasonable amount of work.

## Core Rule

One segment should have one primary dramatic job.

If a 15-second segment asks for too many characters, actions, camera moves, props, VFX, dialogue lines, geography changes, or style changes, it will fail even if the prompt is beautifully written.

## Complexity Budget Table

| Dimension | Low Risk | Medium Risk | High Risk |
|---|---|---|---|
| Named characters | 1-2 | 3 | 4+ |
| Crowd/extras | background silhouettes | small varied group | large active crowd |
| Main actions | 1 | 2 | 3+ |
| Camera moves | locked / one slow move | two motivated moves | orbit/crane/zoom/handheld mix |
| Locations | one | one with visible transition | multiple locations |
| Props | 0-1 | 2 | 3+ or handoff-heavy |
| Dialogue | none / one short line | two short lines | long speech / overlapping lines |
| VFX/particles | none/simple atmosphere | one controlled effect | multiple interacting effects |
| Text in world | none | one prop/sign | multiple readable text elements |
| Style references | one STYLE_BIBLE | two compatible refs | conflicting refs |

## Decision

- Mostly low: proceed.
- Any 2 medium: simplify or clarify.
- Any high: split segment or rebuild storyboard.
- More than 5 shots in a dramatic segment: justify with action/impact logic.
- More than 8 shots in any 15-second segment: rewrite or split.

## Simplification Moves

- reduce shot count
- convert two actions into one readable action
- hold one camera move instead of changing camera style
- move dialogue to a later segment
- move exposition to voiceover or post edit
- split crowd into foreground named characters + varied background extras
- turn exact text into a prop board or add it in post
- remove VFX unless it changes the story

## Budget Line Template

```text
SEGMENT_BUDGET: 2 named chars / varied background extras / 1 main action / 2 shots / one slow push / no rendered text / low risk.
```

For high-risk segments, do not continue until the segment is split or simplified.

