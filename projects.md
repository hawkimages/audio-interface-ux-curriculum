# Project sequence

These projects build technical understanding through UX questions. Work through the first two in order; choose the third based on what you want to learn. You can use a simulator or paper prototype wherever real hardware would add risk without answering the design question.

## 1. A small MIDI controller

**Purpose:** learn how a physical control becomes a message and how the message affects a musical tool.

**Brief:** design a compact controller for one clearly defined musical task—for example, changing three parameters during a live performance, or controlling transport and levels in a recording session. Avoid designing a general-purpose controller until you understand one user's workflow.

**Explore**

- Which actions need dedicated controls, and which can share a control through a mode?
- How will users know which target or mode is active?
- Does the host provide feedback to the controller, or does the controller only send messages?
- What happens when a control is moved after switching modes or loading a different patch?
- Are controls recognizable and usable by touch when the user is looking elsewhere?

**Make:** a task flow, annotated control layout, simple controller prototype (or interaction simulation), and a mapping table connecting control, message, target, and feedback.

**Test:** ask a musician to connect and use it for the chosen task. Observe setup friction, mode errors, mapping surprises, and whether the physical design supports performance. Revise one important issue.

**Keep in scope:** a few controls and one host workflow. Do not attempt to build an audio interface in this project.

## 2. The first recording: audio-interface UX study

**Purpose:** understand the user experience and signal path of an audio interface before considering an electronics build.

**Brief:** choose an existing two-input recording interface and design a clearer first-recording experience for a new user. Use the actual device and manual if available; a faithful mock-up is sufficient for the redesign.

**Investigate**

- What connects to each input, and how does the user identify the right connection?
- How does the user set input gain and recognize clipping?
- How do direct monitoring and software monitoring differ in this setup?
- What does the interface's latency control actually affect?
- How are recording inputs, playback, and headphone monitoring routed?
- Which device state is unclear in the manual, on the panel, or in its companion software?

**Make:** a signal-path diagram based on the manufacturer's documentation, current and revised setup flows, a panel/software prototype, and a state table for input, clipping, monitoring, and disconnect/recovery.

**Test:** have a beginner and a more experienced recorder complete a short setup task. Use safe levels; no loud playback is needed. Compare where they hesitate and whether the new feedback improves their confidence.

**Keep in scope:** interface design and documented behavior. Do not fabricate a preamp, converter, power supply, or USB audio device for this exercise.

## 3. Choose a next build or study

Pick one based on your interests. Define one interaction question before selecting a board or tool.

### A. Improve the controller

Add a small set of controls, a mode change, or feedback from a host. Prototype how mappings are discovered, edited, and restored. Compare whether a physical mode switch, display, or software companion makes the current state clearest.

### B. Simulate a sound effect

Use a documented audio environment or an existing audio-capable development board to prototype a simple effect interaction. Focus on parameter response, bypass, presets, and indication of active state. State which audio behavior is simulated and which is actually running.

### C. Extend the recording-interface study

Prototype a workflow for setting gain, choosing direct monitoring, or recovering from a disconnected device. Use a real interface as a reference and verify behavior against its manual. Do not claim improved audio quality unless it has been measured using appropriate methods.

### D. Explore synthesis or analysis

For a synthesizer, prototype the relationship between a few sound parameters and their controls. For an analyzer, prototype how a user reads one measurement and decides what to do. Use a software simulator if that keeps the project focused on interaction.

## Portfolio case study

Show the reasoning, not just the final panel:

1. The user, context, task, and original uncertainty.
2. The signal path and distinction between audio and control data.
3. Early alternatives and what evidence led to a choice.
4. Prototype scope, actual versus simulated behavior, and known limitations.
5. Test observations, the iteration they prompted, and remaining engineering questions.

## Review checklist

- [ ] The project targets a specific musical task and user context.
- [ ] Controls have an understandable mapping and visible or tactile state.
- [ ] Signal, control messages, and software behavior are not conflated.
- [ ] Latency, clipping, monitoring, or modes are explained where relevant.
- [ ] A second person tried the prototype and findings informed a revision.
- [ ] Prototype limitations and engineering/safety questions are explicit.
