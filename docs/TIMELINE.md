# Build Timeline

🎯 **Start:** April 2026
🎯 **Goal:** Working board in ~2 weeks

> This timeline assumes PCB shipping takes ~7-10 days (JLCPCB cheapest option to US).
> That wait time is your learning window — use it well.

---

## Phase 1: Learn & Order (Days 1-3)

### Day 1 — Orientation
- [ ] Read lcamtuf's audio toy blog post start to finish
  - https://lcamtuf.substack.com/p/mcu-land-part-4-building-an-audio
  - Take notes in `docs/CIRCUIT_NOTES.md` — write down anything confusing
- [ ] Read lcamtuf's mic amplifier post
  - https://lcamtuf.substack.com/p/building-a-decent-microphone-amplifier
- [ ] Clone Sage's repo and open her schematic in KiCad
  - `git clone https://github.com/onionharvester/boardwalk.git`
  - Install KiCad: https://www.kicad.org/download/
  - Open `music_tinbox/music_tinbox.kicad_sch`
- [ ] Visit your makerspace — check and note down:
  - Do they have a soldering station with fine tips? (photo it)
  - Hot air rework station?
  - Solder paste + stencils?
  - Flux, solder wick, tweezers?
  - Do they have any common components you could borrow? (resistors, capacitors, etc.)
  - Is there someone who can teach you to solder?

### Day 2 — Understand the Schematic
- [ ] In KiCad, trace through the 3 schematic sheets:
  - `music_tinbox.kicad_sch` — main board (MCU, flash, mic, buttons, speaker)
  - `mic_preamp.kicad_sch` — mic amplifier circuit
  - `power.kicad_sch` — USB-C power input & voltage regulation
- [ ] For each major IC, skim the first few pages of its datasheet
  - Datasheets are in Sage's repo: `music_tinbox/datasheets/`
  - You don't need to read the whole thing — just understand what the chip does
- [ ] Write up your understanding in `docs/CIRCUIT_NOTES.md`

### Day 3 — BOM & Ordering
- [ ] Create your BOM in `docs/BOM.md`
  - List every unique component from the schematic
  - Find each part on DigiKey or Mouser
  - Note what your makerspace might have
  - Calculate total cost
- [ ] Decide: use Sage's PCB design as-is, or modify it?
  - Recommendation: USE IT AS-IS for your first build
  - If using as-is, export gerbers from her KiCad files
  - If modifying, you need more KiCad learning time
- [ ] Order PCBs from JLCPCB (https://jlcpcb.com)
  - Upload gerber files
  - Default settings are fine (2-layer, 1.6mm, green solder mask)
  - Cheapest shipping option to US
- [ ] Order components from DigiKey/Mouser
  - These usually arrive in 1-3 days

---

## Phase 2: Learn While Waiting (Days 4-10)

> Your PCBs are shipping. Use this time wisely.

### Days 4-5 — Learn to Solder
- [ ] Watch these videos:
  - "SMD Soldering Tutorial" by GreatScott!
  - "How to Solder SMD Components" by EEVblog
- [ ] Go to makerspace, ask someone to show you basics
- [ ] Practice soldering on a scrap/junk board
  - Solder and desolder some 0603 resistors
  - Try soldering an SOIC chip (any old one)
  - Get comfortable with flux, solder wick, tweezers

### Days 6-7 — Understand the Firmware
- [ ] Read lcamtuf's firmware source code
  - <!-- TODO: find the exact link to his audio toy firmware -->
  - It's bare-metal C — no Arduino, no HAL
  - Focus on understanding: ADC sampling, SPI flash read/write, DAC output
- [ ] Set up AVR toolchain on your computer
  - You'll need: avr-gcc, avrdude or pymcuprog (for UPDI programming)
  - <!-- TODO: document your setup steps here -->

### Days 8-10 — Prep & Review
- [ ] Review your schematic notes — do you understand the full signal path?
- [ ] Organize your components when they arrive
- [ ] Make sure you have a UPDI programmer
  - Cheapest option: use an Arduino as a UPDI programmer (SerialUPDI)
  - Or buy a dedicated one (~$10-15)
- [ ] Read about the UPDI programming protocol

---

## Phase 3: Build (Days 11-14)

### Day 11-12 — Solder
- [ ] Go to makerspace with your PCB + components
- [ ] Solder in this order (easiest → hardest):
  1. Passive components first (resistors, capacitors) — smallest parts
  2. ICs (MCU, flash, op-amps) — need steady hands
  3. Connectors (USB-C, UPDI header)
  4. Through-hole parts (buttons, mic, speaker connector)
  5. LEDs last (polarity matters!)
- [ ] Visual inspection — check for solder bridges under magnification
- [ ] Continuity test with multimeter if available

### Day 13 — Flash & Test
- [ ] Connect UPDI programmer to the 3-pin header (GND, +5V, UPDI)
- [ ] Flash the firmware
- [ ] Test: does it power on? Do LEDs light up?
- [ ] Test: press record button, speak, press play — does it work?
- [ ] Debug anything that doesn't work (this is normal and expected)

### Day 14 — Finish
- [ ] Get it working reliably
- [ ] Fit it into the Altoids tin
- [ ] Add any personal touches
- [ ] Update `docs/BUILD_LOG.md` with what you learned
- [ ] 🎉 Done!

---

## If Things Go Wrong

**PCB arrives with errors** → This is why you ordered 5. Check for manufacturing defects.

**Soldering mistake** → Use solder wick + flux to remove and redo. Ask makerspace people for help.

**Board doesn't power on** → Check USB-C connector soldering. Check voltage regulator output with multimeter (should read 3.3V).

**Can't flash firmware** → Check UPDI connections. Make sure programmer is working. Try different baud rate.

**Audio sounds terrible** → Mic preamp might need gain adjustment. Check op-amp soldering.

**Nothing works and you're frustrated** → This is normal for a first hardware project. Take a break. Ask for help. Hardware debugging is slower than software debugging — that's just how it is.
