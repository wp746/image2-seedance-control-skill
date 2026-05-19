# Reference Upload Order SOP — Seedance 多参考图上传顺序

Use this SOP before generating any Seedance 2.0 segment with multiple reference images. It prevents reference conflicts by giving each uploaded image one clear responsibility.

## Core Rule

Every reference image needs a job. Do not upload images as vague inspiration.

The Seedance prompt must name each reference duty in the first line, using compact labels. Because the user-facing Seedance tool displays uploaded references as `@图片1`, `@图片2`, `@图片3` rather than custom asset codes, the final prompt must use those image-number references. For complex asset boards, the duty line must bind each `@图片N` to the exact board/image, asset code, panel/module/label, and ignore scope. Vague delegation is not enough for Seedance 2.0.

Before the fenced Seedance prompt, add a user-only Markdown note that maps the upload order to the generated board names and English labels. This note is not copied into Seedance:

```text
> 上传参考图（这行不复制进 Seedance）：@图片1 = Prompt A01-EN / Character Asset Board / CHAR_A；@图片2 = Prompt A05-EN / Scene Asset Board / SCENE_01；@图片3 = Prompt S01-EN / Storyboard Board / STORYBOARD_01_EN。
```

Example:

```text
本段按顺序上传：@图片1=原始CHAR_A；@图片2=CHAR_A板；@图片3=SCENE_01板；@图片4=PROP_PHONE板；@图片5=当前故事板。参考职责：@图片1最高身份源；@图片2读脸/体型/服装锁；@图片3读空间/光源锁；@图片4读道具/持握锁；@图片5读镜头顺序/机位/动线。
```

Better:

```text
本段按顺序上传：@图片1=A01-EN角色板；@图片2=A05-EN场景板；@图片3=PROP_PHONE道具板；@图片4=S01-EN故事板。参考职责：@图片1（A01-EN/CHAR_A）读FULL BODY 4 VIEWS+FACE GRID+Costume State 02，忽略其它年代服装；@图片2（A05-EN/SCENE_01）读V02入口+V06顶视图+LIGHT DIRECTION，忽略场景板里的无关区域；@图片3（PROP_PHONE）读HAND USE CLOSE-UP；@图片4（S01-EN）读TOP VIEW+CAMERA A/B+C+SHOT PANELS。
```

Forbidden vague line:

```text
角色资产管脸/服装，场景资产管空间，道具资产管手持和位置，故事板管机位/路线。
```

Also forbidden in final Seedance prompts:

```text
@A01-EN controls identity, @SCENE_01 controls space, @STORYBOARD_S01 controls camera.
```

The tool will not show these names after upload. Use `@图片N` and put asset codes in parentheses.

## Standard Upload Stack

Use this order unless a project has a specific reason to change it:

| Order | Reference | Duty |
|---|---|---|
| 1 | original user character/photo/product asset | highest-priority visible source truth |
| 2 | formal character asset board | identity, body, wardrobe, expression baseline |
| 3 | scene asset board | geography, light source, fixed objects |
| 4 | prop/product/vehicle asset board | shape, material, scale, hand relationship |
| 5 | STYLE_LOOK_SAFE only, optional | palette, contrast, lens language, lighting, texture, grain, composition mood; must be abstract and non-contaminating |
| 6 | scene continuity board | blocking, movement path, emotional state in space |
| 7 | current storyboard board | shot order, camera positions, timing, action flow |
| 8 | previous segment final frame | exact in-frame state for continuation |

If the platform visually displays references left-to-right or top-to-bottom, keep the same order.

## Global Visual Bible Upload Boundary

Do not upload a mixed global visual bible to Seedance if it contains people, faces, buildings, city geography, vehicles, weapons, props, maps, floor plans, signs, or readable text. It will contaminate identity, scene, props, vehicles, and text.

