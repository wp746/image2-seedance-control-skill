# Dialogue / Audio / Subtitle Boundary SOP

Use this for spoken lines, voiceover, radio, public address, shouting, whispering, phone calls, subtitles, signs, documents, or other text risks.

## Core Rule

Dialogue is performance and sound. It is not automatically on-screen text.

Storyboard may note dialogue intention. Seedance prompt may describe spoken delivery. Final subtitles should usually be added in post, not generated inside the video frame.

## Responsibility Split

Storyboard board should show:

- who speaks
- who listens
- eye lines
- body distance
- reaction shot timing
- short line intention such as `低声命令` or `不敢回答`
- sound cue marker such as `VOICE`, `RADIO`, `PA`, `WHISPER`

Storyboard board should not put full dialogue paragraphs across thumbnails.

Seedance prompt should write:

- exact short line only when needed for performance or lip rhythm
- speech rate
- pause before and after the line
- breath, swallow, hesitation, interruption
- who hears the line and how they react
- whether the line is diegetic: mouth / radio / loudspeaker / off-screen

Every dialogue Seedance prompt must include:

```text
对白只作为声音和表演节奏，不渲染成字幕；不要画面内文字、不要字幕、不要乱码。
```

Post-production should handle:

- final subtitles
- exact typography
- title cards
- archival captions
- lower thirds
- credits

## Speech Rhythm Gate

Never make characters rush because the segment is only 15 seconds.

Defaults:

- whispered or tense line: 2-5 Chinese characters per second
- normal dramatic speech: 4-7 Chinese characters per second
- urgent command: short burst, then reaction pause
- public speech: split across multiple segments unless it is one slogan-like line

For a line to land, add:

- pre-line breath or eye decision: 0.3-1.0s
- line delivery
- post-line reaction or silence: 0.5-2.0s

If the line cannot fit with reaction time, split the segment.

## Dialogue Prompt Pattern

```text
对白: CHAR_A 低声说"[短句]"，语速慢，先吸气0.4s再开口；说完停0.8s，CHAR_B不立刻回答，眼神先下移再抬起。对白只作为声音/口型/表演节奏，不出现字幕或画面文字。
```

## Hard Fail

Fail or repair if:

- subtitles appear in a clean narrative frame without request
- random text appears because dialogue was written on the storyboard thumbnail
- speech is too fast for the emotion
- the listener has no reaction beat
- characters speak while their face/body performance contradicts the line
- generated text replaces spoken performance

