# ATD-003
## Theater Integration Doctrine and v1.1 Upgrade
### Doctrine plus Build Brief

| Field | Value |
|---|---|
| Document ID | ATD-003 |
| Version | v1.0 |
| Revision | C |
| Date | 2026-06-07 |
| Project Family | AUMX / Scroll School / Aura / Axis Live |
| Extends | ATD-001 RevE (design law), ATD-002 RevB (sealed build brief) |
| Status | Draft for Human Architect confirmation. Pre-build flags F-A, F-B, F-C, G1 ruled in this revision. On confirmation, Part II seals and Build Mode opens for the v1.1 increment. |
| Builder | Claude Code. May not alter sealed ATD-001 RevE or ATD-002 RevB doctrine. Deviations recorded in docs/BUILD-REPORT.md. |
| Truth Posture | Part I is proposed doctrine. Part II is a proposed build brief. Part III is a fixed boundary. |

### Flag Resolutions (pre-build review, 2026-06-07)

| Flag | Ruling | Section |
|---|---|---|
| F-A, branch and base | v1.1 branches off `main` after the v1.0 seal-merge. Seal target is `f5d8c12` (post luminance change order), not `5aba546`. If the Human Architect prefers not to seal v1.0 first, the lawful fallback is to continue v1.1 on the existing branch that carries the accepted v1.0 as its base. | 17 |
| F-B, deliverable filename | The v1.1 deliverable continues to evolve the existing file `aura_theater_v1.html`. The artifact version lives in the build string, not the filename. Deployment renames to `index.html` regardless. | 8 |
| F-C, multi-mount from disk | Accepted split: from-disk runs single-mount playback only. Multi-mount synchronization and Document Picture-in-Picture verify over a served origin (local http server or the deployed subdomain), because file:// yields an opaque origin that partitions BroadcastChannel and denies the secure context PiP requires. | 13, 16 |
| G1, sim_completed resolution | Corrected. `sim_completed` resolves to cyan and holds, awaiting confirmation, identical to `glyph_resolved`. The prior wording "resolves to white" was an error: it would have been self-promotion to confirmed-white without a confirmation event, violating ATD-001 Rule 4 and ATD-A6. White is reached only through a seal. The Builder's law-forced default is adopted as the ruling. | 10 |

---

# PART I. INTEGRATION DOCTRINE

## 1. Position

The theater is a lens, not the cockpit. Axis must function completely with the theater off. The theater adds legibility and witness; it never adds capability, and it never gates work. This position is the parent of every rule below.

## 2. Law T1, Axis Emits and the Theater Witnesses

The integration surface is the event bus, not the user interface. Axis emits a governed event for each real operation. The theater subscribes read-only and renders what it understands, ignoring what it does not.

The consequence is strategic: the theater is never integrated feature by feature. Each new Axis capability, a cron job, a LogBoss field capture, a simulation, a forge operation, ships its event alongside its own logic, and the theater renders it because it was already listening. Integration is a one-line emit, never a second codebase maintained in lockstep. When a project changes, Axis emits the project event and the Project Disc reforms, not because a disc-spin was wired into the project module, but because the disc was always listening.

## 3. Law T2, The Theater Is Never an Input

The theater witnesses. It does not control. No element of the rendered chamber may change Axis state. There is no clicking a disc to do work, no dragging an artifact to seal it, nothing. The only permitted interactions are view operations: changing intensity, popping out a window, moving that window to another screen. View operations cross no governance gate and grant no permission. The instant the theater becomes a control surface it becomes a game, and authority leakage becomes possible. Read-only witness is the entire discipline that keeps Axis serious.

## 4. Law T3, Visual Weight Tiers

Not every event deserves a ceremony. As event volume grows, weight is what prevents the chamber from becoming a slot machine. Every event type declares one of three weights.

| Tier | For | Visual Behavior | Constraints |
|---|---|---|---|
| AMBIENT | Routine, high-frequency events (cron ticks, ordinary field logs, heartbeats) | A soft, brief, low-luminance pulse on the relevant disc or node. Sub-second. Coalesces: many within a short window render as one gentle shimmer. | Never queues. Never blocks. Never produces gold. Never interrupts a higher tier. |
| NOTABLE | Meaningful state changes (project loaded, graduate invoked, glyph lifecycle, simulation, forge form, mode entered) | Full choreography verbs, queued one at a time per ATD-002. | The normal theater motion. May not borrow ceremonial signals. |
| CEREMONIAL | Governance events (seal, registration) | The reserved ceremonies: gold seal pulse on the spine (ATD-A7), registration descent and foundation mark. | Rare. Non-interruptible. Protected from all lower-tier traffic. Gold remains exclusive to this tier. |

