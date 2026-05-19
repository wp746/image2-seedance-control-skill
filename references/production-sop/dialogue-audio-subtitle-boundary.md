# Dialogue / Audio / Subtitle Boundary SOP

Use this for spoken lines, voiceover, radio, public address, shouting, whispering, phone calls, subtitles, signs, documents, or other text risks.

## Core Rule

Dialogue is performance and sound. It is not automatically on-screen text.

When the user provides a script, every spoken line and voiceover line is a locked creative asset. Preserve the user's original wording exactly: character name, line text, dialect, punctuation, ellipses, dashes, quotation marks, numbers, and parenthetical performance notes. Do not summarize, rewrite, polish, shorten, merge, or delete script dialogue.

Storyboard may note dialogue intention and should assign the exact line or exact fragment to the segment. Seedance prompt must include the exact line or exact fragment as spoken delivery. Final subtitles should usually be added in post, not generated inside the video frame.

## Responsibility Split

Storyboard board should show:

- who speaks
- who listens
- eye lines
- body distance
- reaction shot timing
- the exact script line or exact fragment assigned to this segment, kept in prompt text; if the board image cannot reliably render it, mark it as `VOICE`/`DIALOGUE` and keep the full exact line in the prompt body
- sound cue marker such as `VOICE`, `RADIO`, `PA`, `WHISPER`

Storyboard board should not put full dialogue paragraphs across thumbnails.

Seedance prompt should write:

- exact original line or exact contiguous fragment from the script whenever the segment contains dialogue/voiceover
- speaker's immediate emotion, hidden intention, psychology, facial expression, and body tension before the line
- delivery tone: volume, breath, hesitation, tempo, firmness/weakness, and whether the voice breaks or stays controlled
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

- whispered or tense line: 2-3 Chinese characters per second
- normal dramatic speech: 3-4 Chinese characters per second
- urgent command: 4-6 Chinese characters per second only for a short burst, then reaction pause
- public speech: split across multiple segments unless it is one slogan-like line

For a line to land, add:

- pre-line breath or eye decision: 0.3-1.0s
- line delivery
- post-line reaction or silence: 0.5-2.0s

If the line cannot fit with reaction time, split the segment. The split must use exact contiguous fragments and mark the continuation; never paraphrase or remove words.

## Dialogue Prompt Pattern

```text
对白: CHAR_A 此刻强压恐惧，眼神先避开再重新盯住对方，嘴角发紧，先吸气0.4s；用压低但稳定的声音说"[逐字保留原文短句]"，约3-4字/秒；说完停0.8s，CHAR_B不立刻回答，眼神先下移再抬起。对白只作为声音/口型/表演节奏，不出现字幕或画面文字。
```

For script work:

```text
原文台词锁：CHAR_A：（先写当下情绪/心理/表情/呼吸/音量/语气，再接原稿动作或语气）"逐字保留用户剧本台词。"
台词承接：如果本段只说前半句，下一段必须从下一个字继续，不得改写。
```

## Hard Fail

Fail or repair if:

- subtitles appear in a clean narrative frame without request
- any original script dialogue/voiceover line is omitted, paraphrased, shortened, polished, or moved without exact continuation
- random text appears because dialogue was written on the storyboard thumbnail
- speech is too fast for the emotion
- the listener has no reaction beat
- characters speak while their face/body performance contradicts the line
- generated text replaces spoken performance
