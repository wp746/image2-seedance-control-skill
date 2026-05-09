# Prompt Library Index

This skill uses a modular prompt library. Do not overwrite the core workflow when the user provides a strong reference prompt. Add it to the proper branch and update this index.

## Branches

### Asset Prompt Branch

Path: `references/asset-prompts/`

Use for Image2 prompts that design stable visual assets:

- character asset boards
- scene asset boards
- prop asset boards
- wardrobe/material boards
- style/look bibles
- monster/creature sheets
- live-action actor continuity sheets

Current files:

- `character-design-sheet.md`: director-level character design sheet pattern for humans, creatures, monsters, and recurring roles.
- `ue5-metahuman-technical-sheet.md`: technical UE5/MetaHuman-style character reference sheet for strict multi-view continuity, asymmetry, body landmarks, hands/feet, hair/groom, costume/armor/prop detail.
- `cinematic-character-card-generator.md`: film-production character card generator pattern for text/photo inputs, identity preservation, height scale, wardrobe/material breakdown, and AI真人剧 character continuity.
- `master-character-reference-sheet.md`: clean 4:3 single-character master reference sheet for Seedance identity control, with dominant scale sheet, exact expression progression, micro-expressions, head angles, posture, close-up, wardrobe callouts, optional prop, and hand gestures.
- `simple-seedance-character-reference-sheet.md`: lightweight clean Seedance character reference sheet for stylized 3D characters, robots, mascots, simple creatures, and fast identity locking.
- `cultural-child-character-card.md`: culturally grounded child/teen character card pattern for regional authenticity, child proportions, height scale, local wardrobe logic, and actor-like micro-performance.
- `animated-cinematic-character-pitch-board.md`: high-budget animated cinematic character pitch-board pattern for GPT Image 2, emphasizing art-directed asymmetric composition, human vs stylized creature layout choices, character psychology, actor-like performance direction, signature quote, action/idle poses, wardrobe/material accuracy, strict turnaround, head studies, cinematic portrait, always-present props, color/texture guide, and production-ready fidelity notes for film, Seedance, merchandising, and pitch decks.

### Storyboard Prompt Branch

Path: `references/storyboard-prompts/`

Use for Image2 prompts that design Seedance-readable shot boards:

- timing boards
- scene segment storyboards
- action choreography boards
- dialogue scene boards
- product ad boards
- MV rhythm boards
- episode scene boards

Current files:

- `storyboard-control-board.md`: baseline Seedance 2.0 storyboard control board pattern.
- `infographic-8-shot-poster.md`: clean 8-panel infographic storyboard poster for 12-15 second product/process/lifestyle/social ad sequences.
- `two-part-cinematic-production-board.md`: 25-40 second cinematic/story/emotional short pattern using one or two boards split into Storyboard 1 and Storyboard 2, generated separately in Seedance then edited together.
- `sixteen-panel-dance-choreography-board.md`: 4x4 sixteen-panel choreography/storyboard pattern for dance, cultural performance, martial forms, fabric/water/reflection motion, and ordered body-action nodes.
- `smart-shot-directing-sheet.md`: complete cinematic directing sheet method that turns one idea into character references, environment design, floor plan/blocking, side elevation, storyboard, camera plan, lighting notes, mood/style, and cinematography notes before Seedance rendering.
- `previs-action-vfx-music-timeline.md`: director-style PREVIS action storyboard pattern for kinetic action, dance, ink/paint/energy VFX, strict color logic, music/SFX timing, and 2-second beat Seedance timelines.
- `luxury-ad-creative-direction-board.md`: 15-20 second high-end commercial creative direction board for fragrance, car, travel/hotel, skincare, fashion, and premium product ads with styling, set design, route guide, 8-scene storyboard, lighting, audio, cinematography, and Seedance prompt.
- `asset-locked-lookbook-camera-storyboard.md`: asset-locked production board for user-provided characters, products, vehicles, props, or scenes, combining asset reference modules, location/camera floor plan, and a 5-frame Seedance storyboard.
- `vertical-fragrance-mood-ad.md`: 9:16 vertical 12-shot mood storyboard pattern for fragrance, skincare, beauty, quiet UGC-style premium ads, and 15-second atmosphere films.
- `sports-highlight-sequence-board.md`: sports highlight storyboard pattern for tackle-to-goal, fast break, race overtake, or other action chains requiring ball/object continuity, broadcast camera logic, and realistic sports physics.
- `traditional-storyboard-table-board.md`: traditional storyboard table pattern for Seedance-readable 5-8 shot boards with shot number, timing, shot size, frame thumbnail, camera movement, action, dialogue, sound/music, and continuity notes.
- `cinematic-production-plan-sheet.md`: compact GPT Image 2 cinematic pre-production plan sheet pattern for turning one simple idea into a Seedance-readable board containing character references, environment, top-down floor plan, movement paths, numbered camera positions, 4-6 shot storyboard, color palette, lighting, mood, and style notes.
- `one-line-smartshot-storyboard.md`: fast Smartshot-style pattern for expanding one short idea into a detailed 6-9 panel storyboard image with character locks, environment lock, camera style, color/VFX notes, ready video prompt summary, and continuation-friendly final frame.
- `integrated-15s-commercial-production-board.md`: one-page 15-second commercial production board pattern for food, drink, tourism-specialty, mascot, kids/family, anime, and stylized brand ads, combining light asset locks, product/prop design, set design, camera map, palette, sound notes, negative notes, and a 5-shot timeline table.

