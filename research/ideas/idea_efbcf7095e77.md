---
type: idea
title: >-
  Finite inherited-null importance compression still loses rare-alternative
  Gaussian BH amplification
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - weighted-stratification
  - actual-rank-sandwich
  - conditional-source-transfer
---

## Scope and status
This is a new concrete importance-weighted compression diagnostic for [the unrestricted one-sided target](../assets/gaussian_bh_one_sided_universal_order_upper.md), not a proof plan and not a counterexample to that target. The standalone finite-carrier limit below is proved here. Its application to the Lei lower family is conditional on the source's compact population brackets and finite transfer, whose exact construction has not been independently reconstructed in this record. No status or approval is asserted. Unlike [uniform coordinate subsampling](idea_a748e25f6dcf.md), the construction tested here retains EVERY alternative coordinate, its exact weight, and its joint Gaussian loading, and allows arbitrary deterministic model-dependent weights on finitely many inherited null carriers.

## Concrete weighted rule
A finite collection of atoms has p-values p_i in (0,1), nonnegative weights w_i summing to one, and original null labels. Zero weights can be omitted. For its CDF C(t)=sum_i w_i 1{p_i<=t}, put
$$
\rho_q(C)=\sup(\{0\}\cup\{a\in[0,1]:C(qa)\ge a\}).
$$
For finite atoms this is exactly weighted largest step-up: after sorting p-values with multiplicities, select the largest cumulative weight a_k for which p_(k)<=q a_k. Tied p-values are grouped; the selected mass is rho and C(q rho)=rho if rho>0. Indeed, if C(q rho)>rho, then a'=C(q rho) is a larger qualifying mass since C(q a')>=a'. Weighted FDP is C_0(q rho)/(rho vee 0), with value zero at rho=0. In equal-weight models w_i=1/N this is exactly the original ordinary BH rule and FDP.

## Finite inherited-null carrier limit
Fix q in (0,1) and a finite m. Let r_n decrease to zero, Z,epsilon_1,...,epsilon_m be independent standard normals, and
$$
P_{j,n}=\overline\Phi(r_nZ+\sqrt{1-r_n^2}\epsilon_j),\qquad 1\le j\le m.
$$
The null carriers have arbitrary deterministic weights w_{j,n}>=0 with sum_j w_{j,n}=1-a_n, where a_n decreases to zero (monotonicity of a_n is unnecessary). Retain any finite number of original alternative atoms of total weight a_n. Their p-values may have arbitrary dependence on all displayed Gaussian variables; no independence, product formula, density, or limit is assumed for these alternatives. Then the ACTUAL weighted largest-crossing FDR converges to q.

Repeated inherited null indices are exact copies, so merge their weights before applying the claim; there are at most m distinct carriers. The claim permits q-dependent m and arbitrary model-dependent weights: q is fixed first and m(q) is finite. It does not cover weights depending on the observed Gaussian scores, synthetic changed-covariance carriers, or an unbounded number of carriers.

### Exact full-rank sandwich
Take any subsequence along which w_{j,n}->w_j^*. Compactness supplies such a subsequence from every sequence. Let J={j:w_j^*>0}, let
$$
\eta_n=a_n+\sum_{j\notin J}w_{j,n}\longrightarrow0,
\qquad D_n(t)=\sum_{j\in J}w_{j,n}\mathbf1_{\{P_{j,n}\le t\}}.
$$
For the full, unmodified weighted CDF C_n, pathwise for every t in [0,q],
$$
D_n(t)\le C_n(t)\le D_n(t)+\eta_n.
$$
Thus its actual largest rank satisfies
$$
\rho_q(D_n)\le\rho_q(C_n)\le\rho_q(D_n+\eta_n). \tag{RS}
$$
Here the lower carrier corresponds to putting every nuisance atom at p=1 and the upper carrier to putting every nuisance atom at p=0. These are bounds, not an assertion that the actual alternative gates are independent or absent. In particular ALL alternative means and joint loadings remain in C_n. The largest-crossing property proves (RS): every qualifying mass for a smaller CDF qualifies for a larger one. The upper and lower CDFs need only be evaluated on [0,q].

