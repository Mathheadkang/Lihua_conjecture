---
type: idea
title: >-
  Same-rank spectral packet ledger and an exact common-envelope logarithmic loss
  for singular antipodal clones
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_fractional_frame_surface_kernel
  - gaussian_bh_conditional_compound_calibration
  - gaussian_simplex_factor_envelope_obstruction
tags:
  - spectral-slicing
  - same-rank
  - singular-covariance
  - compound-envelope
  - noise-floor
  - unproved-main
---

This planning diagnostic develops idea_fe3dbb76c65f without editing it. No executable main proof or new completion root is claimed. It distinguishes three issues: exact packet bookkeeping, the conditional Gaussian residual law, and the remaining cross-packet estimate. Unlike [the draft simplex diagnostic](../assets/gaussian_simplex_factor_envelope_obstruction.md), the logarithmic obstruction below uses the supremum OUTSIDE the summed null CDF, as in [the approved compound calibration](../assets/gaussian_bh_conditional_compound_calibration.md); it does not confuse that envelope with a sum of coordinatewise suprema.

## 1. Deterministic packet identity with one actual rank

Represent the original finite model as T_i=theta_i+v_i.G, with unit rows and their exact original Gram covariance; arbitrary singular covariance is allowed. Partition the ORIGINAL null labels into deterministic nonempty sets A_1,...,A_M. All coordinates, original means, alternatives and their gates remain in the full original BH calculation. Put t_r=qr/N, u_r=S^{-1}(t_r) and
$$
V_\ell(r,g)=\sum_{i\in A_\ell}1\{v_i.g\ge u_r-\theta_i\}.
$$
Let R(g) be the original largest qualifying BH rank, including ties. The exact identity is
$$
E[\mathrm{FDP}]
=\sum_{r=1}^N\sum_{\ell=1}^M
\frac1r E[1\{R=r\}V_\ell(r,G)].
\tag{SP1}
$$
The same mask 1{R=r} appears for every packet. A packet does not run its own BH rule and receives no separately maximized threshold.

For each packet let S_ell=sum_{i in A_ell} v_i v_i^T and L_ell=||S_ell||op>=1. Every subset J of k packet labels has a valid fractional frame with weights 1/L_ell. Thus [the approved surface kernel](../assets/gaussian_bh_fractional_frame_surface_kernel.md), for u_r>=1 and every deterministic unit exposure w, gives
$$
\phi(y)P\{v_i.G\ge u_r-\theta_i\ (\forall i\in J)\mid w.G=y\}
\le \sqrt e\,h(u_r)t_r^{k/L_\ell}.
\tag{SP2}
$$
In particular
$$
\phi(y)E[1\{R=r\}{V_\ell(r,G)\choose k}\mid w.G=y]
\le { |A_\ell|\choose k}\sqrt e\,h(u_r)t_r^{k/L_\ell}.
\tag{SP3}
$$
The left side retains the exact rank mask. The displayed upper bound discarded it. The surface kernel alone supplies neither a summable same-rank allocation of (SP1) nor justification for replacing its masked terms by separate threshold suprema. The missing allocation is not renamed as a new theorem.

## 2. Observed spectral conditioning is not latent diagonal-noise construction

For n>=3 and 0<rho<1 consider the equicorrelation matrix
$$
\Sigma=(1-\rho)I_n+\rho\,11^T,\qquad
\lambda_+=1+(n-1)\rho.
$$
Conditioning the observed standard principal score
Y=(sum_i T_i)/sqrt(n lambda_+) leaves Gaussian residual covariance
$$
\Sigma-\lambda_+11^T/n
=(1-\rho)(I_n-11^T/n).
\tag{SP4}
$$
Its off-diagonal entries are -(1-rho)/n, and its residuals sum to zero. They are not mutually independent. Nevertheless this SAME original covariance admits
$$
T_i=\sqrt\rho Z+\sqrt{1-\rho}\,\varepsilon_i,
$$
with independent Z,epsilon_i, and diagonal residual (1-rho)I. Thus (SP4) only disproves automatic independence from conditioning on an observed empirical eigenmode; it does not obstruct all exact latent Gaussian factorizations. Its negative residual signs can support a count argument when those signs survive the further conditioning on every alternative. The new sub-Poisson observation idea_e34ba60a4ca5 supplies an inline derivation of that weaker, genuinely sufficient count hypothesis.

