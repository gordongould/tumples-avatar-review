# V23 Sculpt Base — Iteration 8→10 Mechanical Fix List
**Scorer:** senior character sculptor, against canon-baseline (assetB sentry, assetC standing_01, assetA crest, upright_seated_side, haunches_threequarter)
**Target:** parameter-driven UV-sphere base, joined + voxel-remeshed. Every instruction below is directly executable as (location, scale) edits per named sphere.

Conventions: X+ = forward (head end), Z+ = up, Y+ = creature's left. Sizes given as scale factors relative to CURRENT sphere radius (e.g. "×1.4"), positions as offsets in body-length units (L = current chest-to-hip distance) unless noted.

---

## PRIORITY 1 — SILHOUETTE BREAKERS (do all of these together in iter8)

### 1. TAIL — biggest silhouette error. Rebuild all 6 spheres as a ground-running chain.
- **T1 (base):** ×1.5 bigger. Move DOWN so its bottom touches ground plane, move BACK into hip volume by 0.15L so it overlaps haunch with no gap. This sphere should read as continuous with the rump — currently the tail starts behind and above the body like an afterthought.
- **T2:** ×1.35 bigger. Move DOWN to ground contact, keep slight X− (rearward). Eliminate the air gap to T1 (overlap ≥40% of radius).
- **T3:** ×1.2 bigger, keep on ground plane. Close gap to T2.
- **T4:** ×1.1, on ground plane.
- **T5:** current size OK, on ground plane, then begin tip-up — raise Z by ~0.5× its own radius relative to T4.
- **T6 (tip):** ×0.8 smaller. Move UP sharply — tip apex should be ~1.5× T1 diameter above ground (canon standing shows a clear upward flick at the very end; sentry sit shows the same curl).
- **Rule for whole chain: bottom of T1–T4 spheres all on the same ground plane as the feet.** Current tail floats. Canon tail drags.
- Total tail length should be ≈ 1.1× body length (chest front to hip rear). If chain ends short, stretch spacing between T3–T5 rearward, do NOT add segments.

### 2. CREST — currently two pom-pom spheres floating above the skull. Rebuild as a swept-back mass.
- **C1 (crown):** ×1.6 bigger. Move DOWN and BACK — center it so it overlaps the top-rear quadrant of the head sphere by ~50%, not perched above it. Flatten it slightly on Z (scale Z ×0.7) and elongate on X (scale X ×1.4) so it reads as a swept plate, not a ball.
- **C2 (mid-sweep):** ×1.7 bigger. Move BACK (X−) by 0.5 head-diameters and DOWN so it sits at nape height, bridging head and neck-sphere-1. Elongate X ×1.6, flatten Z ×0.7. Its rear tip should overhang the neck's dorsal line.
- **C3 (nape/ruff — currently missing or fused):** ADD a third crest sphere behind C2, resting on the dorsal surface of neck-sphere-1, ×1.3 the current C2 size, elongated X ×1.8, flattened Z ×0.6. This creates the "crest flows into mane" read of assetA.
- **Net effect:** crest silhouette goes from "pompoms on a stick" to a single comma-shaped mass crown→nape→upper neck, matching assetA_crest_canon.

### 3. HEAD + BEAK — head is ~60% of canon size and the beak is a pimple.
- **Head sphere:** ×1.5 bigger. Move FORWARD (X+) slightly so it overhangs the neck front line — canon head projects ahead of the neck, it does not sit centered on the neck column.
- **Beak sphere:** ×1.8 bigger. ELONGATE X ×2.0, FLATTEN Z ×0.65 — canon has a long, low, strong raptor snout, not a nub. Move it DOWN slightly (Z− 0.2× head radius) so the beak line exits the lower half of the skull (assetB shows beak attaches low, with brow ridge above).
- **ADD new sphere "BeakTip":** small (0.35× head radius), placed at the front-lower corner of the beak sphere, pulled DOWN 0.3× head radius — this forms the hooked tip. Two spheres for beak (base + hook), not one.
- **Jowl/cheek (optional but cheap):** ADD a sphere 0.5× head radius tucked under the rear-lower skull, overlapping neck-1 — canon has feather-cheek mass widening the head-neck junction.

---

## PRIORITY 2 — PROPORTION ERRORS (iter9)

