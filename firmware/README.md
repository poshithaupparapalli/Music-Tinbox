# Firmware

C code for the AVR128DA28 microcontroller goes here.

## Source

The firmware is based on lcamtuf's audio toy project.
- Blog post: https://lcamtuf.substack.com/p/mcu-land-part-4-building-an-audio
- <!-- TODO: find and link to his actual source code repository -->

## Key Concepts to Understand

Before trying to modify anything, read through the code and understand:

- [ ] How the ADC samples the mic input (analog → digital conversion)
- [ ] How samples are written to flash memory over SPI
- [ ] How the DAC outputs audio for playback
- [ ] How buttons are read (interrupt-driven? polling?)
- [ ] How playback effects work (reverse = read array backwards, speed = change sample rate)

## Toolchain Setup

<!-- TODO: document how you set up your build environment -->

You'll need:
- `avr-gcc` — compiler for AVR chips
- `avrdude` or `pymcuprog` — to flash firmware via UPDI
- A UPDI programmer (or Arduino running SerialUPDI)

### macOS
```
# TODO
```

### Linux
```
# TODO
```

### Windows
```
# TODO
```
