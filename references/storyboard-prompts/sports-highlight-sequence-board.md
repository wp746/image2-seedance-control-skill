# Sports Highlight Sequence Board Pattern

Use this pattern for sports highlight videos where a complete play must be shown from setup to payoff, such as tackle-to-goal, steal-to-dunk, serve-to-point, sprint finish, or fight-combo-to-knockdown.

## Best For

- football/soccer highlight sequence
- basketball fast break
- racing overtake
- combat sports exchange
- athletic product ads with real sports action
- any sequence where sports physics and action causality matter

## Core Intent

Create a cinematic sports storyboard that preserves:

- ball/object continuity
- athlete identity and jersey continuity
- cause-and-effect action
- field/court geography
- broadcast camera logic
- realistic physics

Sports videos can look impressive but fail if the ball, receiving action, foot contact, or player direction breaks. The board must make these physical relationships explicit.

## Required Structure

For a tackle-to-goal football sequence:

1. midfield pressure / setup
2. clean tackle or interception
3. recovery and first touch
4. counterattack acceleration
5. close-up of boots striking ball
6. wide shot of field opening
7. key pass through defenders
8. sprint toward goal
9. penalty-box approach
10. strike / curled finish
11. ball hits net and goalkeeper reaction
12. celebration

Adapt to other sports by preserving the same logic:

defensive action -> possession/control -> acceleration -> key skill -> final attempt -> impact/result -> reaction.

## Board Requirements

Use:

- professional sports broadcast style
- dynamic stadium lighting
- dramatic crowd atmosphere
- varied camera angles
- wide, tracking, close-up, POV, slow motion
- realistic motion blur
- clear field/court orientation
- arrows for player movement and ball movement
- numbered action beats

## Sports Physics Locks

Add explicit notes:

- ball must stay visible at key contact moments
- player must actually receive/pass/shoot the ball
- foot must contact the ball before the ball changes direction
- no teleporting ball
- no duplicate ball
- no impossible body mechanics
- same jersey number/person through the play
- goalkeeper reaction must follow shot direction
- crowd/stadium should not distract from action logic

## Reusable Image2 Instruction Block

```text
请创作一张高质量 4K 电影级体育高光分镜图，展示一个完整的比赛动作链条，从防守/抢断开始，到快速推进、关键传球、最终得分和庆祝。整体使用专业体育转播风格、动态球场灯光、戏剧化观众氛围、真实运动模糊和强动作因果。

分镜必须清楚标出球员运动方向、球的运动方向、关键触球点、传球路线、射门路线和最终结果。每个动作必须符合真实体育物理：球不能瞬移，球员必须真正接到球再传或射，脚触球后球才改变方向，不能出现重复球或不可能身体动作。

使用多种镜头角度：广角、跟拍、特写、主观视角、慢动作、广播长焦。故事节奏必须从防守强度转为进攻胜利，最后落到情绪庆祝。
```

## Reusable Seedance Prompt Controls

```text
Strictly follow the storyboard action order. Preserve ball continuity and player continuity. The ball must remain visible at every key touch. Each pass, dribble, tackle, and shot must have clear physical cause and effect. No teleporting ball, no duplicate ball, no impossible foot contact, no random player switching, no jersey number drift. Use professional sports broadcast camera language with wide tactical shots, tracking runs, close-ups of boots/ball contact, slow-motion impact, and crowd reaction only after the goal.
```

## Known Failure Modes

Watch for:

- ball rolling past player without being received
- ball direction changing without foot contact
- same player appearing as multiple jersey numbers
- defenders teleporting
- goalkeeper reacting before shot
- Hollywood-style soccer that ignores real football logic

If the sport is important, create a more detailed storyboard than usual.

## When Not To Use

Avoid this pattern for non-sports action, dance, or abstract VFX.

Use `previs-action-vfx-music-timeline.md` for stylized action/VFX.
