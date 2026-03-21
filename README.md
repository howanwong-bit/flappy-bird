# Flappy Bird — Demon Slayer Edition

A Demon Slayer-themed Flappy Bird game built as a single, dependency-free HTML file.

## Characters

Each character has a unique visual style, elemental trail, ambient aura, exclusive breath attack, and super attack:

| Character | Breathing Style | Trail | Breath Attack | Super Attack |
|-----------|----------------|-------|---------------|--------------|
| Tanjiro | Water | Blue droplets + ripple rings | Tenth Form: Constant Flux | Total Concentration: Raging Torrent |
| Zenitsu | Thunder | Electric sparks + zigzag bolts | First Form: Thunderclap Flash | God Speed: Heaven's Thunder |
| Inosuke | Beast | Wind arc slashes | Seventh Fang: Spatial Awareness | Beast Rampage: Primal Fury |
| Rengoku | Flame | Flickering flames + embers | Ninth Form: Rengoku | Flame Breathing: Purgatory |
| Shinobu | Insect | Butterfly scales + poison wisps | Dance of the Butterfly God | Insect Breathing: Compound Eye Hexagon |
| Tengen | Sound | Sound rings + gem sparks | Fourth Form: Constant Resounding Slashes | Sound Breathing: String Performance |
| Muichiro | Mist | Slow mist wisps | Seventh Form: Obscuring Clouds | Mist Breathing: Sea of Clouds and Haze |
| Mitsuri | Love | Pink petals | Sixth Form: Cat-legged Winds of Love | Love Breathing: Swaying Love Wildly |
| Giyu | Water | Deep blue droplets + still ripples | Eleventh Form: Dead Calm | Water Breathing: Flowing Dead Calm |
| Gyomei | Stone | Stone chunks | Fifth Form: Arcs of Justice | Stone Breathing: Volcanic Rock Rapid Conquest |
| Sanemi | Wind | Sharp wind slashes | Ninth Form: Idaten Typhoon | Wind Breathing: Slashing Tornado |
| Obanai | Serpent | Serpentine green sparks | Fifth Form: Slithering Serpent | Serpent Breathing: Coiling Serpent Slash |

## Enemies

Three types of demons spawn and fly across the screen, increasing in difficulty with each stage:

| Enemy | Appears | Movement | Description |
|-------|---------|----------|-------------|
| Flesh Demon | Stage 1+ | Straight | Dark red body, twin horns, glowing red eyes |
| Spider Demon | Stage 3+ | Sine-wave float | Pale purple, 6 animated legs, 4 red eyes, web markings |
| Upper Moon | Stage 5+ | Fast wave | Dark violet, rotating markings, kanji (上), purple glow |

## Core Mechanics

**Flap** — Press/tap to jump upward and navigate pipe gaps.

**Glide** — Hold Space/mouse/touch while falling. The bird soars slowly downward instead of dropping.

**Breath Attack** — The core combat mechanic:
1. Hold Space/mouse/touch to enter glide and charge your breathing technique
2. A charge arc fills around the bird with a character-specific elemental aura
3. Release to fire the breath attack — a projectile that travels forward and kills any demon it hits
4. Touching an enemy directly while gliding also kills it instantly
5. Each demon kill awards +5 points and is tracked separately as a kill count (☠)

**Scoring:**
- Passing a pipe: +1
- Collecting a coin: +2
- Killing a demon (glide contact or breath attack): +5

## Game Features

- **Progressive Stages** — every 10 points advances the stage, increasing pipe speed, tightening gaps, and scaling enemy spawn rate (up to ×1.7 speed, 88px minimum gap)
- **Oscillating Pipes** — after Stage 3, pipes move vertically
- **Dynamic Sky** — background shifts from night blue → purple dusk → demon red → blood moon
- **Shield Orb** — ~15% spawn chance per pipe; blue orb absorbs one collision (180 frames); rare golden **Super Shield** (~5%) lasts 450 frames (2.5× duration)
- **Leaderboard** — top 10 scores stored in `localStorage` with name, score, difficulty, and stage
- **Procedurally Generated Music** — original A-minor action score via Web Audio API (melody, bass, taiko percussion); no audio files required

## Controls

| Action | Input |
|--------|-------|
| Flap (jump up) | Press Space / Click / Tap |
| Glide + charge attack | Hold Space / Hold mouse / Hold touch |
| Release breath attack | Release Space / mouse / touch |
| Navigate menus | Click / Tap |
| Return to menu | Space (from leaderboard or dead screen) |

## Screen Sizes

| Size | Resolution |
|------|-----------|
| Small | 560 × 560 |
| Medium | 820 × 680 |
| Large | 1080 × 820 |

## HUD

- **Score** — large number at top center
- **Stage · Difficulty** — badge below score
- **☠ N** — demon kill counter (top-left)
- **Charge bar** — fills while gliding; shows technique name; flashes white at full charge
- **Shield bar** — shown when shield is active

## Technical Details

- **Single file** — all game logic, audio, and rendering in `index.html`
- **No dependencies** — vanilla JavaScript + Canvas 2D API + Web Audio API
- **Rendering** — `requestAnimationFrame` game loop at native refresh rate
- **Storage** — `localStorage` key: `flappyDSScores`

## Running

```bash
# Option 1: direct browser open
start flappy-bird/index.html

# Option 2: local server (avoids any browser file restrictions)
npx serve flappy-bird
```
