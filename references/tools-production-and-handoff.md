# Tools, Production, and Handoff

Use this module after the motion thesis and behavior are defined. Select tools by the temporal and runtime problem, not popularity.

## Contents

- [Technique routing](#technique-routing)
- [Selection criteria](#selection-criteria)
- [Proof ladder](#proof-ladder)
- [Implementation specification](#implementation-specification)
- [Asset pipeline](#asset-pipeline)
- [Prototyping and inspection](#prototyping-and-inspection)
- [Engine-specific cautions](#engine-specific-cautions)
- [Handoff meeting](#handoff-meeting)

## Technique routing

| Need | Likely route | Notes |
|---|---|---|
| Simple state, hover, focus, enter/exit | CSS transitions/animations or Web Animations | smallest runtime; respect existing framework |
| Component and layout transitions | Motion or target-framework equivalent | useful for shared layout and gesture integration |
| Complex web timelines and scroll choreography | GSAP or equivalent timeline engine | strong sequencing; manage accessibility and cleanup |
| Vector asset animation, fixed authored sequence | Lottie | validate text, responsiveness, accessibility, renderer limits |
| Stateful interactive vector/character | Rive | useful state machines; plan runtime, inputs, fallback |
| Data-driven or generative 2D | Canvas or p5.js | manage resolution, input, semantics, deterministic capture |
| Spatial/3D/material/particles | Three.js/WebGL/WebGPU route | justify cost; profile GPU, memory, loading, fallback |
| Programmatic video and templating | Remotion or video pipeline | deterministic timeline, rendering, fonts, audio, rights |
| Native app motion | platform-native animation/transition APIs | preserve platform conventions and device behavior |

This is routing, not a mandated stack. Verify current libraries and platform support before implementation.

## Selection criteria

- Real-time versus fixed timeline
- User-interruptible versus authored
- DOM semantics and accessibility
- State-machine complexity
- Text and localization
- Asset and design-tool pipeline
- 2D versus 3D, vector versus raster
- Browser/device support
- Bundle, CPU, GPU, memory, battery, and network budgets
- Deterministic rendering and capture
- Team expertise, maintainability, and licensing

## Proof ladder

Use the smallest artifact that proves the decision:

1. Beat sheet proves structure.
2. Storyboard proves composition and sequence.
3. Animatic proves timing and edit.
4. Motion study proves material or signature behavior.
5. Interactive prototype proves input coupling, interruption, focus, and state.
6. Runtime prototype proves performance and integration.
7. Production QA proves actual assets, content, devices, and fallbacks.

Do not use a polished video recording to claim interactive responsiveness.

## Implementation specification

For each behavior include:

```text
ID and purpose:
Trigger and preconditions:
Elements and hierarchy:
Initial / active / final states:
Timing tokens or spring parameters:
Sequencing / overlap / stagger:
Transform origin / path / depth:
Input coupling and interruption:
Cancellation / reversal:
Responsive behavior:
Reduced-motion variant:
Low-performance fallback:
Assets and rights:
Instrumentation:
Acceptance evidence:
```

## Asset pipeline

Record:

- Source file and owner
- License/rights and expiry
- Version and export settings
- Color space, alpha, resolution, frame rate, and compression
- Font embedding and text localization
- Responsive crop or layout
- Loading strategy and placeholder
- Runtime renderer and fallback
- Change and approval history

Avoid bundling unlicensed references into production.

## Prototyping and inspection

- Use representative content and longest translations.
- Test at target scale and frame rate.
- Inspect actual intermediate frames, not only endpoints.
- Test repeated triggering and rapid reversal.
- Profile on representative low and high devices.
- Verify background/foreground, resize, orientation, and reduced-motion changes.
- Capture evidence: recording, profiler trace, state tests, and known limitations.

## Engine-specific cautions

- CSS/layout: prefer transform and opacity when they preserve semantics; do not force everything onto the compositor if visual truth needs layout.
- Timeline engines: scope and clean up instances; avoid conflicting ownership with framework state.
- Lottie: verify renderer differences, masks, effects, text, scaling, and semantic alternative.
- Rive: document state inputs and fallback; avoid hiding core controls inside an inaccessible canvas.
- Canvas/WebGL: provide DOM semantics and keyboard alternatives; handle resolution, context loss, and reduced motion.
- Video: provide captions/transcript, controls, poster, responsive encoding, and silent comprehension.

## Handoff meeting

Review:

1. Intent and thesis
2. Full-speed and slow playback
3. Interaction/state contract
4. Token mapping
5. Reduced motion and fallback
6. Asset source and rights
7. Performance budget
8. Acceptance tests and ownership

The implementer should be able to reproduce the intended temporal quality without guessing from a single easing label.
