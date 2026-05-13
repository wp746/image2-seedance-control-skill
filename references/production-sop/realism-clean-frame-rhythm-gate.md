# Realism / Clean Frame / Rhythm Gate

Use this SOP whenever the project is realist live-action, historical drama, war film, documentary-style, police/crime drama, serious period drama, or any output where visible text contamination would break the shot.

This is a hard gate, not a taste note.

## 1. Realist Visual Medium Lock

Before writing asset prompts, decide the visual medium:

```text
照片级真人电影写实 / live-action cinema realism
```

For war or historical drama, every character, scene, prop, and storyboard board must include:

- real actor face, not game hero face
- natural skin pores, fatigue, asymmetry, age, sweat, dust, injury state when relevant
- real fabric and period material: worn cotton, wool, canvas, leather, chipped metal, dirt, salt, mud, soot
- restrained military costume and prop aging
- source-motivated light and period color science
- documentary or classic war-film lens language, not splash-art composition

Forbidden:

- game concept art
- digital painting / illustration look
- UE/CG/MetaHuman render look unless requested
- anime, webtoon, card-game, RPG, poster hero texture
- glossy clean costume showroom
- plastic skin, over-sharp symmetrical face, heroic fantasy posture

## 2. Chinese Script And Encoding Gate

Use Simplified Chinese for Chinese production-board labels unless the user asks for Traditional Chinese.

Before prompt generation from local `.txt` files:

1. Check whether the file decodes as UTF-8.
2. If it fails, try GB18030/GBK for mainland Chinese scripts.
3. Convert the working text to UTF-8 internally before analysis.
4. If mojibake appears, stop and fix the source text. Do not pass corrupted text into Image2 or Seedance prompts.

Do not let accidental Traditional Chinese or mojibake become part of an asset board. Historical documents inside the story may use their authentic script, but production labels should follow the user's project language.

## 3. Clean Frame Boundary

Separate control-board text from generated footage.

Allowed on Image2 control boards:

- shot numbers
- timecodes
- camera notes
- short production labels
- arrows and floor-plan marks
- dialogue intention as notes outside thumbnail areas

Forbidden in Seedance output frames:

- subtitles or captions
- `S01/S02/S03` labels
- shot-table text
- camera notes
- UI overlays
- production watermarks
- random Chinese/English text
- garbled characters

Every narrative Seedance prompt must end with:

```text
纯净电影画面；不要字幕、不要标题、不要画面内文字、不要 S01/S02/S03 分镜编号、不要 UI、不要水印、不要随机中文/英文、不要乱码文字。对白只作为声音/表演节奏，不渲染成字幕。
```

If the storyboard board contains dialogue text, keep it outside the image thumbnail area. Do not write dialogue directly across the visual frame.

## 4. Crowd And Extras Face Diversity Gate

In war films, historical drama, public meetings, checkpoints, troop formations, evacuation scenes, and battlefield groups, the crowd is part of the realism contract.

Do not let group scenes become same-face duplicates.

Named characters:

- keep exact identity, face, body, wardrobe, rank, injury state, and performance baseline
- use character asset boards as the only identity source

Extras and crowd:

- must be visibly different people
- vary age range, face shape, cheekbones, jaw, nose, eyes, hairline, skin texture, height, body build, posture, fatigue, dirt, sweat, scars, and micro-expression
- keep the same army/unit/civilian style, era, fabric, weathering, and color discipline
- do not copy the hero face into the crowd
- do not create repeated clone rows, mirrored faces, or identical background heads
- for distant crowds, keep faces lower-detail but still varied in silhouettes and posture

Every group-scene Seedance prompt must include:

```text
群众演员必须是不同的人：不同年龄、脸型、身高、体型、发际线、皮肤质感、疲惫程度、站姿和微表情；只统一军装体系和时代质感，不要同脸复制、不要克隆脸、不要把主角脸复制到群演身上。
```

Storyboard boards should show crowd variation through silhouette and posture, not through repeated copied heads.

## 5. Rhythm And Breath Gate

Do not use shot count as a quality proxy. Shot count follows the dramatic function.

Recommended 15-second rhythm:

| Dramatic Function | Shot Count | Timing Logic |
|---|---:|---|
| waiting, dread, fog, empty field, night before action | 1-2 | slow push, hold, breath, environmental sound |
| command hesitation, moral pressure, grief | 1-3 | face/reaction holds, silence before/after line |
| dialogue or interrogation | 2-4 | line, reaction, pause; do not cut before meaning lands |
| stealth or suspense movement | 2-4 | approach, listening, micro-action, held reveal |
| impact combat / explosion / assault | 4-7 | only fast when script explicitly accelerates |
| montage or transition | 4-6 | each image must carry a new idea |

Hard rule:

If a beat needs more than 5 shots to be understandable, it is probably not one 15-second Seedance segment. Split it into multiple storyboards and multiple generations.

One-shot 15-second segment is valid when:

- the camera movement has a story reason
- the actor has a reaction chain
- the sound and atmosphere evolve
- the end frame hands off cleanly

## 6. Pre-Delivery Mini Gate

Before delivery, answer:

- Is the asset board photographic, not game/CG/concept art?
- Are Chinese labels Simplified Chinese by default?
- Is there any text that might leak into the video frame?
- Does the Seedance prompt explicitly forbid subtitles, labels, UI, watermarks, and garbled text?
- If there are crowds/extras, are they differentiated instead of same-face duplicates?
- Does every shot exist for an emotional or narrative reason?
- Would the segment still work if it used fewer shots?
- If the script says slow, waiting, fear, grief, hesitation, or silence, did we give it screen time?
