---
type: search_round
title: >-
  Round 5: capped one-factor spikes, insertion weights, and fixed-dimensional
  tests
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 5
directions:
  - idea_54d9dcf9a649
  - idea_7d255a49227b
  - idea_8546c1f042b9
candidates: []
statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
performed_by: unknown
created_at: '2026-11-10T20:50:45.162Z'
extension_version: 0.0.4
---

## Obstructions

- `idea_54d9dcf9a649` (weak common-factor conditional-FDR spikes and a deterministic alternative ladder): the supplied round-5 report states that retaining the truncation gives the tested one-factor spike family the required order. Divergence of an intermediate conditional moment after discarding that truncation therefore does not establish divergence of actual BH FDR divided by `q sqrt(log(1/q))`. Disposition: no candidate; the proposed moment obstruction does not refute the target in the reported family. This is a family-specific conclusion, not a bound for unrestricted factor structures or covariance.
- `idea_7d255a49227b` (single-null harmonic insertion family): the supplied report places the actual FDR in order q. Failure of a null-proportion-linear auxiliary budget, or divergence of a relaxed insertion quantity, therefore does not supply the target's NOT check. Disposition: no candidate; retain the actual BH contribution and its weights before drawing any asymptotic conclusion. No general alternative-insertion theorem is inferred.
- `idea_8546c1f042b9` (signed covariance comparison and a finite frustrated Gaussian BH test): the reported fixed three-test family is excluded as an asymptotic refutation by the harmonic bound `FDR <= q H_3`. More generally, every fixed dimension has bounded `FDR/q` under the inherited harmonic inequality. A finite comparison failure or nonmonotone path therefore cannot yield an unbounded `FDR/[q sqrt(log(1/q))]` ratio as q tends to zero. Disposition: no candidate; no conclusion about growing-dimensional signed covariance families follows.
- Across the three assigned ideas, the supplied search produced zero candidates. A divergent auxiliary moment, insertion budget, or finite comparison defect is insufficient unless an admissible sequence has a verified unbounded normalized ratio of actual BH FDR. The round does not provide such a sequence.

## Limitations

This record uses the current search-summary context pack and its supplied round-5 report. Because the pack omitted the spike family's model definition, native `show idea_54d9dcf9a649` was additionally used, with explicit authorization, to recover only that assigned family's hypotheses. The single-null insertion and signed three-test dispositions above remain supplied search conclusions, not fresh independent verification of their detailed calculations.

For the supplied spike family, the centered true nulls are conditionally independent given the standard Gaussian common factor G, while the alternatives are deterministic given G. Their conditional p-value density is bounded by `exp(G^2/2)/sigma`. Ordinary BH's leave-one-out rank identity therefore gives `FDR <= E min{1,b exp(G^2/2)}`, with `b=q/(2 sigma)` because the null proportion is one half. For `0<b<1` and `t=sqrt(2 log(1/b))`, direct Gaussian integration and Mills' inequality give the bound `sqrt(2/pi) b(t+1/t)`. Here `log N>=2` implies `sigma>=1/sqrt(2)` and `q=(log N)^(-2)<=1/4`, yielding the target order within this family. This short calculation was independently derived and recorded natively as the draft approach `idea_cc6a8321d5c3`; it does not independently verify the source's conditional-moment spike assertions or extend the family.

The round does not control arbitrary q-dependent dimension growth, means, true-null proportions, signed or singular covariance, factor dimension, or direction complexity. The inherited harmonic bound excludes only sequences with bounded `log N / sqrt(log(1/q))`, with a sequence-dependent growth constant; it does not furnish the universal constant required by the target. No general proof, asymptotic refutation, or change to the target's draft status is established.
