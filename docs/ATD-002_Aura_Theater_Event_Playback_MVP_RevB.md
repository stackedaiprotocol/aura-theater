# ATD-002
## Aura Theater Event Playback MVP
### Build Brief

| Field | Value |
|---|---|
| Document ID | ATD-002 |
| Version | v1.1 |
| Revision | B |
| Date | 2026-06-07 |
| Project Family | AUMX / Scroll School / Aura / Axis Live |
| Governed By | ATD-001 RevD (design law) |
| Status | SEALED upon commit to the aura-theater repo under Human Architect authority. Build Mode opens from this brief and no other. |
| Builder | Claude Code. May not alter confirmed decisions. Deviations recorded as amendments in docs/BUILD-REPORT.md. |
| Truth Posture | Confirmed. Incorporates the dual-counter ruling and the four pre-build review fixes. |
| Errata | E1: Section 5.2 build string corrected from v1.0 to v1.1 by design lead prior to seal-by-commit, resolving Builder Flag F3. |

---

## 1. Build Objective

Produce a single self-contained HTML file, `aura_theater_v1.html`, that plays a scripted JSON event sequence through the full ATD-001 grammar: five modes, the v1 cast, three glyph families, the diamond lifecycle, the Confirmation Seal, the Registration Descent, the Anticipation state, the Witness Ledger, and the Foundation Ring.

No backend. No build tooling. No external dependencies. The file must run from disk and as an OBS browser source at 1920x1080.

The deliverable is judged against the Glance Test and the acceptance checklist in Section 10. The Glance Test is the acceptance test for every visual prototype, permanently.

## 2. Inherited Law

The Builder inherits these rules from ATD-001 RevC without restatement or reinterpretation:

1. Gold is produced by `seal_completed` only. (ATD-D2)
2. Cyan never resolves itself to white without a confirmation event. (Section 3.1, Rule 4)
3. One transition at a time. All choreography queues. (Section 12)
4. Holding is the default. Nothing decays merely because time passes. (Section 10.2)
5. Ledger and HUD derive from the state store, never from animation. (Section 11)
6. Gate glyphs may never appear off-spine. (Section 5.4)
7. No fake activity. The render loop draws what is true. (Section 13)
8. Foundation Ring is session-scoped. No persistence layer in MVP. (ATD-A4)
9. Dual counter per ATD-A5: SEALED counts seal_completed, VAULTED counts vault_registered, and VAULTED always equals foundation_marks.length.

A gap in this brief does not grant permission. Gaps are flagged, not inferred around.

---

## 3. Canvas Layout

Reference frame: 1920 x 1080, 16:9, OBS-safe. All geometry is expressed in normalized coordinates so the renderer scales to any window. Let `W` = width, `H` = height, `S` = min(W, H).

### 3.1 Vertical Architecture

| Element | Center X | Center Y | Radius rx | Notes |
|---|---|---|---|---|
| Aura idle anchor | 0.50 W | 0.14 H | n/a | Hover drift radius 0.015 S |
| Agenda Disc | 0.50 W | 0.30 H | 0.15 S | Smallest disc |
| Project Disc | 0.50 W | 0.50 H | 0.19 S | Middle disc |
| Guild Disc | 0.50 W | 0.70 H | 0.23 S | Largest disc, grounds the stack |
| Foundation Ring | 0.50 W | 0.86 H | 0.13 S | Dim by default |
| Spine | 0.50 W | 0.18 H to 0.86 H | n/a | 1.1 px base weight |

Ellipse vertical squash factor `FT = 0.30` for all discs and the Foundation Ring (ry = rx * FT). Carried from the proven loop.

### 3.2 Guild Seats

Six fixed seat positions on the Guild Disc ellipse at parametric angles, measured counterclockwise from the +x axis:

| Seat | Angle | Default Occupant (v1 script) |
|---|---|---|
| S1 | 330 deg | Builder |
| S2 | 30 deg | Planner |
| S3 | 90 deg | Estimator |
| S4 | 150 deg | Risk Analyst |
| S5 | 210 deg | Scribe |
| S6 | 270 deg | Unassigned, reserved |

