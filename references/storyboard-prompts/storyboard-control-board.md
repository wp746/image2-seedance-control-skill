# Storyboard Control Board Pattern

Use this pattern when creating Image2 storyboard prompts for Seedance 2.0.

## Applicability

Use for every Seedance generation segment, usually 4-15 seconds.

Storyboard boards should not display full character sheets. They should reference asset codes such as `CHAR_A`, `SCENE_01`, and `PROP_PHONE`.

If the user provided original character, scene, or prop assets, those assets are the source of truth. The storyboard may only stage and animate them. It must not redesign faces, costumes, locations, props, materials, colors, or identity traits.

## Required Visible Columns / Labels

Every storyboard prompt should ask Image2 to include readable labels:

- SHOT
- TIME
- SIZE
- VISUAL
- ACTION
- DIALOGUE / LINE
- CAMERA
- PARAM
- SOUND
- EDIT
- ASSETS

## Panel Count Guidance

- 4 panels: emotional/action moment
- 5-6 panels: short hook, action beat, or safest default for direct Seedance execution in a 12-15 second segment
- 8 panels: emotional turn
- 8 panels: practical upper limit for a 15 second direct-generation segment
- 10-12 panels: detailed planning overview or slow micro-beat only; avoid by default for direct Seedance execution
- 16-25 panels: planning overview only, not one Seedance generation

## Shot Count by Dramatic Function

Select the board structure according to the dramatic function of the segment. Do not force every scene into the same shot count.

- **Dialogue / emotional beat**: 3-5 shots. Prioritize eyeline, blocking, reaction, pauses, sound bed, and emotional turn.
- **Rule reveal / comedy chain**: 5-6 shots. Prioritize cause → effect → reaction, VFX trigger, and clear punchline.
- **Action / chase / fight**: 5-7 shots. Prioritize floor plan, movement arrows, impact timing, physical feedback, and edit handoff.
- **Suspense / reveal**: 3-5 shots. Prioritize concealment, gaze direction, slow reveal, sound drop, and final frame.
- **Product / ad beat**: 5 shots. Prioritize product state, sensory detail, sound logo, brand endpoint.
- **Transition / connector beat**: 2-4 shots. Prioritize in-state, movement, out-state, and next segment handoff.

## Storyboard Image Regions

The storyboard image should usually contain these labeled regions:

1. **Segment Info**: segment id, local duration, aspect ratio, scene function, emotion goal.
2. **Reference Duties**: which uploaded asset controls character, scene, prop/UI, style, and current storyboard.
3. **Scene / Prop / Camera Control**: scene code, key props, floor plan or camera map, character placeholders, movement arrows.
4. **Style / Sound / VFX**: palette, lighting, music bed, sound effects, VFX trigger and behavior.
5. **Shot Table**: shot number, local timecode, main content, camera/movement, character action, dialogue, sound/music, emotion, VFX/continuity when needed.
6. **Negative Notes**: only production-critical constraints that prevent drift.

## Seedance Readability Rules

The board must visually encode:

- shot order and timing
- who appears
- where they are
- composition and shot size
- camera movement
- action and body blocking
- dialogue or sound intention
- edit-out frame
- asset references
- asset-lock notes when user-provided assets exist

Avoid:

- full character asset details in storyboard
- tiny paragraphs
- poster composition
- too many actions in one panel
- unclear movement direction

## Reusable Instruction Block

```text
这是给 Seedance 2.0 读取的故事板时间轴控制图，不是海报，也不是资产图。请使用清晰大标签、镜头编号、时间码、景别、画面内容、动作、台词/声音意图、拍摄手法、拍摄参数、剪辑点和资产引用。角色、场景、道具只用资产编号引用，不要在故事板里重复展示完整资产三视图。如果用户提供了原始资产图，必须以用户资产为最高优先级，故事板只负责调度镜头、动作、表演和节奏，禁止重新设计人物、场景和道具。
```
