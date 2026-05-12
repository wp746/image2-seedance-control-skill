# Prop Asset Board Pattern

Use this pattern for props that repeat across shots, enter close-up, drive the plot, carry brand/product information, or require consistent hand interaction.

## Applicability

Use for:
- hero props that appear in multiple shots
- products for commercial/advertorial content
- handheld objects: phones, weapons, tools, documents, jewelry
- vehicles: cars, motorcycles, bikes, boats
- brand-critical items: logos, packaging, labels
- anything Seedance must render with consistent shape, material, and color

Do not use for:
- background objects with no close-up
- one-use items that appear in a single frame
- generic environmental clutter

## Core Pattern

The Image2 board should feel like a prop master's continuity reference sheet. It locks the object's physical identity.

Must include:

- **Prop code**: e.g. `PROP_PHONE`, `PROP_SWORD`, `PRODUCT_01`, `VEHICLE_01`
- **Front / side / detail view**: at least 2-3 consistent views of the same object. Include a macro close-up for any readable text, logo, or distinctive feature
- **Material**: metal, plastic, fabric, wood, glass, leather — be specific about finish (matte, glossy, brushed, weathered)
- **Scale**: relative to hand, body, or a common reference object
- **Color**: exact color with any gradient, pattern, or reflective quality
- **How the hand holds or uses it**: show grip, trigger position, screen orientation, carrying posture. Lock which hand (left/right) and how fingers interact
- **Where it appears in the story**: scene context for state changes (clean → damaged, closed → open, on → off)
- **Forbidden drift**: shape change, color change, material change, unreadable text/logo, random extra parts, scale shift, hand switch

## Prop Types

### Handheld Product / Device

- Front, side, back, screen-on state
- Hand grip reference: which hand, finger positions
- Screen content if critical: keep it large, short, readable
- Brand logo position and size locked

### Weapon / Tool

- Full object from multiple angles
- Grip/holding reference
- Material and wear marks
- Action state: holstered, drawn, activated, damaged

### Vehicle

- Full side profile, front 3/4, rear 3/4
- Distinctive features: grille, lights, wheels, badges
- Color and finish: paint type, reflections, dirt/weathering
- Camera reference: hero angle for product shots

### Jewelry / Accessory

- Macro detail for texture and material
- On-body reference: ear, neck, wrist, hand position
- Light interaction: sparkle, reflection, transparency

### Document / Sign / Screen

- Keep text short, large, isolated
- Use a separate UI/prop board if content is complex
- Show reading angle and hand relationship

## Reusable Instruction Block

```text
这是给 Seedance 2.0 读取的道具资产连续性板，不是产品海报。请展示 PROP_01 的多角度和细节锁定。

必须包含：
- 道具编号：PROP_01
- 正面、侧面、细节特写视图，所有视图保持同一物体
- 材质：具体材质和表面处理（哑光/光泽/拉丝/做旧）
- 尺寸：相对于手或身体的参考比例
- 颜色：精确颜色及渐变色/图案/反光特性
- 持握方式：哪只手、手指位置、使用姿态
- 故事中出现位置：道具状态变化说明
- 大号禁止漂移标签：DO NOT CHANGE SHAPE / DO NOT CHANGE COLOR / KEEP MATERIAL / KEEP HAND POSITION

版式：道具师的连续性参考板，不是海报，不是概念图。文字大而清楚，物体身份一眼锁定。
```

## Drift Labels

Use short, large labels:
- DO NOT CHANGE SHAPE
- DO NOT CHANGE COLOR
- KEEP MATERIAL
- KEEP HAND POSITION
- KEEP LOGO READABLE
- DO NOT ADD PARTS
- DO NOT CHANGE SCALE
