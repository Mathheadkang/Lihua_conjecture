---
type: idea
title: Independent audit of phase2 pointwise q-flux obstruction
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - phase2
  - independent-audit
  - pointwise-q-flux
  - static-mask
  - auxiliary-obstruction
---

## Verdict and scope

Independent Quick audit of the written candidate idea_47c7d6819637 against the frozen original gate (19) of idea_c23fac250465. I did not produce the candidate and did not read its producer's plan, unpublished reasoning, sibling project, or other reviewers' output. No actual mathematical gap was located in the localized static-mask fold argument. This is a quick-screened auxiliary-gate obstruction, conditional on the approved private-noise finite-identification prerequisite below; it is not native proof approval or a Strict three-role audit. No existing node or status is changed.

## Visible materials and trust boundary

Read native show of exactly the candidate and frozen original route, followed by the exact approved prerequisite gaussian_bh_private_noise_cutoff_signed_transport_variation, particularly Proof section 2 (Microscopic ranks and finite identification). The latter was necessary because fixed-positive-sigma L1 convergence, rather than convergence of unmasked expectations, is load-bearing. Its stated scalar microscopic bound is trusted as an approved prerequisite; its deterministic three-type specialization and masked extension are checked here. No new external source or computation was used.

## First potential gap examined: masked finite-to-population fidelity

The approved proof initially samples iid parameter types, whereas the candidate uses exactly N/2,N/4,N/4 replicas. This is not a blocking gap: for each fixed sigma>0, apply the same conditional strong law separately to the three independent private-noise groups; their empirical total and true tails converge uniformly to the displayed H_sigma,V_sigma. All groups have the same positive common loading sigma, so the approved rank-transfer sandwich in Z applies verbatim. The actual largest empirical BH rank equals the continuous-rank supremum because a qualifying r with k/N observations below qr also makes k/N qualify. The population rank is monotone in Z, whose continuous law avoids its countably many discontinuities. At positive limiting ranks the full FDP converges; at microscopic ranks the approved B_{q,sigma}(t) estimate applies since every true coordinate, conditionally on Z, has residual variance exactly 1-sigma^2 and mean zero. It tends to zero as t decreases at each fixed sigma. This proves coupled L1 convergence. Therefore |E[chi(D_N-D)]| <= E|D_N-D| tends to zero for every fixed bounded static latent mask chi. Mere unmasked expectation convergence was not used.

## Other obligations checked

1. Finite legality and actual crossings. The three displayed groups have mean 0,M,M and unit variance. Their covariance is a positive Gram contribution plus strictly positive private diagonal, hence positive definite for 0<sigma and c>0 with sigma^2+c^2<1. The population cutoff is the smallest statistic threshold satisfying qH>=S, which corresponds to the largest ordinary BH p crossing. Contact equality follows by continuity and minimality. No free rank or separately tested block is introduced. Test A's three actual ranks and its signed dilution jumps also check algebraically.

2. Unique maximum and fold. For x=0, r(t) has exactly one mode at M/(1-c^2); L0'=h(L0-r), with L0-r positive at minus infinity and negative at the density-ratio mode. Every zero before the mode has derivative -r'<0; after the mode L0<r. Thus L0 has one strict nondegenerate global maximum t*. The condition c h(M)<h(0) gives t*<M. Uniform tail limits L(t,x)->1 at minus infinity and 0 at plus infinity, for x in a compact neighborhood, keep competing maximizers in a compact set. The strict global gap and implicit function theorem give the unique local even maximizer t(x), still global for small |x|. At t*, L_xx=a0^2 c^-2 y phi(y)/S(t*)<0, so Qcrit''(0)>0. Choosing epsilon small makes Qcrit strictly increasing with |x| on that neighborhood; other latent regions are removed by the static mask rather than assumed irrelevant.

3. Sigma removal and escaping roots. On |Z|<=1, the exact supremum of the true density ratio is exp(Z^2/2)/sqrt(1-sigma^2), and integration gives the same survival-ratio cap. A small neighborhood of q* can be chosen with one half q times this cap uniformly below one. Alternative means are uniformly bounded on |X|<epsilon, their private variance is the fixed c^2<1, and their tail ratio tends uniformly to zero at plus infinity. At minus infinity H_sigma/S tends uniformly to one. Thus every possible crossing lies in a fixed compact statistic interval as sigma decreases, and there is no missed microscopic true- or false-driven population root on the mask. Below Qcrit(X) eventually no crossing exists; above it a strict witness persists. Any selected contact, including a competing bounded macro root, has limiting V0/H0=q/2. The equality set Qcrit(X)=q has at most two points in the mask and has Gaussian probability zero. Hence the two successive value limits equal G(q)=P(|Z|<=1) (q/2) P(|X|<epsilon,Qcrit(X)<=q).

4. Onset. The strict quadratic local minimum gives G(q*)=0 and G(q*+h)>=c_M q* sqrt(h) for all sufficiently small positive h. The value of c_M may depend on the chosen M; it need not be uniform for the contradiction.

5. Flux localization. For every finite model, multiplying the exact grouped q-transport ledger by a fixed measurable 0<=chi<=1 bounds the signed masked FDP increment by the unmasked positive flux integral. A latent factor representation can have more dimensions than rank(Sigma); alternatively replace chi by the fixed conditional weight E[chi|T] in the minimal observation-space Gaussian representation. This weight remains in [0,1] and does not depend on q, so no q derivative of the mask occurs. This addresses the ancillary-factor issue explicitly.

6. Uniform-to-finite consequence. If gate (19) held for every finite model with universal K,q0, the masked expectations would have a common one-sided Lipschitz upper bound on any fixed interval near q*>0. Pass this inequality first through N to infinity at fixed sigma and then through sigma to zero at each endpoint. The square-root onset contradicts it. Equivalently, after choosing small h making the limiting increment strictly larger than the asserted flux budget, choose a positive sigma and then a finite N so the same strict endpoint inequality holds. Thus a lawful finite model must violate the proposed positive-flux bound on a set of q of positive measure; explicit numerical N or sigma is not supplied. This existential finite-N conclusion is valid and does not interchange derivatives with limits.

7. Small-q quantifier. The bound q*<4S(M), with c=M^-2 and c h(M)<h(0) for sufficiently large M, puts q* below any proposed universal q0. M is chosen first and then fixed throughout the two value limits and h comparison.

## Surviving conclusion and limits

Subject only to the declared approved prerequisite and ordinary finite-arrangement flux identity, the argument defeats the dimension-uniform pointwise one-sided positive-q-flux gate (19), not the one-sided main FDR order conjecture. It supplies an existential finite-model violation, not a numerically exhibited finite flux value. The separate two-sided gate (22) is not tested. Signed or integrated budgets of the required FDR order may survive. The unmasked sigma-zero argument is invalid because escaping microscopic pure-null roots can occur; the candidate correctly preserves that failure and repairs only the localized claim.
