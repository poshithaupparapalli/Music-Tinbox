# 🎵 Music Tinbox Build

A pocket-sized audio recorder & player that fits inside an Altoids tin.

**Based on:**
- [Sage's Music Tinbox](https://github.com/onionharvester/boardwalk/tree/main/music_tinbox) — PCB design & hardware reference
- [lcamtuf's Audio Toy](https://lcamtuf.substack.com/p/mcu-land-part-4-building-an-audio) — original concept, firmware, and circuit design

## What It Does

- 🎤 Record audio from an electret microphone
- ▶️ Play back recordings with effects (reverse, fast, slow)
- 💡 LED status indicators
- 🔌 USB-C powered
- 📦 Fits in an Altoids tin

## Project Structure

```
├── hardware/            ← KiCad schematic & PCB files
├── firmware/            ← C code for the AVR128DA28
├── docs/
│   ├── BOM.md           ← Bill of materials (parts list + prices)
│   ├── BUILD_LOG.md     ← Day-by-day progress journal
│   ├── CIRCUIT_NOTES.md ← My notes on how the circuit works
│   └── TIMELINE.md      ← Build schedule
└── references/          ← Datasheets, pinouts, useful links
```

## How It Works

<!-- TODO: Write this in your own words once you understand the signal flow -->
<!-- Hint: trace the path from sound → mic → op-amp → ADC → flash → DAC → speaker -->

## Status

- [ ] Understand the circuit (read lcamtuf's blog post + Sage's schematic)
- [ ] Check makerspace equipment (soldering station, hot air, solder paste)
- [ ] Set up KiCad and open Sage's files
- [ ] Create BOM and price out parts
- [ ] Check what parts makerspace has
- [ ] Order PCB
- [ ] Order remaining components
- [ ] Learn to solder (practice on scrap board first!)
- [ ] Solder the board
- [ ] Flash firmware via UPDI
- [ ] Debug & test
- [ ] Fit in Altoids tin
- [ ] Add custom silkscreen art (optional but fun)

## Budget

Target: ~$50 USD

<!-- TODO: Fill in actual prices once you've made your BOM -->

| Category | Est. Cost | Actual Cost |
|----------|-----------|-------------|
| PCB fabrication + shipping | | |
| Components | | |
| Altoids tin | | |
| **Total** | | |

## Credits

- **Sage (@onionharvester)** — Music Tinbox hardware design
- **lcamtuf** — Original audio toy, firmware, blog series
