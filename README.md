# ambient_organism
**Pure MIDI Pendulum Edition (4-Layer SATB Mod with AWAKE & Reverse FX)**

A highly organic, generative MIDI sequencer for **monome norns**, designed specifically to control the **Sonicware LIVEN Ambient Ø** synthesizer.

It visually and musically simulates four independent swinging pendulums, weaving beautiful ambient soundscapes, evolving chord progressions, and serendipitous melodies.

## Features
* **4 Independent Pendulums**: Each pendulum controls a separate MIDI channel (Ch1 - Ch4) with unique, asynchronous speed ratios.
* **SATB Voicing**: Generates perfectly balanced 4-part harmonies (Soprano, Alto, Tenor, Bass) across 3 octaves.
* **Smart Chord Progression**: Change chords smoothly via encoders or automatically. It strictly adheres to major/minor pentatonic scales based on the current chord, completely eliminating dissonant notes.
* **Physics-linked Arpeggiator (Ch1 & Ch2)**: The speed and position of the pendulums directly control the density and envelope (AMP ATTACK) of the arpeggiator.
* **AWAKE Sequencer Integration (Ch3)**: Transform the Tenor part into a beautiful melody generator powered by the legendary 'Awake' sequencer logic.
* **Sub-Bass Protection (Ch4)**: Automatically folds bass notes into the human ear's optimal low-frequency range (G1-G3).
* **Cinematic Softcut Effects**: Route LIVEN's audio back into norns to receive a lush tape delay, plus a random half-speed reverse effect during Melody mode.
* **Build-up Progression**: Tap K2 to organically stage the number of active pendulums (0 ➡️ 1 ➡️ 2 ➡️ 3 ➡️ 4 ➡️ 3 ➡️ 2 ➡️ 1 ➡️ 0).

## Requirements
* [monome norns](https://monome.org/docs/norns/)
* [Sonicware LIVEN Ambient Ø](https://sonicware.jp/pages/liven-ambient-0) (or any 4-part multitimbral synth - see notes below)
* Audio cable (LIVEN Output -> norns Input) for Softcut FX.

## Controls

### Global Mode (Default)
* **E1**: Shift Chord Progression (I ➡️ IV ➡️ VIm ➡️ V)
* **E2**: Base Speed (Pendulum frequency)
* **E3**: Harmonic Interval (1st ~ 8th)
* **K2**: Build-up / Fade-out Active Pendulums (0 ~ 4)
* **K3**: Play / Pause
* **K1 (Hold) + K2**: Toggle SYNC Mode (pulls all pendulums to Ch2's phase)
* **K1 (Hold) + K3**: Toggle Ch3 Melody Mode (AWAKE)

### AWAKE Mode (when Ch3 Melody is active & K1 is not held)
* **E1**: Change AWAKE Editor Mode (`STEP` / `LOOP` / `SOUND` / `OPTION`)
* **E2 & E3**: Edit Parameters based on the current AWAKE Mode.
* **K2 & K3**: Toggle Tracks, Randomize, etc.

---

## ⚠️ Important Notes for Users (Please Read)
This script is highly customized and tuned specifically for my personal setup. If you are using it, especially with synthesizers other than the LIVEN Ambient Ø, please be aware of the following:

1. **MIDI Device Port Default**: By default, the script tries to connect to MIDI Port 3 (if 3 or more devices are detected). If you don't hear anything, please go to `PARAMETERS > MIDI OUT (LIVEN Ø)` and select your connected MIDI device manually.
2. **Fixed MIDI Channels 1-4**: The four pendulums strictly send notes and CCs on MIDI Channels 1, 2, 3, and 4 respectively. You will need a 4-part multitimbral synthesizer (like the LIVEN, Elektron Digitone, Roland Boutiques, or 4 soft synths in a DAW) to hear all the layers.
3. **LIVEN-Specific CC Messages**: The script constantly sends out specific Control Change (CC) messages to dynamically morph the sound. These include:
   * **CC 52** (Volume) & **CC 53** (Pan)
   * **CC 40** (Amp Attack)
   * **CC 30** (Harmonics - Ch2 only)
   * **CC 32** (Pitch Reset)
   * **CC 38 & 39** (Filter Cutoff & Resonance via AWAKE SOUND mode)
   * *If you use a different synthesizer, these CC numbers might trigger unexpected parameter changes or glitched sounds on your gear. Use with caution!*
4. **Softcut Effects Require Audio Routing**: The random effects (like Half-Speed Reverse) are processed inside norns via Softcut. You must route your synthesizer's audio output into the norns audio inputs to hear these effects.

💬 **A message to fellow creators:**
While the CC mappings are currently hardcoded for the Ambient Ø, please let me know if there's other specific gear you'd like to connect to this script! I'll do my best to update the script to support your setup.

## Credits
Based on the brilliant `Awake` script by tehn and the `halfsecond` Softcut delay engine.
