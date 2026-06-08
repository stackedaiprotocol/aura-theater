# BUILD REPORT — Aura Theater Event Playback MVP (ATD-002 RevB)

Builder: Claude Code. Governing law: ATD-001 RevD. Build brief: ATD-002 RevB (sealed).
Working branch: `claude/youthful-ramanujan-A2inC`. Deliverable: `aura_theater_v1.html`.

This report records authorizations, deviations, and flag resolutions. Per ATD-002 §1 / §2,
the Builder may not alter confirmed decisions; deviations are recorded here, not absorbed.

---

## A. Phase-gate consolidation authorization (recorded BEFORE the consolidated run, per §10.1)

ATD-002 §9 specifies stop-and-present at each phase boundary. §10.1 permits consolidating the
gates "only by explicit Human Architect authorization, recorded in docs/BUILD-REPORT.md before
the consolidated run begins."

**Authorization granted.** The Human Architect explicitly authorized building P1 through P5
continuously with a single presentation at the end (ruling given during pre-build planning,
in answer to the scope question "How far should the first build session go before stopping?").
This entry is recorded prior to the start of the consolidated run, satisfying §10.1. Momentum
is not authorization; this explicit ruling is.

## B. Deviation — clean vanilla build, lineage echoed not imported

The proven loop `aura_unified_loop` (build v1.3) was supplied by the Human Architect and is
committed read-only at `reference/aura_unified_loop_v1.3.html`. Per §12 it is lineage and feel
reference only; it is never imported or copied wholesale. The deliverable is built clean and
vanilla against ATD-002 RevB, echoing the loop's confirmed primitives:

- Easing/util: `damp`, `lerp`, `clamp`, and `easeInOutSine` (the loop's `easeIO`,
  `0.5 - 0.5*cos(pi*t)`); `easeOutCubic` added (not present in the loop).
- Tokens/constants: cyan `159,212,232`, gold `244,213,141`, void `#05070d`, `FT = 0.30`, `TAU`.
- Draw idioms: ellipse-squash discs, vertical-gradient spine (1.1 px), rotating-square diamond,
  ring/node/zero-seat marks.
- HUD/CSS: monospace 11 px, letter-spacing 0.18 em, uppercase; 34x34 corner brackets at 22 px;
  title/readout/footer insets 30 px / 64 px.

Explicitly NOT carried (would violate the brief):
- The loop's `Math.random()` star/jitter fields — ATD-A6 (§3.4) prohibits RNG anywhere in the
  file. All instability is re-expressed as layered sine functions of scene time.
- 9-seats-per-disc — the brief mandates 6 fixed Guild seats (§3.2).
- The self-cycling phase-timeline narrative — the theater is event-script-driven (§8).

## C. Flag resolutions

- **F1 — Seal-by-commit.** ATD-001 RevD and ATD-002 RevB committed verbatim to `docs/` (supplied
  by the design lead, no Builder alteration), completing the seal-by-commit defined in the brief
  status line.
- **F2 — Reference loop (RESOLVED).** Supplied as `aura_unified_loop_9.html` (internal build
  v1.3). Stored at `reference/aura_unified_loop_v1.3.html` to match the §12 path. Source filename
  noted here for the record.
- **F3 — Build string (RESOLVED).** Design-lead Errata E1 corrected §5.2 Lower Left from
  `v1.0` to `v1.1`. The HUD renders `BUILD: ATD-002 v1.1`.

## D. Implementation notes

- Determinism: all animation is a function of the playback clock (elapsed seconds), with no RNG
  and no wall-clock-dependent integrators, so restart reproduces the identical ceremony
  (checklist item 12) and equal timestamps yield equal frames (§3.4).
- Ledger timestamps are derived deterministically as a fixed base time (14:00:00) plus the
  event `t` offset, so the witness trail is reproducible.
- `surfaceSignal` has no duration in the §4 timing table; a local fade constant is used for the
  amber surfacing only. Recorded here as a render detail, not a new governance constant.

## E. Acceptance checklist results

To be completed at P5 (see §10). Results recorded here after the full SEQ-001 verification run.
