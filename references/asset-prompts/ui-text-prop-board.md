# UI / Text Prop Board Pattern

Use this when exact or semi-exact text appears as a prop or interface:

- phone screen
- chat message
- contract
- telegram
- document
- sign
- brand slogan
- map label
- warning label
- rule card
- title card intended for post

## Core Rule

Text-bearing props should be isolated in a prop/UI board. Do not put complex readable text inside storyboard thumbnails or final clean narrative frames.

## Reusable Image2 Prompt

```text
请创建一张 UI_TEXT_PROP_BOARD / 文字道具与界面参考板，用于锁定剧情中需要出现的文字类道具。

这不是故事板，不是最终视频画面。它只负责道具文字、界面布局、纸张/屏幕材质、持握关系和可读性。

必须包含：
1. PROP/UI 编号：[PROP_CODE]
2. 文字内容：只保留剧情必须文字，短、大、清晰；复杂长文用版式块表示，不要求模型生成每个小字。
3. 载体材质：手机屏幕/纸张/木牌/金属牌/墙面/布标等。
4. 尺寸与比例：相对手、桌面、墙面或人物的比例。
5. 使用方式：谁拿、哪只手、距离镜头多近、是否需要特写。
6. 清洁版本：无手持、正面、无遮挡。
7. 场景版本：在真实光线和环境中出现，但不进入故事板缩略图主体。
8. 禁止项：不要乱码、不要随机字、不要多余文字、不要把这张板当成字幕、不要把文字扩散到背景。

如果最终视频需要字幕、标题或说明文字，标注为“后期添加”，不要要求 Seedance 在画面中生成。
```

