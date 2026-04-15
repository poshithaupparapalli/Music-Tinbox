# Circuit Notes

> This is YOUR learning journal. As you read the schematics, datasheets, and blog posts,
> write down what you learn here. Explain things in your own words — if you can't explain it,
> you don't understand it yet.

---

## Signal Flow (The Big Picture)

<!-- TODO: Trace the full path of audio through the circuit -->
<!-- Start from sound hitting the mic, end at sound coming out the speaker -->
<!-- Draw it out on paper first if that helps -->

### Recording Path
<!-- How does sound get from the air into memory? -->


### Playback Path
<!-- How does stored data get turned back into sound? -->


---

## Major Components

### AVR128DA28 (Microcontroller)
<!-- What does this chip do? What peripherals does it have that matter for this project? -->
<!-- Hint: look at ADC, DAC, SPI sections in the datasheet -->


### W25Q64JVSSIQ (Flash Memory)
<!-- How much audio can this store? How does the MCU talk to it? -->
<!-- Hint: SPI protocol — what pins are involved? -->


### AD8531 / TLV271 (Op-Amps)
<!-- Why can't we just plug the mic directly into the MCU? -->
<!-- What does "gain" mean in this context? -->


### Electret Microphone (CMC-5044PF-A)
<!-- How does this thing actually work? -->


### MCP1700 (Voltage Regulator)
<!-- Why do we need this? Why not just run everything off USB 5V? -->


---

## Things I Don't Understand Yet

<!-- Keep a running list here. Cross them off as you figure them out. -->
<!-- Ask me (Claude), your makerspace people, or the internet -->

- [ ] 
- [ ] 
- [ ] 

---

## Useful Resources

- lcamtuf's audio toy post: https://lcamtuf.substack.com/p/mcu-land-part-4-building-an-audio
- lcamtuf's mic amplifier post: https://lcamtuf.substack.com/p/building-a-decent-microphone-amplifier
- lcamtuf's PCB design tutorial: https://lcamtuf.substack.com/p/designing-your-own-pcbs
- AVR128DA28 datasheet: in `references/` folder (or Sage's repo under `datasheets/`)
- KiCad getting started: https://docs.kicad.org/