Weight is a fixed property of the event type. A routine event can never escalate to ceremony, and a busy field day cannot turn a cron tick into gold. The seal stays meaningful precisely because the cron tick is a whisper beneath it.

## 5. Optionality, Intensity Modes

The theater exposes three intensities. These are view settings, distinct from the five Axis modes, and they never alter Axis behavior.

| Intensity | Renders | Use |
|---|---|---|
| OFF | Nothing. The theater is not drawn and consumes no render loop. | The operator who finds it a distraction loses nothing. |
| GLANCE | The compact profile: discs, spine, active-disc glow, ceremonies, foundation marks, and a single status line. Ambient whispers are faint or coalesced; the witness ledger is suppressed. | The small HUD witness in a cockpit corner. |
| THEATER | The full profile from ATD-002: all tiers, full HUD, witness ledger. | The full window on a second or third screen. |

Naming guard: GLANCE is the intensity; AMBIENT is the weight tier. They are not the same word and not the same concept.

## 6. Doctrine Preservation

ATD-003 extends the grammar; it does not breach sealed law. The following remain inviolate and constrain every upgrade in Part II:

1. Five modes only. Free, Plan, Forge, Meeting, Build. Help is not a mode. Help is a transient witness event, never a mode transition.
2. Three discs, fixed. Forge creating a disc does not create a fourth permanent disc. A forge operation reforms the Project Disc into a forge form or raises an ephemeral craft lattice that resolves; the three-disc spatial doctrine holds.
3. Gold is gate-locus and ceremonial only. Per ATD-A7, gold fires on the spine, never on the artifact, and only at a seal.
4. Dual counter, no fake activity, one transition at a time, determinism for scripted sources. All carried forward unchanged.

## 7. The Inner-Child Principle (recorded design value)

The theater teaches the old while it delights the young by the same mechanism: watching the lifecycle resolve, flicker to white to gold to foundation, is how anyone learns the governance model without reading a charter. The delight and the pedagogy are one act. This is recorded as a design value, not a decorative permission. The restraint of the architecture is what makes its moments of wonder trustworthy. An instrument that delights teaches while it delights; a toy delights and teaches nothing. Because every animation is backed by a real event, the theater is structurally incapable of being a toy.

---

# PART II. BUILD BRIEF, v1.1 INCREMENT

## 8. Scope and Deliverable

Upgrade the existing `aura_theater_v1.html` to artifact version v1.1, implementing Laws T2 and T3, the intensity modes, the GLANCE compact profile, an event source adapter, and multi-mount synchronization. All of it is verifiable now through playback and BroadcastChannel, with zero dependency on Axis emitting anything. Remains a single self-contained vanilla file. The filename does not change (F-B); the artifact version lives in the build string, and deployment renames the file to `index.html` regardless.

Build string: set Lower Left to `AURA THEATER v1.1`. This decouples the artifact version from the document revision and supersedes the build-string coupling that produced erratum E1. The build string now names the artifact, not the brief.

## 9. Visual Weight Implementation

Each event type carries a `weight` field: `ambient`, `notable`, or `ceremonial`. The interpreter routes by weight:

- `ambient`: render a direct, non-queued micro-pulse; if another ambient event of the same class arrives within `T_AMBIENT_COALESCE` (suggest 0.8 s), merge into the existing shimmer rather than spawning a second. Ambient events bypass the choreography queue entirely and never delay it.
- `notable`: enqueue one choreography on the existing FIFO queue per ATD-002 Section 12.
- `ceremonial`: run the reserved, non-interruptible ceremony. Lower-tier traffic continues to render but cannot delay or interrupt it.

## 10. Expanded Event Dictionary

Added to the ATD-001 Section 9.1 dictionary. Each row declares weight, target, and behavior. (These additions are canonical and will be folded into ATD-001 at its next consolidation; see Section 18.)

