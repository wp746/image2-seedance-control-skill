# Prop Layout Bible

Use this for plot-critical, recurring, close-up, handheld, readable, mechanical, or branded props.

## Prop Priority

Design a prop board only when the prop:

- repeats across shots or episodes
- appears in close-up
- drives the plot
- is handled by a character
- has readable text/UI
- has a state change
- can easily drift in Seedance

Do not create prop boards for generic background clutter.

## Fixed Hero Prop Layout

One important prop per board when the prop is plot-critical.

Required modules:

1. `PROP ID`: code, name, story function.
2. `MULTI VIEW`: front, side, back/top, 3/4.
3. `DETAIL`: material, wear, markings, readable text if needed.
4. `SCALE`: next to hand/body/common object.
5. `HAND LOGIC`: left/right hand, grip, finger position, use posture.
6. `STATE CHANGE`: clean/damaged/open/closed/on/off/loaded/unloaded etc, only if scripted.
7. `SCENE ANCHOR`: where it appears and where it sits.
8. `DO NOT CHANGE`: shape, material, color, scale, text, hand position.

## Multi-Prop Board

Use only for secondary props. If one board contains many props:

- each prop must have a large code: `PROP_01`, `PROP_02`.
- each prop gets at least one main view, one detail view, and one use/hand/placement note.
- group props by scene or function.
- include a `REFERENCE USE` strip: which later prompts should @ which prop.

Example:

```text
REFERENCE USE:
@PROP_RADIO = radio shape and telegraph setup.
@PROP_DOCUMENT = envelope shape and short readable text.
@PROP_WEAPON_SET = generic weapon continuity, not hero identity.
```

## Text/UI Props

If exact text matters:

- isolate the text in a large single panel.
- keep text short.
- use English variant for cleaner rendering when possible.
- do not mix complex UI text into scene/storyboard boards.

## Image2 Prompt Injection

Chinese:

```text
必须使用固定道具资产版式：PROP编号、正/侧/背或顶/3-4多视图、材质细节、相对手部尺度、持握方式、剧情状态变化、场景锚点、禁止漂移。重要道具一张图只做一个；多道具板只用于次要道具，每个道具必须有清晰PROP编号，并在底部写明后期引用职责。不要把道具板做成产品海报或故事板。
```

English:

```text
Use the fixed prop asset layout: PROP ID, front/side/back-or-top/3-quarter views, material detail, hand/body scale, grip/use logic, scripted state changes, scene anchor, and forbidden drift. One important hero prop per board. Multi-prop boards are only for secondary props; every prop must have a clear PROP code and a bottom reference-duty strip. Do not turn the prop board into a product poster or storyboard.
```

## Negative Rules

- no random extra parts
- no prop redesign between views
- no unreadable critical text
- no hand switching unless scripted
- no modernized version unless requested
- no mixing prop identity with character identity
