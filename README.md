# 🛸 UAP Signal Generator

## Overview

This is a browser-based synthesizer that emits a composite audio signal designed to act as a “summoning dog whistle” for UAP (Unidentified Aerial Phenomena).

The signal is a blend of multiple frequency layers, modulation, chirps, and noise, intended to carry a hidden signature.

## Features
- 7.83 Hz modulation (carrier via amplitude modulation on 100 Hz)
- 528 Hz harmonic tone
- 17 kHz ultrasonic tone
- 2.5 kHz chirps every 10 seconds
- 432 Hz ambient pad
- Breath / organic noise layer
- Pulse mode or continuous playback
- Low volume base (structure matters more than loudness)

## Use Cases / Warnings
- This is for experimentation and demonstration only.
- Ultrasonic and high-frequency tones may be inaudible or harmful to pets or sensitive hearing.
- Use responsibly, in controlled environments.
- This is not guaranteed to “summon” anything.

## Technical Approach
- Uses Web Audio API (native browser audio synthesis)
- Oscillators, gain nodes, modulation, scheduling
- Noise generated from buffer of random samples
- Chirp implemented by short gain ramp at intervals
- Toggle between pulsed and continuous modes

## File Structure
```
/  
  index.html         ← main UI + script  
  README.md          ← this file  
```

## Usage
1.	Open index.html in a modern browser (Chrome, Firefox, Edge).
2.	Click Start Signal to begin playback.
3.	Click Stop Signal to end playback.
4.	(If implemented) Use the toggle to switch between pulsed and continuous mode.

## Implementation Notes
- The 7.83 Hz modulator is implemented as an LFO applied to the gain of a 100 Hz “carrier.”
- The 17 kHz tone is continuous; depending on browser and hardware it may be filtered or inaudible.
- The 2.5 kHz chirp is scheduled every 10 seconds with a rapid exponential decay of amplitude.
- The “breath” noise layer is a looping white-noise buffer at low amplitude.
- All amplitude levels are calibrated to avoid clipping — final gain is deliberately low.

## Possible Extensions
- Add UI controls for each frequency / amplitude
- Add a “save to WAV / export audio file” function
- Add preset signals or randomization
- Add real-time modulation / envelope shaping
- Host via HTTPS so it can run on mobile or remote devices

## License & Attribution

This project is open source. Use, adapt, and distribute freely.
Inspired by the concept shared at: https://x.com/JasonWilde108/status/1910816547070685522?s=19