Let P_j^*=barPhi(epsilon_j) and D^*(t)=sum_{j in J}w_j^*1{P_j^*<=t}; the limiting weights sum to one. Almost surely no P_j^* equals q sum_{k in S}w_k^*, for any j in J and any subset S of J. There are finitely many comparisons, every P_j^* is continuous, and independence between a threshold and P_j^* is unnecessary because the weights and subsets are deterministic. Denote rho*=rho_q(D^*).

Here is a direct proof that BOTH ranks in (RS), and hence the actual full rank, converge to rho*, including rho*=0. In either bounding rule, at its selected mass b_n, the selected positive carriers form some S_n subset J and
$$
b_n=\sum_{j\in S_n}w_{j,n}+e_n,\qquad 0\le e_n\le\eta_n.
$$
For the lower rule e_n=0; for the upper rule e_n=eta_n when its mass is positive, with the same formula allowing zero. On any subsequence with S_n=S fixed, b_n converges to b*=sum_{j in S}w_j^*. The nonzero margin in all finite comparisons makes S={j:P_j^*<=q b*}. Thus b* is a qualifying limiting crossing, so b*<=rho*. Conversely, if rho*>0 its selected set S* has P_j^*<q rho* for every j in S*. For all sufficiently large n these same indices satisfy P_{j,n}<=q sum_{k in S*}w_{k,n}; consequently the lower bounding rule, and hence either rule, has rank at least sum_{k in S*}w_{k,n}->rho*. If rho*=0 the upper argument already forces every rank limit to zero. Finite-set compactness completes the proof. The strict finite margin then also makes the selected set of positive carriers in the ACTUAL rule equal S* eventually. When rho*=0, no positive carrier is eventually rejected, since its weight is bounded away from zero while the full rank tends to zero.

### Explicit vanishing-weight payment
For any null atom of deterministic weight w>0 in ANY weighted rule, rejection implies P<=q rho<=q and rho>=w and rho>=P/q. Hence its individual FDP contribution obeys, pathwise,
$$
\frac{w\mathbf1_{\{P\le q\rho\}}}{\rho}
\le\mathbf1_{\{P\le q\}}\min\{1,qw/P\}.
$$
Every P_{j,n} above is exactly uniform marginally, despite dependence with all alternatives and all other nulls. Integrating the displayed scalar envelope gives
$$
\mathbb E\frac{w_{j,n}\mathbf1_{\{P_{j,n}\le q\rho_n\}}}{\rho_n}
\le q w_{j,n}\{1+\log(1/w_{j,n})\}. \tag{WP}
$$
This is a proved carrier-weight entropy payment, not a guessed inequality. The zero-weight convention is w log(1/w)=0. Since m is fixed, the sum of (WP) over j not in J tends to zero. Their joint Gaussian gate probabilities have never been replaced by products.

### Limit and exact independent weighted baseline
The positive-carrier FDP contributions converge almost surely to the limiting independent weighted all-null contributions by (RS) and selection stability. Each lies in [0,1], so bounded convergence applies. The omitted zero-limit carrier contributions vanish by (WP). It remains to compute the limiting independent weighted all-null FDR, rather than to assume ordinary equal-weight BH applies.

For independent uniform P_j^* and deterministic positive weights summing to one, force coordinate j to p=0 and call its actual weighted largest rank rho_j. Then rho_j>=w_j^* and depends only on the other p-values. Largest-step-up monotonicity gives the exact leave-one-out identity
$$
\mathbf1_{\{j\text{ rejected}\}}/\rho
=\mathbf1_{\{P_j^*\le q\rho_j\}}/\rho_j.
$$
For completeness: rho<=rho_j under the forced-zero replacement. If P_j^*<=q rho_j, restoring P_j^* leaves the forced-zero rejection set qualifying, so rho=rho_j. If j is originally rejected, replacing its p-value by zero cannot create a larger crossing: at any proposed larger rank j was already below that larger threshold, so its replacement does not change the count. Thus rho=rho_j also in this direction. Conditioning on all other p-values gives expected weighted contribution q w_j^*. Summing gives FDR=q. Every convergent-weight subsequence therefore has limit q; compactness proves the full-sequence limit. This also proves uniform convergence over all deterministic choices of weights and, by conditioning, externally randomized weights independent of the observed Gaussian scores.

