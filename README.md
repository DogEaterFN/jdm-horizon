# JDM Horizon | Sakura Drift

An arcade drift game that doubles as a math practice tool. Drive a stylized AE86, RX-7, or R34 through a flat sakura touge or around a snow-capped Mt. Fuji with a neon tunnel piercing its core. Fuel and tires drain as you drive, and the only way to refuel is to answer math questions at the gas station.

Built in a single HTML file using Three.js and the WebAudio API. No build step, no dependencies to install, no asset files to download.

## The Math Angle

The game is built around a small bank of statistics, algebra, and arithmetic questions. Fuel and tires drain as you drive, NOS depletes after use, and the only way to refill any of them is to answer a math question at the gas station.

Each question is rated **Easy**, **Medium**, or **Hard**, with the gauge refill scaling accordingly:

| Difficulty | Refill |
| --- | --- |
| Easy | +10% |
| Medium | +15% |
| Hard | +20% |

Wrong answers still grant half credit, so you can recover without being stranded.

Topics covered include:

- Median (Q2), mode, IQR, range, mean
- Absolute value and scientific notation
- Area and circumference formulas (circle, triangle)
- Order of operations with nested absolute values
- Ratios reduced to lowest form
- Linear equation form

A built-in **Stats** tab (ESC > Stats) tracks total questions answered, accuracy %, and a per-difficulty breakdown. This gives you (or your teacher) a clean readout of how much practice you've actually put in.

## Controls

| Action | Key |
| --- | --- |
| Accelerate | W |
| Brake / Reverse | S |
| Steer Left / Right | A / D |
| Handbrake (drift) | Space |
| NOS (10-second boost) | Q |
| Use gas station | E |
| Cycle day / sunset / night | T |
| Toggle rain | V |
| Cycle camera | C |
| Respawn | R |
| Settings | Esc |

## Features

- **3 cars**: 1983 Toyota Sprinter Trueno AE86, 2000 Mazda RX-7 FD Type RB, 2000 Nissan Skyline R34 GT-R. Each has distinct stats and a different engine sound (4-cylinder, rotary, inline-6) synthesized live in the WebAudio API.
- **2 maps**: Sakura Plaza (flat karting touge with cherry blossoms, asphalt paddock, and red/white curbs) and Mt. Fuji Touge (windy loop around a snow-capped volcanic peak with a neon tunnel piercing the mountain).
- **Drift combo system**: Chain consecutive clean drifts to build a multiplier from x1.5 up to x8.0. Each combo bank is cashed in when you straighten cleanly. Crashing into a wall resets the multiplier AND forfeits the in-progress drift bank.
- **Upgrades**: Speed, grip, drift, NOS tank. Each car upgrades independently, persists across sessions.
- **Lap timer**: Detects laps via quadrant tracking, prevents reverse-shortcuts, stores best time per car / per map.
- **Mini-map**: Top-right overlay showing track outline, gas station, tunnel entrances, and your heading.
- **Weather**: Press V to toggle rain. Lateral grip drops 38% in the wet, drifting kicks in much earlier.
- **Time of day**: Day, sunset, and night with custom sky shaders. Headlight cones glow only at night.
- **Tunnel**: Fully enclosed concrete walls with arched ceiling, sunset-palette neon strips along the walls, ceiling apex, and floor edges, point lights for ambient glow, and stone facade portals at each entrance.
- **Crash penalty**: Hard wall hits cost 10% of your coins (with a 1.5s cooldown so a single bump doesn't drain you).
- **Brake light pulse**: Taillights brighten when you press S, bloom amplifies the effect at night.
- **Graphics presets**: Low / Medium / High via ESC > Settings > Graphics. Toggles shadow res, bloom, env reflections, clearcoat paint, particle counts, and multisample AA.
- **Pause on blur**: Game freezes when the window loses focus so you don't lose your run while alt-tabbed.

## How to Run

### Online

Open the [Live Demo](#live-demo) link.

### Locally

1. Clone or download this repository.
2. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
3. Click **START ENGINE**.

No build step, no install. The browser fetches Three.js from a CDN on first load.

## Tech Stack

- **Three.js r160** (loaded via the unpkg CDN) for 3D rendering, with `EffectComposer`, `UnrealBloomPass`, and `PMREMGenerator` for post-processing and environment reflections.
- **WebAudio API** for synthesized engine, tire, NOS, and crash sounds. No audio files are shipped.
- **Vanilla HTML, CSS, and JavaScript** in a single file. No bundler, no framework.

## Project Structure

```
index.html              The entire game (HTML, CSS, JS in one file)
README.md               This file
LICENSE                 MIT
.github/workflows/      GitHub Pages deployment workflow
.gitignore              Standard ignores
```

## License

[MIT](LICENSE).

## Credits

All cars are stylized recreations built from primitive geometry in code. No copyrighted models are shipped. Three.js is used under its MIT license.
