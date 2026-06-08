# BUILD REPORT — Aura Theater Event Playback MVP (ATD-002 RevB)

Builder: Claude Code. Governing law: ATD-001 RevE (supersedes RevD; adds ATD-A7 gate
locus doctrine). Build brief: ATD-002 RevB (sealed).
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

## E. Acceptance checklist results (P5)

Verified against full SEQ-001 playback in headless Chromium (puppeteer-core +
@sparticuz/chromium) at 1920x1080. Logic invariants asserted programmatically;
visual beats captured to `docs/p5-shots/`; machine report at `docs/p5-verify.json`.

| # | Item | Result | Evidence |
|---|------|--------|----------|
| 1 | Glance Test (mode / cast / lifecycle in <5s) | PASS | Mode in HUD + active-disc emphasis; labeled saucers at seats; diamond lifecycle flicker→white→gold→purple→mark. Shots t01,t21,t47,t85,t92. Final human Glance Test is the standing acceptance test. |
| 2 | Gold seal-pulse fires exactly twice, nowhere else | PASS | Gold drawn only in the seal ceremony bump (t46, t79 ceremonies) + residue marks (residue, not a source). t47_8/t81_9 shots show the two pulses. |
| 3 | No cyan→white without a seal ledger entry | PASS | Craft glyphs hold cyan/resolved; only `runSeal` turns a diamond white and it logs SEALED. |
| 4 | Anticipation windows breathe, held white, zero busywork | PASS | `breath()` on period T_ANTIC_PERIOD over awaiting diamond + Aura; held geometry persists. Shots t40 (and t73). |
| 5 | Exactly one transition at a time; bursts queue | PASS | Single active queue item + T_QUEUE_GAP; no overlap, no warnings logged. |
| 6 | Private events: full choreography, generic ledger labels | PASS | `ITEM PROPOSED` / `ITEM SEALED` shown for the private diamond_002 events; `BUILD OUTPUT` never appears in the ledger (p5-verify.json). |
| 7 | Mark persists; HUD SEALED:2 / VAULTED:1; 1 mark; VAULTED==marks always | PASS | Digest: sealed 2, vaulted 1, marks 1. VAULTED and mark count both increment only at descent completion. Shot t92. |
| 8 | Mode transitions dim T_DIM then reform T_REFORM; no silent transitions | PASS | `modeTransition` queues dim (T_DIM) + reform (T_REFORM) with dim overlay; mode/disc switch at the boundary. |
| 9 | Gate glyph visuals appear on the spine only | PASS | Per ATD-A7 (RevE): the gold pulse is a gate-channel signal and fires on the spine (full-length gold tint + a gold gate node at the spine's heart). The diamond receives only white stabilization + a white ring; it emits no gold. The Register gate runs on the spine (descent). Shots t47_8, t80_8. |
| 10 | state_hold leaves the chamber fully structured; nothing decays | PASS | Hold is the default; t92 holds indefinitely. Shot t92. |
| 11 | Runs from disk, no network, 1920x1080 OBS browser source | PASS | `external: []` (request interception aborted any non-file/data URL); renders full-frame at 1920x1080. |
| 12 | Restart reproduces identical ceremony (determinism) | PASS | Independent replays produce an identical state digest; no `Math.random()` anywhere in the file (only the comment naming the prohibition). |

Builder responsibility ends at the tagged, accepted artifact (§12). Deployment to
`aura.scrollschool.io/theater/` (cPanel `public_html/theater/index.html`) is the Human
Architect's step; no Builder deploy action taken.

## F. Post-P5 amendment — ATD-A7 gate locus doctrine (ATD-001 RevE)

The P5 candidate flagged a tension between §5.4 (gate glyphs on the spine only) and §8.1
(seal acts on the diamond), and rendered the gold pulse at the diamond as one defensible
reading. The Human Architect ruled the question via **ATD-001 RevE / ATD-A7**: a gate
glyph and the gold pulse are gate-channel signals that render on the spine only; a
ceremony may act on its subject at the subject's location, but that effect is white
stabilization, never gold. "Confirmation comes to the work; gold belongs to the gate."

Build updated to comply (no doc alteration by Builder — RevE supplied by the design lead
and committed verbatim to `docs/`):
- The seal gold pulse now fires on the **spine**: a full-length gold tint plus a gold gate
  node at the spine's heart (`drawSpine`).
- The diamond's seal visual is now **white only** — white stabilization + a white ring
  closure; the diamond emits no gold (`drawDiamonds`, sealing stage).
- Re-verified headless: gold appears only during the two seal pulses (on the spine) and as
  foundation residue; diamonds hold white; all other invariants unchanged
  (SEALED 2 / VAULTED 1 / 1 mark, deterministic, no network). Evidence: shots t47_8 and
  t80_8 (gold on spine, diamond white).

RevD is retained in `docs/` as superseded lineage; RevE is the current governing law.
