# Scene Nine-View Layout Bible

Use this for every recurring or important scene. The goal is not to create a beautiful environment poster; the goal is to make Seedance reproduce the same space accurately.

## Fixed Layout

Default canvas: 16:9 horizontal, inheriting `PROJECT_BOARD_SYSTEM`.

One board usually controls one scene code only. Do not mix unrelated locations into one scene board unless making a high-level location index.

## Required Nine Views

For a standard scene asset, create a 3x3 nine-view board:

1. `V01 ESTABLISHING / 建立`: wide exterior or full room view.
2. `V02 ENTRANCE / 入口`: main entry direction.
3. `V03 EXIT / 出口`: exit or reverse direction.
4. `V04 CAMERA A / 机位A`: primary shooting angle.
5. `V05 CAMERA B / 机位B`: reverse angle.
6. `V06 CAMERA C / 机位C`: side or diagonal angle.
7. `V07 DETAIL / 关键物`: key fixed object, furniture, sign, window, road, ridge, door, etc.
8. `V08 LIGHT / 光线`: light source and shadow direction.
9. `V09 SCALE / 尺度`: faceless human placeholders showing scale and standing/sitting/action zones.

Add a bottom strip or corner mini-map:

- top-down floor plan / geography map
- entrance/exit arrows
- camera-safe zones
- character standing zones
- prop anchor zones
- light direction
- no-go / forbidden layout drift

## Indoor Scene Rules

Must lock:

- walls, ceiling height, floor material
- doors and windows
- fixed furniture positions
- practical lights and light direction
- camera positions and safe zones
- character blocking zones
- prop anchor positions

If day and night both appear, either:

- create separate `SCENE_01_DAY` and `SCENE_01_NIGHT`, or
- create one nine-view board with two clearly separated light-state swatches, only if the space is simple.

## Outdoor Scene Rules

Must lock:

- horizon and main direction
- roads, rivers, slopes, ridges, buildings, gates, bridges
- sun/moon/weather direction
- foreground/midground/background layers
- crowd or vehicle path zones
- camera-safe zones

Do not turn scene boards into landscape postcards. Use labels, arrows, floor/geography plan, and scale placeholders.

## Human Placeholders

Scene boards should not create new character identities.

Use:

- faceless grey silhouettes
- labeled position markers: `CHAR_A POS`, `EXTRA ZONE`
- backs or distant figures without readable faces

Do not show clear main-character faces in scene boards unless the user explicitly asks for an asset-locked integrated board.

## Image2 Prompt Injection

Chinese:

```text
必须使用固定九视角场景资产版式：同一个SCENE只做一个空间，3x3九宫格展示建立镜头、入口、出口、机位A、机位B、机位C、关键物、光线、尺度。底部必须有俯视平面图/地理图，标注入口出口、摄影机安全区、人物占位区、道具锚点、光线方向和禁止漂移。只使用无脸灰色人形或位置标记，不得生成清晰主角脸。不要风景海报，不要混入故事板。
```

English:

```text
Use the fixed nine-view scene asset layout: one SCENE code per board, 3x3 grid showing establishing view, entrance, exit, camera A, camera B, camera C, key fixed detail, lighting direction, and scale view. Add a bottom top-down floor/geography plan with entrance/exit arrows, camera-safe zones, character blocking zones, prop anchors, light direction, and forbidden drift. Use faceless grey silhouettes or position markers only; do not create clear main-character faces. This is not a landscape poster and not a storyboard.
```

## Negative Rules

- no mixed locations in one recurring scene board
- no clear character identity faces
- no random time/weather variants unless scripted
- no decorative poster layout
- no tiny labels
- no flipped floor plan
- no movable doors/windows/furniture between views
