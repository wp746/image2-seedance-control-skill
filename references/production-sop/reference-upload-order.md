# Reference Upload Order SOP — Seedance 多参考图上传顺序

Use this SOP before generating any Seedance 2.0 segment with multiple reference images. It prevents reference conflicts by giving each uploaded image one clear responsibility.

## Core Rule

Every reference image needs a job. Do not upload images as vague inspiration.

The Seedance prompt must name each reference duty in the first line, using compact labels.

Example:

```text
@参考职责: 原始CHAR_A=最高身份源 CHAR_A板=脸/体型/服装锁 SCENE_01板=空间/光源锁 PROP_PHONE板=道具/持握锁 当前故事板=镜头顺序/机位/动线 上段末帧=起始姿态/情绪/光线
```

## Standard Upload Stack

Use this order unless a project has a specific reason to change it:

| Order | Reference | Duty |
|---|---|---|
| 1 | original user character/photo/product asset | highest-priority visible source truth |
| 2 | formal character asset board | identity, body, wardrobe, expression baseline |
| 3 | scene asset board | geography, light source, fixed objects |
| 4 | prop/product/vehicle asset board | shape, material, scale, hand relationship |
| 5 | style/look bible | palette, lens language, lighting, texture |
| 6 | scene continuity board | blocking, movement path, emotional state in space |
| 7 | current storyboard board | shot order, camera positions, timing, action flow |
| 8 | previous segment final frame | exact in-frame state for continuation |

If the platform visually displays references left-to-right or top-to-bottom, keep the same order.

## Segment Type Adjustments

### First Segment

No previous final frame exists. Use:

```text
original assets -> asset boards -> current storyboard
```

The Seedance prompt must define the opening frame precisely.

### Continuation Segment

Use the previous final frame as a high-priority continuity reference:

```text
previous final frame -> original assets -> asset boards -> current storyboard
```

In the prompt, state:

```text
上一段末帧负责本段第一帧姿态、站位、光线、情绪和道具状态；资产板负责身份与空间不漂移；当前故事板负责本段镜头顺序和动作。
```

If identity drifts when the previous final frame is first, move original character asset and character board before it, but explicitly say previous final frame controls only pose and lighting.

### Product / Commercial Segment

Prioritize product identity:

```text
original product photo -> product asset board -> hand/use board -> scene board -> storyboard
```

The prompt must state that the product reference overrides decorative style references.

### Action Segment

Prioritize action readability:

```text
character boards -> location/floor plan -> current action storyboard -> previous final frame
```

If action and identity conflict, simplify the action before adding more references.

### Dialogue / Emotional Segment

Prioritize face and eyeline:

```text
character boards -> previous final frame -> scene board -> current storyboard
```

Avoid far-distance faces. Keep dialogue beats close enough for identity lock.

## Conflict Rules

When references disagree:

1. User original asset wins visible identity.
2. Formal asset board wins normalized continuity if it preserves the original asset.
3. Current storyboard wins shot order and camera logic.
4. Previous final frame wins only the opening state of a continuation segment.
5. Style references never override identity, wardrobe, scene geography, or prop shape.

Do not upload two different faces for the same character unless one is explicitly labeled as "old version / do not use".

## Prompt Reference Line Template

Use compact duty labels to save characters:

```text
@参考职责: 原始CHAR_A(最高身份源) CHAR_A板(脸/体型/服装/表演基准) SCENE_01板(空间/光源/固定物) PROP_01板(形状/材质/持握) 当前故事板(S01-S05镜头/机位/动线) 上段末帧(首帧姿态/光线/情绪)
```

For 2000-character pressure, compress to:

```text
@参考: 原CHAR_A=身份最高 CHAR_A板=脸/服/体型 SCENE=空间/光 PROP=形/握 故事板=镜头/动线 末帧=首帧
```

## Upload Checklist

Before generation:

- Are all references named in the Seedance prompt?
- Does each reference have one clear duty?
- Is there any conflicting face, outfit, prop, or location?
- Is the current storyboard included?
- For continuation, is the previous final frame included or described?
- Is the reference order written in the production log?

