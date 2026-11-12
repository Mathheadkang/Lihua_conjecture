---
type: search_round
title: >-
  OU bridge round 5: exact replication, four null directions, and fixed-seed
  dilution
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:19:05.111Z'
extension_version: 0.0.4
---

## Obstructions

- **Uniform global replication preserves the full bridge ratio.** Replace every test of an arbitrary finite seed by exactly L identical copies, preserving its mean and loading vector. With the largest nonstrict BH convention, the actual rejection count is exactly R'=LR, including simultaneous ties: any feasible copied rank r in the kth block makes rank Lk feasible, and feasible block endpoints correspond exactly to feasible seed ranks. Therefore the full FDP agrees pointwise with the seed FDP on the same latent Gaussian space. The null fraction, F, full OU budget J(f), and bridge ratio are unchanged. This holds for arbitrary seed latent rank and mixed labels. Increasing multiplicity through uniform global replication cannot amplify a seed's ratio; nonuniform replication is not covered.

- **At most four distinct true-null loading directions have a uniform positive budget-to-FDR bound.** Let w_1,...,w_K be the distinct true-null loading vectors, with 1<=K<=4, allowing arbitrary multiplicities, arbitrary nonpositive true-null means, and arbitrary alternative loadings and rank. Put M(x)=max_a w_a dot x, u_q=S^{-1}(q)>=1, and g(x)=-(u_q-M(x))_+. This g is 1-Lipschitz. If the full actual-BH FDP f(x)>0, some rejected true-null score is at least u_q, so its loading projection is at least u_q and fg=0. Consequently Cov(f,g)=F E[(u_q-M(G))_+]. The direct OU covariance identity and the Lipschitz bound give J(f)>=Cov(f,g). The union bound gives P(M<t)>=1-4S(t) for t>=S^{-1}(1/4), and hence

  $$
  J(f)\geq c_4F,\qquad
  c_4=\int_{S^{-1}(1/4)}^1(1-4S(t))\,dt>0.
  $$

  Also F<=P(f>0)<=Kq<=4q. Thus the complete bridge ratio is at most 4/c_4. This excludes an unbounded ratio within this restricted family, even with unbounded null multiplicities and arbitrary alternative rank. It extends the earlier null-count obstruction to a restriction on distinct true-null directions. The proof step is saved as draft approach idea_15bc4ed41a8d; it is not an approved analytic dependency or a proof of the unrestricted bridge.

- **Fixed-seed zero-mean null-label dilution does not amplify the limiting ratio.** Fix one finite seed whose true-null means are zero. After uniform global cloning, retain an alpha fraction of every original null block at mean zero and shift the remaining fraction 1-alpha to mean epsilon>0, using the actual mean-based null labels. Here alpha is a fixed admissible fraction in (0,1]. For almost every latent point, outside the finitely many seed threshold hyperplanes, all rejection decisions stabilize as epsilon decreases to zero. Therefore the full perturbed FDP converges to alpha f_0, F_epsilon converges to alpha F_0, and pi0_epsilon=alpha pi0_0. Direct Mehler differentiation in the fixed finite latent dimension gives J(f_epsilon) converging to alpha J(f_0): its differentiated kernel is dominated by a constant times exp(-t)/sqrt(1-exp(-2t)), which is integrable on (0,infinity). For F_0>0 and J(f_0)>0, the complete ratio therefore converges to alpha times the seed ratio. This fixed-seed perturbation supplies no unbounded amplification. It is not a uniform assertion over jointly varying seeds, ranks, clone counts, or epsilon scales.

## Limitations

No worker produced a new candidate in this round. The preceding calculations exclude only the stated families or limits; they neither refute nor establish the universal BH-specific bridge. The repeated low-rank hole argument was already covered by the round-2 obstruction and is not a new finding here.

Unbounded interacting true-null directions, heterogeneous replication, and near-constant full FDP with quantitatively certified positive excess and a complete signed OU budget remain unresolved. The fixed-seed dilution limit does not control a joint growing-N, growing-rank, and vanishing-epsilon construction. Uniform replication preserves any unknown seed ratio and therefore cannot itself settle whether seed ratios are universally bounded.

The generic analytic estimate, its source verification and interchanges, the general signed-mixture reduction, and the unrestricted BH-specific gate remain proof obligations. The claimed FDR consequence remains conditional. None of this round's restricted-family calculations is an approved result or a numerical certificate.