## Conditional application to the actual rare-alternative lower family
The source in [the existing rare-alternative diagnostic](idea_a748e25f6dcf.md) has null loading r, primary-alternative mass r and loading -1, secondary-alternative mass tau_r and loading -1, and exact secondary survival
$$
W_r(a)=\{1-qe^{a^2/2}\}\overline\Phi(a/r)/q,
\qquad\tau_r=W_r(b_r)\sim(1-q)r^2/q.
$$
The total alternative mass is r+tau_r, not tau_r alone. The distribution over secondary means is retained exactly; it is not an atom of mass tau_r at a fixed mean. Retaining every alternative in a deterministic finite realization preserves their original common -Z gate and all null-to-alternative covariances -r.

Native source pages 57--58 were read. They claim that for each fixed q and error epsilon, every sufficiently small r admits all sufficiently large N with average finite FDR at least ell_<= (q)-epsilon, using compact brackets and a uniform DKW transfer. This record has NOT independently reconstructed the preceding population brackets (source Lemmas 3.11--3.13). Therefore the following transfer is explicitly CONDITIONAL on that source result, rather than treating the old draft diagnostic as an approved lemma.

Assuming that average lower transfer, choose r_n->0 and sufficiently large N_n so average original FDR>=ell_<= (q)-epsilon_n with epsilon_n->0. For iid source type layouts Omega, the expected alternative fraction is a_r=r+tau_r. Markov gives P{empirical alternative fraction>sqrt(a_r)}<=sqrt(a_r). Since FDP<=1, some deterministic layout having empirical alternative fraction<=sqrt(a_r) also has original FDR>=ell_<= (q)-epsilon_n-sqrt(a_r). Thus there are deterministic layouts with alternative mass tending to zero and original FDR approaching the source lower envelope from below. One can use the original singular model directly; no positive-definite perturbation is needed for this diagnostic.

For ANY fixed finite m(q), replace the many original nulls by at most m(q) inherited null carriers with arbitrary deterministic weights summing to their original total mass, while retaining every alternative with its exact original weight, mean and joint loading. Along the preceding family the proved limit gives compressed FDR->q, whereas the conditional original lower transfer gives original FDR>=ell_<= (q)-o(1). Consequently a proposed universal bridge
$$
\operatorname{FDR}_{\rm original}(q)
\le C_0\operatorname{FDR}_{\rm compressed}(cq)+C_1q
$$
with finite fixed C_0,C_1,c>0 and finite m(q), cq<1, would fail: choose q first so ell_<= (q)/q>C_0 c+C_1, then let r decrease and choose finite N as above. The same proof at level cq makes compressed FDR tend to cq. This conclusion remains conditional on the explicitly named source lower-family transfer; the standalone weighted finite-carrier limit and entropy payment do not.

## What this construction failure does and does not show
Importance reweighting of finitely many INHERITED null carriers does not cure this rare-alternative compression loss, even when the rare alternative shaping measure and its full correlated loading are retained. The entropy payment (WP) controls vanishing carrier weights but leaves every positive-weight finite null carrier in an independent-null limit. A different construction may use synthetic changed-covariance Gaussian carriers or an unbounded number of inherited carriers with a new low-entropy budget; neither is ruled out here. An all-null geometric covering obstruction alone would not prove this stronger claim; the actual full-rank sandwich and weighted payment above are essential.

This route differs from the inspected failed [compatible rank-chain transport plan](../plans/plan_ee2f7b97740a.md) and [FDP entropy/Mills plan](../plans/plan_one_sided_order_fdp_entropy_mills_coherence_20261107.md): it constructs and analyzes the actual weighted compressed BH rule rather than estimating their signed transport or trace gates. It supplies no missing main-theorem Gaussian allocation and no executable pending main plan. The target remains unrefuted; no protected statement, proof, dependency, earlier failed plan, approval, or loop state is edited.
