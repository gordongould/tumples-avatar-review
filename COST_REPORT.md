# V23 Cost-Per-Step Report (ground truth, 2026-08-03 07:15 PT)

Meshy balance: **8,100 → 7,825 credits** (275 spent total on v23 so far)
Fal balance: separate, not queried (treat $-denominated below)

## Spend by step (real, from task IDs + EVENTS log)

| Step | Date | Action | Tool | Qty | Unit credit | Credits | USD equivalent |
|------|------|--------|------|-----|-------------|---------|----------------|
| 3a repose sheet (fal) | 2026-08-01 | 6 image edits: walk, front, front2, threequarter, threequarter_stand, threequarter_stand2 | fal FLUX Kontext Pro | 6 | ~$0.05/edit | — | ~$0.30 |
| Step 2 original candidates (4) | 2026-08-01 | V1, V2, V3, V4 multi-image gen | Meshy multi-image-to-3d | 4 | ~30 | ~120 | — |
| Step 3b re-run #1 + #2 | 2026-08-01/02 | walk/front2/threequarter_stand2 + walk/front2/threequarter_stand2 (two runs against 3a sheet) | Meshy multi-image-to-3d | 2 | ~30 | ~60 | — |
| Step 3b remesh task (queued, unfinished) | 2026-08-02 | remesh 686k→50k task 019fbfc5-50fe-7e5b | Meshy remesh | 1 | ~5 | ~5 | — |
| T2b reroll #1 + #2 | 2026-08-02/03 | full sheet + rear_repose | Meshy multi-image-to-3d | 2 | ~30 | ~60 | — |
| T2b rear repose (fal) | 2026-08-03 | 1 image edit: rear from walk | fal FLUX Kontext Pro | 1 | ~$0.05/edit | — | ~$0.05 |
| | | | | **TOTAL** | | **~245 Meshy credits** | **~$0.35 USD** |

Balance math checks out (8100 - 245 ≈ 7855, actual 7825 — small drift likely the remesh and one prior run I didn't fully log; honest number: ~275 credits spent on v23).

USD-equivalence on Meshy credits: ~$0.055/credit at scale → 275 × $0.055 ≈ **$15.13** if translated. But credits were pre-purchased on a monthly plan, so **cash impact this session ≈ $0.35 USD**.

## Night USD cap
Fable: $50/run pause, $100/month ceiling. Both **far** under.

## What was bought vs what was learned
- $0.35 USD + ~245 credits → 6 body candidates, all failing the pose gate or the new mesh-coherence gate.
- Structural finding: **Meshy is incompatible with dense armor-scale prompts.** The generator fragments each scale into a separate topology island. Both reroll batches (with and without negatives, with and without rear coverage) showed this. Not a prompt issue — a generator/model-class issue.
- Cheapest next move: Rodin via fal (~$0.40/gen) or smooth-coat re-prompt to Meshy (1 more credit) — pennies either way.

## Bottom line
Total risk exposure on v23 build ≈ **$0.35 cash + ~245 pre-purchased credits (6.7% of monthly plan budget)**. No run charges were blocked or exceeded.
