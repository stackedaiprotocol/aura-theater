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

---

# v1.1 INCREMENT — ATD-003 RevC (Integration Doctrine)

Governing: ATD-001 RevE + ATD-002 RevB (sealed) + ATD-003 RevC (sealed by this commit).
Working branch: `claude/youthful-ramanujan-A2inC` (continues accepted v1.0 `f5d8c12`).

## G. Authorizations and rulings (recorded BEFORE the v1.1 run)

- **Branch (F-A):** v1.1 continues on `claude/youthful-ramanujan-A2inC` — the lawful fallback,
  since v1.0 is not yet sealed to `main`. The Builder does not create branches or merge to
  `main` without explicit Human Architect authorization.
- **Gate consolidation (§15 / §10.1):** Human Architect authorized building **P1→P2
  continuously, stop-and-present after P2** (GLANCE legibility judgment), then **P3→P4
  continuously**. Recorded here before the run; momentum is not authorization, this ruling is.
- **G1 (sim_completed):** RevC adopts the law-forced default — `sim_completed` resolves to
  **cyan and holds, awaiting confirmation** (identical to `glyph_resolved`). White only via a
  seal. Implemented accordingly.
- **F-B:** deliverable remains `aura_theater_v1.html`; artifact version lives in the build string.
- **F-C:** from-disk = single-mount playback; multi-mount sync + Document PiP verified over a
  served origin (local http) only.
- **Build string:** Lower-Left changes from `BUILD: ATD-002 v1.1` to `BUILD: AURA THEATER v1.1`
  (§8) — the build string now names the artifact, not the brief; supersedes the E1 coupling.

## H. P2-gate refinements (design-lead-authorized at GLANCE approval)

The Human Architect approved the GLANCE compact profile at 480×270 with three refinements,
folded in before P3 (these refine the P2 deliverable; no sealed doctrine altered):

1. **Mode word brightened.** In the GLANCE status line the mode word renders brightest
   (`.gmode` = `--bright`), counters a step quieter (`.gctr` = `--hud`), so a glance lands on
   mode first.
2. **Ceremonial-only GLANCE echo.** In GLANCE, `seal_completed` / `vault_registered` surface a
   single transient line that fades over `T_GLANCE_ECHO` (3.2 s). Notable and ambient stay silent
   in GLANCE; THEATER's full ledger is unchanged; "ambient never ledgers" is preserved. Purpose:
   keep gold meaningful in the corner view.
3. **Ambient perceptibility floor.** A lone whisper now reads in THEATER (core-dot peak ≈ 0.52),
   so a real event never renders as literally nothing. Bursts still coalesce (one pulse, no
   strobe). GLANCE still lets whispers fade near to nothing. Evidence: `seq2_t4_lone_whisper_theater.png`.

## I. v1.1 acceptance checklist results (P3–P4)

Carried items 1–12 re-run on SEQ-001 (unchanged): `2 / 1 / 1`, gold only on the spine seal +
residue, deterministic, no external network. New items on SEQ-002:

| # | Item | Result | Evidence |
|---|------|--------|----------|
| 13 | Three weight tiers distinct; ambient never queues / blocks / golds | PASS | `ambientInQueue:false`; ambient routed direct, visual-only. v1.1-verify.json |
| 14 | cron whispers (t56/t69) don't delay/interrupt the seal ceremony | PASS | ambient bypasses the queue; ceremony non-interruptible; SEQ-002 ends 1/1/1 |
| 15 | logboss burst t23–t24.2 coalesces to one shimmer | PASS | `liveLogbossPulses:1, merged:3` |
| 16 | forge_disc_created reforms Project Disc; no 4th disc | PASS | `discCount:3`; `seq2_t40_forgeform.png` |
| 17 | help_opened is a transient gesture; no mode change | PASS | mode forge→forge across t72–t74 |
| 18 | OFF halts loop; GLANCE one-line legible at 480×270; THEATER full; V cycles | PASS | `seq2_t61_glance_480x270.png`, `seq2_off_480x270.png` |
| 19 | Two instances sync via BroadcastChannel over a served origin | PASS | localhost: pageB(broadcast) `hasDiamond:true`, `ledgerLen:11` matching pageA. v1.1-verify-p4.json |
| 20 | Theater is never an input — clicking canvas changes no state | PASS | `clickNoState:true` (digest identical before/after two clicks) |
| 21 | Gold only at seals on spine; dual counter; SEQ-002 ends 1/1/1; playback deterministic | PASS | end `1/1/1`; `deterministic:true` (broadcast/socket exempt by nature) |

Verification: headless Chromium. Logic/digests at file:// (`docs/v1.1-verify.json`); served-origin
checks (multi-mount, click, network) over `http://localhost` (`docs/v1.1-verify-p4.json`). Stills
in `docs/v1.1-shots/`. Builder responsibility ends at the accepted artifact; no merge/tag/PR/deploy.