Global look should usually be controlled by `STYLE_LOCK_TEXT` inside the Seedance prompt. Upload a style image only when it is explicitly `STYLE_LOOK_SAFE`: abstract swatches, grain, light, lens, weather, and material samples, with no story content.

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
本段本地时间 0:00-0:15；上一段末帧只负责本段 0:00 首帧姿态、站位、光线、情绪和道具状态；原始资产/角色板仍是身份最高源；当前故事板负责本段镜头顺序和动作。
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
5. User-provided style references override the skill's default taste, but style references never override identity, wardrobe, scene geography, prop shape, vehicles, signs, text, story facts, clean-frame rules, or crowd diversity.
6. `STYLE_LOCK_TEXT` is safer than uploading a mixed visual bible image. Use it in every Seedance prompt.

Do not upload two different faces for the same character unless one is explicitly labeled as "old version / do not use".

## Reference Conflict Gate

If references conflict, do not continue by hoping the model will resolve it.

| Conflict | Status | Fix |
|---|---|---|
| two different faces for one character | `HOLD` | pick one identity source or label old version as do-not-use |
| style reference changes wardrobe/identity | `FIX` | limit style duty to look only |
| visual bible contains characters/scenes/vehicles/props/text | `FIX` | do not upload globally; extract STYLE_LOCK_TEXT and split content into proper asset boards |
| previous final frame overrides identity | `FIX` | move original character/board before final frame; final frame controls only start state |
| storyboard redesigns asset | `REBUILD` | rebuild storyboard as execution board only |
| exact text appears in multiple inconsistent refs | `FIX` | create one UI/text prop board |
| too many references for one segment | `SPLIT` | reduce to source asset + needed board + current storyboard |

## Prompt Reference Line Template

Use compact duty labels to save characters:

```text
本段按顺序上传：@图片1=原始CHAR_A；@图片2=CHAR_A板；@图片3=SCENE_01板；@图片4=PROP_01板；@图片5=当前故事板；@图片6=上段末帧。参考职责：@图片1最高身份源；@图片2读脸/体型/服装/表演基准；@图片3读空间/光源/固定物；@图片4读形状/材质/持握；@图片5读镜头/机位/动线；@图片6只管首帧姿态/光线/情绪。
```

For board-rich projects, prefer exact panel targeting:

```text
本段按顺序上传：@图片1=A01-EN角色板；@图片2=A06-EN场景板；@图片3=A10-EN道具板；@图片4=S03-EN故事板。参考职责：@图片1（A01-EN/CHAR_A）读FACE GRID+FULL BODY+指定服装状态，忽略其它状态；@图片2（A06-EN/SCENE_01）读V04 CAMERA A+V08 LIGHT+TOP VIEW PLAN；@图片3（A10-EN/PROP_01）读Hand-use detail；@图片4（S03-EN）读TOP VIEW+SHOT PANELS S01-S03。
```

When using style references:

```text
@参考职责: STYLE_LOOK_SAFE=仅控制色彩/光线/镜头质感/颗粒/构图气质，不控制人物身份、服装、剧情、道具、车辆、招牌、文字或场景布局；混有人物/场景/道具/文字的视觉圣经图不要上传，只使用STYLE_LOCK_TEXT文字锁
```

For 5000-character pressure, compress to:

```text
@参考: 原CHAR_A=身份最高 CHAR_A板=脸/服/体型 SCENE=空间/光 PROP=形/握 故事板=镜头/动线 末帧=首帧
```

## Upload Checklist

Before generation:

- Are all references named in the Seedance prompt?
- Does each reference have one clear duty?
- Is there any conflicting face, outfit, prop, or location?
- If a style reference is uploaded, is its duty limited to style treatment?
- Is the style reference truly STYLE_LOOK_SAFE, with no people/scenes/vehicles/props/maps/readable text?
- If the visual bible is unsafe, was it converted to STYLE_LOCK_TEXT instead of uploaded?
- Is the current storyboard included?
- For continuation, is the previous final frame included or described?
- Is the reference order written in the production log?