Seat position: `x = cx + cos(a) * rx`, `y = cy + sin(a) * rx * FT`. Seat geometry never changes at runtime.

### 3.3 HUD Regions

| Region | Anchor | Inset |
|---|---|---|
| Upper Left | top-left | 30 px top, 64 px left |
| Upper Right | top-right | 30 px top, 64 px right, right-aligned |
| Lower Left | bottom-left | 30 px bottom, 64 px left |
| Lower Right | bottom-right | 30 px bottom, 64 px right, right-aligned |
| Witness Ledger | right edge, vertically centered | 64 px right, last 5 entries, oldest at lowest opacity |
| Corner brackets | four corners | 22 px, 34 x 34 px, carried from existing loop |

HUD typography carries from the existing loop: monospace, uppercase, 11 px, letter-spacing 0.18 em.

### 3.4 Color Tokens

| Token | Value | Channel |
|---|---|---|
| `--void` | #05070d | Background |
| `--flicker` | rgba(223,240,247, alpha-modulated) with 0.08 s irregular alpha jitter | FLICKER |
| `--cyan` | 159,212,232 | CYAN (carried as LINE from existing loop) |
| `--white` | 223,240,247 | WHITE |
| `--gold` | 244,213,141 | GOLD (carried from existing loop) |
| `--purple` | 178,148,232 | PURPLE |
| `--amber` | 232,178,102 | AMBER |
| `--fault` | 220,80,80 | RED, reserved, unused in v1 script |

Flicker is implemented as alpha instability on the white token, never as a separate hue. Flicker always means unresolved.

**Determinism law (ATD-A6).** All instability, flicker, breathing, and drift is computed from layered sine functions of scene time. `Math.random()` is prohibited anywhere in the file. Two playbacks of SEQ-001 must be pixel-equivalent at any given timestamp. A deterministic renderer makes any future discrepancy between two viewers' screens a transport problem, never a rendering one.

---

## 4. Timing Table

All durations in seconds. These are constants in one table at the top of the file, named exactly as below.

| Constant | Value | Governs |
|---|---|---|
| `T_DIM` | 1.2 | Mode transition dim and hold |
| `T_REFORM` | 3.5 | Disc reform spin and lattice re-resolution |
| `T_ARRIVE` | 2.4 | Saucer arc-in, decelerate, dock |
| `T_DEPART` | 2.0 | Saucer lift and orbital exit |
| `T_GLYPH_FORM` | 1.5 | Craft glyph formation to active |
| `T_RELAY` | 1.8 | Relay line draw plus pulse traversal |
| `T_SEAL` | 2.8 | Confirmation Seal ceremony, full sequence |
| `T_DESCENT` | 4.5 | Registration Descent, spine entry to foundation mark settle |
| `T_ANTIC_PERIOD` | 5.0 | Anticipation breath period (one pulse per period) |
| `T_QUEUE_GAP` | 0.4 | Minimum gap between queued transitions |
| `T_LEDGER_FADE` | 0.6 | Ledger entry fade-in |

Easing: `easeInOutSine` for arrivals and reforms, `easeOutCubic` for docking deceleration, damped interpolation (`damp`) for Aura movement. No elastic, no bounce, no snap.

---

## 5. HUD Text States

The HUD is a pure projection of the state store. Required templates:

### 5.1 By Mode

| Mode | Upper Left | Upper Right |
|---|---|---|
| Free | AURA / FREE MODE / LISTENING | ACTIVE DISC: AGENDA / COUNCIL: IDLE |
| Plan | AURA / PLAN MODE / PURPOSE FORMING | ACTIVE DISC: AGENDA / COUNCIL: SEATED |
| Forge | AURA / FORGE MODE / SYNTHESIS | ACTIVE DISC: PROJECT / OUTPUT: FORMING |
| Meeting | AURA / MEETING MODE / COUNCIL IN SESSION | ACTIVE DISC: GUILD / SCRIBE: ACTIVE |
| Build | AURA / BUILD MODE / EXECUTION | ACTIVE DISC: PROJECT / TASK CHAIN: RUNNING |

### 5.2 By State (Lower Right, overrides)

