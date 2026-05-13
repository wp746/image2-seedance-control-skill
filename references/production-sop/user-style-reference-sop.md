# User Style Reference SOP

Use this SOP whenever the user provides or requests a visual style source:

- reference image
- reference video
- screenshots / frames
- film title or a named film look
- director, cinematographer, studio, brand, campaign, MV, or game look
- phrase such as "提取这个电影的风格", "按这张图的风格", "像这个参考片", "保持这个调性"

The user style source has priority over the skill's default taste.

## 1. Core Rule

Do not invent a new style when the user gives a style reference.

First extract a STYLE_BIBLE, then apply it consistently to:

- project continuity bible
- character boards
- scene boards
- prop boards when material/finish matters
- storyboard boards
- Seedance prompts
- reference upload duty line
- output acceptance criteria

STYLE_BIBLE controls visual treatment, not story facts.

## 2. Style Reference Boundary

Style references control:

- palette and color separation
- contrast curve and exposure bias
- lens language, focal length tendency, depth of field
- lighting quality, direction, ratio, color temperature, source logic
- texture: grain, halation, digital sharpness, softness, haze, dust, bloom
- composition habits: negative space, symmetry/asymmetry, foreground occlusion, frame density
- camera mood: locked, handheld, dolly, observational, immersive, distant
- editing/rhythm tendency when the reference is video
- sound/mood tendency if reference video has meaningful sound

Style references must not override:

- character identity
- age, face, body, wardrobe continuity
- scene geography
- prop shape, material, or story usage
- plot facts
- clean-frame/no-text rules
- crowd/extras face diversity
- platform safety or project-specific constraints

## 3. Extraction Dimensions

When analyzing a style reference, extract only observable production traits.

Use this compact table:

```markdown
## STYLE_BIBLE
- Source:
- Scope: global / scene / segment / shot
- Visual medium:
- Palette:
- Contrast/exposure:
- Lens/DOF:
- Lighting:
- Texture/grain:
- Composition:
- Camera movement:
- Editing rhythm:
- Production design/material:
- Sound/mood:
- Forbidden drift:
- Compact prompt lock:
```

The compact prompt lock should be short enough to repeat in every Seedance prompt:

```text
STYLE_LOCK: [palette], [contrast/exposure], [lens/DOF], [lighting], [texture], [camera mood]. 不改变人物身份/服装/场景/道具/剧情。
```

## 4. Film Style Extraction

If the user names a film, extract a production-style direction rather than copying exact frames.

Good:

```text
低饱和冷灰绿色调，阴天自然光，高反差室内阴影，长焦压缩空间，轻微手持，颗粒感，压抑纪实节奏。
```

Bad:

```text
完全复制某电影某镜头。
```

If the film reference conflicts with the story, adapt the style DNA to the user's scene. For example, do not force neon lighting into a daylight battlefield just because the reference film has neon; translate the trait into contrast, color separation, lens, or atmosphere.

## 5. Reference Image / Video Handling

For a still image:

- extract palette, light, contrast, texture, composition, lens feel, production design
- do not assume motion rhythm unless the user says so

For a video:

- extract all still-image traits
- also extract camera movement, edit density, shot duration tendency, actor blocking, sound mood, pacing curve

For a mixed reference pack:

- assign duties:
  - identity reference controls faces/bodies/wardrobe
  - style reference controls look
  - storyboard reference controls shot logic
  - previous final frame controls continuation state

Do not let one reference perform all jobs unless the user explicitly says it is the only source.

## 6. Prompt Application Pattern

Every asset prompt should include:

```text
风格参考只控制色彩、光线、镜头质感、颗粒、构图和氛围；不得改变角色身份、服装结构、时代、道具或剧情事实。
```

Every Seedance prompt using a style reference should include:

```text
STYLE_BIBLE 负责色彩/光线/镜头质感/颗粒/构图气质；角色资产负责身份；场景资产负责空间；故事板负责镜头顺序。不得让风格参考改变人物、服装、道具、地点或剧情。
```

## 7. Acceptance Gate

Before delivery or after generation, check:

- Does the output visibly match the user style reference?
- Is the match specific, not just "cinematic"?
- Did the style reference stay within its duty?
- Did it preserve identity, story, props, scene geography, clean frame, and crowd diversity?
- Is the style lock repeated consistently across all segments?
- If a segment intentionally departs from style, is the reason scripted?

If the user style is missing or replaced by the skill's default look, mark the segment as failed and rebuild the STYLE_BIBLE.
