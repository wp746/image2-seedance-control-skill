# Bilingual Output Contract

Use this module for every final prompt file. The user must receive Chinese and English prompt variants for every Image2 board and every Seedance 2.0 prompt.

## Why

Chinese prompts help the user understand and inspect intent. English board prompts often produce cleaner in-image labels because Image2 handles English text more reliably. Both variants must mean the same thing.

## Required Output Pattern

For every asset, scene, prop, style, and storyboard prompt, output two blocks:

```markdown
### Prompt A01-CN - Character Asset Board - CHAR_A
```text
[Chinese Image2 prompt]
```

### Prompt A01-EN - Character Asset Board - CHAR_A
```text
[English Image2 prompt with identical meaning]
```
```

For every Seedance prompt, output two blocks:

```markdown
### Seedance Prompt S01-CN - Segment 01 Video
```text
[Chinese Seedance prompt]
```

### Seedance Prompt S01-EN - Segment 01 Video
```text
[English Seedance prompt with identical meaning]
```
```

## Equivalence Rules

- CN and EN prompts must describe the same asset codes, same scene codes, same prop codes, same timecodes, same shot count, same camera, same actions, same dialogue intent, same sound design, same lighting, same negative constraints.
- Do not add extra creative ideas to the English version.
- Do not simplify the English version into a summary. It must be production-equivalent.
- If exact Chinese dialogue appears in a Seedance prompt, keep the original Chinese dialogue inside the English prompt as quoted dialogue, then explain the performance direction in English.
- Board labels:
  - CN Image2 prompt asks for large Chinese labels plus asset codes.
  - EN Image2 prompt asks for English labels plus asset codes.
  - Both label systems must use the same layout and same visual modules.

## File Structure Additions

The final markdown file must include:

```markdown
## Language Strategy / 双语策略
- CN prompts: for user review and Chinese production understanding.
- EN prompts: for cleaner Image2 label rendering and downstream visual references.
- Meaning lock: CN and EN prompts are production-equivalent; only board label language changes.
```

## Self Review

Check every pair:

- same asset/storyboard id
- same layout
- same modules
- same reference duties
- same local segment timecode
- same negative constraints
- no missing English counterpart
- no missing Chinese counterpart
