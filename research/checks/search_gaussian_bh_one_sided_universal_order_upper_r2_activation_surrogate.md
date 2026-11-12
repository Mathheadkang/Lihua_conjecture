---
type: search_round
title: 'Round 2: surrogate divergence versus actual BH activation'
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_03cdfe6cf120
candidates: []
statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
performed_by: unknown
created_at: '2026-11-10T20:43:09.602Z'
extension_version: 0.0.4
---

## Obstructions

- The tested AH-main hugging surrogate loses the actual BH activation conditions. Its reported divergence already occurs for one centered Gaussian true null, whereas the actual ordinary BH FDR in that model is exactly q: with N=1 and a uniform null p-value, rejection is the event p <= q. Thus divergence of this relaxed auxiliary integral cannot establish a counterexample to the main bound. A proof route using this surrogate must retain the actual activation constraints or justify a different finite bound; no such bridge was verified in this round.
- The earlier harmonic obstruction remains applicable: FDR <= q H_N <= q(1+log N). Consequently a sequence with bounded log N / sqrt(log(1/q)) cannot have an unbounded FDR / [q sqrt(log(1/q))] ratio. This is inherited from the supplied board, not a new round-2 result; its sequence-specific growth constant gives no universal bound across arbitrary dimension growth.

## Limitations

The round reported zero candidates. No admissible sequence with a verified unbounded normalized actual BH FDR was supplied. A growing-depth Gaussian hierarchy remains an unchecked construction direction because its actual BH FDR has no verified asymptotic lower bound in the available record; increasing depth alone is not such a bound.

The context pack supplies the latest search report and the reference to idea_03cdfe6cf120, but no surrogate formula, candidate body, numerical parameter list, or hierarchy calculation. This summary therefore records the reported obstruction without claiming a fresh verification or new coverage of those families. Arbitrary rapidly growing dimensions, general covariances including singular ones, and q-dependent means remain unrestricted by this round's search. No proof, confirmed counterexample, or target-status change follows from the absence of candidates.
