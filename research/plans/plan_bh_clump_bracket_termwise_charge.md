---
id: plan_bh_clump_bracket_termwise_charge
title: Termwise charge plan for the pathwise clump-bracket bound
type: plan
status: succeeded
target_asset: bh_clump_bracket_pathwise_bound
inspired_by:
  - idea_abf904b3bad8
tags:
  - benjamini_hochberg
  - pathwise
  - fdr
proof_digest: d1b62766479486eb204ea11c5b821f5674c5c6e498e7591613e5dd5d2b0a7382
statement_digest: 505283800a561693969245cf14db866c63b7fbf613631c942f088194185139db
dependency_digests:
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: d1b62766479486eb204ea11c5b821f5674c5c6e498e7591613e5dd5d2b0a7382
---

# Termwise charge plan for the pathwise clump-bracket bound

## Goal

Target: [asset](../assets/bh_clump_bracket_pathwise_bound.md)

Prove the statement exactly as written: the well-definedness claims ($R_{i,0}\ge1$, $D_i\ge1$), that $R_{i,0}$ and $R_{i,*}$ depend only on $(p_j)_{j\notin K_l}$, the pathwise inequality, and its expectation version. The route is termwise: every rejected $i\in S$ satisfies $\Psi_i\ge 1/R$, and all other terms are nonnegative. Everything is elementary and uses only the approved definition of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) with the largest qualifying rank, multiplicities, and non-strict comparisons.

Notation: for $x\in[0,1]^N$ and $t\in\mathbb R$ let $F_x(t)=|\{j:x_j\le t\}|$, and write $\widehat k(x)=\widehat k_q(x)$.

## Plan

1. [x] **Order-statistic counting.** For $x\in[0,1]^N$, $k\in\{1,\dots,N\}$ and $t\in\mathbb R$: $x_{(k)}\le t$ if and only if $F_x(t)\ge k$. (Order statistics are taken with multiplicities; if $x_{(k)}\le t$ then $x_{(1)},\dots,x_{(k)}$ are $k$ coordinates at most $t$; conversely if $k$ coordinates are at most $t$, the $k$-th smallest is at most $t$.) Hence $k$ qualifies for $x$ (that is, $x_{(k)}\le qk/N$) if and only if $F_x(qk/N)\ge k$.

2. [x] **Rejection count equals the largest qualifying rank.** For every $x$, $R_q(x)=\widehat k(x)$. If $\widehat k(x)=0$ the rejection set is empty by definition. If $k:=\widehat k(x)\ge1$, then $R_q(x)=F_x(qk/N)\ge k$ by Step 1. If $F_x(qk/N)\ge k+1$ (so $k<N$), then $F_x(q(k+1)/N)\ge F_x(qk/N)\ge k+1$, so $k+1$ qualifies, contradicting maximality. Hence $R_q(x)=k$. This is where the largest-qualifying-rank convention and the non-strict comparisons are used; ties are handled because $F_x$ counts multiplicities.

3. [x] **Coordinatewise monotonicity.** If $x\le y$ coordinatewise then $R_q(x)\ge R_q(y)$. Indeed $F_x(t)\ge F_y(t)$ for every $t$, so by Step 1 every rank qualifying for $y$ qualifies for $x$, giving $\widehat k(x)\ge\widehat k(y)$, and Step 2 converts this to rejection counts.

