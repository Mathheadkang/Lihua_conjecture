---
type: falsification_check
title: 'Falsification check: gaussian_bh_one_sided_universal_order_upper'
target_asset: gaussian_bh_one_sided_universal_order_upper
outcome: no_counterexample_found
statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
performed_by: unknown
created_at: '2026-11-10T20:50:45.269Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, idea_03cdfe6cf120: no plausible candidate.
- Round 3, idea_0e63e86f1cc7: no plausible candidate.
- Round 3, idea_19c44519bec3: no plausible candidate.
- Round 3, idea_3bc65c83bcb2: no plausible candidate.
- Round 4, idea_47b8626c3e53: no plausible candidate.
- Round 4, idea_47c7d6819637: no plausible candidate.
- Round 4, idea_52a020fe86cd: no plausible candidate.
- Round 5, idea_54d9dcf9a649: no plausible candidate.
- Round 5, idea_7d255a49227b: no plausible candidate.
- Round 5, idea_8546c1f042b9: no plausible candidate.
- Obstruction: Every admissible finite Gaussian model has super-uniform true-null p-values, including singular covariance and arbitrary true-null means at most zero. The arbitrary-dependence BH harmonic bound therefore gives
- Obstruction: $$
- Obstruction: \operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
- Obstruction: \le q\frac{|I_0^{(1)}(\theta)|}{N}H_N
- Obstruction: \le qH_N\le q(1+\log N),
- Obstruction: \qquad H_N=\sum_{k=1}^N\frac1k.
- Obstruction: $$
- Obstruction: Consequently, for any sequence of admissible models with $q_m\downarrow0$, writing $L_m=\log(1/q_m)$, if $\log N_m/\sqrt{L_m}\le B$ eventually for one finite sequence-specific $B$, then
- Obstruction: $$
- Obstruction: \limsup_{m\to\infty}
- Obstruction: \frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q_m;N_m,\theta_m,\Sigma_m)}
- Obstruction: {q_m\sqrt{L_m}}\le B.
- Obstruction: $$
- Obstruction: Thus fixed dimension, and more generally any one sequence with bounded $\log N_m/\sqrt{L_m}$, cannot yield an unbounded normalized ratio. This conclusion permits arbitrary means, null proportions, singular covariance, rank, and factor structure within each sequence. Its constant depends on the sequence's growth bound $B$: it supplies no single universal constant across arbitrarily varying growth coefficients. Any proposed sequence whose normalized ratio tends to infinity must have $\log N_m/\sqrt{L_m}\to\infty$; this is a necessary condition, not a sufficient construction or a proof of the target.
- Obstruction: The tested AH-main hugging surrogate loses the actual BH activation conditions. Its reported divergence already occurs for one centered Gaussian true null, whereas the actual ordinary BH FDR in that model is exactly q: with N=1 and a uniform null p-value, rejection is the event p <= q. Thus divergence of this relaxed auxiliary integral cannot establish a counterexample to the main bound. A proof route using this surrogate must retain the actual activation constraints or justify a different finite bound; no such bridge was verified in this round.
- Obstruction: The earlier harmonic obstruction remains applicable: FDR <= q H_N <= q(1+log N). Consequently a sequence with bounded log N / sqrt(log(1/q)) cannot have an unbounded FDR / [q sqrt(log(1/q))] ratio. This is inherited from the supplied board, not a new round-2 result; its sequence-specific growth constant gives no universal bound across arbitrary dimension growth.
- Obstruction: The finite equicorrelated null family assigned through `idea_0e63e86f1cc7` obstructs an absolute square-root cluster contraction modulus, according to the supplied search report and idea disposition. Failure of that auxiliary modulus does not supply a counterexample to the actual BH FDR bound. No candidate was written for this idea.
- Obstruction: The two-test correlated strong-alternative family assigned through `idea_19c44519bec3` remains an unfinished trace-versus-coherence-deficit stress test. Its disposition concerns a two-test auxiliary estimate; it supplies no verified sequence with unbounded actual FDR divided by `q sqrt(log(1/q))`. No candidate was written for this idea.
- Obstruction: Independent null dust assigned through `idea_3bc65c83bcb2` obstructs discarding rank-specific Mills weights in zero-mean boundary payments. Growth of the raw, unweighted surface flux is not growth of the corresponding actual BH payment: the reported Mills-weighted term remains bounded. No candidate was written for this idea.
- Obstruction: The latest search report states that these three ideas produce auxiliary obstructions while the actual BH FDR in the corresponding tested models remains of order q. An auxiliary divergence therefore does not pass the target's NOT check. A proof route using these estimates must retain the actual activation constraints and BH weights, or establish a separately justified replacement bound. This unresolved proof-step obligation was recorded natively as the draft approach `idea_44c8e93114bf`.
- Obstruction: The tested two-test family associated with `idea_47b8626c3e53` defeats the proposed contraction monotonicity, but its actual BH FDR is strictly below q. Loss of this monotonicity therefore fails to refute the target: a failure of an intermediate comparison is not an unbounded actual-FDR ratio. This statement concerns the reported two-test model and its tested parameter range only.
- Obstruction: The localized moving-q fold family associated with `idea_47c7d6819637` has uncontrolled positive auxiliary flux while its actual BH FDR is bounded by q/2 through the PRDS structure of that specific model. Thus positive-flux growth alone cannot supply the target's NOT check. The PRDS argument applies to the tested fold model; it makes no claim that arbitrary signed Gaussian covariance satisfies PRDS.
- Obstruction: The mean-ordered alternative-insertion family associated with `idea_52a020fe86cd` has a divergent auxiliary insertion quantity, but the exact coefficient retained in its actual FDR calculation is bounded by 1/2. The unweighted or otherwise relaxed insertion divergence therefore does not imply divergence of actual BH FDR. This coefficient bound is restricted to the reported insertion construction and is not a general alternative-insertion theorem.
- Obstruction: Across these three assigned directions, any proof step replacing the actual BH contribution by a contraction modulus, positive flux, or relaxed insertion increment must justify the replacement with the activation conditions and exact BH weights intact. The reported auxiliary failures establish an obstruction to those proposed estimates, while the tested actual FDR remains of order q. No candidate was produced this round.
- Obstruction: `idea_54d9dcf9a649` (weak common-factor conditional-FDR spikes and a deterministic alternative ladder): the supplied round-5 report states that retaining the truncation gives the tested one-factor spike family the required order. Divergence of an intermediate conditional moment after discarding that truncation therefore does not establish divergence of actual BH FDR divided by `q sqrt(log(1/q))`. Disposition: no candidate; the proposed moment obstruction does not refute the target in the reported family. This is a family-specific conclusion, not a bound for unrestricted factor structures or covariance.
- Obstruction: `idea_7d255a49227b` (single-null harmonic insertion family): the supplied report places the actual FDR in order q. Failure of a null-proportion-linear auxiliary budget, or divergence of a relaxed insertion quantity, therefore does not supply the target's NOT check. Disposition: no candidate; retain the actual BH contribution and its weights before drawing any asymptotic conclusion. No general alternative-insertion theorem is inferred.
- Obstruction: `idea_8546c1f042b9` (signed covariance comparison and a finite frustrated Gaussian BH test): the reported fixed three-test family is excluded as an asymptotic refutation by the harmonic bound `FDR <= q H_3`. More generally, every fixed dimension has bounded `FDR/q` under the inherited harmonic inequality. A finite comparison failure or nonmonotone path therefore cannot yield an unbounded `FDR/[q sqrt(log(1/q))]` ratio as q tends to zero. Disposition: no candidate; no conclusion about growing-dimensional signed covariance families follows.
- Obstruction: Across the three assigned ideas, the supplied search produced zero candidates. A divergent auxiliary moment, insertion budget, or finite comparison defect is insufficient unless an admissible sequence has a verified unbounded normalized ratio of actual BH FDR. The round does not provide such a sequence.