| Event | Weight | Target | Behavior |
|---|---|---|---|
| cron_fired | ambient | relevant disc | Whisper pulse. Coalesces. |
| logboss_field_event | ambient | Guild Disc | Whisper. Coalesces under burst. |
| logboss_field_flag | notable | Guild Disc | A flagged field item earns a single notable pulse, not a ceremony. |
| sim_started | notable | Project Disc | Simulation glyph forms; project disc enters a sim posture. |
| sim_completed | notable | Project Disc | Sim glyph resolves to cyan and holds, awaiting confirmation, identical to glyph_resolved. White is reached only through a seal (G1). |
| forge_disc_created | notable | Project Disc | Project Disc reforms into a forge form, or raises an ephemeral craft lattice that resolves. No fourth permanent disc. |
| anvil_activity | notable | Project Disc | Craft motion on the project layer. Forge-family. |
| help_opened | ambient | Aura | Aura performs a brief witness gesture. No mode change. |
| help_closed | ambient | Aura | Aura returns to prior state. |

All existing events retain their behavior; weights are assigned to them as: ambient (none currently), ceremonial (`seal_completed`, `vault_registered`), notable (all others).

## 11. Intensity Modes and the GLANCE Profile

Implement OFF, GLANCE, THEATER as a runtime setting, cycled by operator key `V`, and settable by URL parameter (`?intensity=glance`) so a host frame or popout can request a profile on load.

GLANCE compact render profile:

| Element | GLANCE |
|---|---|
| Discs, spine | Rendered, scaled to container |
| Active-disc glow | Rendered, the primary mode signal |
| Ceremonies (seal, descent) | Rendered fully. Gold still fires on the spine. |
| Foundation marks | Rendered |
| Ambient whispers | Faint or coalesced only, to avoid clutter at small size |
| Notable choreography | Rendered in reduced form |
| Witness ledger | Suppressed |
| HUD | A single status line: mode plus `SEALED: N / VAULTED: N` |
| Target legibility | Must read clearly at 480 x 270 |

OFF renders nothing and halts the render loop to consume no cycles.

## 12. Event Source Adapter

Abstract the input behind one normalized interface so the interpreter is transport-agnostic. One active source at a time, default `playback`.

| Source | Mechanism | Status |
|---|---|---|
| playback | Embedded or loaded JSON script, advanced on `t` offsets. Deterministic. | Implement now. |
| broadcast | `BroadcastChannel('axis-theater')`. Receives normalized events from another same-origin window or page. | Implement now. |
| socket | WebSocket endpoint receiving the ATD-001 Section 9.2 payload. | Stub the client now; the server is Phase 5. Define the message shape; do not require a live server. |

The payload shape is the ATD-001 Section 9.2 canonical event, extended with the `weight` field. This is the subscribe-ready contract Axis will emit against later.

## 13. Multi-Mount and Popout

- Operator key `P` opens a popout via `window.open` at the same artifact with `?intensity=theater`.
- Where supported, offer Document Picture-in-Picture as the always-on-top variant.
- Synchronization: the source-of-truth instance broadcasts its event stream on `BroadcastChannel('axis-theater')`; secondary mounts run source `broadcast` and render in sync. Opening the file in two windows, one GLANCE and one THEATER, must show one synchronized chamber. This proves the tri-mount (stream surface, cockpit mini, popout) before Axis exists.

Origin constraint (F-C). Multi-mount synchronization and Document Picture-in-Picture require a served origin. Over `file://`, `window.open` produces an opaque, null origin that partitions `BroadcastChannel`, and PiP is denied for lack of a secure context. Therefore: from disk, the artifact runs single-mount playback only, which fully satisfies the carried-forward from-disk requirement. Multi-mount sync and PiP are verified over http(s), either a local server during build or the deployed `aura.scrollschool.io` origin. This is an accurate platform boundary, not a compromise of doctrine, and it aligns with the fact that the live cockpit mount will always be served.

## 14. Verification Script, SEQ-002 LIVING CHAMBER

A roughly 76-second script exercising the new grammar. Embedded alongside SEQ-001; operator selects which to play.

