# Text Rendering Boundary SOP

Use this SOP for every Image2 board and every Seedance prompt when the project contains Chinese labels, signs, documents, subtitles, wall slogans, maps, UI, captions, or any exact text risk.

## Core Problem

Image models usually render English labels more reliably than Chinese labels. If an English production-board prompt also asks for Chinese signs or small Chinese content inside the image, the English labels may stay clean while the Chinese content becomes mojibake. If a pure Chinese board prompt asks for many small labels, the small text may collapse.

The solution is not to force one language to do every job. Split text into duties.

## Three Text Modes

### 1. CN_REVIEW_BOARD

Purpose: user review and Chinese production understanding.

Allowed:

- Simplified Chinese labels only.
- Very short labels, ideally 2-6 Chinese characters.
- Asset codes as stable anchors: `CHAR_A`, `SCENE_01`, `PROP_RADIO`, `CAM_A`.
- No tiny paragraph labels.

Not recommended for Seedance upload when label clarity is critical.

### 2. EN_PRODUCTION_BOARD

Purpose: stable Image2 label rendering and Seedance visual reference.

Required:

- English labels and asset codes only.
- No Chinese labels inside the image.
- No Chinese wall text, signs, posters, documents, or subtitles inside the image.
- In-world Chinese text that is not plot-critical must become blurred texture blocks, unreadable signage, or graphic shapes.

This is the default board to upload to Seedance when the user needs the model to read diagrams, panel names, arrows, camera maps, and reference duties.

### 3. TEXT_PROP_PLATE

Purpose: exact or semi-exact Chinese text that must exist as a prop, title card, document, sign, telegram, map label, or UI.

Required:

- Use a separate `UI_TEXT_PROP_BOARD` or dedicated text plate.
- One text-bearing prop per board when exact readability matters.
- Large isolated text only; no small background text.
- If the final viewer must read it, prefer post-production typography instead of Seedance generation.

## Hard Rules

- Do not mix English production labels with Chinese in-world text in the same Image2 board unless the Chinese text is intentionally blurred and unreadable.
- Do not ask Image2 to render exact Chinese wall slogans, shop signs, permits, map labels, or document paragraphs inside scene boards or storyboard boards.
- Do not place Chinese dialogue, subtitles, or historical captions inside storyboard thumbnails.
- For historical Chinese signage that is decorative only, prompt it as `blurred period Chinese signage texture, unreadable`.
- For historically important text, make a separate `TEXT_PROP_PLATE` and add final readable typography in post.
- Seedance narrative prompts must continue to say: no subtitles, no captions, no random Chinese/English text, no watermarks, no corrupted text.

## Image2 Prompt Injection

Chinese:

```text
文字渲染边界：本图如果是英文生产板，只允许英文标签和资产编号，不要生成任何可读中文小字；中文招牌、墙标、文件、报纸只做模糊时代纹理或色块。若剧情需要精确中文文字，必须另做 TEXT_PROP_PLATE / UI_TEXT_PROP_BOARD，或在后期添加。不要中英混排小字、不要长中文、不要乱码、不要随机文字。
```

English:

```text
Text rendering boundary: if this is an EN production board, use English labels and asset codes only. Do not generate readable Chinese small text inside the image. Chinese signs, wall slogans, documents, newspapers, and posters should appear only as blurred period texture or graphic blocks. If exact Chinese text is required, create a separate TEXT_PROP_PLATE / UI_TEXT_PROP_BOARD or add it in post-production. No mixed tiny bilingual text, no long Chinese text, no corrupted text, no random text.
```

## Seedance Prompt Injection

Chinese:

```text
纯净电影画面；不要字幕、不要标题、不要画面内文字、不要控制板标签、不要随机中文/英文、不要水印、不要乱码。对白和旁白只作为声音/口型/表演节奏；历史字幕、地点字幕、文件可读文字和片名都在后期添加，除非本段明确使用单独TEXT_PROP_PLATE做特写。
```

English:

```text
Clean cinematic frame only: no subtitles, no captions, no on-screen text, no control-board labels, no random Chinese/English text, no watermark, no corrupted text. Dialogue and voiceover are sound/lip/performance rhythm only. Historical captions, location cards, readable documents, and titles must be added in post-production unless this segment explicitly uses a separate TEXT_PROP_PLATE close-up.
```

## Self Review

- Does every EN production board forbid readable Chinese text?
- Does every CN review board keep labels short and large?
- Is exact Chinese text isolated into a prop/text plate or moved to post?
- Are scene/storyboard boards free of tiny Chinese labels?
- Do Seedance prompts explicitly forbid subtitles, random text, and corrupted text?
