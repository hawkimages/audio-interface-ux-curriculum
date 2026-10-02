# Reference shelf

Use these resources to answer questions raised by the projects, rather than trying to read everything first. Start with the source nearest to the device or protocol you are studying; consult a hardware or firmware specialist when moving from a UX prototype to a real circuit.

## Your electronics reference

- **Paul Scherz and Simon Monk, _Practical Electronics for Inventors_** — use the index to find chapters/sections on electricity, microcontrollers, op-amps, analog signals, ADC/DAC, and power supplies. Editions vary, so follow the headings in your copy. Pair a concept with a small annotated block diagram; do not treat the book alone as a validated audio-interface design.

## MIDI and controller prototyping

- **MIDI Association, MIDI articles and specifications** — primary background on MIDI messages and standards: [midi.org](https://midi.org/).
- **Arduino documentation** — board and programming references if you choose an Arduino-based controller: [docs.arduino.cc](https://docs.arduino.cc/).
- **FortySevenEffects Arduino MIDI Library** — a widely used library for MIDI on Arduino-compatible boards; consult its own documentation and examples for supported transports and board requirements: [github.com/FortySevenEffects/arduino_midi_library](https://github.com/FortySevenEffects/arduino_midi_library).
- **Teensy Audio Library** — examples and documentation for audio experiments on Teensy; useful for a later audio-prototyping stage, not required for a MIDI controller: [pjrc.com/teensy/td_libs_Audio.html](https://www.pjrc.com/teensy/td_libs_Audio.html).

Choose a board only after checking its USB-MIDI support, available controls/inputs, library compatibility, power requirements, and documentation. A connector that fits USB does not by itself tell you whether a device carries MIDI or audio.

## Learning audio paths and interfaces

- **Manufacturer manuals for an interface you own or can borrow** — the most relevant source for its input types, gain, meters, direct monitoring, routing, and driver/software behavior. Use the block diagram and specifications as a starting point; do not assume every interface works the same way.
- **MIDI Association** — keep MIDI control distinct from audio transport: [midi.org](https://midi.org/).
- **USB Implementers Forum, document library** — standards background for USB, including class specifications. USB Audio Class material is technical; use it to understand terminology and consult specialists for implementation: [usb.org/documents](https://www.usb.org/documents).
- **Bela documentation** — an optional platform for interactive, low-latency audio projects, with hardware and software documentation: [learn.bela.io](https://learn.bela.io/).
- **Pure Data documentation** — a software environment for exploring signal flow and simulating audio behavior without building a circuit: [puredata.info](https://puredata.info/).

When reading about ADC/DAC, I²S, sample rate, bit depth, gain, impedance, or latency, write down the UX implication and the engineering question separately. A UX prototype can validate that users understand a meter; it cannot establish converter performance or electrical safety.

## Books for design context

- **Jenifer Tidwell, Charles Brewer, and Aynne Valencia, _Designing Interfaces_** — reusable interaction patterns to critique and adapt for constrained hardware interfaces.
- **Don Norman, _The Design of Everyday Things_** — useful for feedback, mapping, discoverability, and error recovery in physical controls.
- **Nicolas Collins, _Handmade Electronic Music_** — hands-on experimental electronics and sound-making; use appropriate safety precautions and distinguish creative circuits from production-ready audio hardware.

These complement, rather than replace, observing musicians and testing with the device and workflow you are designing for.

## How to use this list

1. Pick one project and identify what you need to learn next.
2. Read the relevant textbook section and one primary source (board documentation, protocol material, or device manual).
3. Draw the signal/control path and annotate terms that are still unclear.
4. Ask a musician about workflow questions and an engineer about circuit, firmware, and performance questions.
5. Record what is verified, simulated, assumed, or still unknown in your project notes.