```json
{
  "script_id": "SEQ-002",
  "title": "LIVING CHAMBER",
  "events": [
    { "t": 0.0,  "event_type": "mode_entered",       "weight": "notable",    "mode": "free",  "subject_id": "system" },
    { "t": 4.0,  "event_type": "cron_fired",          "weight": "ambient",    "mode": "free",  "subject_id": "cron_a", "disc": "guild" },
    { "t": 6.0,  "event_type": "cron_fired",          "weight": "ambient",    "mode": "free",  "subject_id": "cron_b", "disc": "guild" },
    { "t": 9.0,  "event_type": "mode_entered",        "weight": "notable",    "mode": "plan",  "subject_id": "system" },
    { "t": 14.0, "event_type": "project_loaded",      "weight": "notable",    "mode": "plan",  "subject_id": "project_22", "disc": "project", "label": "PRJ-22" },
    { "t": 19.0, "event_type": "graduate_invoked",    "weight": "notable",    "mode": "plan",  "subject_id": "planner", "seat": "S2" },
    { "t": 23.0, "event_type": "logboss_field_event", "weight": "ambient",    "mode": "plan",  "subject_id": "lb_1", "disc": "guild" },
    { "t": 23.6, "event_type": "logboss_field_event", "weight": "ambient",    "mode": "plan",  "subject_id": "lb_2", "disc": "guild" },
    { "t": 24.2, "event_type": "logboss_field_event", "weight": "ambient",    "mode": "plan",  "subject_id": "lb_3", "disc": "guild" },
    { "t": 27.0, "event_type": "mode_entered",        "weight": "notable",    "mode": "forge", "subject_id": "system" },
    { "t": 31.0, "event_type": "sim_started",         "weight": "notable",    "mode": "forge", "subject_id": "sim_a", "disc": "project", "label": "SIM-A" },
    { "t": 33.0, "event_type": "cron_fired",          "weight": "ambient",    "mode": "forge", "subject_id": "cron_c", "disc": "project" },
    { "t": 35.0, "event_type": "sim_completed",       "weight": "notable",    "mode": "forge", "subject_id": "sim_a" },
    { "t": 39.0, "event_type": "forge_disc_created",  "weight": "notable",    "mode": "forge", "subject_id": "forge_form_1", "disc": "project" },
    { "t": 43.0, "event_type": "glyph_loaded",        "weight": "notable",    "mode": "forge", "subject_id": "glyph_synthesis", "disc": "project", "family": "craft" },
    { "t": 47.0, "event_type": "glyph_resolved",      "weight": "notable",    "mode": "forge", "subject_id": "glyph_synthesis" },
    { "t": 49.0, "event_type": "proposal_formed",     "weight": "notable",    "mode": "forge", "subject_id": "diamond_001", "disc": "project", "label": "FORGE OUTPUT" },
    { "t": 52.0, "event_type": "awaiting_human",      "weight": "notable",    "mode": "forge", "subject_id": "diamond_001" },
    { "t": 56.0, "event_type": "cron_fired",          "weight": "ambient",    "mode": "forge", "subject_id": "cron_d", "disc": "guild" },
    { "t": 60.0, "event_type": "seal_completed",      "weight": "ceremonial", "mode": "forge", "subject_id": "diamond_001", "actor": "human_architect", "label": "FORGE CONFIRMED" },
    { "t": 64.0, "event_type": "vault_registered",    "weight": "ceremonial", "mode": "forge", "subject_id": "diamond_001" },
    { "t": 69.0, "event_type": "cron_fired",          "weight": "ambient",    "mode": "forge", "subject_id": "cron_e", "disc": "guild" },
    { "t": 72.0, "event_type": "help_opened",         "weight": "ambient",    "mode": "forge", "subject_id": "help" },
    { "t": 74.0, "event_type": "help_closed",         "weight": "ambient",    "mode": "forge", "subject_id": "help" },
    { "t": 76.0, "event_type": "state_hold",          "weight": "notable",    "mode": "forge", "subject_id": "system" }
  ]
}
```

What it proves: ambient coalescing (t23 to t24.2 logboss burst becomes one shimmer), ambient non-blocking during anticipation and ceremony (t56 and t69 cron under the seal), the forge form reforming the Project Disc without a fourth disc, help as a non-mode witness gesture, and the seal still firing gold on the spine with one mark in the foundation ending `SEALED: 1 / VAULTED: 1`.

Script selection: operator keys `1` and `2` select SEQ-001 and SEQ-002 respectively. `R` restarts the active script, per the carried-forward operator keys.

## 15. Build Phases

| Phase | Scope | Present |
|---|---|---|
| P1 | Weight field, three-tier routing, expanded event dictionary, ambient coalescing | SEQ-002 t0 to t39, tiers visibly distinct |
| P2 | Intensity modes (OFF/GLANCE/THEATER), GLANCE compact profile | Side-by-side GLANCE and THEATER stills |
| P3 | Source adapter (playback, broadcast, socket stub), popout, multi-mount sync | Two synced windows |
| P4 | Full SEQ-002 playback, acceptance checklist | Complete run plus checklist results |

