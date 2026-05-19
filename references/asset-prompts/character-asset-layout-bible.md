# Character Asset Layout Bible

Use this for every character asset prompt. It defines what is fixed and what is story-specific.

## Fixed Layout

Default canvas: 16:9 horizontal, inheriting `PROJECT_BOARD_SYSTEM`.

One board may contain:

- 1 main/recurring character, or
- at most 2 supporting characters, or
- a group/crowd board only when individual identity continuity is less important than type diversity.

If there are more than 2 supporting characters, split into additional boards. Do not cram 3-6 named characters into one 16:9 sheet.

## Single Character Board Locked Modules

Use the same module order for every single-character board:

1. `HEADER / IDENTITY LOCK`: asset code, name, role, age range, height, body type, story function.
2. `FULL BODY 4 VIEWS`: front, 3/4 front, side, back. This is mandatory and must remain visually dominant.
3. `FACE CLOSE-UP GRID`: front, 3/4, side, low angle, high angle. Same face, same age, same hairline.
4. `EXPRESSION / PERFORMANCE`: story-specific expression arc, usually 5-8 expressions.
5. `COSTUME + MATERIAL`: main wardrobe, footwear, accessories, fabric aging, stains, wear marks.
6. `PROP INTERACTION`: only props this character actually uses or repeats in the script.
7. `SCENE INTERACTION`: 1-3 small panels showing how the character stands/sits/moves in key scenes, not full storyboards.
8. `SCALE + SILHOUETTE`: height scale, posture, gait, body rhythm.
9. `DO NOT CHANGE`: face, age, body, hair, costume, prop hand, era.

## Dynamic Modules Chosen By Story Function

Choose only the modules the script needs. Do not design unused references.

- If the character changes age/time state: add `AGE / TIME STATE`, with exact story states.
- If hairstyle changes: add `HAIR STATE`, with allowed states and forbidden drift.
- If costume changes: add `WARDROBE STATE`, with scene-by-scene state, not random alternates.
- If injury/dirt/wetness changes: add `PHYSICAL STATE`, with state progression.
- If the role has emotional arc: add `EMOTION ARC`, from entry state to exit state.
- If the role handles weapons/tools/documents: add `HAND + PROP LOGIC`.
- If the role appears in action scenes: add `MOTION BASELINE`, posture, speed, weight, combat/working rhythm.
- If the role is a leader: add `COMMAND PERFORMANCE`, gesture, gaze, map/desk behavior.
- If the role is a civilian or crowd type: add occupation, age, class, wardrobe diversity.

## Supporting Character Board

At most 2 characters per 16:9 board.

Each supporting character must still have:

- 2 body views: front and 3/4
- 3 face close-ups
- costume/material lock
- expression baseline
- one prop or scene interaction if relevant
- clear separation so faces do not mix

## Crowd / Group Board

Use when the script needs soldiers, villagers, office workers, refugees, students, etc.

The board must emphasize difference:

- age difference
- profession/function difference
- hairstyle difference
- clothing difference
- height/body type difference
- facial feature difference
- posture and behavior difference

If the group wears uniform clothing, diversity must come from:

- height
- body type
- face shape
- eye/nose/mouth structure
- age impression
- posture
- gear wear pattern

If the group is same age, diversity must come from face, hair, body type, posture, and accessories.

## Image2 Prompt Requirements

Every character prompt must explicitly say:

```text
Use the fixed Character Asset Layout Bible. Do not invent a new layout. Keep the same board substrate, palette, typography, margins, panel style, label style, and module order as the project board system.
The first visible top title must start with the asset board index: A01 / CHAR_CODE / ENGLISH CHARACTER ASSET BOARD. The A-number must match the prompt number exactly and be the largest left-aligned title. Do not start the board title with only CHAR_CODE or the character name.
```

Chinese injection:

```text
必须使用固定角色资产版式：顶部主标题必须以本资产编号开头，例如 A01 / CHAR_CODE / CHARACTER ASSET BOARD，并且 A编号必须和提示词编号完全一致、最大号、左对齐；顶部身份锁，主体为全身四视图，右侧为人脸特写网格，下方为表情/服装材质/道具互动/场景互动/身高剪影/禁止漂移。不要重新发明版式。单主角一张；辅助角色一张最多两人；超过两人拆下一张；群像板必须重点区分年龄、职业、发型、服饰、高矮胖瘦和五官。
```

English injection:

```text
Use the fixed character asset layout. The first visible top title must begin with the asset number, for example A01 / CHAR_CODE / CHARACTER ASSET BOARD; the A-number must match the prompt number exactly, largest and left-aligned. Then show header identity lock, dominant full-body four-view sheet, face close-up grid, expression/performance row, costume/material row, prop interaction, scene interaction, height/silhouette scale, and forbidden drift strip. Do not invent a new layout. One main character per board; at most two supporting characters per 16:9 board; split if more than two; group boards must clearly differentiate age, occupation, hair, wardrobe, height, body type, and facial features.
```

## Negative Rules

- no alternate random costumes unless scripted
- no unrelated prop references
- no detailed character turnarounds inside storyboard boards
- no more than two named supporting characters per 16:9 board
- no decorative poster layout
- no mixed board styles