### 4. NECK — right length now, wrong shape. Convert pillar → S-curve with feather mass.
Current: 4 spheres stacked dead vertical, uniform thickness.
- **N1 (base, at chest):** ×1.35 bigger — this is the feathered throat mass and should bulge FORWARD (X+) of the chest line. Move X+ by 0.3× its diameter.
- **N2:** ×1.15 bigger. Move BACK (X−) 0.15× diameter — this starts the S (base forward, mid back).
- **N3:** keep size. Move BACK another 0.1× diameter.
- **N4 (top, under skull):** ×0.9 smaller. Move FORWARD (X+) 0.2× diameter — head approaches over the chest, completing the S.
- **Dorsal neck ruff:** ADD 2 spheres along the BACK of the neck (call them NR1 behind N2, NR2 behind N3), each 0.6× the local neck sphere, elongated X ×1.5, flattened on the neck-facing side. These are the navy dorsal feather mass that canon shows as a continuous dark ridge from crest to shoulders. Cheap, huge identity win.

### 5. LEGS — currently uniform pillars; canon is thick-upper / bird-thin-lower / broad-foot. All four legs same recipe:
- **F_up / B_up (upper/thigh):** ×1.5 bigger, move UP so upper half is buried inside body volume (only the lower half exits the silhouette). Rear B_up specifically: ×1.7 — canon haunch is a massive rounded bulge at the rear (see haunches_threequarter), the single biggest leg mass in the sculpt.
- **F_lo / B_lo (lower):** ×0.65 THINNER (scale X and Y down, keep Z length). ELONGATE Z ×1.3 — canon lower legs are long thin sticks, digitigrade. This is the "bird-thin lower segments" note from iter7 scoring.
- **F_ft / B_ft (foot):** ×1.4 bigger, FLATTEN Z ×0.5, ELONGATE X ×1.6 — broad flat 3-toed pad, front edge forward of the leg axis. Feet currently dainty; canon feet are wide planted paddles.
- **Stance width (from front view):** move all four leg attachment points OUT on Y by 0.15L — front view shows legs pinched too close under the body; canon stands with feet under the shoulder/hip corners.

### 6. BODY — small tweaks only.
- **Chest sphere:** ×1.15 bigger, drop Z slightly (0.1 diameter DOWN), push X+ 0.05L — canon has a deep keel chest that the neck rises out of, and the chest is the deepest point of the torso.
- **Hip sphere:** ×0.9 smaller on X (shorter front-to-back) but keep Z height — canon hips are tall but tighter than the current blob, with the haunch (B_up, grown in step 5) carrying the rear volume instead.

---

## PRIORITY 3 — POLISH (iter10)

7. **Voxel remesh pass:** after 8+9 changes, remesh and check for pinch artifacts at (a) tail-base/hip junction, (b) crest/neck junction, (c) the new dorsal ruff spheres. These are the three new overlap-heavy zones.
8. **Ground-contact audit:** in side view, confirm contact points: 4 feet + tail T1–T4 all on the same plane. Canon creature reads heavy and grounded; any floating sphere kills the read.
9. **Silhouette check against assetC_stills/standing_01:** overlay at same body length. The three profile lines that must match: (a) crest comma crown→nape, (b) neck S front-line, (c) tail ground-line + tip flick. If those three match, the sculpt passes.

---

## DELETE / ADD summary
- **DELETE:** none — every current sphere has a job after rescale.
- **ADD (4 new spheres):** BeakTip (hook), C3 or "Nape" crest sphere, NR1 + NR2 (dorsal neck ruff). Optional 5th: jowl/cheek.
- Sphere count goes ~30 → ~34. Still trivially remeshable.

## One-paragraph version for the parameter file
Tail: thicken base ×1.5, drop entire chain to ground plane, close inter-sphere gaps, tip flicks up at T5–T6. Crest: ×1.6–1.7 bigger all three, swept back and down to overlap nape, elongate X flatten Z, add nape sphere. Head: ×1.5, pushed forward; beak ×1.8 elongated flat + new hook-tip sphere below. Neck: keep 4-stack but fatten base ×1.35, shift mid spheres back, top forward (S-curve), add 2 dorsal ruff spheres. Legs: uppers ×1.5 buried into body (rear ×1.7), lowers ×0.65 thin ×1.3 tall, feet ×1.4 flat wide pads, stance wider on Y. Body: chest +15% deeper, hips −10% front-to-back.
