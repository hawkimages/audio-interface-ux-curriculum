# Curriculum roadmap

This self-paced sequence moves from understanding a musical context to evaluating a working interaction. Complete the core activity in each module and save the evidence in a design journal. The order is recommended, but modules can be revisited as a project demands.

## Choose a learning track

All learners follow the same research and interaction-design foundations.

- **No-code track:** use sketches, paper controls, cardboard, a clickable screen prototype, and a narrated walkthrough. Simulate sound and state changes with labels, cards, or a partner.
- **Software track:** use a digital prototyping tool for screens and transitions. A DAW, audio patching environment, or browser prototype can simulate behavior.
- **Hardware track (optional):** build on the other tracks with a low-voltage development board or an existing MIDI controller. Follow the board manufacturer's safety guidance; do not work with mains voltage.

Do not let implementation tools replace user research or interaction testing. A convincing prototype is one that makes the behavior understandable, not necessarily one that produces finished audio.

## Module 1 — Choose a context and frame the problem

**Learn:** product categories, users, use environments, and the difference between a feature request and a user need.

**Do:** choose a product (for example, a compact synth, pedal, mixer, or field recorder). Write a one-paragraph brief covering intended users, where and how it is used, the problem to solve, and what is out of scope.

**Evidence:** a problem statement, assumptions list, and three questions to investigate.

## Module 2 — Observe people and workflows

**Learn:** contextual inquiry, open-ended interviewing, observation, consent, and avoiding leading questions.

**Do:** interview or observe at least two people with different levels of experience. Ask them to demonstrate a real task, such as setting a tempo, balancing a mix, or saving a sound. If access to musicians is limited, use a clearly labeled proxy and record what remains uncertain.

**Evidence:** anonymized notes, task breakdowns, and insights separated from assumptions.

## Module 3 — Understand sound and signal flow

**Learn:** the user's mental model of an audio path: sources, processing, routing, monitoring, and output. Identify where controls affect sound and where they affect configuration.

**Do:** draw a signal-flow diagram for the chosen product. Mark points where a user can hear, see, or otherwise confirm a change.

**Evidence:** a labeled diagram plus a short explanation in language a new user could understand.

## Module 4 — Define tasks and interaction requirements

**Learn:** task analysis, frequency and importance, critical tasks, constraints, and success criteria.

**Do:** select three core tasks and one recovery task. For each, note the starting state, user action, expected result, failure cases, and observable completion signal.

**Evidence:** task flows and testable requirements. Avoid requirements that prescribe a solution before the user need is understood.

## Module 5 — Design the physical control system

**Learn:** affordances, control-response mapping, grouping, labeling, tactile differentiation, reach, and the trade-offs among knobs, buttons, sliders, encoders, and switches.

**Do:** sketch two competing control layouts. Mark frequently adjusted controls, risky actions, navigation controls, and any controls that must be identifiable by touch.

**Evidence:** annotated layout alternatives and a rationale for the selected arrangement.

## Module 6 — Design display and navigation

**Learn:** information hierarchy, screen constraints, direct manipulation, menu depth, mode visibility, and consistency between physical controls and on-screen labels.

**Do:** storyboard one task that uses both hardware and a display. Include initial, intermediate, and completion states.

**Evidence:** low-fidelity screens or paper cards, an information hierarchy, and a navigation map.

## Module 7 — Make system state and feedback legible

**Learn:** immediate feedback, latency, persistent versus transient messages, mode errors, confirmation, undo, and graceful recovery.

**Do:** specify feedback for normal operation, loading, saving, invalid input, disconnected peripherals, and an error that could interrupt a performance.

**Evidence:** a state table that identifies trigger, user-visible feedback, available action, and recovery path for each state.

## Module 8 — Prototype the interaction

**Learn:** choosing fidelity based on the question, Wizard-of-Oz techniques, clickable flows, physical mock-ups, and keeping prototypes safe.

**Do:** build a prototype that supports one end-to-end task. Make physical controls movable or clearly represented and simulate any behavior you cannot implement.

**Evidence:** a prototype, a short setup guide, and a list of simulated behaviors and known limitations.

## Module 9 — Test with users and iterate

**Learn:** usability-test planning, neutral task prompts, observation, severity, and separating what happened from why you think it happened.

**Do:** test the prototype with at least three people when feasible. Ask each to complete a task without step-by-step coaching. Record hesitation, errors, workarounds, and their confidence.

**Evidence:** a test plan, findings ranked by impact, and a before/after change log. If testing with fewer people, explain the limitation rather than treating the results as conclusive.

## Module 10 — Check accessibility and varied use

**Learn:** motor, visual, auditory, cognitive, and situational access needs; inclusive research; and why important status should not rely on color or sound alone.

**Do:** review labeling, contrast, touch targets, control force and spacing, screen readability, and operation under realistic lighting and attention conditions. Identify ways to use the device without relying on a single sensory channel.

**Evidence:** an accessibility review with prioritized changes and unresolved questions.

## Module 11 — Validate the product in context

**Learn:** setup and teardown, portability, cables, gloves or limited reach where relevant, live-performance pressure, studio workflows, and handoff between people.

**Do:** rehearse a core task in the intended context using a timed or interrupted scenario. Check whether the design makes mode, routing, and output state clear.

**Evidence:** a context walkthrough, risks list, and a revised prototype or design recommendation.

## Module 12 — Communicate and hand off

**Learn:** interaction specifications, design rationale, prototype limitations, and communicating states and edge cases to collaborators.

**Do:** prepare a concise case study that links research findings to requirements, design decisions, test findings, and iteration.

**Evidence:** final prototype, annotated interaction flows, evaluation summary, and next-steps backlog.

## Completion checklist

- [ ] A specific user and use context are described.
- [ ] Research evidence is distinguished from assumptions.
- [ ] Signal flow and core tasks are understandable.
- [ ] Controls, display, feedback, and error recovery work as one system.
- [ ] The prototype can be tested without unsafe electrical connections.
- [ ] Findings have led to at least one documented iteration.
- [ ] Accessibility and unresolved risks are documented.
- [ ] Another person can understand the design and its limitations.
