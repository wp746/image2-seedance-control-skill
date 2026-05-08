# Two-Part Cinematic Production Board Pattern

Use this pattern for 25-40 second animated shorts, emotional micro-stories, sci-fi/fantasy shorts, action beats, or complex scene sequences where one long storyboard should be planned together but generated in Seedance as two separate video halves.

## Best For

- 30-second animated short
- emotional sci-fi/fantasy micro-story
- complex scene sequence
- hand-to-hand fight planning
- one character crossing multiple emotional beats
- story with a setup half and payoff half

## Core Method

Do not ask the video model to “make a video.”

Give it a production board.

Workflow:

1. Write or ask for a short 25-40 second story.
2. Split the story into `Part 1` and `Part 2`.
3. Generate one wide cinematic storyboard sheet containing both sections, or two individual storyboard sheets if cleaner.
4. Upload the storyboard and character reference to Seedance 2.0.
5. Generate each video half separately.
6. Edit the halves together.

Important: one board may contain both sections, but prompt Seedance for each section separately to avoid confusion.

## Board Layout

Create a large horizontal cinematic production storyboard sheet with:

- project title and duration
- two clearly separated storyboard sections
- numbered storyboard frames
- visual/action rows
- camera movement rows
- emotional beat rows
- cinematic annotations
- style/tone notes
- color palette swatches
- camera language section
- audio direction section

## Story Structure

Use two sections:

### Storyboard 1: Setup / Discovery / First Objective

Usually 5-6 shots:

- establish the world
- introduce the character
- show the problem
- reveal the key object or motivation
- start the journey
- end with a clear transition into Part 2

### Storyboard 2: Struggle / Payoff / Resolution

Usually 6-8 shots:

- continue the action
- intensify danger or emotion
- reach the key location or objective
- perform the decisive action
- show impact across space/time/another character
- land the emotional resolution
- optional final quiet image

## Shot Annotation Fields

Each shot should include:

- shot number
- short shot title
- visual description
- action
- emotion
- camera language
- optional narrator or dialogue line

## Footer Sections

Must include:

- visual style and tone
- color palette
- camera language
- audio direction

## Reusable Image2 Instruction Block

```text
创建一张高级电影制作故事板海报，用于一部 25-40 秒的风格化短片。整张图是导演前期制作板，不是海报。16:9 横向大画布，分成 TWO SEPARATE STORYBOARD SECTIONS：Storyboard 1 和 Storyboard 2。两个部分可以放在同一张制作板里，但必须用清晰标题、分区线、编号和色彩区分。

整体风格要像高端导演 pre-production board + 电影概念艺术。包含编号分镜帧、画面/动作行、镜头运动行、情绪节拍行、电影注释、色卡、camera language、audio direction。每个镜头必须有清晰的画面示意、动作、情绪和摄影方式。角色设计在所有镜头中必须保持完全一致。

底部加入：VISUAL STYLE AND TONE、COLOR PALETTE、CAMERA LANGUAGE、AUDIO DIRECTION。
```

## Seedance Usage Pattern

When using the board in Seedance, do not ask for the whole 30 seconds at once. Generate parts separately:

```text
Use the attached character reference and storyboard image as strict references. Follow only Storyboard 1: [section title]. Preserve the exact character design, material wear, colors, body proportions, scene style, and shot order. Generate this section as a continuous video segment.
```

Then repeat for Storyboard 2.

## Why This Works

- The full board preserves overall story continuity.
- Separate Seedance prompts prevent the model from mixing the two halves.
- Character reference controls identity.
- Storyboard controls timing, camera, and emotion.
- Editing joins the two halves cleanly.

## When Not To Use

Avoid this pattern for:

- simple 8-shot product/process videos
- dialogue-heavy drama scenes
- projects requiring many locations and many characters
- full episodes longer than one scene

For simple process videos, use `infographic-8-shot-poster.md`.

For drama episodes, split by scene and use `storyboard-control-board.md`.
