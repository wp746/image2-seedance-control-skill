# Board Format And Style Bible

Use this module for every Image2 board in a project before writing asset, scene, prop, or storyboard prompts.

## Core Problem It Solves

Image2 will randomly drift board substrate, palette, layout mood, and typography unless the prompt defines a single board system first. Every project must therefore create and inherit a `PROJECT_BOARD_SYSTEM`.

## PROJECT_BOARD_SYSTEM Required Fields

Every final prompt file must define these fields once in `Production Control` and repeat the compact lock inside every Image2 prompt:

```text
PROJECT_BOARD_SYSTEM:
- Canvas: [16:9 / 9:16 / 4:3], same across this project unless explicitly stated.
- Board substrate: matte warm-gray digital production board, clean flat surface, no paper texture, no newspaper texture, no kraft paper, no oil paper, no parchment, no scrapbook.
- Palette: fixed project UI palette with 5-7 colors. Use the same background, line, label, accent, warning, and neutral colors on every board.
- Typography: one consistent sans-serif system. CN version uses Noto Sans CJK / Source Han Sans-like bold labels. EN version uses Inter / Helvetica-like bold labels. No Songti, no serif, no mixed calligraphy, no handwritten text.
- Text rule: large labels only, no long paragraphs inside the image. Image2 prompt carries detail; board image carries visual structure.
- Grid rule: consistent margins, gutters, header height, label style, icon style, arrows, color-coded zones.
- Label language: CN board uses short Chinese labels with optional asset codes; EN board uses English labels and asset codes only.
- Text boundary: EN production boards must not contain readable Chinese in-world text. Any Chinese sign, wall slogan, document, newspaper, map label, or subtitle must be blurred/unreadable texture, isolated into a TEXT_PROP_PLATE, or added in post-production.
- Negative substrate: no torn paper, no paper aging, no random texture, no poster art, no decorative collage, no mixed fonts, no tiny text.
```

## Recommended Default Board System

Use this default unless the user specifies a different design system:

```text
统一画板系统 / PROJECT_BOARD_SYSTEM:
16:9 horizontal matte warm-gray digital production board, clean flat UI-like layout, background #E7E3DA, panels #F8F6EF, divider lines #2A2A2A, primary labels #111111, accent red #B43A32, camera blue #2F5D8C, sound amber #B8842C, warning black/yellow. No paper texture, no newspaper, no kraft paper, no oil paper, no parchment. Consistent sans-serif typography only: Chinese review boards use Noto Sans CJK / Source Han Sans-like bold labels; English production boards use Inter / Helvetica-like bold labels and asset codes only. Large text only, no tiny paragraphs. Same margins, same arrow style, same label tags, same icon style across every asset board and storyboard in this project. Exact Chinese signs/documents/subtitles are handled by TEXT_PROP_PLATE or post-production, not by small text inside scene/storyboard boards.
```

## Image2 Prompt Injection Block

Repeat this compact block inside every Image2 prompt:

```text
必须继承 PROJECT_BOARD_SYSTEM：统一16:9横版哑光暖灰数字制作板，干净平面化排版，固定色板，固定粗体无衬线字体风格，固定边距/分栏/箭头/标签样式。禁止牛皮纸、报纸、油纸、羊皮纸、拼贴、随机纸纹、随机深浅背景、随机字体、宋体/手写体/书法体、小字段落和乱码文字。板内只允许大号短标签和资产编号，复杂说明写在提示词里，不写进图里。英文生产板只允许英文标签和资产编号，不生成可读中文小字；中文招牌/墙字/文件只做模糊时代纹理，精确文字另做TEXT_PROP_PLATE或后期添加。
```

English variant:

```text
Inherit PROJECT_BOARD_SYSTEM: unified 16:9 horizontal matte warm-gray digital production board, clean flat layout, fixed palette, fixed bold sans-serif typography, consistent margins, columns, arrows, labels, and icon style. No kraft paper, newspaper, oil paper, parchment, collage, random paper texture, random dark/light background, mixed fonts, serif fonts, handwriting, calligraphy, tiny paragraphs, or corrupted text. Use large short labels and asset codes only; put complex instructions in the prompt, not inside the image. EN production boards use English labels and asset codes only; do not render readable Chinese small text. Chinese signs, wall slogans, and documents become blurred period texture unless isolated in a TEXT_PROP_PLATE or added in post.
```

## Typography Rules

- Do not ask Image2 to render long Chinese paragraphs.
- Chinese board labels must be short: 2-6 Chinese characters where possible.
- English production boards must not render readable Chinese in-world text.
- Use asset codes as the main readable anchors: `CHAR_A`, `SCENE_01`, `PROP_RADIO`, `CAM_01`, `S01`.
- For complex concepts, use icons, arrows, floor plans, color zones, silhouettes, and thumbnails instead of text.
- If exact text matters, create a separate prop/UI board with one large isolated text block.

## Self Review

Before finalizing a prompt file, check:

- Does every Image2 prompt explicitly inherit the same board system?
- Did any prompt ask for paper, newspaper, kraft, oil paper, parchment, poster, scrapbook, or decorative collage?
- Did any prompt ask for mixed font styles or long Chinese text inside the image?
- Did any EN production board accidentally ask for readable Chinese signs, documents, wall slogans, or subtitles?
- Is exact Chinese text isolated into TEXT_PROP_PLATE/UI_TEXT_PROP_BOARD or assigned to post-production?
- Are board labels short enough for Image2?
- Does the Chinese version prioritize user comprehension, and the English version prioritize stable visual label rendering?
