# UniRig prep notes (overnight no-spend queue, 2026-08-03)

## What it is
VAST-AI UniRig (SIGGRAPH 2025): one autoregressive transformer that rigs 3,103+ diverse skeleton types — bipeds, quadrupeds, birds, insects, arthropods, fictional. Trained on RigNet-XL. Handles tail chains and unusual bone structures natively.

Repo: https://github.com/VAST-AI-Research/UniRig
Paper: One Model to Rig Them All (arXiv 2504.12451)

## Why it matters for v23
Fable designated UniRig as the fallback when Blender Rigify's quadruped metarig fails. Given that both Meshy runs have fragmented topology and the tail is disconnected, a model that infers bone chains from geometry semantics (not template alignment) is the right tool. Especially because UniRig does NOT require the mesh's bones to be pre-named or template-matched — it reads the shape.

## Setup path (not installing overnight — needs GPU + conda env)
```
git clone https://github.com/VAST-AI-Research/UniRig ~/unirig
cd ~/unirig
conda create -n unirig python=3.11
conda activate unirig
pip install -r requirements.txt
# model weights via: python download.py
```

## Hardware check
- Host: Mac mini (Apple Silicon). UniRig officially targets PyTorch on Linux/CUDA. MPS support exists in PyTorch 2.x but not guaranteed for the point-cloud backbone (PointTransformer).
- Decision for morning ruling: either (a) try MPS on the mini, (b) rent an A100/H100 on RunPod/Lambda for ~$1/hr for a single inference (pennies for a one-off), or (c) use a Hugging Face hosted UniRig space if one exists.

## What it needs from us
- A clean GLB body (one of the failed candidates OR a Rodin regeneration OR a smooth-coat version).
- Mesh fused into a single connected component per bone-influencing region. The current per-scale-shell fragmentation (300+ islands) will wreck UniRig too — it expects a main body volume with appendage tips. Clean-up comes FIRST.
- Quad topology preferred. Current 500k+ tri meshes will want decimation to ~50k before rigging.

## Integration point in v23 pipeline
Replaces Step 3 Rigify if Rigify fails twice. Inputs: fused GLB. Outputs: skinned GLB with bones. Feed to Step 4 quill layer unchanged.

## Open question for Fable (morning)
Given that the actual failure mode isn't rigging — it's mesh fragmentation — should UniRig be attempted only AFTER we get a clean fused body, or is there value in running it on a fragmented body to see if its topology reasoning holds up?

## Cost
- Claude Sonnet 4.6 (this overnight writing task): ~0.01
- UniRig install/run: future spend, ~$0-0.50 if RunPod one-shot
- No overnight spend beyond notes.
