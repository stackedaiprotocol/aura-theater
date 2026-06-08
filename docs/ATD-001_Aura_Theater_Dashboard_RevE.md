# ATD-001
## Aura Theater Dashboard
### Governed Design Specification
| Field | Value |
|---|---|
| Document ID | ATD-001 |
| Version | v0.5 |
| Revision | E |
| Date | 2026-06-07 |
| Project Family | AUMX / Scroll School / Aura / Axis Live |
| Supersedes | ATD-001 v0.4 RevD |
| Status | PRESERVED DESIGN LAW. Amended per P5 build-surfaced interpretation (gate locus doctrine). |
| Vault Path | AUMX-VAULT / Scroll School / public / ATD-001_Aura_Theater_Dashboard_RevE.md |
| Companion | ATD-002 RevB Aura Theater Event Playback MVP (sealed build brief) |
| Truth Posture | Confirmed design law. Amendments recorded, not absorbed. |
---
## 0. Confirmation Record
The following design decisions were confirmed by the Human Architect on 2026-06-07 and now govern this document:
| ID | Decision | Status |
|---|---|---|
| ATD-D1 | The animation grammar is the governance grammar. Visual encoding maps 1:1 to the Charter lifecycle. | CONFIRMED |
| ATD-D2 | Gold is reserved exclusively for human confirmation events. No other event class may produce gold. | CONFIRMED |
| ATD-D3 | The Vault is rendered as a persistent Foundation Ring beneath the Guild Disc. Registered work descends and accumulates as visible marks. | CONFIRMED |
| ATD-D4 | Vault Registration is a ceremony, not a mode. The mode system is exactly the five Axis modes: Plan, Build, Meeting, Forge, Free. | CONFIRMED |
| ATD-D5 | The system renders anticipation. When the user holds, the chamber waits visibly. When the user responds, the system responds. | CONFIRMED |
Superseded provisions of v0.1 (six-mode system, eleven-glyph flat registry, blue and purple identity colors, vault-as-mode) are discarded per the Governed Artifact Iteration Cycle. Only the confirmed revision advances.
### 0.1 RevC Amendment Record
The following amendments were adopted 2026-06-07 per architectural review, under Human Architect authority. Recorded formally, not absorbed silently.
| ID | Amendment | Section Affected |
|---|---|---|
| ATD-A1 | Color language corrected: six normal governance channels plus one reserved fault channel (Red). | 3 |
| ATD-A2 | Dashboard and deck color systems formally separated. ATD channels govern live motion only. Purple is motion-memory. Merlot is print Mythos. | 3.1 |
| ATD-A3 | Cast section restructured: Aura classified as non-seat actor; five seat-bound graduates. Six-seat doctrine protected. | 5.3 |
| ATD-A4 | OI-1 ruled with MVP default: Foundation Ring persists for the active session only. VAULT-loaded historical marks deferred as a dim inherited foundation layer in a later phase. | 4.2, 16 |
| ATD-A5 | Dual counter ruled. SEALED counts seal_completed events. VAULTED counts vault_registered events and always equals the foundation mark count. The HUD carries both. Resolves the cross-document counter contradiction surfaced in pre-build review. | 4.2, 8.2, 10.1, 11.1 |
| ATD-A6 | Flicker doctrine codified: flicker is not a separate hue. It is alpha instability on the white token. Unconfirmed truth is unstable white; confirmation is stabilization. All instability is computed deterministically from scene time. | 3.1 |
| ATD-A7 | Gate locus doctrine ruled, resolving the tension between Section 5.4 (gate glyphs on spine only) and Section 8.1 (seal acts on the diamond). Distinction: a gate glyph is the iconographic symbol and renders on the spine only; a ceremony's effect on its subject is permitted at the subject. The gold pulse is a gate-channel signal and fires on the spine. The diamond receives white stabilization and a white ring closure at its location, and never itself emits gold. Confirmation comes to the work; gold belongs to the gate. | 5.4, 8.1 |
---
## 1. Purpose
The Aura Theater Dashboard is the visual rendering of Axis operation. It is not analytics. It is not a game. It is an instrument that makes governed work visible.
### 1.1 The Glance Test
Any viewer, including a stranger encountering the livestream, must be able to answer three questions within five seconds:
1. What mode is Axis in?
2. Who is working right now?
3. Where is the work in its lifecycle?
Every element of the system earns its place by serving at least one of these questions. An element that serves none is decoration, and decoration is debt.
### 1.2 The Single Story
The dashboard tells exactly one story, in every mode, at every scale:
AI proposes. Work is performed. A human confirms. The record seals. The Vault registers. The foundation grows.
There are no other plots. Variety comes from mode, cast, and tempo, never from new narrative structure.
---
## 2. Design Pillars
| Pillar | Meaning |
|---|---|
| Governance grammar is animation grammar | Color, motion, and ceremony encode Charter states directly. The dashboard does not reference the doctrine. It renders it. |
| Gold cannot be counterfeited | Gold appears only at human confirmation. Scarcity by law, not by taste. |
| What is confirmed becomes foundation | Registered work descends to the Foundation Ring and persists. Finished work is visible proof, not a vanished number. |
| The chamber waits with you | Idle is honest. Anticipation is rendered. No fake activity, ever. |
| Small grammar, total legibility | Six color channels, five modes, six seats, three glyph families. Learnable in one viewing. |
| Text is the auditable witness | Ledger and HUD derive from state, never from animation. If motion and text disagree, text is true. |
---
## 3. Color Constitution
Six normal governance channels. One reserved fault channel. Each normal channel maps to a Charter concept. No element may borrow a channel it has not earned.
| Channel | Governance Meaning | May Be Produced By |
|---|---|---|
| FLICKER | Unconfirmed. A proposal exists. Nothing more is claimed. | Proposal formation, unresolved items, decaying claims |
| CYAN | Working. Intelligence in motion. Authority not granted. | Active glyphs, working graduates, live relays, thinking states |
| WHITE | Confirmed. A human said yes. Structure is true. | Confirmed nodes, resolved geometry, white illuminations |
| GOLD | Human confirmation event. The seal. | seal_completed only. Reserved by ATD-D2. |
| PURPLE | Memory. Vault traffic. | Registration descent, vault read or write, memory bridge |
| AMBER | The Zero Seat is surfacing something. | Caution, classification gaps, governance observations |
### 3.1 Rules
1. Gold is event-scoped. It pulses at confirmation, leaves a residue mark in the Foundation Ring, and otherwise does not exist on screen.
2. White is state-scoped. Confirmed structures hold white illumination until superseded. White geometry is the visible accumulation of trust within a session.
3. Flicker is never decorative. If something flickers, something is genuinely unresolved. Flicker is not a separate hue: it is alpha instability on the white token. Unconfirmed truth is unstable white, and confirmation is stabilization. All instability is computed deterministically from scene time, never from random number generation.
4. Cyan never resolves itself. Cyan work transitions to white only through a confirmation event. The system cannot promote its own output. This is Law V rendered.
5. Amber does not block. It surfaces. The Zero Seat observes; the human decides.
6. RED is the reserved fault channel. It sits outside the six normal governance channels, participates in no ceremony, and appears only for severe fault states.
7. ATD color channels govern live motion only. They do not amend the Scroll School print-card color constitution. Purple is motion-memory. Merlot is print Mythos. The dashboard and the deck are separate color jurisdictions.
---
## 4. Spatial Doctrine
A fixed vertical architecture. Geometry is stable; meaning moves through it.
```
            [ AURA ]                 guide presence, hovers above
         AGENDA DISC                 purpose, intent, planning
              |
         PROJECT DISC                work, execution, assembly
              |
          GUILD DISC                 council, craft, six seats
              |
       FOUNDATION RING               the Vault, persistent registered work
```
### 4.1 The Spine
The central axis connects all layers. It is the alignment and orchestration channel.
- Pulses softly during multi-disc activity.
- Brightens white at confirmation.
- Carries the registration descent (purple) as the only downward traffic in the system.
- Stillness of the spine reads as stillness of the institution. This is acceptable and honest.
### 4.2 The Foundation Ring
Position: base of the spine, beneath the Guild Disc. Per ATD-D3.
- A faint ring, dim by default.
- Each completed registration descends the spine and settles into the ring as a small persistent gold-residue mark.
- Marks remain visible for the duration of the session. Per ATD-A5, the witness layer carries two counters: SEALED counts confirmation events, VAULTED counts registrations, and VAULTED always equals the number of marks in the Foundation Ring. Two seals and one registration today reads SEALED: 2 / VAULTED: 1, with one mark standing in the foundation. Sealing and registration are distinct events, and the counters keep the distinction permanently visible.
- The ring is the rendered form of institutional memory. What is confirmed becomes foundation.
- Persistence (ruled per ATD-A4): the Foundation Ring persists for the active session only in MVP. A later phase may load historical registration marks from VAULT as a dim inherited foundation layer beneath the live session marks. The first build is not a database problem.
### 4.3 Disc Meanings
| Disc | Meaning | Emphasized By |
|---|---|---|
| Agenda | Purpose, intent, prioritization, interpretation | Plan Mode, new purpose arrival |
| Project | Execution, assembly, task chains, forging | Build Mode, Forge Mode |
| Guild | Invoked council, craft presence, six fixed seats | Meeting Mode, invocation events |
---
## 5. Entity Model
### 5.1 Aura
The guide, witness, and threshold presence. Hovers above the Agenda Disc at idle.
| State | Behavior |
|---|---|
| Idle | Slow hover above Agenda Disc, faint breathing luminance |
| Listening | Slight brightening, orientation toward input |
| Anticipating | Holds position near the awaiting step, gentle periodic pulse (see Section 7) |
| Invoked | Descends or arcs toward the active disc |
| Working | Holds near active layer, light thread to the work |
| Witnessing | Still, while graduates operate |
| Sealing | Aligns with the spine during confirmation |
| Released | Returns to idle hover |
### 5.2 Guild Seats
Six fixed seat positions on the Guild Disc. Seat geometry never changes. Graduates come and go; seats do not. Seat scarcity keeps the council legible and makes invocation an appointment, not a spawn.
### 5.3 V1 Cast
The cast divides into one non-seat actor and five seat-bound graduates. The division protects the six-seat doctrine: Aura never occupies a seat, and seats are never created for convenience.
**Non-seat actor**
| Actor | Role Family | Notes |
|---|---|---|
| Aura | Guide | Not seat-bound. Hovers and moves freely per Section 5.1. |
**Seat-bound graduates**
| Graduate | Role Family | Notes |
|---|---|---|
| Planner | Strategy | Plan Mode anchor |
| Estimator | Analysis | Scope, time, cost projection |
| Risk Analyst | Analysis | Amber-adjacent; pairs with Zero Seat surfacing |
| Builder | Execution | Build Mode anchor |
| Scribe | Record | Meeting synthesis, ledger feed, registration assistant |
The registry may grow. The seat count may not, without a governance event.
### 5.4 Glyph Families
Glyphs are organized by family. Family determines color channel, position, and behavior. A new glyph inherits its grammar from its family rather than inventing it.
| Family | Members (v1) | Channel | Lives On | Behavior |
|---|---|---|---|---|
| CRAFT | Estimate, Synthesis, Build Chain | Cyan while active, white when confirmed | Discs | Forms, works, awaits confirmation |
| GATE | Confirm, Seal, Register | White and gold (seal pulse, spine only), purple (register descent) | Spine only | Gate glyphs and the gold pulse render on the spine only (ATD-A7). A ceremony may still act on its subject at the subject's location, but that effect is white stabilization, never gold. |
| SIGNAL | Risk, Caution | Amber | Near the relevant disc or item | Surfaces. Does not block. Does not resolve itself. |
### 5.5 The Diamond
The diamond is the work artifact: an output, decision, document, or result. Its lifecycle is the lifecycle:
```
FLICKER (proposed) -> CYAN (in work) -> WHITE (confirmed) -> GOLD PULSE (sealed) -> PURPLE DESCENT (registering) -> FOUNDATION MARK (registered)
```
The diamond is the single object viewers learn to follow. Everything else is context for it.
---
## 6. Mode System
Exactly five modes, 1:1 with the Axis Charter. Per ATD-D4. Vault Registration is a ceremony available from any mode, not a mode.
| Mode | Primary Disc | Tempo | Typical Cast | Typical Craft Glyphs |
|---|---|---|---|---|
| Free | Agenda (dim) | Minimal | Aura only | None |
| Plan | Agenda | Slow | Aura, Planner, Estimator, Risk Analyst | Estimate, Synthesis |
| Forge | Project | Medium-generative | Aura, Builder, Scribe | Synthesis, Build Chain |
| Meeting | Guild | Conversational | Aura, Scribe, plus invoked seats | Synthesis |
| Build | Project | Medium-sequential | Aura, Builder, Risk Analyst | Build Chain |
### 6.1 Mode Transition Ceremony
Mode separation is a governance event and is rendered as one. No silent transitions.
1. Activity settles. In-flight choreography completes or holds.
2. The chamber dims slightly. One beat of stillness. Approximately 1.0 to 1.5 seconds.
3. The incoming primary disc reforms: slow spin, lattice re-resolution, 3 to 4 seconds.
4. Luminance returns. HUD text updates to the new mode.
The dim-and-hold teaches viewers the grammar: when the room dims, the purpose is changing. Disc reform is deliberately the most expensive animation in the system, because a context change is the heaviest event there is.
---
## 7. Anticipation Doctrine
Per ATD-D5. The system is conversational. Its rhythm is call and response with the human, and both halves of that rhythm are rendered.
### 7.1 The Waiting State
When the system has proposed, asked, or completed a step and the human has not yet responded:
- The chamber enters HOLDING. All completed geometry remains illuminated white. Nothing decays merely because time passes.
- The awaiting item, typically a flickering proposal or a gate glyph, carries a slow periodic pulse. Roughly a breath every 4 to 6 seconds. Quiet, patient, unmistakably alive.
- Aura holds position oriented toward the awaiting item. The posture reads: the chamber is waiting with you, not on you.
- HUD reflects it plainly: STATE: AWAITING CONFIRMATION or STATE: HOLDING.
- No busywork. No ambient padding. The honesty of the wait is the point. An institution that can be still is an institution that is not performing.
### 7.2 The Response
When the human responds:
- The chamber answers within one frame-perceptible beat: a brightening of the relevant item, Aura's invocation movement, the choreography of consequence.
- If the response is a confirmation, the Gate sequence runs (Section 8.1).
- If the response is a redline or new direction, the affected geometry transitions honestly: flicker returns where confirmation was withdrawn, and the relevant disc may reform.
Call and response. The user sends, the system responds. The user waits, the system waits in anticipation. This loop is the heartbeat of the entire interface.
---
## 8. Ceremonies
Ceremonies are the reserved, high-meaning animation sequences. There are three. No other event class may borrow their signals.
### 8.1 The Confirmation Seal
Trigger: seal_completed. The only producer of gold in the system. Per ATD-A7, gold is a gate-channel signal: it fires on the spine, not on the diamond. The diamond's reward for confirmation is stabilization to full white, consistent with the flicker-to-white lifecycle (ATD-A6). Confirmation comes to the work; gold belongs to the gate.
1. The confirmed diamond or node brightens to full, stable white at its location.
2. A white ring closes around it. The ring is white, not gold. Confirmation embraces the work where it lives.
3. The spine brightens white along its full length.
4. One restrained gold pulse fires on the spine. Short. Clean. This is the gate firing. Gold appears here and nowhere else.
5. Geometry stabilizes and holds white. The diamond carries no gold.
6. Ledger entry: SEALED, with item and timestamp. The SEALED counter increments (ATD-A5).
Total duration approximately 2.5 to 3 seconds. The seal is rare, and the system protects its rarity structurally.
### 8.2 The Registration Descent
Trigger: vault_registered. Available from any mode.
1. Motion across the chamber slows.
2. The sealed diamond detaches and enters the spine.
3. Purple channel: the diamond descends the spine slowly. The only downward traffic in the system.
4. The Foundation Ring receives it. A brief low glow.
5. A small persistent gold-residue mark settles into the ring.
6. HUD increments the VAULTED counter: SEALED: N / VAULTED: N. Ledger entry: REGISTERED.
Total duration approximately 4 to 5 seconds. Deliberately the slowest ceremony, because memory deserves weight.
### 8.3 The Mode Transition
As specified in Section 6.1. Dim, hold, reform, return.
---
## 9. Event Grammar
The dashboard is event-driven from day one. The simulated event file and the future live socket share one interface.
### 9.1 Event Dictionary (v1)
| Event | Meaning |
|---|---|
| mode_entered | Axis enters Free, Plan, Forge, Meeting, or Build |
| agenda_loaded | New purpose or agenda. Agenda Disc reform. |
| project_loaded | New project or workflow. Project Disc reform. |
| graduate_invoked | A graduate arrives and docks at a seat |
| graduate_released | A graduate departs; seat returns to dim |
| glyph_loaded | A craft glyph forms (flicker, then cyan when active) |
| glyph_resolved | A craft glyph completes its work (cyan holds, awaiting gate) |
| relay_activated | Connection between entities or discs begins |
| relay_resolved | Connection completes |
| proposal_formed | A diamond appears in flicker state |
| awaiting_human | The chamber enters anticipation (Section 7.1) |
| seal_completed | Human confirmation. Ceremony 8.1. Gold. |
| vault_registered | Registration. Ceremony 8.2. Purple descent, foundation mark. |
| zero_seat_surfaced | Amber signal glyph appears with reference |
| state_hold | Explicit hold of current arrangement |
| fault | Severe fault only. Red. Outside normal ceremony. |
### 9.2 Canonical Payload
```json
{
  "event_type": "seal_completed",
  "timestamp": "2026-06-07T12:00:00Z",
  "mode": "build",
  "actor": "human_architect",
  "subject_id": "diamond_004",
  "disc": "project",
  "lifecycle_stage": "sealed",
  "visibility": "public",
  "label": "PBHO-014 CONFIRMED"
}
```
Required fields: event_type, timestamp, mode, subject_id, visibility. The visibility field drives public redaction (Section 11.3).
---
## 10. State Model
### 10.1 State Store
The single source of truth. The render loop draws what is true; nothing animates that state does not justify. This enforces the no-fake-activity principle structurally rather than by discipline.
```json
{
  "mode": "free",
  "transition": null,
  "anticipation": { "active": false, "subject_id": null, "since": null },
  "active_disc": "agenda",
  "agenda": null,
  "project": null,
  "seats": [null, null, null, null, null, null],
  "aura_state": "idle",
  "diamonds": [],
  "glyphs": [],
  "relays": [],
  "foundation_marks": [],
  "ledger": [],
  "sealed_today": 0,
  "vaulted_today": 0
}
```
### 10.2 Hold Semantics
Holding is the default, not a feature. Completed arrangements persist until an event supersedes them: a new agenda, a mode change, a release, a reset. White geometry accumulated within a session remains visible as the session's structure of confirmed trust.
---
## 11. Witness Layer
### 11.1 HUD Regions
| Region | Content |
|---|---|
| Upper Left | AURA, mode, primary state |
| Upper Right | Active disc, scene, anticipation or protocol state |
| Lower Left | Station, orbit, build identity |
| Lower Right | Input state, dual counter (SEALED: N / VAULTED: N), vault state |
Style carries forward from the existing loop: monospace, uppercase, wide tracking, low opacity. Channel colors per Section 3.
### 11.2 The Witness Ledger
Right edge. Monospace. The last five events, oldest fading. Derived purely from the state store, never from animation. If motion and ledger disagree, the ledger is true. The ledger is the auditable trail of the public stream.
### 11.3 Public Redaction
Redaction is a filter on the state-to-text projection only. Events carrying visibility: private render their full choreography but project generic text: ITEM SEALED rather than the item label. Choreography is never falsified to hide content; text is generalized instead.
### 11.4 Witness Templates
Templates required for: Idle, Listening, Anticipating, Planning, Forging, Meeting, Building, Sealing, Registering, Holding, Released, Fault.
---
## 12. Motion Physics
| Quality | Rule |
|---|---|
| Easing | easeInOutSine and easeOutCubic families, damped arrival. Carried from the proven loop. |
| Tempo | Slow to medium. Ceremonies have fixed durations (Sections 6.1, 8). |
| Concurrency | One transition at a time. Arrivals, relays, formations queue. The queue protects the liturgy from event bursts. |
| Arrival | Saucers arc inward, decelerate, dock. Seat ring brightens on dock, not before. |
| Departure | Light dims, thread fades, lift, orbital exit, seat returns to dim. |
| Prohibited | Elastic bounce, hard snaps, jitter, particle bursts, collision chaos, ambient busywork. |
---
## 13. Architecture
Three layers. Strict separation.
| Layer | Responsibility | Rule |
|---|---|---|
| State Store | Holds truth (Section 10) | Mutated only by the event interpreter |
| Event Interpreter | Validates events, mutates state, enqueues transitions | The only writer. Rejects malformed or out-of-grammar events. |
| Choreography Library | Parameterized verbs: enterGraduate(seat), reformDisc(disc, form), runSeal(subject), runDescent(subject) | Reads state, renders, never decides |
### 13.1 Stack (v1)
| Layer | Choice |
|---|---|
| Rendering | HTML Canvas, single file, carried forward from aura_unified_loop |
| Animation | Existing damped easing utilities, refactored into the choreography library |
| State | In-memory JSON store |
| Event input | JSON event file playback (simulated queue) |
| Live input | WebSocket or local bridge, later. Same interface, different transport. |
| Stream | OBS browser source, 16:9 safe |
| Upgrade path | PixiJS or beyond only after the grammar is proven. Not before. |
---
## 14. MVP Scope
### 14.1 Included
- Three discs, spine, Foundation Ring
- Aura with full state set including Anticipating
- Six seats, six v1 graduates
- Three glyph families, eight v1 glyphs
- Diamond lifecycle, full six-stage rendering
- Five modes with transition ceremony
- Confirmation Seal and Registration Descent ceremonies
- Anticipation doctrine, holding and response
- HUD, Witness Ledger, redaction filter
- JSON event playback with hold semantics
### 14.2 Excluded
- Live backend integration
- Interactive control surface
- 3D rendering
- Analytics, drill-down, dense data display
- Expanded cast or glyph registry
- Audio (designed later against the Aura Radio constraint, not improvised)
---
## 15. Success Criteria
The dashboard succeeds if:
1. A stranger passes the Glance Test in under five seconds.
2. Gold appears only at human confirmation, and viewers learn this without being told.
3. The Foundation Ring fills across a session and the accumulation feels earned.
4. Waiting states feel patient and alive, never dead and never busy.
5. The interface remains sparse. Restraint survives feature growth.
6. The simulated playback file can be swapped for a live socket without touching the renderer.
---
## 16. Open Items
| ID | Item | Question | Status |
|---|---|---|---|
| OI-1 | Foundation persistence horizon | Ruled per ATD-A4: session-only in MVP; VAULT-loaded inherited layer deferred. | RULED, CLOSED |
| OI-2 | Graduate visual differentiation | How do six cast members remain distinguishable within the monochrome-plus-channels constitution: silhouette, seat position, label, or motion profile? | OPEN |
| OI-3 | First real event source | Which Axis surface emits the first live events when Phase 5 arrives? | OPEN, deferred |
| OI-4 | Audio doctrine | Event-to-sound mapping, designed against Aura Radio compatibility. | OPEN, deferred past MVP |
---
## 17. Closing Statement
The dashboard tells one story with a small grammar and total honesty. Proposals flicker. Work runs cyan. Confirmation turns structure white. Gold belongs to the human alone. Memory descends in purple and becomes foundation. When the human pauses, the chamber waits in anticipation, and when the human speaks, the chamber answers.
The chamber waits. The user invokes. The work resolves. The seal completes. The foundation grows.
End of ATD-001 v0.5 RevE. Preserved as design law. Build authority flows through ATD-002 RevB.