| State | Lower Right |
|---|---|
| Idle / holding | STATE: HOLDING / SEALED: N / VAULTED: N |
| Anticipating | STATE: AWAITING CONFIRMATION / SEALED: N / VAULTED: N |
| Sealing | SEAL: COMPLETING |
| Registering | VAULT: OPEN / MEMORY: WRITING |
| Post-registration | VAULT: CLOSED / SEALED: N / VAULTED: N |

Lower Left is static identity: STATION: AURA-BASE 01 / BUILD: ATD-002 v1.1.

### 5.3 Ledger Entry Format

`HH:MM:SS  EVENT_LABEL` in channel color of the event class. Examples:

```
14:02:11  AGENDA LOADED
14:02:36  PLANNER SEATED
14:03:04  PROPOSAL FORMED
14:03:41  SEALED            (gold)
14:04:12  REGISTERED        (purple)
```

Redaction: events carrying `"visibility": "private"` project generic labels (ITEM SEALED) while choreography runs fully. v1 script includes one private event to prove the filter.

---

## 6. Foundation Mark Behavior

1. Marks are placed on the Foundation Ring ellipse starting at 90 deg (front center), advancing clockwise in 14 deg increments per registration.
2. Each mark: a 2.5 px gold-residue point at 0.35 alpha with a faint 6 px halo. Dim. Permanent for the session.
3. Mark settle: at descent completion, the mark appears at 1.0 alpha and decays to its resting 0.35 alpha over 2.0 s. The decay is the only animation a mark ever performs.
4. Capacity: 24 marks (one ring circuit). Mark 25 onward consolidates: every full circuit collapses to a single brighter milestone notch and the count continues in the HUD. v1 script will not reach this; the rule exists so the behavior is law before it is needed.
5. Marks are not interactive, not labeled, and never flicker. The foundation does not gossip about its contents. The ledger and VAULT hold the detail.

---

## 7. The First Playback Script

Script ID: `SEQ-001 FIRST LIGHT`. Duration: 92 seconds, then permanent hold. Embedded in the file as a JSON array; the player advances on `t` offsets from playback start. The script exercises every event type and every glyph family at least once, in lawful order.

```json
{
  "script_id": "SEQ-001",
  "title": "FIRST LIGHT",
  "events": [
    { "t": 0.0,  "event_type": "mode_entered",      "mode": "free",    "subject_id": "system",      "visibility": "public" },
    { "t": 5.0,  "event_type": "agenda_loaded",     "mode": "free",    "subject_id": "agenda_001",  "visibility": "public",  "label": "SS-OPS-0607" },
    { "t": 10.0, "event_type": "mode_entered",      "mode": "plan",    "subject_id": "system",      "visibility": "public" },
    { "t": 16.0, "event_type": "graduate_invoked",  "mode": "plan",    "subject_id": "planner",     "visibility": "public",  "seat": "S2" },
    { "t": 20.0, "event_type": "graduate_invoked",  "mode": "plan",    "subject_id": "estimator",   "visibility": "public",  "seat": "S3" },
    { "t": 24.0, "event_type": "glyph_loaded",      "mode": "plan",    "subject_id": "glyph_estimate", "visibility": "public", "disc": "agenda", "family": "craft" },
    { "t": 28.5, "event_type": "relay_activated",   "mode": "plan",    "subject_id": "relay_001",   "visibility": "public",  "from": "planner", "to": "estimator" },
    { "t": 31.0, "event_type": "glyph_resolved",    "mode": "plan",    "subject_id": "glyph_estimate", "visibility": "public" },
    { "t": 34.0, "event_type": "proposal_formed",   "mode": "plan",    "subject_id": "diamond_001", "visibility": "public",  "disc": "agenda", "label": "PLAN PROPOSAL" },
    { "t": 37.0, "event_type": "awaiting_human",    "mode": "plan",    "subject_id": "diamond_001", "visibility": "public" },
    { "t": 46.0, "event_type": "seal_completed",    "mode": "plan",    "subject_id": "diamond_001", "visibility": "public",  "actor": "human_architect", "label": "PLAN CONFIRMED" },
    { "t": 50.0, "event_type": "mode_entered",      "mode": "build",   "subject_id": "system",      "visibility": "public" },
    { "t": 56.0, "event_type": "graduate_invoked",  "mode": "build",   "subject_id": "builder",     "visibility": "public",  "seat": "S1" },
    { "t": 59.5, "event_type": "glyph_loaded",      "mode": "build",   "subject_id": "glyph_build_chain", "visibility": "public", "disc": "project", "family": "craft" },
    { "t": 64.0, "event_type": "zero_seat_surfaced","mode": "build",   "subject_id": "signal_001",  "visibility": "public",  "label": "CLASSIFICATION NOTE" },
    { "t": 67.0, "event_type": "glyph_resolved",    "mode": "build",   "subject_id": "glyph_build_chain", "visibility": "public" },
    { "t": 70.0, "event_type": "proposal_formed",   "mode": "build",   "subject_id": "diamond_002", "visibility": "private", "disc": "project", "label": "BUILD OUTPUT" },
    { "t": 72.5, "event_type": "awaiting_human",    "mode": "build",   "subject_id": "diamond_002", "visibility": "public" },
    { "t": 79.0, "event_type": "seal_completed",    "mode": "build",   "subject_id": "diamond_002", "visibility": "private", "actor": "human_architect" },
    { "t": 83.0, "event_type": "vault_registered",  "mode": "build",   "subject_id": "diamond_002", "visibility": "public" },
    { "t": 90.0, "event_type": "graduate_released", "mode": "build",   "subject_id": "estimator",   "visibility": "public",  "seat": "S3" },
    { "t": 92.0, "event_type": "state_hold",        "mode": "build",   "subject_id": "system",      "visibility": "public" }
  ]
}
```