## Limitations

This record uses the current search-summary context pack and its supplied round-5 report. Because the pack omitted the spike family's model definition, native `show idea_54d9dcf9a649` was additionally used, with explicit authorization, to recover only that assigned family's hypotheses. The single-null insertion and signed three-test dispositions above remain supplied search conclusions, not fresh independent verification of their detailed calculations.

For the supplied spike family, the centered true nulls are conditionally independent given the standard Gaussian common factor G, while the alternatives are deterministic given G. Their conditional p-value density is bounded by `exp(G^2/2)/sigma`. Ordinary BH's leave-one-out rank identity therefore gives `FDR <= E min{1,b exp(G^2/2)}`, with `b=q/(2 sigma)` because the null proportion is one half. For `0<b<1` and `t=sqrt(2 log(1/b))`, direct Gaussian integration and Mills' inequality give the bound `sqrt(2/pi) b(t+1/t)`. Here `log N>=2` implies `sigma>=1/sqrt(2)` and `q=(log N)^(-2)<=1/4`, yielding the target order within this family. This short calculation was independently derived and recorded natively as the draft approach `idea_cc6a8321d5c3`; it does not independently verify the source's conditional-moment spike assertions or extend the family.

The round does not control arbitrary q-dependent dimension growth, means, true-null proportions, signed or singular covariance, factor dimension, or direction complexity. The inherited harmonic bound excludes only sequences with bounded `log N / sqrt(log(1/q))`, with a sequence-dependent growth constant; it does not furnish the universal constant required by the target. No general proof, asymptotic refutation, or change to the target's draft status is established.

Object search: 0 candidate(s) in 5 round(s).