4. [x] **Zeroing a rejected coordinate keeps the count.** Let $R=R_q(p)\ge1$, let $i\in\mathcal R_q(p)$, and let $p'$ equal $p$ except $p'_i=0$. Then $R_q(p')=R$. Proof: $p_i\le q\widehat k(p)/N=qR/N$ (definition of the rejection set and Step 2). For every $t\ge p_i$ both $p_i\le t$ and $0\le t$ hold, so $F_{p'}(t)=F_p(t)$. For each rank $k\ge R$ we have $t=qk/N\ge qR/N\ge p_i$, so by Step 1 the rank $k$ qualifies for $p'$ if and only if it qualifies for $p$. Since $R$ qualifies for $p$ and no $k>R$ does, $\widehat k(p')=R$, and Step 2 gives $R_q(p')=R$. (Ranks $k<R$ are irrelevant to the maximum.)

5. [x] **Well-definedness and dependence.** Fix $l$ and $i\in K_l$. The vector $p^{(i,0)}$ has $p^{(i,0)}_i=0$, so $p^{(i,0)}_{(1)}=0\le q/N$, rank $1$ qualifies, and $R_{i,0}=\widehat k(p^{(i,0)})\ge1$ by Step 2. $D_i\ge1$ because $j=i$ satisfies $p_i\le p_i$. So the denominator of $\Psi_i$ is at least $1$, and $0\le\Psi_i\le1$. For fixed $i$, the coordinates of $p^{(i,0)}$ and $p^{(i,*)}$ indexed by $K_l$ are the constants $0$ or $1$ fixed by $i$ and $K_l$, and the others are $(p_j)_{j\notin K_l}$; hence $R_{i,0}$ and $R_{i,*}$ are functions of $(p_j)_{j\notin K_l}$ alone.

6. [x] **Termwise charge.** Assume $R\ge1$ and $i\in\mathcal R_q(p)\cap K_l$ for some $l$. Claim: $\Psi_i\ge1/R$. Check each piece:
   - (indicator) $p^{(i,*)}\le p$ coordinatewise, so $R_{i,*}\ge R$ by Step 3; with $p_i\le qR/N$ (Step 4) this gives $p_i\le qR_{i,*}/N$, so the indicator equals $1$.
   - ($Np_i/q$) $p_i\le qR/N$ gives $Np_i/q\le R$.
   - ($D_i$) every $j\in K_l$ with $p_j\le p_i$ has $p_j\le qR/N=q\widehat k(p)/N$, hence $j\in\mathcal R_q(p)$; so $D_i\le|\mathcal R_q(p)|=R$. Ties $p_j=p_i$ are included on both sides.
   - ($R_{i,0}$) with $p'$ from Step 4, $p^{(i,0)}\ge p'$ coordinatewise (coordinate $i$ is $0$ in both, coordinates in $K_l\setminus\{i\}$ are raised to $1\ge p_j$, the rest coincide). By Step 3 and Step 4, $R_{i,0}=R_q(p^{(i,0)})\le R_q(p')=R$.
   Hence $1\le\max\{R_{i,0},D_i,Np_i/q\}\le R$ and $\Psi_i\ge1/R$.

7. [x] **Pathwise sum.** If $R=0$ the left side is $0\le\sum_{i\in S}\Psi_i$ since every $\Psi_i\ge0$. If $R\ge1$, then $R\vee1=R$ and, since the $K_l$ partition $S$,
   $$
   \frac{|\mathcal R_q(p)\cap S|}{R}=\sum_{i\in\mathcal R_q(p)\cap S}\frac1R\le\sum_{i\in\mathcal R_q(p)\cap S}\Psi_i\le\sum_{i\in S}\Psi_i=\sum_{l=1}^L\sum_{i\in K_l}\Psi_i,
   $$
   using Step 6 for each rejected $i\in S$ and $\Psi_i\ge0$ for the unrejected ones.

8. [x] **Measurability and expectation.** On a probability space with a random vector $p$ taking values in $[0,1]^N$ (measurable), each order statistic $x\mapsto x_{(k)}$ is continuous, so $\widehat k(x)=\max_k k\,\mathbf 1\{x_{(k)}\le qk/N\}$ and $R_q(x)=|\{j:x_j\le q\widehat k(x)/N\}|$ are Borel, and so is $x\mapsto\mathcal R_q(x)\cap S$ (finitely many Borel indicators $\mathbf 1\{x_j\le q\widehat k(x)/N\}$). The maps $p\mapsto p^{(i,0)},p^{(i,*)}$ are continuous, $D_i=\sum_{j\in K_l}\mathbf 1\{p_j\le p_i\}$ is Borel, and $\Psi_i$ is a Borel function of $p$ with values in $[0,1]$ (denominator at least $1$ by Step 5). Both sides of the pathwise inequality are therefore bounded nonnegative random variables, and taking expectations of the inequality of Step 7, which holds at every sample point, gives the expectation bound. No independence or distributional assumption enters; $S\subseteq I_0$ plays no role beyond fixing which coordinates are summed.

## Verification

Steps 1 to 3 give the standard structural facts of ordinary BH (count equals largest qualifying rank; monotone nonincreasing in each coordinate), proved from the approved definition including ties. Step 5 gives the two well-definedness claims and the claimed dependence of $R_{i,0},R_{i,*}$ only on coordinates outside the clump. Steps 4 and 6 bound each of the three entries of the denominator of $\Psi_i$ by $R$ and show the indicator is $1$ for every rejected $i\in S$. Step 7 sums these charges, which yields the displayed pathwise inequality for every deterministic $p$, every $S\subseteq I_0$, and every partition into clumps. Step 8 transfers it to expectations on an arbitrary probability space. The equality case observed in the search (all $p_j=q$, so $R=N$ and $\Psi_i=1/N$ for all $i$ when $S=\{1,\dots,N\}$ is one clump) is consistent with Step 6 being tight.

## Assumed definitions

- [benjamini_hochberg_step_up](../definitions/benjamini_hochberg_step_up.md) (approved).
- [false_discovery_rate](../definitions/false_discovery_rate.md) (approved), used only to name the left side of the expectation bound.
- No unproved dependencies; Steps 1 to 4 are proved inside the plan rather than cited.

## Outcome

Succeeded. The complete proof is under `## Proof` in [the target asset](../assets/bh_clump_bracket_pathwise_bound.md), following Steps 1 to 8 of this plan without change: count equals largest qualifying rank (with ties), coordinatewise monotonicity, zeroing a rejected coordinate keeps the count, the termwise charge $\Psi_i\ge1/R$ for every rejected $i\in S$, summation, and measurability for the expectation form. Nothing is assumed beyond the approved definitions [benjamini_hochberg_step_up](../definitions/benjamini_hochberg_step_up.md) and [false_discovery_rate](../definitions/false_discovery_rate.md); there are no dependencies.

## Verdict

confirmed

Checked each step against the approved BH and FDR definitions. Step 1 (rank $k$ qualifies iff $F_x(qk/N)\ge k$) holds with ties and non-strict comparisons. In Step 2, $R_q(x)=F_x(q\widehat k/N)\ge\widehat k$. Strict excess would force $\widehat k<N$ and make rank $\widehat k+1$ qualify, so $R_q=\widehat k$; the case $\widehat k=0$ is handled. Step 3 follows because $x\le y$ gives $F_x\ge F_y$. In Step 4, zeroing a rejected $p_i\le qR/N$ leaves $F$ unchanged on $[p_i,\infty)$, so qualification is unchanged for every rank $k\ge R$; changes at lower ranks do not affect the maximum. Step 5: rank 1 qualifies for $p^{(i,0)}$, so the denominator is $\ge1$ and $0\le\Psi_i\le1$. Since $p^{(i,0)}$ and $p^{(i,*)}$ equal the constants $0$ or $1$ on $K_l$, the dependence claim holds. Step 6: the inequalities run the right way. $p^{(i,*)}\le p$ gives $R_{i,*}\ge R$, so the indicator is 1. $Np_i/q\le R$. $D_i\le|\mathcal R_q(p)\cap K_l|\le R$. $p^{(i,0)}\ge p'$ together with Step 4 gives $R_{i,0}\le R$. Steps 7-8: dropping the nonnegative terms for non-rejected $i$ is valid, and $R=0$ is handled. All maps are Borel (continuous order statistics, finite max and indicators, continuous substitution maps), and both sides are bounded, so the expectations exist.

Hand checks: (a) $N=1$, $p_1=q$ with one clump of size one gives $R=1$, $R_{1,0}=R_{1,*}=D_1=Np_1/q=1$ and $\Psi_1=1$, so equality holds. (b) $N=2$, $p=(q,q)$ tied at the threshold with one clump of size two gives $R=2$; $p^{(1,0)}=(0,1)$ gives $R_{1,0}=1$, but $D_1=2$ and $Np_1/q=2$, so $\Psi_1=\Psi_2=1/2$ and equality holds. (c) $R=0$ makes the left side 0. No gaps found. The only implicit point is that the random $p$ in the expectation form must be a measurable random vector, which "random p-values" implies.