### Seedance Prompt Branch

Path: `references/seedance-prompts/`

Use for Seedance 2.0 video prompts that turn existing Image2 assets/storyboards into motion:

- relationship introductions
- product ad timelines
- dialogue scenes
- action/martial arts
- VFX/dance prompts
- scene continuation prompts
- reference-image binding language

Current files:

- `romantic-couple-introduction.md`: Seedance relationship-introduction prompt using a couple character sheet, detail -> identity -> relationship -> presence -> full reveal.
- `product-ad-timeline.md`: concise product ad timeline prompt structure for 12-20 second commercials using product boards/storyboards.
- `cinematic-production-sheet-timeline.md`: Seedance prompt pattern that treats an uploaded Image2 cinematic production plan sheet as a strict directing document, preserving character identity, scene geography, CAM positions, shot order, color, lighting, VFX, and continuity for a 4-15 second segment.
- `character-storyboard-first-pass-continuation.md`: Seedance prompt pattern for using a character/location sheet plus 3x3 storyboard as first-pass references, then using the previous 15-second video's last frame as the main reference for seamless 15-30 second continuation while keeping original sheets as secondary continuity anchors.
- `named-reference-stack-action-prompt.md`: Seedance prompt pattern for multi-reference action scenes using explicit labels such as `@[CurrentStoryboardRef]`, `@[HeroRef]`, `@[VillainRef]`, and `@[LocationRef]` so each uploaded image has one clear responsibility: shot flow, identity lock, antagonist lock, or environment lock.

### Production SOP Branch

Path: `references/production-sop/`

Use for industrialized long-form or multi-segment production control:

- project continuity bibles
- shot seam checking
- Seedance repair and regeneration
- version/state tracking
- post-generation quality control

Current files:

- `project-continuity-bible.md`: project-level continuity bible for locking characters, scenes, props, timeline, style, sound, VFX, emotion, and forbidden drift across clips, scenes, episodes, or long-form production.
- `shot-seam-review.md`: shot-to-shot and segment-to-segment continuity review SOP using IN state, action, OUT state, next handoff, direction, emotion, light, sound, and edit checks.
- `seedance-repair-sop.md`: post-generation defect diagnosis and repair workflow for identity drift, scene drift, prop drift, motion failure, camera failure, emotion failure, style failure, and seam failure.

## Selection Rule

Before writing the final Image2 prompt file:

1. Identify the project type.
2. Identify required assets.
3. Identify storyboard type by scene function: action, dialogue, emotional beat, product, MV, travel, horror, comedy, etc.
4. For multi-segment, multi-scene, episode-based, or industrial production, identify required Production SOP files.
5. Load only the relevant reference file(s).
6. Adapt the pattern to the user's project. Do not copy reference prompts blindly.

## Update Rule

When the user provides a high-quality prompt reference:

1. Decide whether it belongs to asset prompts or storyboard prompts.
2. Save it as a new reference file or merge its reusable technique into an existing file.
3. Preserve the core idea and applicability conditions.
4. Add it to this index.
5. Do not replace unrelated existing branches.