### 7.1 What the Script Proves

| Beat | Grammar Proven |
|---|---|
| t 0 to 10 | Honest idle, agenda reform, mode transition ceremony |
| t 16 to 31 | Seat doctrine, arrivals, craft glyph lifecycle, relay, queue discipline |
| t 34 to 46 | Flicker proposal, nine seconds of true Anticipation, the gold Seal |
| t 50 to 67 | Second mode transition, Build choreography, amber Zero Seat surfacing that does not block |
| t 70 to 79 | Private-visibility redaction proven in ledger while choreography runs fully |
| t 83 | Registration Descent, first foundation mark, SEALED count agrees |
| t 90 to end | Graceful release, then permanent hold. The chamber keeps its structure. |

Note the teaching beat: `diamond_001` is sealed but never registered in v1. Sealing and registration are distinct events, and the script makes the distinction visible.

---

## 8. Internal Architecture

Three layers, strict separation, per ATD-001 Section 13.

```
script JSON  ->  EVENT INTERPRETER  ->  STATE STORE  <-  RENDER LOOP
                       |                                    ^
                       v                                    |
               CHOREOGRAPHY QUEUE  ------------------------ +
```

1. **Event Interpreter.** Validates each event against the Section 9.1 dictionary in ATD-001. Rejects unknown types and out-of-grammar transitions (a `seal_completed` on a diamond not in flicker-or-cyan lineage is a rejected event, logged to console, never rendered). Mutates the state store. Enqueues at most one choreography per event.
2. **State Store.** The Section 10.1 schema from ATD-001, verbatim. The only mutable object in the system.
3. **Choreography Queue.** FIFO, single active transition, `T_QUEUE_GAP` between completions. Ceremonies (Seal, Descent, Mode Transition) are non-interruptible. Anticipation is a held state, not a queued transition.
4. **Render Loop.** Stateless with respect to decisions. Reads the store, draws what is true, every frame.

Keyboard (operator only): SPACE pause, R restart script, H toggle HUD, L toggle ledger. No interactive control surface beyond this, per MVP exclusions.

---

## 9. Build Phases

Sequential. Each phase ends with stop-and-present. The Builder does not begin the next phase until the Human Architect confirms or flags.

| Phase | Scope | Present |
|---|---|---|
| P1 | Static geometry: void, discs, spine, Foundation Ring, seats, corner brackets, HUD frame. No motion. | Full-frame screenshot state |
| P2 | State store, event interpreter, HUD and ledger as pure projections. Events change text only. | Script runs, text-only |
| P3 | Choreography verbs: arrivals, departures, glyph lifecycle, relays, disc reform, Aura states including Anticipating | Beats t 0 to 37 |
| P4 | Ceremonies: Confirmation Seal, Registration Descent, foundation marks, mode transitions in full | Beats t 37 to end |
| P5 | Full SEQ-001 playback, OBS browser-source verification, acceptance checklist run | Complete loop plus checklist results |

