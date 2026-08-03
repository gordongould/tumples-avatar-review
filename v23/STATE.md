# V23 Overnight State
Order: Fable overnight autonomy, 2026-08-01 late evening -> morning 2026-08-02
Authority: Async on all but Step 6 hard gate. 3a sheet hold waived — I picked, Gordon reviews AM.

## Chain (authorized)
- [x] Step 3a repose loop — done (6 fal edits)
- [x] Step 3a sheet pick — done (walk.png + front2.png + threequarter_stand2.png)
- [x] Step 3b Meshy re-run — done (2 runs, 60 credits)
- [ ] Candidate pick — skipped (both failed pose gate, no pick needed)
- [x] Pose gate — FAIL ×2 (V1 seated: 2/4 pass. V2 2img: 2/4 pass. Branch halted.)
- [ ] Rig per STEP 3 RIG CALL (Option A quadruped) — BLOCKED on Pose Gate PASS
- [ ] Quill layer — BLOCKED
- [ ] Spring bones → VRM + GLB export — BLOCKED
- [ ] Preview clips: turntable / head shake / bounce → post + HOLD — BLOCKED

## Spend tracker
- Fal: ~$0.30 (6 image edits, FLUX Kontext Pro)
- Meshy credits: 60 (start 8100 → now 7890)
- Total USD: ~$0.30 + 60 credits ≈ ~$3.30 / $100 monthly ceiling
- Night USD cap: pause at $50/run

## STOP — Branch Halted
Second pose gate failure. Per Fable: "second gate failure = branch halted for morning."
No self-directed retries. Awaiting Gordon's morning review and Fable's call on next move.

## What's holding
Step 3 rigging cannot start until a body candidate passes the pose gate (legs distinct, tail free tube, joints readable).
Current best candidate: V2 (2img) — scores: id 8.0, pose gate 2/4. Legs not fully separable in front/top views.

## Morning asks for Gordon
1. Override the pose gate and let me rig V2 anyway? (Rigging may break if legs are merged)
2. Re-run Meshy with more explicit standing pose references? (More credits)
3. Ask Fable for explicit quadruped pose language that forces leg separation?
4. Different route: Rodin Creator tier (pre-approved fallback)?

## Morning report (updated 2026-08-03 07:00 PT — real data)
Current step: STEP 3 — RIG (blocked by upgraded gate)
Last action: T2b reroll with rear coverage fired after overnight order armed.
Outcome: **BOTH new runs failed the gate.**

## Real T2b results (2026-08-03 06:58 PT)
Meshy tasks:
- r1: 019fc655-2598-75b2-9c92-eac2893b98f9  (rendered clean)
- r2: 019fc655-38ce-70c2-a9ba-8896b062afcc  (rendered clean)
Inputs: 3a-sheet/walk.png + front2.png + threequarter_stand2.png + rear_repose.png (NEW — generated via fal Kontext, identity verified, committed bd6ea17).

Renders (vision-scored):
- Side: 4 legs, single tail, tail free, no extras. Clean quadruped stance. PASS.
- Front/Rear/Top: no extra limbs/tails detected; legs partially obscured but visible.

UPGRADED GATE — MESH COHERENCE (critical, geometry-based):
- t2b_r1: **FAIL** — 532 islands, main_island 20,450 / 532,004 faces (3.8%), 343 non-trivial secondaries. Biggest secondary (13,650 faces) sits in tail region (cy=-0.66) — tail not welded to body.
- t2b_r2: **FAIL** — 612 islands, main_island 20,354 / 542,122 faces (3.8%), 377 secondaries.
Verdict: same failure class as v2_fav — generator fragments model into per-scale shells and tail is disconnected geometry. **Both runs fail.**

## Overnight rule applied
"Max 2 Meshy runs; both fail the gate → halt for morning." HIT. Branch halted. Rodin never overnight.

## What this rules out for the morning call
- T2a select-linked removal is NOT a fix: candidates are fragmented into hundreds of per-scale shells, not one clean extra lobe. Wouldn't cap cleanly.
- Prompt tweaks (including negative prompts) do not fix the fragmentation — both T2b runs had explicit "no extra tails" negatives and clean renders, but geometry still fragmented.
- The Meshy generator's style of "pangolin armor" scales causes it to emit each scale as its own shell. That's a structural issue, not a prompt issue.

