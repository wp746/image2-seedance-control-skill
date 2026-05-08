# Seedance Repair SOP

Use this SOP after Seedance 2.0 generates a video segment and the output has drift, weak motion, broken continuity, or poor editability.

The goal is not to regenerate blindly. Diagnose the defect, choose the smallest repair, and preserve usable footage.

## Repair Workflow

1. Compare output against original user assets, formal asset boards, storyboard board, project continuity bible, and previous segment out frame.
2. Classify the defect.
3. Decide repair level.
4. Rewrite only the needed prompt, board, or segment.
5. Regenerate or patch.
6. Re-check seams.

## Defect Categories

### 1. Identity Drift

Symptoms: face changes, age changes, hairstyle changes, body proportion changes, costume redesign, character becomes a different actor.

Repair:

- upload original asset and formal character sheet together
- add stronger identity lock
- reduce storyboard density
- use closer reference frame
- regenerate only the affected segment

Repair language:

```text
严格保持 CHAR_A 与上传角色资产完全一致：同一张脸、同一年龄感、同一发型、同一五官比例、同一服装结构。不要重新设计角色，不要改变演员身份。
```

### 2. Scene Drift

Symptoms: layout changes, door/window/object positions change, time/weather changes, background becomes another location.

Repair:

- add scene asset board or floor plan
- state fixed anchors
- lock entrance/exit and light direction
- regenerate with fewer shots

Repair language:

```text
严格保持 SCENE_01 空间布局：入口在画面左后方，主光来自右侧，桌子/车辆/门/路口位置不变。禁止场景翻转、换地点、改变时间和天气。
```

### 3. Prop / Product Drift

Symptoms: prop shape/color changes, logo/text unreadable, hand switches prop, product scale changes.

Repair:

- include prop asset board
- specify hand relationship
- avoid long shots where product must be readable
- use insert shot or macro close-up

Repair language:

```text
严格锁定 PROP_01 的形状、尺寸、颜色、材质和持握方式。道具始终在 CHAR_A 右手中，不能变形、换色、消失或新增部件。
```

### 4. Motion Failure

Symptoms: action not completed, movement melts or floats, physics wrong, body parts distort, too many actions happen at once.

Repair:

- split action into fewer beats
- one primary action per shot
- add start/end pose
- use simpler camera movement
- reduce VFX load

Repair language:

```text
本镜头只执行一个主动作：CHAR_A 从车门内迈出右脚并站稳。不要同时转身、挥手、奔跑或做多余动作。动作从静止开始，到站稳结束。
```

### 5. Camera Failure

Symptoms: camera jumps randomly, impossible orbit, framing loses subject, lens language changes, camera contradicts floor plan.

Repair:

- lock camera position and movement
- use `locked-off`, `slow push-in`, `side tracking`, etc.
- match CAM number from floor plan
- reduce complex camera moves

Repair language:

```text
镜头使用 CAM 3，85mm 人像特写，轻微 slow push-in。不要旋转镜头，不要突然切换机位，不要拉远，不要丢失人物面部。
```

### 6. Emotion / Performance Failure

Symptoms: emotion too flat, emotion jumps too fast, wrong expression, no reaction after conflict.

Repair:

- add micro-expression instruction
- add reaction shot or hold frame
- define emotional start and end
- reduce external movement

Repair language:

```text
情绪从克制紧张逐渐转为坚定，不要突然大笑或崩溃。眼神先回避，随后看向镜头，嘴角只有极轻微变化。
```

### 7. Light / Style Failure

Symptoms: different grade, lighting direction changes, glossy scene becomes documentary or animation, VFX changes color/texture.

Repair:

- restate global style bible
- lock palette and light direction
- include previous best frame as reference
- regenerate segment with style lock first

Repair language:

```text
保持全片统一的深黑高端电影调色，紫金点缀，强侧逆光和闪光灯曝光感。禁止变成白天、低饱和纪录片、卡通或普通商业棚拍。
```

### 8. Seam Failure

Symptoms: next segment does not start from previous ending, character position jumps, sound or emotion breaks, action repeats or skips.

Repair:

- write previous out frame and next in frame explicitly
- use the previous segment's final frame as reference
- add sound bridge
- rewrite first 1-2 seconds of next segment

Repair language:

```text
本段第一帧必须承接上一段最后画面：CHAR_A 站在车门旁，身体朝右，右手扶着车门，紫色礼服被风吹向画面左侧，闪光灯仍在背景闪烁。
```

## Repair Level Decision

- Level 1: Prompt tightening. Use when the shot is mostly correct but needs stronger constraints.
- Level 2: Segment regeneration. Use when the shot concept is correct but execution fails.
- Level 3: Storyboard rewrite. Use when the board asked for too much or the shot logic is flawed.
- Level 4: Asset rebuild. Use when Seedance cannot hold the asset because the source is unclear.

## Repair Output Format

When producing a repair prompt, write:

```markdown
## Repair Diagnosis
- 问题类型:
- 影响镜头:
- 原因:
- 保留可用部分:
- 需要重做部分:

## Repair Strategy
- 修复等级:
- 参考资产:
- 关键锁定:
- 接缝要求:

## Seedance Repair Prompt
```text
...
```
```

Keep repair prompts narrow. Do not rewrite the whole film unless the continuity bible or asset system is wrong.
