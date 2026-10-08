# Floating Music Mouse

A browser instrument in the spirit of Laurie Spiegel's *Music Mouse*: move the mouse and a 4‑voice harmony follows,
constrained to a scale. Layers can float on their own with tethered Brownian motion.

Everything lives in a single `index.html` with no build step and no dependencies (the IBM Plex Mono web font is optional).
Open the file in a browser. If your browser blocks Web MIDI for local files, serve the folder (`npx serve .`) and open it via `http://localhost`.

## Playing

1. Pick a **scene** on the start screen (or keep *Classic Mouse*) and press **Initialize Instrument**.
2. Move the mouse: **X** and **Y** each steer two of the four voices.
3. Press **Space** to freeze the current sound as a layer and start a new one (up to 8).
4. Press **M** (or **Esc**) to open the editor. Click the field to go back to playing.

On touch screens, drag on the field to play and use the **Edit** button. Press **?** at any time for the full shortcut list.

## Musical output options

| Area | Options |
| --- | --- |
| **Instruments** (per layer) | Saw, Square, Triangle, Sine, Super Saw, Hollow Pulse, Soft Pad, Choir, Breath Flute, Organ, E‑Piano, FM Bell, Marimba, Plucked String (Karplus‑Strong), 8‑Bit Chip |
| **Scales** (per layer) | Diatonic, Pentatonic, Octatonic, Middle Eastern, Quartal, Chromatic, Natural/Harmonic Minor, Dorian, Phrygian, Lydian, Mixolydian, Blues, Whole Tone, Hungarian Minor, Hirajoshi, In Sen, Pelog |
| **Modes** | Chord, Arp, Line, Improv, Strum |
| **Articulation** (Chord) | Sustain (continuous glide), Pluck (re‑strike on the clock), Touch (strike only when a note changes) |
| **Rhythm** (per layer) | 1/4, 1/8, 1/8T, 1/16, 1/16T, 1/32, so layers can run polyrhythmically; 11 patterns (some with rests), gate length, swing and humanize |
| **Pitch** | Global key, 1–6 octave range, lowest octave, per‑layer octave shift, 3 voicings, parallel or contrary motion |
| **Mix** | Per‑layer level, pan, tone and mute; master volume |
| **FX** | Reverb, tempo‑synced delay (+ feedback), Haas widener, tremolo, phaser, ring mod, overdrive, shaper, bitcrusher, harmonics, mangler |
| **Brownian** | Drift on/off per layer, drift chaos and tension, Atmosphere (brown‑noise bed + wandering anchors) |
| **Web MIDI out** | Any output port, one channel per layer or a single channel, optional 24 PPQN clock with start/stop |
| **Recording** | Master audio to **WAV** (or the browser's compressed format), and/or every note to a **.mid** file. Press **O** to start and stop |
| **Presets** | Save/Load JSON (v5 presets still load), plus 7 factory scenes |

## Interface

- **Top bar**: layer chips (click to select, `+` to add), current scale, mode, sound and tempo. Nothing else stays on screen while you play.
- **Editor** (right drawer, or a bottom sheet on phones), with four tabs:
  - **Layer**: sound, harmony and rhythm for the active layer.
  - **Global**: scenes, clock, key and range, feel, Brownian settings.
  - **FX**: the effects rack, grouped as Space, Motion and Color.
  - **Output**: volume, speakers, MIDI out, recording, presets.
- **Field**: octave lines are labelled, a ring flashes on every note, and the active layer shows the notes it is playing.

## Notes for v5 users

- Atmosphere moved from `7` to `H`, because `7` also sets velocity.
- `Backspace` now removes only the active layer. `Shift+Backspace` resets everything.
- `S` cycles Sustain → Pluck → Touch, and `F` cycles 2‑2 → 1‑3 → Spread.
- New keys: `A` strum, `N` rate, `[ ]` scales, `← →` key, `, .` octave, `L` mute, `O` record, `Enter` pause, `Tab` next layer.
