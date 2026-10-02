# Learning path: from MIDI controls to audio I/O

This path is for a UX designer who wants to prototype physical musical interfaces and communicate effectively with electronics and firmware collaborators. The goal is technical fluency through user-centered projects—not independent qualification to design production audio circuitry.

Use *Practical Electronics for Inventors* as a reference alongside the topics below. Editions differ, so find the relevant sections using the index and chapter headings rather than relying on page numbers. For each topic, make a one-page note: what it does, what the user might notice, and what you need an engineer to verify.

## Stage 1 — Map the product space

Start by comparing product categories before picking hardware:

| Product | What moves through it? | UX questions to notice |
| --- | --- | --- |
| MIDI controller | Control messages; not audio | Can the player understand mappings, modes, feedback, and what the controller currently controls? |
| Recording/playback interface | Analog audio in and digital audio to/from a host, then analog monitoring/output | Can users connect the right source, set levels, avoid clipping, and understand monitoring and latency? |
| Synthesizer | Generates audio, usually with direct sound-shaping controls | Can users make a sound quickly, understand parameter changes, and manage saved patches? |
| Effects processor | Accepts and transforms audio in real time | Can a performer adjust or bypass processing and recover from a wrong setting without disrupting play? |
| Analyzer | Measures or visualizes audio | Can users interpret the visualization and distinguish a useful measurement from noise or overload? |
| Hybrid instrument | Combines several of these roles | Are modes and signal paths coherent, or does mode switching make the product hard to understand? |

**Try:** select one product in each of two categories and sketch what goes in, what happens, and what comes out. Note which parts are audio and which are control data.

**Checkpoint:** explain why a MIDI controller is a lower-risk first hardware project than a USB recording interface, and identify what a MIDI controller cannot teach you about audio conversion.

## Stage 2 — Learn just enough electronics to ask better questions

Read the matching parts of your textbook while examining a simple documented board or circuit. Focus on concepts, not calculations for a production design:

1. **Electrical basics:** voltage, current, resistance, ground, digital inputs and outputs. Relate these to buttons, encoders, LEDs, and power.
2. **Microcontroller basics:** pins, firmware, debouncing, scanning controls, and serial communication. Notice how sampling a physical control becomes an action in the interface.
3. **Audio signal basics:** amplitude, frequency, waveform, and the difference between a digital control value and an analog audio signal.
4. **Analog stages:** buffers and op-amps, gain, impedance, noise, clipping, and why microphone, instrument, line, and headphone connections are not interchangeable.
5. **Conversion and digital audio:** ADC and DAC purpose, sample rate, bit depth, and I²S as a common digital-audio connection between chips.
6. **Power and grounding:** why noisy or poorly planned power can affect audio and hardware behavior. Treat circuit and power design as an engineering review topic, not a copy-and-build exercise.
7. **Computer connection:** distinguish MIDI-over-USB from USB Audio Class. They serve different purposes even when the same connector is used.

**Checkpoint:** draw a simple block diagram and annotate where the signal is analog, digital audio, or control data. For each block, list one possible user-visible failure or ambiguity.

## Stage 3 — Build a MIDI control prototype

Use a documented microcontroller or an existing MIDI-capable controller. Keep the initial prototype small: a few knobs or buttons, a clear mapping, and a visible response in a host application or instrument. You can simulate the sound engine; learning controller interaction does not require designing a synthesizer.

Study the MIDI message types you need for the interaction, how the host receives them, and how a controller might receive feedback. Test timing by playing, not only by reading specifications: perceived responsiveness depends on the whole setup, including the host and connected instrument.

**Checkpoint:** another person can connect the prototype, understand what each control affects, recognize its current mode, and recover from a mapping mistake without coaching.

## Stage 4 — Trace an audio interface workflow

Choose an existing two-input recording interface to study. Read its manual and use it in a normal, safe recording workflow. Trace the path from input connector through input gain and conversion to the computer; then trace playback and direct monitoring back to headphones or outputs.

Investigate these UX questions:

- How does a user distinguish microphone, instrument, and line-level inputs?
- How are gain and clipping communicated? Can the user see a problem before a take is ruined?
- What does direct monitoring do, and how does it relate to software monitoring?
- Where does latency enter the workflow, and what can the user reasonably control?
- How are input, playback, and monitor mixes routed and labeled?
- What setup or recovery information is missing when a device is disconnected or unavailable?

**Checkpoint:** draw the device's signal path from its manual and explain gain staging, clipping, monitoring, and latency in language suitable for a new user. Mark which details need confirmation from an engineer or manufacturer.

## Stage 5 — Prototype an audio-interface experience

Design the connection and recording flow for the studied interface. Use a paper control panel, clickable screens, or a narrated simulation of meters and routing. Test source selection, level setting, monitoring, a clipping mistake, and recovery. Do not build an ADC/DAC circuit just to validate a UX hypothesis.

**Checkpoint:** test with people who have different levels of recording experience. Record where they hesitate, what they misunderstand, and which feedback or layout change you made in response.

## Stage 6 — Pick a specialization

Use your interests and evidence to choose what to study next:

- **Controller:** richer mappings, MIDI feedback, sequencing, and performance ergonomics.
- **Recording interface:** input circuitry, converters, USB audio behavior, monitoring, and gain workflow—with engineering support.
- **Effects:** audio path, bypass, presets, and real-time parameter changes.
- **Synthesizer:** sound-generation concepts, parameter relationships, and patch editing.
- **Analyzer:** measurement concepts, calibration, and making data interpretable.
- **Hybrid instrument:** mode design, routing, and keeping several workflows coherent.

For any path, state what the device does, what you are simulating, what you have measured, and what remains unverified. A prototype's finish is not evidence that its audio performance or electrical safety is production-ready.

## Completion checklist

- [ ] I can distinguish control data from digital and analog audio.
- [ ] I can sketch and explain a product's signal path.
- [ ] I have prototyped at least one physical control interaction.
- [ ] I can explain gain, clipping, monitoring, latency, ADC/DAC, and MIDI at a UX-collaboration level.
- [ ] I have tested the interface with another person and iterated on evidence.
- [ ] I know which electrical, audio-quality, and compliance questions require engineering expertise.
