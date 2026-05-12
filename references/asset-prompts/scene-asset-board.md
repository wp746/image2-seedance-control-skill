# Scene Asset Board Pattern

Use this pattern when the project has recurring or important locations that must stay visually consistent across shots and segments.

## Applicability

Use for:
- recurring indoor or outdoor locations
- any location Seedance must render consistently across multiple shots
- complex environments with fixed objects and light sources

Do not use for:
- one-off establishing shots with no continuity requirement
- abstract/generative backgrounds with no fixed geography

## Core Pattern

The Image2 board should feel like a film-production location scout + art department reference. It locks the physical reality of the space.

Must include:

- **Scene code**: e.g. `SCENE_01`, `SCENE_OFFICE`, `SCENE_STREET`
- **Multiple angles of the same space**: at least 3-4 consistent views (wide establishing, mid, close detail, reverse angle). All must show the same room/space with the same geometry, light, and objects
- **Entrance and exit**: clearly label doors, passages, stairs, or any entry/exit the camera or characters will use
- **Camera-safe zones**: mark areas where the camera can safely position without breaking set continuity
- **Light direction and atmosphere**: lock the primary light source direction, quality (hard/soft), color temperature, and any atmospheric elements (dust, fog, rain)
- **Key furniture/objects and their fixed positions**: tables, chairs, doors, windows, vehicles, signs, plants — everything that should not move between shots
- **Color palette**: dominant wall/floor/ceiling colors, material finishes, accent colors
- **Forbidden drift**: layout flip, object pop-in/out, door/window position change, time/weather change unless scripted, light source relocation

## Scene Types

### Interior

- Show walls, ceiling height, floor material
- Door and window positions locked
- Light source: practical lamps, windows, overhead
- Furniture layout as top-down + 3/4 view

### Exterior

- Show geography, horizon, sky direction
- Building/structure positions locked
- Light source: sun/moon position, weather state
- Background depth and any moving elements (traffic, pedestrians, water)

### Vehicle Interior

- Show seat positions, window layout, dashboard/controls
- Light source: windows, interior lights
- Camera-safe zones within vehicle
- Driver/passenger eyeline and hand positions

## Reusable Instruction Block

```text
这是给 Seedance 2.0 读取的场景资产连续性板，不是风景海报。请使用清晰大标签展示 SCENE_01 的多角度空间锁定。

必须包含：
- 场景编号：SCENE_01
- 同一空间的多个角度（广角建立、中景、细节、反向），所有角度必须展示同一空间、同一几何结构、同一光线和物体位置
- 入口和出口位置，用箭头标注
- 摄影机安全区：标记 CAM 可以放置的区域
- 主光源方向和光质（硬/柔）、色温、大气元素
- 关键家具/物体的固定位置：桌椅、门窗、车辆、标牌、植物等
- 主色调和材质
- 大号禁止漂移标签：DO NOT FLIP LAYOUT / DO NOT MOVE DOORS / DO NOT CHANGE WEATHER / KEEP LIGHT DIRECTION

版式：影视美术部门用的场景参考板，不是海报，不是概念图。文字大而清楚，空间关系一目了然。
```

## Drift Labels

Use short, large labels:
- DO NOT FLIP LAYOUT
- KEEP DOOR POSITION
- KEEP LIGHT DIRECTION
- DO NOT CHANGE WEATHER
- DO NOT MOVE FURNITURE
- DO NOT CHANGE TIME OF DAY