---

## 10. Acceptance Checklist

Build is complete when every line passes. Run against the full SEQ-001 playback.

1. Glance Test: a viewer joining at any timestamp can answer mode, cast, and lifecycle within five seconds.
2. The gold seal-pulse fires exactly twice in 92 seconds, both at `seal_completed`, and nowhere else. Persistent gold-residue foundation marks are the residue of those events, not a third source.
3. No cyan element ever transitions to white without a confirmation event in the ledger.
4. During t 37 to 46 and t 72.5 to 79, the chamber visibly waits: held white geometry, breathing pulse on period `T_ANTIC_PERIOD`, zero busywork.
5. Exactly one transition animates at any moment. Burst events queue with visible discipline.
6. The t 70 and t 79 private events render full choreography while the ledger shows generic labels.
7. The foundation mark from t 83 persists to end-of-session. The HUD reads SEALED: 2 / VAULTED: 1 per ATD-A5, and the foundation holds exactly 1 mark. VAULTED equals the mark count at every moment of playback.
8. Mode transitions dim, hold for `T_DIM`, reform for `T_REFORM`. No silent transitions.
9. Gate glyph visuals appear on the spine only.
10. `state_hold` at t 92 leaves the chamber fully structured indefinitely. Nothing decays.
11. File runs from disk, no network requests, and renders correctly as a 1920x1080 OBS browser source.
12. Killing and restarting the file reproduces the identical ceremony. Determinism is a feature, guaranteed by the Section 3.4 determinism law.

### 10.1 Phase Gate Provision

Phase gating follows Section 9: stop-and-present at each phase boundary, Human Architect confirmation before the next phase begins. Any consolidation of gates (for example, building P1 through P5 continuously with a single presentation) is permitted only by explicit Human Architect authorization, recorded in docs/BUILD-REPORT.md before the consolidated run begins. Momentum is not authorization.

---

## 11. Out of Scope

Live event transport, persistence, audio, interactivity beyond operator keys, additional cast or glyphs, mobile layout, and any rendering library. The grammar is proven in Canvas or it is not proven.

---

## 12. Infrastructure and Deployment

| Item | Ruling |
|---|---|
| Repository | `github.com/stackedaiprotocol/aura-theater`. Canonical owner is stackedaiprotocol. Verify no stale `renoschubert` entry in Windows Credential Manager before first push. |
| Branching | Builder works on a working branch, committing per phase. Merge to `main` is the seal, performed only on Human Architect confirmation after P5 acceptance. |
| Reference lineage | The proven loop, `aura_unified_loop` v1.3 HTML, is committed to the repo at `reference/aura_unified_loop_v1.3.html`, read-only, supplied by the Human Architect. It is lineage and feel reference only. The build is clean vanilla against this brief; the reference is never imported or copied wholesale. |
| Deployment target | GoDaddy cPanel, `aura.scrollschool.io`, subfolder `public_html/theater/`, file `index.html` (the renamed deliverable). Folder permissions 0755, file 0644. AutoSSL already covers the subdomain; no DNS work; no Vercel involvement in MVP. |
| Deployment actor | The Human Architect performs the cPanel upload per established hosting pattern. The Builder's responsibility ends at the tagged, accepted artifact. |
| Stream cutover | The existing v1.3 loop remains live at the subdomain root throughout. OBS gains a second browser source at `https://aura.scrollschool.io/theater/`. Cutover is the Human Architect's choice; the old loop persists as fallback scene. |
| Vercel and Axis | No role in MVP by design. Phase 5 live integration (Axis as event emitter via Render backend, possible second mount inside the Axis cockpit on Vercel) is a separate future design session, gated on the grammar being proven in playback. See ATD-001 OI-3. |

---

End of ATD-002 v1.1 RevB. Sealed upon commit to the aura-theater repo under Human Architect authority. Build Mode opens from it.