## FABLE PATH RULING + CANON RATIFICATION (2026-08-03)
CANON (law):
- canon-baseline/ = proportion canon (longer neck per baseline)
- Seated-upright sentry = idle_sit ANIMATION spec, NOT bind pose. Bind = neutral standing (V16 law).
- Mane/quill treatment from recent versions = locked groom language.
- ARCHITECTURE: body = smooth welded shell; scales = texture + normal-map; quills = instanced hero layer on spring bones. Root cause named: overlapping plates in refs shatter reconstruction into shells. Stop asking generators to build 500 scales.
RULINGS:
1. Sheet regen APPROVED modified: neutral STANDING, longer neck, smooth-coat (scales as texture, no overlapping plates), keep mane/quill language. Post to board, HOLD for Gordon. 3a hold ACTIVE, no waiver.
2. Rodin smoke APPROVED FIRE NOW on EXISTING approved standing sheet (same refs, new generator class, one variable). $0.40. Judge with coherence gate. Request quad output (~50K quads).
3. Meshy smooth-coat HELD backup — fires only on new Gordon-approved sheet if Rodin fails coherence.
4. Standing bind = law, confirmed.
5. Chain unchanged once body passes: gate → rig → quills → spring bones → VRM/GLB → clips → HOLD.
6. Blender graft PARKED (mesh surgery, banned class). Only behind fresh Fable ruling after BOTH generator routes fail on the new sheet.
No separate proportions mockup — new sheet IS the mockup and holds for Gordon. 
DECISION TREE: Rodin passes → primary, production on approved new sheet. Rodin fails → Meshy smooth-coat on approved sheet, max 2 candidates. Both fail → halt + report; graft considered only then. NO production run on new sheet before Gordon picks it.
PROCESS: breach closed. 4:00 auto-reset + disk recovery working as designed — keep schedule.

## Candidate paths for Gordon (morning)
1. **Rodin via fal (fal-ai/hyper3d/rodin/v2.5, concat multi-view, ~$0.40/gen, existing FAL_KEY):** try a different generator that may produce welded geometry. Costs pennies. Fable said fires on fresh ruling now that T2b failed.
2. **Blender-side welding:** write a script that joins islands by proximity (scale shells contact body at points). Risky — could soften silhouette. Would need visual diff check.
3. **Reduce to smooth-coat prompt** (no armor scales): get a welded smooth body, then add scales as a texture/detail pass later (Step 4 quill layer already planned this way for hero quills).
4. **Override the coherence gate:** renders pass pose gate, gate is a new critical proved by v2_fav's real duplicate; but coherence could be over-strict if scales are intentionally separate shells. Needs Gordon's ruling on whether scale-shell fragmentation is acceptable.
5. **Rig a smooth proxy now** so bones / quill layer / spring bones progress while the body-perfection loop continues async.

**Fable note (added 07:15 PT):** Paths 1 and 3 are fastest + cheapest (~$0.40 fresh Rodin, or 30 more Meshy credits with smooth-coat language). Path 4's question is legitimate — worth knowing whether Meshy's per-scale-shell topology is actually wrong for rigging, or whether Blender's join-by-distance could fuse them pre-rig. That's a 30-minute experiment if wanted. Path 5 is the long-run correct answer but delays canon body approval. My read: try Rodin first (30 min, ~$0.40, fresh generator class) before spending more Meshy credits on a known-fragmenting model.

## Spend tracker (overnight)
- fal Kontext rear repose: ~$0.05
- Meshy T2b: 2 runs = 60 credits (7890 → 7830)
- Total session: ~$3.35 / $100 monthly ceiling

## STATE
Halted at T2b, awaiting morning ruling on the five paths above.
Board: https://gordongould.github.io/tumples-avatar-review/

Review entry: V23 Step 3b — Meshy re-run failed pose gate ×2, branch halted per stop rules.

## Halted?
YES. Awaiting morning.
