# Production Runbook SOP — 工业化执行手册

Use this SOP when the project must move from prompt writing into repeatable production. It defines how a team names files, generates boards, uploads references, records takes, accepts output, and repairs defects.

This is the execution layer above the creative SOPs. It does not replace the project bible, storyboard pairing principle, seam review, or repair SOP. It makes them operational.

---

## When To Use

Use for:

- multi-segment shorts
- episode-based live-action drama or webtoon production
- projects with recurring characters, scenes, props, or style
- commercial work with client review
- any workflow where the user asks for industrialized production, team handoff, stable output, or SOP

For one simple 4-15 second clip, use only the lightweight fields in the prompt file. For anything longer, run this SOP.

## Production Units

Always define the unit before writing prompts:

| Unit | Meaning | Example |
|---|---|---|
| `PROJECT` | whole title or campaign | `coming_home` |
| `EP` | episode | `EP01` |
| `SCENE` | script scene/location/time block | `SC03_living_room` |
| `SEG` | one Seedance generation segment, usually 4-15s | `SEG02` |
| `SHOT` | storyboard shot inside one segment | `S03` |
| `TAKE` | generated attempt from Seedance | `T02` |
| `PATCH` | repair/regeneration pass | `P01` |

Never mix cumulative episode timecode with Seedance segment timecode. `SEG` prompts always start at `0:00`.

## Folder And File Naming

Recommended production folder:

```text
PROJECT_SLUG/
  00_brief/
  01_project_bible/
  01_style_bible/
  02_assets/
  03_storyboards/
  04_seedance_prompts/
  05_generations/
  06_reviews/
  07_repairs/
  08_final_edit/
```

Recommended filenames:

```text
PROJECT_EP01_bible_v001.md
PROJECT_EP01_STYLE_BIBLE_v001.md
PROJECT_EP01_CHAR_A_asset_v001.png
PROJECT_EP01_SCENE_01_asset_v001.png
PROJECT_EP01_PROP_PHONE_asset_v001.png
PROJECT_EP01_SC03_SEG02_storyboard_v001.png
PROJECT_EP01_SC03_SEG02_seedance_prompt_v001.txt
PROJECT_EP01_SC03_SEG02_T01.mp4
PROJECT_EP01_SC03_SEG02_review_T01.md
PROJECT_EP01_SC03_SEG02_repair_P01.md
```

Version rules:

- `v001`, `v002` are prompt or board versions.
- `T01`, `T02` are Seedance generated takes from the same prompt version.
- `P01`, `P02` are repair passes with a changed prompt, changed board, or changed reference stack.
- Do not overwrite a generated take. Keep bad takes because they diagnose failure modes.

## Production Flow

### 1. Intake

Lock:

- project title
- format and target platform
- total duration
- aspect ratio
- style target
- source assets or references
- user style references: image, video, film title, director/cinematographer reference, brand look, or "no style reference"
- episode or scene scope
- deadline and review owner if relevant
- source text encoding. If Chinese `.txt` files are GBK/GB18030/Big5, convert or decode to UTF-8 before analysis. Never feed mojibake or unreadable characters into prompt generation.

If the user gives only an idea, clarify before writing prompts.

### 2. Creative Lock

Create or write:

- style reference analysis / STYLE_BIBLE when the user provides a style image, reference video, film title, or asks for a specific look
- project continuity bible for recurring elements
- scene type map: DIALOGUE / ACTION / SUSPENSE / TRANSITION / PRODUCT / ATMOSPHERE
- A-roll / B-roll split
- required asset list
- segment list with local duration

Gate to continue:

- Every recurring character has a code.
- Every repeated scene has a code.
- Every plot-critical prop has a code.
- If a user style reference exists, STYLE_BIBLE exists and states scope: global / scene / segment / shot.
- Every segment has a dramatic function and target duration.

### 3. Asset Boards

Generate asset boards before storyboard boards:

1. character boards
2. scene boards
3. prop or product boards
4. style/look bible when user provides or requests a style
5. optional scene continuity board

Gate to continue:

- Faces, wardrobe, scene geography, prop shape, and color logic are readable.
- No board contains contradictory variants unless labeled as state changes.
- User-provided original assets remain the source of truth.
- User style references are applied as visual treatment only; they do not redesign identity, props, geography, or story facts.

### 4. Storyboard Boards

For each segment:

1. load `storyboard-seedance-pairing-principle.md`
2. load `scene-type-playbook.md`
3. load `user-style-reference-sop.md` when the user provides style references or asks to extract a film look
4. load `realism-clean-frame-rhythm-gate.md` when the project is realist, historical, war, documentary, or text-risk
5. choose the storyboard pattern by scene function
6. create one storyboard prompt for the segment
7. create one matching Seedance prompt immediately after it

Gate to continue:

- Storyboard and Seedance prompt have the same shot numbers and local timecodes.
- Board text stays minimal.
- If STYLE_BIBLE exists, storyboard and Seedance prompt include the relevant compact style lock.
- Seedance prompt explicitly forbids rendered subtitles, captions, shot labels, UI text, watermarks, random text, and garbled text.
- Seedance prompt is at or below 2000 characters.
- Shot count matches dramatic rhythm. Slow emotional beats are not allowed to become fast-cut coverage.
- Segment duration is 4-15s unless the user explicitly asks for shorter.

### 5. Reference Upload

Use `reference-upload-order.md` to assemble the reference stack. Each uploaded image must have exactly one job:

- original asset: source truth
- asset board: identity or space lock
- storyboard: shot flow and camera logic
- previous final frame: segment continuity

Never upload several conflicting identity sources without labeling their duties in the Seedance prompt.

### 6. Generation Log

For every generated take, record:

```markdown
## Generation Log
- Project:
- EP / Scene / Segment:
- Prompt version:
- Reference stack:
- Take:
- Seedance settings:
- Duration:
- Aspect ratio:
- Generated at:
- Initial verdict: PASS / REPAIR / REGENERATE
- Notes:
```

### 7. Acceptance Review

Use `output-acceptance-scorecard.md`.

Gate:

- `PASS`: deliver or edit.
- `CONDITIONAL`: usable with edit or small repair.
- `FAIL`: repair or regenerate.

Do not decide by taste only. Decide by identity, continuity, motion, editability, and story function.

### 8. Repair

Use `seedance-repair-sop.md` only after classifying the defect. Repair the smallest unit:

| Defect | Smallest likely repair |
|---|---|
| slight identity drift | prompt tightening or closer reference |
| wrong scene layout | scene board or floor plan repair |
| prop changes | prop board + hand relationship lock |
| action failure | reduce action beats, regenerate segment |
| shot logic impossible | rewrite storyboard |
| asset unreadable | rebuild asset board |

### 9. Final Continuity Review

Before final edit:

- compare every segment end frame to next segment start frame
- check sound bridges and room tone
- check emotional progression
- check costume, dirt, wetness, injury, and prop states
- check that B-roll breathes instead of interrupting A-roll

## Production Status Board

Use this compact table in long project prompt files or review docs:

```markdown
| Unit | Asset Lock | Storyboard | Seedance Prompt | Lint | Take | Score | Status | Next Action |
|---|---|---|---|---|---|---|---|---|
| SC01_SEG01 | PASS | PASS | PASS | PASS | T02 | 86 | PASS | edit |
| SC01_SEG02 | PASS | FIX | HOLD | N/A | N/A | N/A | REWRITE | simplify action |
```

Status values:

- `LOCKED`: approved source element
- `DRAFT`: written but not reviewed
- `PASS`: ready for next stage
- `HOLD`: blocked by missing input
- `FIX`: needs prompt or board repair
- `REGENERATE`: use same concept but rerun Seedance
- `REBUILD`: source asset or storyboard is wrong

## Delivery Gate

Before telling the user the prompt file is ready:

1. Load the selected references from the index.
2. Run prompt self-review.
3. Run the prompt lint script if a prompt file exists locally.
4. Confirm upload order is included or referenced.
5. Confirm each segment has acceptance criteria.
6. Mention unresolved assumptions only if they affect production.