Recommended gate: stop-and-present after P2. The GLANCE compact profile is a legibility judgment that wants the Human Architect's eyes before the rest proceeds. P1, and P3 through P4, may run continuously under recorded authorization per ATD-002 Section 10.1.

## 16. Acceptance Checklist

Carried forward from ATD-002 Section 10, all twelve still pass. Added for v1.1:

13. Three weight tiers are visually distinct. Ambient never queues, never blocks, never produces gold.
14. During the t52 to t60 anticipation and the t60 seal, the concurrent cron whispers (t56) neither delay nor interrupt the ceremony.
15. The logboss burst at t23 to t24.2 coalesces into one gentle shimmer, not three separate animations.
16. `forge_disc_created` reforms the Project Disc. No fourth permanent disc appears. Three-disc doctrine intact.
17. `help_opened` renders as a transient witness gesture. The mode does not change. Five-mode doctrine intact.
18. Intensity OFF renders nothing and halts the loop. GLANCE renders the compact one-line profile, legible at 480 x 270. THEATER renders the full profile. Cycled by `V`.
19. Over a served origin (local http server or the deployed subdomain), two instances synchronize via BroadcastChannel within one frame of tolerance on scripted events. From disk, single-mount playback is the verified mode per item 11; multi-mount is not expected over file:// (F-C).
20. The theater remains never an input: clicking the canvas changes no state. Only operator keys and host view controls act.
21. Preserved: gold only at seals and only on the spine (ATD-A7). Dual counter holds. Playback source remains deterministic; live and broadcast sources are exempt from the determinism check by nature.

---

# PART III. OUT OF SCOPE, PHASE 5 BOUNDARY

The following are deliberately excluded from this brief and belong to the cockpit-integration session. They require work in the Axis repository, not the theater repository, and the theater Builder does not touch them.

| Item | Belongs To |
|---|---|
| Axis actually emitting events from real operations | Axis frontend and Render backend, separate session |
| Embedding the theater inside the Axis cockpit React application | Axis frontend |
| A live WebSocket server | Axis backend. The client adapter and message shape are delivered here; the server is not. |
| First real event source ruling (ATD-001 OI-3) | The cockpit-integration session |

The theater is made subscribe-ready by this brief. Axis is made to emit by the next one. The seam between them is the normalized event payload, defined and frozen here.

---

## 17. Infrastructure

| Item | Ruling |
|---|---|
| Repository | `github.com/stackedaiprotocol/aura-theater`, continuing from the accepted v1.0 artifact `f5d8c12`. |
| Branch and base (F-A) | Recommended path: the Human Architect first seals v1.0 by merging `f5d8c12` to `main`, then authorizes a new working branch `claude/atd-003-integration` off `main`. This keeps `main` as canonical lineage and each version's seal a clean merge. Lawful fallback if v1.0 is not sealed first: continue v1.1 on the existing branch that already carries the accepted v1.0 as its base. The Builder does not switch or create branches without explicit Human Architect authorization. |
| Build string | `AURA THEATER v1.1`, per Section 8. |
| Deployment | Unchanged from ATD-002 Section 12. Human Architect performs the cPanel upload after acceptance. No Builder deploy. |

## 18. Consolidation Note

The expanded event dictionary (Section 10) and the visual weight tiers (Law T3) are canonical from this document forward. At the next revision of ATD-001, they fold into Section 9.1 and Section 3 respectively, and ATD-001 increments to RevF. Until then, ATD-003 governs them and the cross-reference stands. Recorded, not absorbed.

---

End of ATD-003 v1.0 RevC. Pre-build flags F-A, F-B, F-C, G1 ruled. On Human Architect confirmation, Part II seals and Build Mode opens for the v1.1 increment. Part I is doctrine effective on the same confirmation.

---

## Build session record (continuing on branch claude/youthful-ramanujan-A2inC)

Per the F-A ruling's lawful fallback and the Human Architect's session decision, the v1.1
increment is built on `claude/youthful-ramanujan-A2inC` (which carries accepted v1.0 `f5d8c12`
as its base), not a new branch off `main`. v1.0 was not sealed to `main` first; the Builder
does not create branches or merge to `main` without explicit authorization. Gate authorization
and checklist results are recorded in `docs/BUILD-REPORT.md`.