## 3. A singular family forces zero diagonal residual in every exact Gaussian factor split

Fix positive integers m,L and let N=2mL. For each j<=m retain L original copies of G_j and L original copies of -G_j, with independent standard Gaussian G_j. All original means are zero and all labels are true nulls. Each 2L-by-2L block has covariance ss^T, where s has L entries +1 and L entries -1. This is an admissible unit-diagonal singular covariance, including the exact multiplicities.

For ANY independent Gaussian factor representation with this same covariance,
$$
\Sigma_0=AA^T+D,\qquad D=\operatorname{diag}(d_i)\succeq0,
$$
one has D=0. For any two labels i,k in the same block, choose x supported on that pair with x_i=s_k and x_k=-s_i. Then Sigma_0 x=0 and
$$
0=x^T\Sigma_0x=\|A^Tx\|^2+d_i+d_k.
$$
Nonnegativity forces d_i=d_k=0. Every coordinate belongs to such a pair. This is a statement about exact Gaussian factor-plus-independent-diagonal-noise representations, not arbitrary nonlinear conditioning.

After conditioning on the complete factor vector, all original p-values are consequently deterministic. Conditional coordinate independence holds, but the approved compound envelope can lose the desired order.

Let W_j=2S(|G_j|). These are independent Uniform(0,1) variables. Write
$$
U=m\min_j W_j,\qquad p_{\min}=\frac{\min_jW_j}{2}.
$$
With probability one, exactly L original p-values attain p_min. For the common-supremum compound envelope
$$
M_q(G)=\sup_{0<t\le q}\frac{\sum_{i=1}^N1\{p_i\le t\}}{Nt},
\qquad K_q=\max\{1,M_q\},
$$
the non-strict threshold t=p_min gives M_q>=1/U whenever p_min<=q. Suppose 0<q<1/4 and m>=ceil(1/q). On 2q<=U<=1, this condition holds and
$$
\min\{1,2qK_q\}\ge 2q/U.
$$
The density of U is (1-u/m)^{m-1} on [0,m]. On [0,1] it is at least e^{-1}: log(1-x)>=-x/(1-x) gives (m-1)log(1-1/m)>=-1. Therefore
$$
E\min\{1,2qK_q\}
\ge \frac{2q}{e}\int_{2q}^1\frac{du}{u}
=\frac{2q}{e}\log\frac1{2q}.
\tag{SP5}
$$
This is already larger than every fixed multiple of q sqrt(log(1/q)) for sufficiently small q. It concerns the common envelope itself and hence also applies if a larger calibration constant such as 4e is used.

The actual BH FDR in this SAME finite family equals q. Indeed for q<1/2 the larger p-value in each antipodal pair cannot be selected. A qualifying rank inside a clone multiplicity always makes the endpoint of that block qualify, so the largest rank is R=L K, where K is exactly the largest BH rank on W_1,...,W_m at level q. The latter are independent uniforms. To verify their exact FDR, replace W_j by zero and call the resulting rank K_j>=1. The deterministic BH replacement identity gives
$$
E\frac{1\{j\ {\rm selected}\}}{K\vee1}
=E\frac{1\{W_j\le qK_j/m\}}{K_j}
=q/m,
$$
since K_j depends only on the other uniforms. Summing over j gives q. In the physical all-null model FDR=P(R>0)=q as well. Thus (SP5) refutes this full-factor envelope certificate for the target order; it does not refute the target.

At L=1 the covariance already has nonpositive off-diagonal entries, so the unconditioned null count is sub-Poisson and the new count argument avoids (SP5). At larger L, independent antipodal blocks with clone multiplicities can be treated exactly in this special family. Neither observation supplies the arbitrary original-geometry packet allocation.

## 4. Exact noise-floor limitation under positive-definite regularization

