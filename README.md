# Tactile MPF Interactive Viewers

Interactive 3D HTML viewers for the **Manifold Particle Filter (MPF)** results on the external 768-grasp Shadow Hand benchmark.

Supplementary material for the SDU thesis on single-shot in-hand pose estimation via MPF + contrastive learning.

## Viewers

| File | Configuration |
|------|---------------|
| [`argmax.html`](argmax.html) | Argmax cluster representative (Approach 1, baseline) |
| [`posterior_mean.html`](posterior_mean.html) | Posterior-mean cluster representative (Approach 2, MUPF-style) |

Both viewers cover the **same 768-grasp external test set** so individual probes (`graspqp_<N>`) can be compared side by side across the two ablation variants.

## Live site

Once GitHub Pages is enabled (`Settings → Pages → Source: main → /(root)`):

- `https://<username>.github.io/tactile_html/`
- `https://<username>.github.io/tactile_html/argmax.html`
- `https://<username>.github.io/tactile_html/posterior_mean.html`

## What each viewer shows

For every probe:
- Predicted top-1 object pose (rank-1 mode)
- Ground-truth pose (frozen object pose during MuJoCo replay)
- Top-K = 10 posterior modes with their selection scores
- Active tactile sites (taxels that fired) and inactive ones
- Per-mode cost breakdown (active surface + inactive evidence + hand penetration)

## Headline numbers

| Metric | Argmax | Posterior mean |
|---|---|---|
| Top-1 tilt ≤ 10° | 12.7 % | 11.3 % |
| Top-1 tilt ≤ 20° | 31.4 % | 29.9 % |
| Best-K tilt ≤ 10° | 64.2 % | 63.0 % |
| Best-K tilt ≤ 20° | 88.5 % | 88.2 % |

The two strategies produce essentially identical aggregate results on the full benchmark — the negative-at-scale result documented in the thesis.
