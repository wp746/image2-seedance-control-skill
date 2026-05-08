# Shot Seam Review SOP

Use this SOP to make generated shots connect without feeling broken. It applies before writing storyboard prompts and after Seedance outputs video segments.

The purpose is to make every shot pass its state to the next shot: image, motion, sound, emotion, and story logic.

## When To Use

- any multi-shot storyboard
- every 4-15 second Seedance segment
- every transition between generated segments
- all 1-3 minute shorts and episode-based projects
- whenever the user asks for seamless continuity, one-take feeling, or no fragmentation

## Seam Principle

Every shot must define:

```text
IN STATE -> ACTION -> OUT STATE -> NEXT SHOT HANDOFF
```

If the out state of one shot cannot become the in state of the next shot, the edit will feel broken.

## Seam Fields

For each shot, track:

- `IN_FRAME`: what the first frame should inherit
- `IN_POSITION`: character/object position
- `IN_DIRECTION`: screen direction, eyeline, body facing
- `IN_EMOTION`: carried emotion
- `MAIN_ACTION`: one primary action
- `CAMERA_MOVE`: movement and lens
- `SOUND`: dialogue, environment, music, effect
- `OUT_FRAME`: exact final frame
- `OUT_STATE`: body, prop, emotion, space, light state
- `NEXT_HANDOFF`: what the next shot must pick up

## Seam Checklist

Before finalizing a storyboard, check every adjacent pair:

- Character continuity: face, age, hair, wardrobe state, injury/dirt/wetness, prop hand, body position.
- Spatial continuity: left/right direction, eyeline, distance to key objects, entrances/exits, floor plan, camera position.
- Motion continuity: believable continuation, no teleporting, no impossible speed change, no unintended repetition.
- Emotional continuity: emotion progresses, reaction follows cause, hold time exists after major conflict or reveal.
- Light and style continuity: time, weather, light direction, color grade, camera texture, genre.
- Dialogue and sound continuity: line order, speaking intention, room tone, music, impact, silence.
- Edit logic: match cut, reaction cut, insert, whip, dissolve, hard cut, usable final frame.

## Review Table

Use this compact table internally or in long-form production files:

```markdown
| Seam | Previous Out | Next In | Direction | Emotion | Prop/Costume | Light | Sound | Verdict | Fix |
|---|---|---|---|---|---|---|---|---|---|
| S01->S02 | | | PASS/FAIL | PASS/FAIL | PASS/FAIL | PASS/FAIL | PASS/FAIL | PASS/FAIL | |
```

## Image2 Seam Board Prompt

Use this when a complex sequence needs a visual continuity seam board:

```text
请创建一张镜头接缝连续性检查板，用于确保 Seedance 2.0 多镜头视频无割裂衔接。

项目：[PROJECT_TITLE]
段落：[SCENE_OR_SEGMENT]
画幅：[ASPECT_RATIO]
风格：[STYLE]
镜头列表：[SHOT_LIST]
资产编号：[ASSET_CODES]

这是一张 continuity seam board / 镜头接缝检查图，不是海报。请用清晰表格和左右对照方式展示每个镜头的 OUT FRAME 与下一个镜头的 IN FRAME。

每一组接缝必须包含：
- Previous OUT / 上一镜结束画面
- Next IN / 下一镜开始画面
- Character Position / 人物位置
- Screen Direction / 屏幕方向
- Eyeline / 视线方向
- Emotion Carryover / 情绪承接
- Prop State / 道具状态
- Costume State / 服装状态
- Light Continuity / 光线连续
- Sound Bridge / 声音桥接
- Edit Type / 剪辑方式
- PASS or FIX / 通过或需要修正

用绿色标记通过项，用红色标记需要修正项。所有文字必须大而清楚。画面要像专业剪辑师和导演使用的连续性检查表。
```

## Repair Decision

If a seam fails:

- minor face/costume/prop drift: regenerate that segment with stronger asset lock
- wrong direction/space: rewrite storyboard with floor plan and screen direction
- emotion jump: add reaction shot or hold frame
- action missing: split into action start, impact, reaction
- light/style mismatch: restate global visual bible and match previous out frame
- sound gap: add room tone, music bridge, breath, footsteps, or impact tail

Do not solve seam failures by adding random new shots. Add only shots that carry cause, effect, or emotional transition.