For this same physical dimension set
$$
\Sigma_\epsilon=(1-\epsilon)\Sigma_0+\epsilon I_N,\qquad0<\epsilon<1.
$$
Consider ANY exact split Sigma_epsilon=AA^T+D with D diagonal PSD. In one block of size b=2L put P=I_b-ss^T/b. Since the corresponding principal block of AA^T is PSD,
$$
0\le\operatorname{tr}[P(\Sigma_\epsilon-D)]
=\epsilon(b-1)-(1-1/b)\sum_{i\ {\rm in\ block}}d_i.
$$
Consequently
$$
\sum_{i=1}^N d_i\le N\epsilon.
\tag{SP6}
$$
An independent residual variance floor d_i>=delta for all coordinates therefore requires delta<=epsilon. There is no uniform positive floor as epsilon decreases to zero. This does not say a floor is mathematically necessary for an eventual proof; it shows one cannot obtain one for free from an exact factorization.

For the natural exact split D=epsilon I,
T_i=s_i sqrt(1-epsilon)G_j+sqrt(epsilon)E_i.
Condition on all G_j. For each fixed finite m,L and almost every G, the conditional null CDF at every fixed threshold away from a limiting p-value converges to its deterministic indicator. Choosing a threshold just above p_min and then decreasing it to p_min proves liminf M_{q,epsilon}(G)>=M_{q,0}(G) for the maximal finite empirical ratio (and suffices using just p_min). Fatou yields the lower bound (SP5) in the limit inferior of the capped conditional certificate. Thus even nonsingular exact regularizations with positive private noise cannot uniformly remove this envelope loss by letting that floor vanish.

## 5. Other required calibrations and failed-route boundary

Perfect clones: all N original nulls equal G. Actual FDR=q. Complete-factor conditioning yields the exact capped certificate q+2q(1-q), which is O(q). The packet kernel has L=N and must retain the clone count; no independent-coordinate claim is valid before conditioning.

Unbalanced antipodal clones: a labels equal G and b labels equal -G. Actual rejecting tails have probabilities qa/(a+b) and qb/(a+b), hence actual FDR=q. With w=a/(a+b), the complete-factor capped envelope is at most (4+2 log 2)q, using the two weight integrals and binary entropy. This special two-packet payment does not extend by summing independently over arbitrarily many directions; (SP5) gives an exact obstruction to doing so.

Independent nulls: no conditioning is required; their compound CDF is m t<=Nt, so K=1 and the count/product calibrations give a universal O(q) bound. Conditioning on every null score instead can produce the same first-order-statistic logarithmic loss. Choosing the conditioning is part of the unresolved construction.

The rare-alternative common-factor lower family was re-read in Progress P4a--P4c of plan_one_sided_order_fdp_entropy_mills_coherence_20261107. Its actual null rows are r e_0+sqrt(1-r^2)e_i; its alternative rows are -e_0 with their fixed positive means. Conditioning on G_0 genuinely gives independent null residuals and deterministic alternative gates, so this family is a positive calibration case for factor/count methods. It has finite models with FDR of order qU, not a valid O(q) trace payment in a low-coherence packet. No new universal envelope upper bound for this family is inferred here.

The failed mixed-trace plan plan_one_sided_order_mixed_trace_replica_cells_20261108 was re-read because (SP3) must not become another unsigned separate-face payment: its P17/P21 signed remainder and P27--P33 distinct-face obstruction retain endpoint FDP masks and inverse heat denominators. The failed entropy/Mills plan above was re-read because its O(q) trace-versus-deficit certificate is actually false on the rare-alternative family. The present diagnostics neither retry those certificates nor assume their unpaid cancellations.

## Exact unpaid gate and planning conclusion

Constructing an arbitrary deterministic spectral/Gram packet decomposition is easy; constructing one with a uniformly summable payment of (SP1) is not supplied by (SP2), diagonal factorization, or the new sub-Poisson calibration. One must specify for each packet the FINAL conditional law after all alternatives are fixed, retain its exact residual covariance, prove its count mgf or explicitly retain dependence, and allocate the masked contributions with the SAME largest R. No allocation accomplishing this uniformly, without dimension, entropy or noise-floor loss, has been derived. Therefore no filler pending main plan is created.
