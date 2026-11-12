---
type: plan
status: failed
title: Joint Gaussian extremum and one-common-factor reduction
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by:
  - idea_c781d2dc45a5
  - idea_ce4038795c70
  - idea_eee4c8503f61
adapts:
  - multifactor_radial_fdr_bounds
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md).

Test and, only if it survives, prove a new finite-array extremal principle: after optimizing the actual mean vector and its true-null labels jointly with the covariance, a Gaussian BH FDR maximizer can be chosen in the class consisting of one signed common Gaussian factor and independent Gaussian residuals. This is a proposed extremal lemma, not an established reduction. It is substantially stronger than the target and can fail while the target remains true. The first task is its finite-array gate, not an application of the existing restricted-model bound to an unrestricted covariance.

This route keeps the full jointly Gaussian alternative mechanism. It uses neither a null-only FDR-linking inequality nor a positive-correlation assumption on the original covariance. In particular, it asserts no monotonicity in any individual negative null mean and makes no zero-null-mean least-favourable reduction. The approved construction `gaussian_bh_negative_null_mean_nonmonotonicity` explicitly prevents that shortcut.

The fresh context pack has no pending plan and lists two failed plans, addressed individually below. Native library searches for `Gaussian BH`, `Gaussian level-set perimeter heat semigroup`, `Gaussian covariance extremum rank one factor KKT`, and `Gaussian BH one factor sharp upper` found no matching library result. Additional native reads were needed to identify the exact weighted-jump and completion obstructions and to inspect the terminal restricted-class proof. The optional negative-triangle test `idea_eee4c8503f61` was read natively because it was created after the context pack. The proposed extremal principle has no known proof in those materials. The terminal calculation below reproves every tool it needs; no result absent from the target's dependencies is invoked as a black box.

## Plan

1. [x] **Set up a compact labelled finite-array optimization without changing the statistical target.** Fix an integer $N\geq1$, a label set $J\subseteq[N]$, and $0<q\leq1/64$. Let $f_{q,J}$ be the ordinary BH FDP with $J$ held fixed in the function. Initially take $\theta_i\leq0$ for $i\in J$ and $\theta_i>0$ for $i\notin J$. Put

   $$
   H_{N,J}(q;\theta,\Sigma)
   =\mathbb E_{\theta,\Sigma}f_{q,J}(T).
   $$

   Compactify the means by allowing $\theta_i\in[-\infty,0]$ on $J$ and $\theta_i\in[0,+\infty]$ off $J$. At a zero alternative mean retain the limiting non-null label, and interpret infinite means as deterministic p-values 1 or 0. These are auxiliary labelled limits, not a redefinition of the approved true-null set. Prove equality of the compactified supremum with the original sign-stratum supremum by finite-mean approximation and continuity. For fixed finite $N$, couple covariances through their positive-semidefinite square roots; every finite coordinate has a continuous unit-variance marginal, so all the finitely many BH threshold hyperplanes have probability zero even at singular covariances. Deterministic p-values 0 and 1 are strictly outside the interior threshold grid. This gives a maximum on each compactified stratum.

   A useful explicit mean truncation error must also be proved: when $M/2>z(q/N)$, replacing a mean beyond $M$ in its permitted direction by the corresponding infinite mean changes the BH grid bins with probability at most $\overline\Phi(M/2)$ per changed coordinate, uniformly in the covariance. Here and below $z(t)=\overline\Phi^{-1}(t)$. A union bound controls the FDP expectation error. Do not truncate means without carrying this error.

2. [ ] **First finite-array gate: settle a genuine extremal comparison before attempting a general reduction.** For $a\in[-1,1]^N$, define

   $$
   C(a)_{ii}=1,\qquad C(a)_{ij}=a_i a_j\quad(i\ne j).
   $$

   This is the covariance of

   $$
   T_i=\theta_i+a_i Z+\sqrt{1-a_i^2}\,\varepsilon_i,
   $$

   with independent standard normals $Z,\varepsilon_1,\ldots,\varepsilon_N$. Write

   $$
   M_N(q)=\max_{J,\theta,\Sigma\in\mathcal C_N}H_{N,J}(q;\theta,\Sigma),
   \qquad
   A_N(q)=\max_{J,\theta,a\in[-1,1]^N}H_{N,J}(q;\theta,C(a)),
   $$

   where the mean constraints and compactification are exactly those in step 1. The proposed finite-array extremal lemma is

   $$
   M_N(q)=A_N(q),\qquad N\geq1,\quad0<q\leq1/64.\tag{E}
   $$

   Its reverse inequality is immediate; its forward inequality is completely unproved. Optimizing the mean vector and labels on both sides is essential: (E) does not assert domination at each fixed mean vector or fixed null set.

   The first gate is (E) at $N=3$, $q=1/64$, including every label set, the negative-null region, and singular covariance faces. Derive the exact finite BH grid-cell Gaussian probability formula, retaining all ranks and their rational FDP values. Then obtain either an analytic proof of this finite case or a certified non-factor lower bound exceeding a certified upper bound for the entire one-factor optimization $A_3(1/64)$. If needed, use deterministic interval integration and branch bounds on the compact mean and factor boxes with the tail error from step 1. A factor upper bound must cover all means and all labels, not merely the best sampled factor model. A numerical local optimum or Monte Carlo comparison cannot pass or refute this gate. A certified strict gap ends this plan as failed and does not refute the target. After the first gate, repeat the structural check at $N=4$ and levels $1/64,1/256$ before claiming a general extremal proof.

   As an optional first candidate, evaluate the centered all-null negative equicorrelation triangle from `idea_eee4c8503f61`, with correlation in $[-1/2,0)$. In that all-null subproblem only, coordinatewise coupling proves that zero means maximize the rejection event. Three negative edges exclude a one-factor representation, but this sign fact proves no FDR comparison. Moreover, because (E) optimizes over all labels, exceeding the all-null factor maximum alone does not refute (E): the candidate must exceed the entire $A_3(1/64)$, including mixed-label factor models. A strict finite-level gap, even if only of order $q$, refutes exact (E) and this plan; it does not refute the original asymptotic conjecture. Any approximate replacement with a lower-order slack would require a new proved inequality, not an assumed repair.

   The plan-writing stage performs no such optimization. Any substantial scientific optimization or integration is to run only in a new isolated UC Davis directory, with at most two CPU processes and recorded code, interval precision, parameters, tail bounds, and certificates. Local work is limited to short deterministic identity checks. If bounded computation is inconclusive, report that honestly and pursue the analytic gate; do not count an inconclusive search as a pass.

3. [ ] **Derive the correct endpoint variational calculus.** At finite means and positive-definite covariance, differentiate the finite Gaussian grid-cell probabilities. For a symmetric zero-diagonal matrix $H$, prove

   $$
   D_\Sigma H_{N,J}[H]
   =\sum_{i<j}H_{ij}B_{ij},\qquad
   B_{ij}=\mathbb E_{\theta,\Sigma}[\partial_{ij}f_{q,J}],
   \tag{V}
   $$

   with derivatives understood distributionally and evaluated at this single endpoint. Derive the first and second derivatives in the actual finite means as well. The second covariance derivative contains fourth distributional derivatives of the same labelled FDP; calculate it from the Gaussian rectangle formula rather than assuming a sign. Recheck all mixed threshold-corner normalizations, including $N=2$ and rank jumps across more than one rank.

   **The matrix $B$ in (V) is not an integrated corner matrix.** Endpoint KKT conditions at an actual maximizer constrain $B$. They imply no uniform diagonal/block completion estimate for the matrix integrated along the old null-noise interpolation path. Neither of the failed plans' certificates, including the more general fixed-alternative completion certificate, follows from (V).

4. [ ] **Prove the new extremal lemma by explicit admissible variations, or stop at the obstruction.** Represent $\Sigma$ by unit Gram rows $v_i$. Two concrete families of variations supply a checkable starting point.

   For an orthogonal projection $P$ onto a two-dimensional factor plane and its quarter-turn $Q$, rotate row $i$'s plane component by angle $s\alpha_i$, leaving its orthogonal component fixed. This preserves every row norm and PSD for every $s$. With a consistently chosen orientation,

   $$
   \Sigma'_{ij}(0)
   =(\alpha_i-\alpha_j)\langle QPv_i,Pv_j\rangle,
   \qquad
   \Sigma''_{ij}(0)
   =-(\alpha_i-\alpha_j)^2\langle Pv_i,Pv_j\rangle.
   \tag{P}
   $$

   Also allow an entirely new orthogonal factor direction $e$ and put

   $$
   v_i(s)=\sqrt{1-s^2\alpha_i^2}\,v_i+s\alpha_i e.
   $$

   Then

   $$
   \Sigma'_{ij}(0)=0,\qquad
   \Sigma''_{ij}(0)
   =2\alpha_i\alpha_j-(\alpha_i^2+\alpha_j^2)\Sigma_{ij}.
   \tag{N}
   $$

   Derive the resulting second-variation forms by substituting (P) and (N) into (V) and the endpoint Hessian, also permitting mean directions in the exact sign-constrained critical cone. A zero null mean permits only directions toward nonpositive means; a limiting zero alternative mean permits only directions toward nonnegative means. Finite negative means must be optimized in their own interiors rather than moved to zero by assumption.

   The substantive, unproved task is to show that a **global** maximizer of the compact labelled problem can be replaced by a maximizer whose off-diagonal Gram products have the form $a_i a_j$: either a non-factor maximizer admits a strictly improving feasible variation, or an explicitly described flat family reaches the factor class. Specify a monotone quantity for each flat-family iteration and prove termination or compact convergence. Mere first-order stationarity, a PSD stress matrix, or verification of (P)/(N) does not prove this task. A local maximum need not be global, and absence of a single positive second variation is insufficient. If these variations do not yield a valid uncrossing/replacement lemma, record the exact unresolved case and fail this approach rather than insert (E) as an assumed theorem.

5. [ ] **Resolve every extremal boundary before using (E).** Supply a separate argument for singular full covariances and singular alternative blocks; use Gram variations, without an inverse Schur complement. Account for all covariance rank strata, mean boundaries, and infinite-mean limits from step 1. When a boundary freezes some p-values at 0 or 1, retain the original threshold grid $qk/N$: after $b$ fixed zero p-values it is $q(b+r)/N$, not a silently rescaled ordinary BH problem on the remaining coordinates. Induction, if used, must explicitly include this grid and its fixed false-discovery labels. Prove that factor limits stay in the closed class $C(a)$, and that compactification and smoothing do not introduce a maximizer larger than the original Gaussian supremum. No fixed positive spectral gap, bounded mean vector, bounded $N$, or positive alternative covariance determinant can survive as an unstated assumption in (E).

6. [ ] **Only after (E) is proved, reprove a uniform terminal one-factor bound directly.** This step adapts the radial-truncation architecture of `multifactor_radial_fdr_bounds` to $d=1$, but proves its conditional rank identity and scalar integral from the explicit kernels rather than citing its dependencies.

   Given $Z$, the p-values are independent, including deterministic conditional coordinates. Force null $i$'s p-value to zero and call the resulting rank $R_i$. Prove the exact BH identity

   $$
   \frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
   =\frac{\mathbf1\{p_i\leq qR_i/N\}}{R_i}.
   $$

   Consequently, conditionally on $Z$, the expected FDP is at most

   $$
   \frac qN\sum_{i\in J}\sup_{0<t\leq q}\frac{F_{r_i,W_i}(t)}t,
   \qquad r_i=|a_i|,\quad W_i=\operatorname{sign}(a_i)Z,
   $$

   where $F_{r,w}(t)=\overline\Phi((z(t)-rw)/\sqrt{1-r^2})$ is the boundary-null kernel. For $a_i=0$, choose either sign of $Z$. The comparison with the actual null kernel uses only $\theta_i\leq0$ inside its own conditional CDF and does not compare two FDPs under different mean vectors.

   Put $u=z(q)>0$, $b=z(q/2)$, and $G_r(w)=\sup_{0<t\leq q}F_{r,w}(t)/t$. For $0<r<1$, with $\sigma=\sqrt{1-r^2}$, derive from the conditional-to-marginal density ratio the explicit majorant

   $$
   G_r(w)\leq\sup_{x\geq u}\frac1\sigma
   \exp\!\left\{\frac{w^2}2-\frac{(rx-w)^2}{2\sigma^2}\right\}.
   $$

   For $w\leq ru$ the supremum is at $x=u$, and for $w\geq ru$ it is at $x=w/r$. Integrating this majorant on $(-\infty,u]$ therefore gives exactly the checkable bound

   $$
   \int_{-\infty}^{u}\phi(w)G_r(w)\,dw
   \leq\frac12+\frac{(1-r)u}{\sigma\sqrt{2\pi}}
   =\frac12+\frac{u}{\sqrt{2\pi}}\sqrt{\frac{1-r}{1+r}}.
   \tag{K}
   $$

   Handle $r=0$ by $G_0=1$ and $r=1$ by its indicator kernel, whose central integral vanishes. Prove the required $r=0$ bound directly from $\Phi(u)\leq1/2+u/\sqrt{2\pi}$. Kernel monotonicity in $w$ and marginal calibration give $G_r(w)\leq1/\overline\Phi(w)$ for every $r\in[0,1]$. Thus the added strip $[u,b]$ costs at most

   $$
   \int_u^b\frac{\phi(w)}{\overline\Phi(w)}\,dw=\log2.
   $$

   On $|Z|>b$ bound FDP by one, costing exactly $q$. On $|Z|\leq b$, integrate each oriented scalar kernel using (K), the strip bound, and nonnegativity. This proves, including every actual negative null and every factor/residual endpoint,

   $$
   H_{N,J}(q;\theta,C(a))
   \leq q\left(\frac32+\log2+\frac{u}{\sqrt{2\pi}}\right).
   \tag{F}
   $$

   The same bound extends to the labelled limiting means by step 1. All constants in (F) are independent of $N,J,\theta,a$. This restricted-model calculation alone does not establish any assertion for a general covariance.

7. [ ] **Close the unrestricted quantifiers using the proved extremal lemma.** For each finite admissible model at a fixed $q\leq1/64$, use its actual label set to bound its FDR by $M_N(q)$, use the now-proved equality (E), and then use the uniform terminal bound (F). Only at this point take the supremum over $N$, all means, and all PSD unit-diagonal covariances, including singular ones. Derive $u=z(q)\sim\sqrt{2\log(1/q)}$ from elementary normal-tail inequalities. The additive constant in (F) is $o(\sqrt{\log(1/q)})$, yielding exactly the target constant $1/\sqrt\pi$. Do not interchange a finite-$N$ optimization or a mean/spectral cutoff limit with $q\downarrow0$; (E) and (F) must hold uniformly for every finite $N$ first.

## Progress

Execution on 2026-11-04, continued from the earlier partial executions, ends with a certified obstruction at the first finite-array gate. Step 1 is established below. At step 2, the entire one-factor class, with all means, labels, and singular boundaries, is bounded strictly below an admissible full-model example at $N=3,q=1/64$. Thus the proposed exact extremal lemma (E) is false. Steps 2--7 are not marked completed and are not pursued past this failed gate. The target asset and its statement are unchanged; its asymptotic upper-bound conjecture remains unresolved. The full arguments and certificate provenance are retained below, with the decisive comparison in subsection 16 and the scope of failure stated separately.

### 1. Compactification, approximation, and the uniform tail error

Give each permitted extended mean interval its order topology, and give $\mathcal C_N$ its Euclidean topology. The mean intervals are compact, and $\mathcal C_N$ is closed and bounded: each correlation lies in $[-1,1]$ by its two-coordinate principal minor. Thus their finite product is compact. Write $S(\Sigma)$ for the positive-semidefinite square root, which is continuous on positive-semidefinite matrices, and couple all models by
$$
T_i=\theta_i+(S(\Sigma)G)_i,\qquad G\sim\mathcal N_N(0,I_N).
$$
At an infinite mean, define its p-value to be respectively 1 or 0 instead of evaluating an infinite test statistic. If $(\theta^{(n)},\Sigma^{(n)})$ converges to a compactified parameter, then for each fixed $G$ all finite test-statistic coordinates converge, and an infinite-mean coordinate tends to its stipulated infinite sign, since the corresponding Gaussian-noise coordinate stays bounded along this convergent covariance sequence. Every finite limiting coordinate has variance 1, including at singular $\Sigma$. It therefore hits none of the finitely many levels $z(qk/N)$, $1\leq k\leq N$, with positive probability. The deterministic limiting p-values 0 and 1 also lie outside these threshold hyperplanes, because $0<qk/N<1$. Off those null events, every coordinate's BH grid bin eventually agrees with its limiting bin. The labelled FDP is consequently eventually constant. Bounded convergence proves continuity of $H_{N,J}$ on this compact domain, including all covariance and mean boundaries.

For each compactified parameter, replace a null mean $-\infty$ by $-m$, an alternative mean $+\infty$ by $m$, and any limiting alternative zero mean by $1/m$, leaving the other coordinates and covariance fixed. These finite models lie in the original sign stratum and converge to the compactified parameter. Continuity gives equality of its maximum with the original stratum supremum. In particular, retaining a non-null label at its limiting zero mean is justified by approximation and does not change the approved definition of a true null. Taking the maximum over the finitely many $J$ gives the desired labelled compact optimization. The factor class is also closed: $a\mapsto C(a)$ is continuous on the compact cube $[-1,1]^N$.

For the explicit truncation error, suppose $M/2>z(q/N)>0$. Couple a finite extreme mean and its infinite replacement with the same noises and labels. For $\theta_i\geq M$, its grid bin differs from that of p-value 0 only if $T_i<z(q/N)$, an event of probability
$$
\overline\Phi(\theta_i-z(q/N))\leq\overline\Phi(M/2).
$$
For $\theta_i\leq-M$, its grid bin differs from that of p-value 1 only if $T_i\geq z(q)$, with probability
$$
\overline\Phi(z(q)-\theta_i)\leq\overline\Phi(M/2).
$$
Both statements use only unit marginal variance and are uniform in the covariance. Replacing a set $D$ of such coordinates changes no FDP unless at least one bin changes. Since FDP lies in $[0,1]$,
$$
|H_{N,J}(\theta,\Sigma)-H_{N,J}(\theta^{\mathrm{replaced}},\Sigma)|
\leq |D|\overline\Phi(M/2).
$$
This completes checklist item 1 without a spectral-gap or finite-mean assumption.

### 2. Exact finite BH grid probabilities

Put $t_k=qk/N$ for $0\leq k\leq N$, and define bins $B_1=[0,t_1]$, $B_k=(t_{k-1},t_k]$ for $2\leq k\leq N$, and $B_{N+1}=(q,1]$. Let $b_i\in\{1,\ldots,N+1\}$ denote the bin of $p_i$. For a bin vector $b$, set
$$
r(b)=\max\bigl(\{0\}\cup\{k:|\{i:b_i\leq k\}|\geq k\}\bigr),
\qquad
w_J(b)=\begin{cases}|\{i\in J:b_i\leq r(b)\}|/r(b),&r(b)>0,\\0,&r(b)=0.\end{cases}
$$
If $r>0$, there are exactly $r$ p-values at most $t_r$: if there were $s>r$, then $p_{(s)}\leq t_r\leq t_s$ would contradict maximality of $r$. Thus $w_J$ is the actual labelled FDP, including every rank jump. For finite means define $I_k=[z(t_k),z(t_{k-1}))$, with $z(0)=+\infty$, for $1\leq k\leq N$, and $I_{N+1}=(-\infty,z(q))$. Endpoints can be chosen arbitrarily for finite Gaussian coordinates. The exact formula is
$$
H_{N,J}(q;\theta,\Sigma)
=\sum_{b\in\{1,\ldots,N+1\}^N}w_J(b)
\mathbb P_{\theta,\Sigma}\{T_i\in I_{b_i}\text{ for every }i\}.
\tag{P1}
$$
At an infinite mean, restrict the corresponding index to bin 1 or $N+1$. Formula (P1) remains valid at singular covariance by the square-root representation above; it is not a density formula requiring an inverse covariance.

For a factor model and finite means, put $\sigma_i=\sqrt{1-a_i^2}$ and
$$
F_i(t,z)=\begin{cases}
\overline\Phi((z(t)-\theta_i-a_i z)/\sigma_i),&\sigma_i>0,\\
\mathbf1\{\theta_i+a_i z\geq z(t)\},&\sigma_i=0.
\end{cases}
$$
Let $\pi_{i1}=F_i(t_1,z)$, $\pi_{ik}=F_i(t_k,z)-F_i(t_{k-1},z)$ for $2\leq k\leq N$, and $\pi_{i,N+1}=1-F_i(q,z)$. Conditional independence gives the exact one-dimensional formula
$$
H_{N,J}(q;\theta,C(a))
=\int_{\mathbb R}\phi(z)\sum_b w_J(b)\prod_i\pi_{i,b_i}(z)\,dz.
\tag{P2}
$$
For infinite means the associated bin probability is deterministic. This includes $a_i=0,\pm1$, all labels, and all compactified means; it supplies an integrand for certification but is not itself a global upper certificate. At $N=3$, (P1) and (P2) have 64 bins with their exact weights $0,1/3,1/2,2/3,1$ as determined by $w_J$.

### 3. Rigorous reductions for the three-dimensional label cases

Here set $a=q/3$, $b=2q/3$, $c=q$; these local threshold letters are unrelated to the vector of factor loadings. An empty null set gives FDR 0. For a single null $i$, its FDP contribution is pointwise at most $g(p_i)$, where $g=1$ on $[0,a]$, $g=1/2$ on $(a,b]$, $g=1/3$ on $(b,c]$, and $g=0$ above $c$. Indeed, if its bin is $k\leq3$ and it is rejected, its actual rank is at least $k$. A finite negative-null p-value is superuniform: $\mathbb P(p_i\leq t)\leq t$. Writing $g=\tfrac12\mathbf1_{p\leq a}+\tfrac16\mathbf1_{p\leq b}+\tfrac13\mathbf1_{p\leq c}$ gives
$$
\operatorname{FDR}\leq a+\frac{b-a}{2}+\frac{c-b}{3}=\frac{11q}{18}<q.
\tag{P3}
$$
The same bound extends by continuity to labelled limits, uniformly over all covariances and all alternative mechanisms.

For two nulls, maximize the labelled FDP pointwise over the alternative p-value. Index each null by $\ell=0,1,2,3$ according to the intervals $(c,1]$, $(b,c]$, $(a,b]$, $[0,a]$. Enumerating the four possible alternative bins by the BH rank rule gives the following exact envelope:

| $e(\ell_1,\ell_2)$ | 0 | 1 | 2 | 3 |
|---|---:|---:|---:|---:|
| 0 | 0 | 0 | $1/2$ | 1 |
| 1 | 0 | $2/3$ | $2/3$ | 1 |
| 2 | $1/2$ | $2/3$ | 1 | 1 |
| 3 | 1 | 1 | 1 | 1 |

Each row and column is nondecreasing. Thus this envelope, unlike the actual mixed-label FDP, is coordinatewise nondecreasing in the two test statistics. Coupling their noises proves that its expectation is largest at zero null means, even when the original null means are negative or infinite. The alternative was removed by a pointwise supremum, so no assumption on its mean or correlation was used in this envelope reduction.

Write $Q_\rho(s,t)$ for $\mathbb P(X\geq z(s),Y\geq z(t))$ for centered unit-variance bivariate Gaussian variables of correlation $\rho\in[-1,1]$, with the singular endpoints defined by continuity. Taking the two-dimensional finite differences of the displayed table gives the universal bound
$$
\begin{aligned}
\operatorname{FDR}_{|J|=2}\leq U(\rho):={}&q+\frac23Q_\rho(c,c)-Q_\rho(c,b)-\frac13Q_\rho(c,a)\\
&+\frac13Q_\rho(b,b)-\frac23Q_\rho(b,a).
\end{aligned}
\tag{P4}
$$
This is a reduction to a one-dimensional correlation supremum, not a claim that $U\leq q$. In fact the exploratory values below suggest $\sup U>q$.

A further rigorous factor-specific loss is available when the two nulls have negative correlation. The opposite signs of their loadings guarantee that at least one of them, say $i$, has nonnegative covariance with the alternative. On $\{p_i\leq a,p_{\mathrm{alt}}\leq b\}$ the envelope equals 1 and BH rejects the alternative: its rank is at least 2. Its actual FDP is at most $2/3$. Hence
$$
\mathbb E e-\operatorname{FDR}\geq\frac13\mathbb P(p_i\leq a,p_{\mathrm{alt}}\leq b)
\geq\frac b3\mathbb P(p_i\leq a).
\tag{P5}
$$
The last inequality follows by nonnegative bivariate Gaussian association and the permitted alternative mean $\theta_{\mathrm{alt}}\geq0$. For completeness, association here follows by differentiating a bivariate Gaussian upper rectangle in its correlation: its derivative is the positive bivariate density at the two endpoints, so its probability is at least the product of its marginals for nonnegative correlation; singular cases follow by continuity. This argument retains each actual negative null mean.

**Completion of the mixed-label factor bound at $q=1/64$.** Put $t=q/3=1/192$. For centered nulls, the three p-value intervals $D_1=(2t,3t]$, $D_2=(t,2t]$, $D_3=[0,t]$ each have Gaussian marginal probability $t$. Subtract the single-coordinate contributions $g_0(p)=\tfrac12\mathbf1_{p\leq t}+\tfrac12\mathbf1_{p\leq2t}$ from the table. Its remaining joint expectation is
$$
\begin{aligned}
L(\rho):=U(\rho)-q={}&\frac23\mathbb P(D_1,D_1)
+\frac16\{\mathbb P(D_1,D_2)+\mathbb P(D_2,D_1)\}\\
&-\frac12\{\mathbb P(D_2,D_3)+\mathbb P(D_3,D_2)\}
-\mathbb P(D_3,D_3).
\end{aligned}
\tag{P13}
$$
Here $\mathbb P(D_j,D_k)$ means the joint event that the first and second null p-values fall in those intervals.

First suppose $0\leq\rho<1$. A test-statistic interval $I=[h,k]$ on the positive half-axis with Gaussian measure $t$ has self-joint probability at most $Q_\rho(t,t)$. To prove this, increase $h$ and choose $k(h)$ with $\Phi(k)-\Phi(h)=t$. The derivative of $H(h)=\mathbb P(X,Y\in I)$ is
$$
H'(h)=2\phi(h)\{\mathbb P(Y\in I\mid X=k)-\mathbb P(Y\in I\mid X=h)\}\geq0.
$$
Both conditional normals have variance $1-\rho^2$, and the first mean is closer to the interval midpoint $m=(h+k)/2$, because
$$
(m-\rho k)^2-(m-\rho h)^2=\rho(k-h)(\rho-1)(h+k)\leq0.
$$
The probability that a fixed-variance normal hits a fixed interval decreases with the distance of its mean from its midpoint; differentiating its two endpoint CDFs proves this directly. Sending $h$ to $z(t)$ and $k$ to infinity proves the self-joint assertion. For two possibly different positive intervals $I,J$ of measure $t$, use $X=\sqrt\rho Z+\sqrt{1-\rho}\varepsilon_1$, $Y=\sqrt\rho Z+\sqrt{1-\rho}\varepsilon_2$ and conditional Cauchy--Schwarz to obtain
$$
\mathbb P(X\in I,Y\in J)
\leq\sqrt{\mathbb P(X\in I,Y\in I)\mathbb P(X\in J,Y\in J)}
\leq Q_\rho(t,t).
$$
The intervals in test-statistic space corresponding to the $D_j$ all lie on the positive half-axis, and $D_3$ is already the upper half-line. Thus the positive terms in (P13), whose coefficients sum to one, total at most $Q_\rho(t,t)$; its last negative term is exactly $-Q_\rho(t,t)$. Hence $U(\rho)\leq q$ for nonnegative correlation, including $\rho=1$ by continuity. The envelope's monotonicity gives the same bound for the actual negative null means without any condition on the alternative dependence.

For $\rho=-r<0$, the centered Gaussian p-value copula density, at $x=z(p_1),y=z(p_2)>0$, is
$$
c_{-r}(p_1,p_2)=\frac1{\sqrt{1-r^2}}
\exp\left\{-\frac{2rxy+r^2(x^2+y^2)}{2(1-r^2)}\right\}.
$$
On $0<p_1,p_2\leq q$, $x,y\geq u=z(q)>2.1$, and therefore
$$
c_{-r}\leq\frac1{\sqrt{1-r^2}}\exp\{-r u^2/(1-r)\}\leq1.
$$
The last majorant decreases in $r$: its log derivative is $r/(1-r^2)-u^2/(1-r)^2<0$. For $r\geq1/10$ it is at most $e^{-49/100}/\sqrt{99/100}<2/3$. Drop the negative terms in (P13); the positive rectangles each have area $t^2$ and coefficients summing to one, so $L(\rho)\leq2t^2/3$ in this range.

For $0<r\leq1/10$, restrict the negative rectangles to $p\in[t/4,2t]$, where $0<z(p)\leq z(t/4)<3.1$. There $c_{-r}\geq e^{-961/900}>17/50$. The negative square $D_3^2$ can be restricted to $[t/4,t]^2$, with area $9t^2/16$. The two negative cross rectangles can be restricted to $[t/4,t]\times(t,2t]$ and its transpose; their weighted total area is $3t^2/4$. Their combined weighted area is $21t^2/16$. The positive terms total at most $t^2$ by the density upper bound 1. Hence
$$
L(\rho)\leq\left(1-\frac{17}{50}\frac{21}{16}\right)t^2
=\frac{443}{800}t^2<\frac23t^2.
\tag{P14}
$$
The elementary strict constants $\overline\Phi(2.1)>1/64$, $\overline\Phi(3.1)<1/768$, $e^{-49/100}/\sqrt{99/100}<2/3$, and $e^{-961/900}>17/50$ were checked by the retained exact rational certificate below. Thus $U(\rho)\leq q+2t^2/3$ for every negative correlation, with $\rho=-1$ included by continuity.

To retain the negative null means in (P5), put $F_i(s)=\overline\Phi(z(s)-\theta_i)$ and $\delta_i(s)=s-F_i(s)\geq0$. The increasing normal hazard gives $\delta_i(ks)\leq k\delta_i(s)$ for $k\geq1$. Indeed, for $d=-\theta_i\geq0$ the derivative of $\log(\overline\Phi(x+d)/\overline\Phi(x))$ is nonpositive because $h(x)=\phi(x)/\overline\Phi(x)$ is increasing. Its derivative is $h(h-x)>0$: $h>x$ is immediate for $x\leq0$ and follows from $\overline\Phi(x)<\phi(x)/x$ for $x>0$.

For nonpositive correlation, positive centered thresholds, and the two actual negative means, the joint tail $Q_\theta$ satisfies
$$
0\leq Q_0(s,v)-Q_\theta(s,v)\leq v\delta_1(s)+s\delta_2(v).
\tag{P15}
$$
To prove this, raise the first centered threshold to $z(s)-\theta_1$, then the second to $z(v)-\theta_2$. At a positive conditioned coordinate, a nonpositive correlation makes the other conditional mean nonpositive and its conditional variance at most one. Its conditional upper tail is therefore at most the corresponding centered marginal tail. Integrating the two lost slabs gives (P15).

The nonsymmetric version of (P4) has negative coefficients $-1/2$ on $(c,b),(b,c)$, $-1/6$ on $(c,a),(a,c)$, and $-1/3$ on $(b,a),(a,b)$. The positive joint terms decrease under negative shifts. For each null $i$, (P15) bounds the possible increase from those negative terms by
$$
\frac{7t}{6}\delta_i(3t)+\frac{11t}{6}\delta_i(2t)+\frac{7t}{6}\delta_i(t)
\leq\frac{25t}{3}\delta_i(t).
$$
The single-coordinate contribution decreases by $\tfrac12\delta_i(t)+\tfrac12\delta_i(2t)\geq\tfrac12\delta_i(t)$. The actual envelope expectation $U_\theta$ consequently obeys
$$
U_\theta\leq U(\rho)-\kappa(\delta_1(t)+\delta_2(t)),
\qquad\kappa=\frac12-\frac{25t}{3}>\frac{2t}{3}.
$$
Choose the null $i$ with nonnegative alternative covariance and apply (P5). Since $b/3=2t/3$, it gives
$$
\begin{aligned}
\operatorname{FDR}
&\leq U(\rho)-\kappa(\delta_1(t)+\delta_2(t))
-\frac{2t}{3}(t-\delta_i(t))\\
&\leq U(\rho)-\frac23t^2\leq q.
\end{aligned}
\tag{P16}
$$
First proving these inequalities for finite means and $-1<\rho<0$, then applying the established compactification continuity, includes zero-labelled alternatives, infinite means, and singular endpoints. Thus every two-null one-factor model at $N=3,q=1/64$ has FDR at most $q$. Along with (P3) and the empty-null case, this controls all mixed-label factor cases.

For three nulls only, FDP equals $\mathbf1\{R>0\}$. The BH rejection event is coordinatewise nondecreasing in the test statistics, since every condition $p_{(k)}\leq qk/3$ is preserved by decreasing any p-value. Coupling with the same noise therefore makes zero null means optimal for this all-null problem, at every covariance. This argument is limited to the all-null rejection event and proves no mixed-null mean monotonicity.

### 4. All-null pair/triple formula and a singular-boundary warning

For centered all-null $N=3$, let $Q_{ij}(s,t)$ and $Q_{123}(s,t,v)$ denote upper Gaussian rectangle probabilities with the indicated marginal p-value thresholds and the actual covariance submatrix. A three-dimensional finite-difference expansion of the rejection event in (P1) gives
$$
H_{3,[3]}=q+\sum_{i<j}d(\rho_{ij})+\mathcal T,
\qquad d(\rho)=Q_\rho(b,b)-2Q_\rho(a,b),
\tag{P6}
$$
where
$$
\begin{aligned}
\mathcal T={}&Q_{123}(c,c,c)
-\sum_{\mathrm{distinct\ placements}}Q_{123}(a,c,c)\\
&-\sum_{\mathrm{distinct\ placements}}Q_{123}(c,b,b)
+\sum_{\mathrm{six\ permutations}}Q_{123}(a,b,c).
\end{aligned}
\tag{P7}
$$
Each of the first two sums has three terms. This identity includes the rank-three event and is valid at singular covariance. Under independence each pair correction and the triple remainder are zero, so its centered all-null FDR is exactly $q$. Together with (P3), (P16), and all-null mean monotonicity, this proves the complete factor-label reduction at the first gate:
$$
A_3(1/64)=\max_{a\in[-1,1]^3}H_{3,[3]}(1/64;0,C(a)).
\tag{P17}
$$
The centered equicorrelation $-1/2$ triangle has $T_1+T_2+T_3=0$, so all triple terms vanish, but this alone gives no comparison with the factor maximum.

The tempting shortcut $\mathcal T\leq0$ for every signed factor is false. The following singular boundary must remain in any whole-factor upper bound. Take factor loadings $(\rho,1,1)$, so $T_2=T_3=Z$ and $T_1=\rho Z+\sqrt{1-\rho^2}\varepsilon$. Enumerating whether the duplicate pair or the singleton is first rejected gives exactly
$$
H_{\mathrm{dup}}(\rho)=q+Q_\rho(c,c)-Q_\rho(a,c)-Q_\rho(b,c).
\tag{P8}
$$
Its positive edge has $d(1)=b-2a=0$, so its triple remainder is
$$
\mathcal T_{\mathrm{dup}}(\rho)
=Q_\rho(c,c)-Q_\rho(b,c)-Q_\rho(a,c)-2Q_\rho(b,b)+4Q_\rho(a,b).
\tag{P9}
$$
It is zero at $\rho=0$. To see strictly positive remainders without trusting quadrature, differentiate a bivariate rectangle at independence. If $A=\phi(z(a))$, $B=\phi(z(b))$, and $C=\phi(z(c))$, differentiation of the Gaussian density followed by integration by parts gives
$$
\frac{d}{d\rho}Q_\rho(s,t)=\phi_2(z(s),z(t);\rho),
\qquad
\mathcal T_{\mathrm{dup}}'(0)=C^2-C(A+B)-2B^2+4AB.
\tag{P10}
$$
Here $\phi_2$ denotes the centered bivariate unit-variance Gaussian density. For $q=1/64$, rational interval arithmetic gives
$$
\begin{gathered}
0.01499489152<A<0.01499489153,\\
0.02761823555<B<0.02761823556,\\
0.03922164045<C<0.03922164046,
\end{gathered}
$$
and direct interval substitution in (P10) gives
$$
-2.023756723\cdot10^{-6}<\mathcal T_{\mathrm{dup}}'(0)<-2.023751918\cdot10^{-6}.
\tag{P11}
$$
These intervals are reproducible with exact rational alternating-series bounds: use Machin's formula $\pi=16\arctan(1/5)-4\arctan(1/239)$, bounding each arctangent by successive 100-term partial sums; bracket $1/\sqrt{2\pi}$ by rational square comparisons; bracket each quantile in $(2,3)$ by rational bisection using
$$
\frac12-\overline\Phi(x)
=\frac1{\sqrt{2\pi}}\sum_{n=0}^{\infty}\frac{(-1)^n x^{2n+1}}{2^n n!(2n+1)};
$$
and bound $e^{-x^2/2}$ by its alternating series. For $2<x<3$, both series have decreasing terms after finitely many initial terms, so successive partial sums after term 100 bound their sums with the next term as remainder. All decimal endpoints displayed above are rationals, not rounded floating-point claims.

There is also an explicit nonzero parameter. For $|\rho|\leq1/100$ and $2<x,y<3$, differentiating the explicit density gives
$$
|\partial_\rho\log\phi_2(x,y;\rho)|<10,\qquad \phi_2(x,y;\rho)<1/5.
$$
Indeed, the log derivative is $\rho/(1-\rho^2)+[xy(1+\rho^2)-\rho(x^2+y^2)]/(1-\rho^2)^2$, whose absolute value is below 10 on this box; the density bound follows already from its prefactor. Thus $|Q_\rho''(s,t)|<2$ for these thresholds. The absolute coefficients in (P9) sum to 9, giving $|\mathcal T_{\mathrm{dup}}''|<18$. Taylor's theorem and (P11), with $h=10^{-7}$, now give
$$
\mathcal T_{\mathrm{dup}}(-h)
\geq h(2.023751918\cdot10^{-6})-9h^2
>1.12\cdot10^{-13}>0.
\tag{P12}
$$
This is a counterexample to the auxiliary nonpositive-triple-remainder shortcut only. It neither refutes (E) nor implies any violation of the target upper bound.

### 5. Retained exploratory diagnostics, not extremal certificates

Non-interactive SSH authentication was first checked read-only using the user-authorized alias `ucd-pkbh`: it resolved to host `pkbhattacharya.ucdavis.edu`, user `mingshuo`; Python 3.8.0, SciPy 1.10.1, and NumPy 1.24.4 were available. All substantial diagnostics ran in the new isolated remote directory `/home/mingshuo/remote/lihua_joint_extremum_20261104_1010`, with one CPU process per script, `OPENBLAS_NUM_THREADS=1`, and `OMP_NUM_THREADS=1`; no cleanup or deletion was performed. The retained files are `explore_gate.py` / `explore_gate.log`, `explore_remainder.py` / `explore_remainder.log`, and `explore_duplicate.py` / `explore_duplicate.log`.

The scripts use double-precision adaptive quadrature on $Z\in[-10,10]$, whose omitted Gaussian probability is at most $2\overline\Phi(10)$, and SciPy multivariate-normal integration with 100000 requested points and $10^{-10}$ requested absolute tolerance for the exploratory triangle values. These quadrature tolerances are not interval error certificates. Differential evolution used seed $648+|J|$, population multiplier 6, at most 30 iterations, one worker, and subsequent floating-point polishing. The mixed-label search boxes were null means in $[-3,0]$ and alternative means in $[0,7]$; those boxes do not cover all means and were not used for an upper bound.

At $q=1/64$, the retained exploratory outputs include:

| Case | Exploratory value |
|---|---:|
| Centered all-null equicorrelation triangle, $\rho=-0.1$ | $0.0156348057552$ |
| Centered all-null factor loadings $(1,-0.1,-0.1)$ | $0.0156308529885$ |
| Duplicate-boundary search in (P8), $\rho\simeq-0.135855$ | $0.0156325368503$ |
| Two-null envelope search in (P4), $\rho\simeq-0.313624$ | $0.0156258344665$ |

In particular, the duplicate boundary exceeds the initial sampled factor values; omitting it would understate even the known factor lower bound. None of these rows certifies a maximum. A negative triangle's sign pattern, a candidate larger than sampled factors, or the values of $U$ cannot establish a strict gap against the entire $A_3(1/64)$.

The retained script SHA-256 hashes are respectively `278d56c43802fb6d56bd52772062c22fbc68d49b6d31571214d42ed90a6f9cc7`, `1f827022f833d4b3722322f69d700a75622bc710ae01ce813c8d770ff966d7c9`, and `57b5195d5859ced4252b243a17282e153c83e8180ea739ca38883cddcc2a766b`. Local computation was limited to short exact rational bin-enumeration and series checks. The complete rational certificate was retained as `/private/tmp/lihua_joint_extremum_rational_certificate_20261104_1040.py` and its `.log`, SHA-256 `55c07c94e152e73b962bf3d7030cad4eef5ad0f57ffb77f15493c5082fde960f`; it ran in under one second. It checks the quantile/density brackets, the strict derivative interval, the explicit Taylor counterexample, and every numerical constant in the mixed-label argument using exact `Fraction` comparisons. No source PDF, manuscript, definition, approval record, or loop state was edited.

### 6. Direct all-null bound for nonnegative Gaussian correlations

Take centered all-null Gaussian statistics, any finite $N$, and $\Sigma_{ij}\geq0$ for $i\ne j$. Put $t_r=qr/N$. Force coordinate $i$'s p-value to zero and denote the resulting BH rank by $R_i\geq1$. The exact deterministic identity is
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
=\frac{\mathbf1\{p_i\leq t_{R_i}\}}{R_i}.
$$
Decreasing an already rejected p-value to zero changes no qualifying rank above the current rank: that coordinate was already below every larger rank threshold. Conversely, if $p_i\leq t_{R_i}$, restoring it leaves at least $R_i$ p-values below $t_{R_i}$, while increasing a p-value cannot increase the rank. Thus the rejection events and their ranks agree.

Conditional on $T_i=x$, couple the other statistics as $T_j=\Sigma_{ji}x+Y_j$, with centered Gaussian residual covariance $\Sigma_{-i,-i}-\Sigma_{-i,i}\Sigma_{i,-i}$ independent of $x$. This covariance may be singular. Nonnegative coefficients and monotonicity of forced-zero BH rank imply that $g_{ir}(u)=\mathbb P(R_i\geq r\mid p_i=u)$ is nonincreasing in $u$. The centered marginal p-value is uniform, so
$$
H_{ir}(v):=\mathbb P(R_i\geq r\mid p_i\leq v)
=\frac1v\int_0^v g_{ir}(u)\,du
$$
is nonincreasing in $v>0$. With $H_{i,N+1}=0$ and $H_{i1}=1$, the identity gives
$$
\begin{aligned}
\mathbb E\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
&=\sum_{r=1}^N\frac{\mathbb P(p_i\leq t_r,R_i=r)}r\\
&=\frac qN\sum_{r=1}^N\{H_{ir}(t_r)-H_{i,r+1}(t_r)\}\\
&=\frac qN\left[1+\sum_{r=2}^N\{H_{ir}(t_r)-H_{ir}(t_{r-1})\}\right]\leq\frac qN.
\end{aligned}
$$
Summing proves FDR $\leq q$, including singular covariance. The established all-null coupling extends this to nonpositive all-null means. Thus every same-sign factor model is bounded by $q$. As a short deterministic check, all 375 coordinate cases formed from $p\in\{0,q/3,2q/3,q,1\}^3$ satisfied the forced-zero identity in exact rational arithmetic; the argument above proves the identity for all p-value vectors.

### 7. Proved reduction of the complete factor cube to its star boundary

Fix $N=3,q=1/64$ and centered all-null statistics. Up to permutation and simultaneous reversal of all loading signs, every factor model with nonzero mixed-sign loadings has covariance
$$
\Sigma(r,s,\zeta)=
\begin{pmatrix}1&-r&-s\\-r&1&\zeta\\-s&\zeta&1\end{pmatrix},
\qquad r,s>0,\quad rs\leq\zeta\leq\min(r/s,s/r).
\tag{P18}
$$
Indeed its squared loadings are $rs/\zeta,r\zeta/s,s\zeta/r$. Write $F(\zeta)$ for its rejection probability at fixed $r,s$. We prove that its maximum on this interval is at an endpoint. An interval reduced to a point is immediate; otherwise $r,s<1$ and its interior has $\zeta<1$ and positive-definite covariance.

Put $A=z(q/3)$, $B=z(2q/3)$, $C=z(q)$; these are statistic thresholds, distinct from the earlier density letters. At the corner $T_2=U,T_3=V$, the conditional mean and variance of $T_1$ are
$$
\mu=-\frac{(r+s)(U+V)}{2(1+\zeta)}
     -\frac{(r-s)(U-V)}{2(1-\zeta)},\qquad
v=1-\frac{(r+s)^2}{2(1+\zeta)}
    -\frac{(r-s)^2}{2(1-\zeta)}.
$$
The factor constraints imply $r-\zeta s,s-\zeta r\geq0$ and $|r-s|/(r+s)\leq(1-\zeta)/(1+\zeta)$. Consequently $\mu=-\{(r-\zeta s)U+(s-\zeta r)V\}/(1-\zeta^2)\leq0$ at positive corners and $0\leq v'\leq1/(1+\zeta)$. The latter upper bound also uses $v\geq0$, hence $(r+s)^2/\{2(1+\zeta)\}\leq1$. Define $H_\tau(U,V)=\overline\Phi((\tau-\mu)/\sqrt v)$, so $0\leq H_\tau\leq\overline\Phi(\tau)$ for $\tau\in\{A,B,C\}$.

Let $\phi_{UV}=\phi_2(U,V;\zeta)$ and
$$
R_{UV}=\frac{\phi_{UV}}{\phi_{BB}}
=\exp\left\{\frac{K_{UV}}{1+\zeta}-\frac{J_{UV}}{1-\zeta}\right\},
\quad K_{UV}=B^2-\frac{(U+V)^2}{4},\quad J_{UV}=\frac{(U-V)^2}{4}.
$$
For a statistic upper rectangle $\Gamma(\tau,U,V)$, Gaussian differentiation gives $\partial_\zeta\Gamma=\phi_{UV}H_\tau(U,V)$. Applying this identity to every actual term of (P6)--(P7) gives $F'(\zeta)/\phi_{BB}=D=1-2R_{AB}+E$, with
$$
\begin{aligned}
E={}&-H_C(B,B)+R_{AB}\{H_C(A,B)+H_C(B,A)\}\\
&+R_{CC}(H_C-H_A)(C,C)\\
&-R_{AC}\{(H_C-H_B)(A,C)+(H_C-H_B)(C,A)\}\\
&-R_{BC}\{(H_B-H_A)(B,C)+(H_B-H_A)(C,B)\}.
\end{aligned}
\tag{P19}
$$
This includes the entire triple remainder and assumes no sign for it.

The strict rational bounds $2.5616<A<2.5618$, $2.3109<B<2.3111$, $2.1538<C<2.1540$, and $\phi(C)<0.04$ suffice. Put $\delta=A-B$ and
$$
f(\zeta)=\frac{\delta B}{1+\zeta}+\frac{\delta^2}{2(1-\zeta^2)},\qquad R_{AB}=e^{-f}.
$$
Direct differentiation gives $f''>0$. On $0\leq\zeta\leq0.95$, its two endpoint values are below $0.63$, so $R_{AB}>0.53$, while $R_{CC}<e^{0.71}<2.1$. Keeping only positive terms in (P19) gives
$$
D\leq1-2(1-q)R_{AB}+qR_{CC}
<1-2(1-q)0.53+2.1q=-0.010625.
$$
On $\zeta\geq0.97$, $f'>0$ and $R_{AB}<0.44$; the decreasing ratios $R_{AC},R_{BC}$ are respectively below $0.23,1$. With $b=2q/3$, dropping only nonnegative terms gives
$$
D\geq1-q-2R_{AB}-2qR_{AC}-2bR_{BC}
>1-q-0.88-0.46q-2b>0.076354.
$$
On $0.95\leq\zeta\leq0.97$, the following bounds hold, and also $R_{AB}>0.43$ and $6<f'<18$:

| Ratio | Upper bound | Absolute derivative upper bound |
|---|---:|---:|
| $R_{AB}$ | $0.55$ | $9.9$ |
| $R_{CC}$ | $1.5$ | $0.281$ |
| $R_{AC}$ | $0.4$ | $18.8$ |
| $R_{BC}$ | $1.1$ | $7.81$ |

The conditional means obey
$$
|\mu'|\leq\frac{U+V}{(1+\zeta)^2}+\frac{|U-V|}{1-\zeta^2},\qquad v'<0.513.
$$
For $w=\tau-\mu\geq C$ and $0<v\leq1$, differentiation in $w,v$, using $C^2>3$, proves
$$
\frac{\phi(w/\sqrt v)}{\sqrt v}\leq\phi(C),\qquad
\frac{w\phi(w/\sqrt v)}{v^{3/2}}\leq C\phi(C).
$$
Hence $|H_\tau'|\leq0.04(|\mu'|+0.553)$. At corners $BB,AB,CC,AC,BC$, respectively, this is strictly below $0.071,0.244,0.068,0.349,0.177$, uniformly in $\tau\in\{A,B,C\}$; reversed corners have the same bounds. Differentiate the complete expression (P19), bound each difference derivative by the sum of its two bounds, and use $H_C\leq q,H_B\leq b$:
$$
\begin{aligned}
|E'|<&\,0.071+2(0.55)(0.244)+1.5(2)(0.068)\\
&+2(0.4)(2)(0.349)+2(1.1)(2)(0.177)\\
&+2q(9.9)+q(0.281)+2q(18.8)+2b(7.81)\\
=&\,\frac{2826791}{960000}<2.944574.
\end{aligned}
$$
But $(1-2R_{AB})'=2R_{AB}f'>5.16$, so $D'>2.21$ on the middle strip. The two outer signs and the middle derivative show that $D$ changes sign at most once, only from negative to positive. Since $\phi_{BB}>0$, $F$ is monotone or first decreases and then increases on any feasible interval. Its maximum is therefore at an endpoint.

At $\zeta=rs$ the first loading has absolute value one; at $\zeta=\min(r/s,s/r)$ the second or third does. Singular endpoints follow by the established Gaussian-probability continuity. Models with a zero loading are limits of nonzero models, and compactness of the star boundary preserves the upper comparison along a subsequence. Same-sign models have FDR $\leq q$ by subsection 6, and the star model $(1,0,0)$ has independent statistics and FDR $q$. Permutation and simultaneous sign reversal now prove the exact reduction
$$
A_3(1/64)=\max_{(\beta,\gamma)\in[-1,1]^2}
H_{3,[3]}(1/64;0,C(1,\beta,\gamma)).
\tag{P20}
$$
Every factor label/mean boundary was already included by (P17). This proves a dimension reduction, rather than an evaluation of this maximum or a comparison with $M_3$.

All new constants were independently checked using exact rational arithmetic in /private/tmp/lihua_onefactor_star_reduction_certificate_20261104.py and its .log, SHA-256 e73f7badb021740fe700293b7c9dd31b18f5022177bf34ed1857695a082140dd; runtime was about $0.06$ seconds. The script independently brackets the three quantiles by Machin/alternating-series bounds and checks every outer sign, middle ratio/derivative bound, conditional-tail derivative, and the exact $E'$ coefficient. Its coarse inputs include
$$
0<K_{CC}<0.71,\quad -0.23<K_{AC}<-0.217,\quad
0.0415<J_{AC}<0.0417,\quad
0<K_{BC}<0.36,\quad0.00615<J_{BC}<0.00625.
$$
For exponential comparisons it sums the first 30 nonnegative terms of $e^t$, bounds the remaining tail by $t^{30}/\{30!(1-t/31)\}$ for $0\leq t<2$, and takes reciprocals for negative arguments. The constants are strict rational certificates, rather than quadrature tolerances. This continuation launched no remote computation.

### 8. A rigorous parameter-box envelope for the remaining two-dimensional problem

Take the star representation $T_1=Z$, $T_2=\beta Z+\sqrt{1-\beta^2}\varepsilon_2$, $T_3=\gamma Z+\sqrt{1-\gamma^2}\varepsilon_3$. Given $Z=z$, the last two coordinates are independent. For $h_k=z(qk/3)>0$ define
$$
F_k(v,z)=\overline\Phi\left(\frac{h_k-vz}{\sqrt{1-v^2}}\right)\quad(|v|<1),
\qquad F_k(\pm1,z)=\mathbf1\{\pm z\geq h_k\}.
$$
Its interior derivative is
$$
\partial_vF_k(v,z)=
\phi\left(\frac{h_k-vz}{\sqrt{1-v^2}}\right)
\frac{z-vh_k}{(1-v^2)^{3/2}}.
$$
Thus, for a closed loading interval $I$, the supremum $\overline F_k^I(z)=\sup_{v\in I}F_k(v,z)$ is obtained from its endpoints and the possible critical point $v=z/h_k\in I\cap(-1,1)$. Include deterministic endpoints explicitly, including threshold equality. The three suprema are nondecreasing in $k$, so define a valid four-bin distribution with probabilities $\overline\pi_k^I(z)$.

Let $b_1(z)$ be the bin of $\overline\Phi(z)$. For a parameter rectangle $I\times J$ put
$$
\overline\Psi_{I,J}(z)=\sum_{k,l=1}^4
w_{[3]}(b_1(z),k,l)\overline\pi_k^I(z)\overline\pi_l^J(z).
$$
The all-null rejection event is coordinatewise monotone. Quantile coupling of independent bin variables with the dominating CDFs proves, simultaneously for every $(\beta,\gamma)\in I\times J$,
$$
H_{3,[3]}(1/64;0,C(1,\beta,\gamma))
\leq\int_{\mathbb R}\phi(z)\overline\Psi_{I,J}(z)\,dz.
\tag{P21}
$$
The right side decreases when either parameter interval is refined. Truncation to $[-L,L]$ costs at most $2\overline\Phi(L)$ since $0\leq\overline\Psi\leq1$. Split the finite integral at $A,B,C$, where the fixed coordinate changes bin, and at the endpoint/critical-point switches $z=v h_k$. With rigorously bounded integration and tail errors, (P21) is a valid branch upper bound covering the entire loading square. No integration or branch certificate implementing it has yet been produced; the pointwise CDF envelopes alone do not evaluate the integral.

### 9. Remaining obligation before the next continuation

The next execution must complete the first gate itself: either prove $M_3(1/64)=A_3(1/64)$ analytically, or provide a certified full-model lower bound strictly above a certified upper bound for the whole factor class. The exact factor optimization is now the two-dimensional compact square in (P20), with all means, labels, and singular faces included. The next concrete task is to implement and certify the one-dimensional integrals in (P21) and an exhaustive two-dimensional branch cover, retaining tail errors and all boundary boxes. The duplicate boundary must remain. A nonfactor lower bound must also be certified; the retained negative-triangle decimal is still exploratory.

The full-model side is not claimed to have the same label reduction: a certified nonfactor lower bound suffices for a strict-gap route, whereas a proof of equality must still control all unrestricted means and labels. No endpoint KKT argument or integrated-corner estimate has been assumed. The $N=4$ screening and general reduction remain downstream of the unresolved finite gate. Failure of a future exact reduction would concern the stronger auxiliary (E), not the original $q\sqrt{\log(1/q)}$ target.

### 10. A certified full-model lower bound

The next continuation, still on 2026-11-04, supplies a strict lower bound for the centered all-null negative triangle. This supersedes the last sentence about its merely exploratory value in subsection 9. It does not yet supply the missing upper bound for the entire factor class.

Let $F(r)$ denote its FDR when every off-diagonal covariance is $r$, for $-1/10\leq r\leq0$. Its covariance eigenvalues are $1-r,1-r,1+2r$, all positive. Retain $A=z(q/3),B=z(2q/3),C=z(q)$ and $q=1/64$. The complete Plackett formula (P19), with the conditional corners specialized to this path, gives
$$
F'(r)=3\mathcal B(r),\qquad
F(-1/10)=q-3\int_{-1/10}^0\mathcal B(r)\,dr.
\tag{P22}
$$
Here the factor 3 differentiates all three edges, not just one. To make the endpoint derivative explicit, put
$$
H_t(U,V;r)=\overline\Phi\!\left(
\frac{t-r(U+V)/(1+r)}{\sqrt{1-2r^2/(1+r)}}\right),\qquad
\phi_{UV}(r)=\phi_2(U,V;r).
$$
Symmetry of the conditional law in its two corner arguments gives
$$
\begin{aligned}
\mathcal B={}&\phi_{BB}-2\phi_{AB}-\phi_{BB}H_C(B,B)
+2\phi_{AB}H_C(A,B)\\
&+\phi_{CC}(H_C-H_A)(C,C)
-2\phi_{AC}(H_C-H_B)(A,C)
-2\phi_{BC}(H_B-H_A)(B,C).
\end{aligned}
$$
Thus all rank-three terms are retained. Independence gives $F(0)=q$ directly from (P6)--(P7).

An independent worker supplied an exact-rational certificate; the executing worker read its complete code, its derivative estimates, and the saved log. The numerical inputs are certified by the Machin/arctangent and alternating Gaussian-integral method already described in subsection 4:
$$
\begin{gathered}
2.561681934933<A<2.561681934935,\\
2.310991338256<B<2.310991338259,\\
2.153874694060<C<2.153874694063.
\end{gathered}
$$
Each midpoint value of $\mathcal B$ is enclosed using exact `Fraction` arithmetic, rational square-root brackets, and exponential series with a positive geometric tail bound. There is no floating-point normal-CDF or quadrature oracle in this certificate.

The following analytic bounds justify its quadrature error. For $r\in[-1/10,0]$ and $U,V,t\in\{A,B,C\}\subset(2.15,3)$, write $L=\log\phi_{UV}$. The explicit bivariate density gives
$$
\phi_{UV}<0.002,\quad |L'|<12,\quad |L''|<26,
\quad |\phi_{UV}'|<0.024,\quad |\phi_{UV}''|<0.34.
$$
For example its exponent is at least $2.15^2>4.6$ on this negative-correlation range, its prefactor is below $0.17$, and $e^{4.6}>85$. Bounding the differentiated rational exponent gives the displayed logarithmic derivative bounds; the code checks the resulting rational inequalities. For the conditional mean $\mu=r(U+V)/(1+r)$ and variance $v=1-2r^2/(1+r)$,
$$
\begin{gathered}
v>0.97,\quad \sqrt v>0.98,\quad -2/3\leq\mu\leq0,\\
|\mu'|<7.41,\quad |\mu''|<16.47,\quad
0\leq v'<0.47,\quad |v''|<5.49.
\end{gathered}
$$
Consequently $w=(t-\mu)/\sqrt v$ satisfies $2<w<4$, $|w'|<8.5$, and $|w''|<33$. Since $\phi(w)<0.055$ and $w\phi(w)<0.11$ for $w\geq2$, every conditional tail has
$$
0\leq H_t\leq q<0.016,\qquad |H_t'|<0.5,\qquad |H_t''|<10.
$$
A positive difference of two such tails is at most $q$, and its first and second derivative absolute bounds are 1 and 20. Applying the product rule to the complete expression for $\mathcal B$ therefore yields
$$
\begin{aligned}
|\mathcal B''|<&\;3(0.34)
+3\{0.34(0.016)+2(0.024)(0.5)+0.002(10)\}\\
&+5\{0.34(0.016)+2(0.024)(1)+0.002(20)\}
=1.63552<2.
\end{aligned}
$$
These are derivatives along the full one-dimensional equicorrelation path, including the two conditioning correlations.

For the composite midpoint rule with 32 equal cells, length $1/10$, and the factor 3 in (P22), the FDR error is at most
$$
\frac{3(1/10)^3(2)}{24\cdot32^2}
=\frac1{4096000}.
$$
Combining this error with the rational midpoint enclosures gives the following outward-rounded bounds, whose comparison with the threshold is also checked as an exact rational inequality:
$$
0.01563456094228375186
\leq F(-1/10)\leq
0.01563504922353886641,
\qquad F(-1/10)>0.0156344.
\tag{P23}
$$
The retained certificate is `/private/tmp/lihua_negative_triangle_certificate_20261104_v1.py`, SHA-256 `dc65165078a3ea2f69ce31bf01a964ec07a9af1dd9cfbfaba179ed0cc9ce5211`; its `.log` has SHA-256 `2a6d764ca4db2c1732325e075cb596fd09fd396839fdcd6d1afdea311aabe61c`. Its short exact calculation took about 49 seconds. This is an admissible full-model lower bound, with no optimization claim.

### 11. Certified supremum of the negative pair correction

The same independent worker supplied a second exact-rational certificate for $d$ from (P6). For $-1<\rho<1$ the bivariate Plackett identity gives
$$
d'(\rho)=\phi_2(B,B;\rho)-2\phi_2(A,B;\rho)
=\phi_2(B,B;\rho)\{1-2e^{-f(\rho)}\},
$$
where, with $\delta=A-B>0$,
$$
f(\rho)=\frac{\delta B}{1+\rho}
+\frac{\delta^2}{2(1-\rho^2)},\qquad
f'(\rho)=-\frac{\delta B}{(1+\rho)^2}
+\frac{\delta^2\rho}{(1-\rho^2)^2}<0
\quad(-1<\rho<0).
$$
Since $f(-1+)=+\infty$, $d(-1)=d(0)=0$, and exact exponential bounds give
$$
e^{f(-0.123846)}>2>e^{f(-0.123845)},
$$
there is exactly one critical point on $(-1,0)$, it is the global maximum, and it lies in this bracket. In particular this covers the entire negative-correlation interval, including the singular endpoint by continuity.

On $[-1/8,0]$ the same density calculation with the slightly weaker estimates $|L'|<13$, $|L''|<29$, $\phi_{UV}<0.002$ gives $|\phi_{UV}''|<0.4$, and hence $|d'''|<6/5$. A 32-cell composite midpoint enclosure of
$$
d(-0.123846)=-\int_{-0.123846}^{0}d'(\rho)\,d\rho
$$
has error at most $1/10485760$; here its interval length is less than $1/8$. Also $|d'|<0.006$, so moving from the bracket's left endpoint to the maximizer costs less than $0.006\cdot10^{-6}=6\cdot10^{-9}$. All midpoint values, input quantiles, and the strict root bracket are enclosed by exact rational arithmetic. The outward-rounded result is
$$
\sup_{-1\leq\rho\leq0}d(\rho)
\leq0.00000344875897091133<0.000004.
\tag{P24}
$$
The executing worker read the complete code and saved log and checked the normalization of both error terms. The files are `/private/tmp/lihua_negative_pair_sup_certificate_20261104_v1.py`, SHA-256 `e43339d30137344f0bd3f9dc5013a37b792779f659e0ad4489cdf0ae1a523f9d`, and its `.log`, SHA-256 `939dbc75f4ac29bac31a6b4e63412771a3996ec41c86ff244eada0526b804efd`. Its exact calculation took about 2.7 seconds.

For later use, $d(\rho)\leq0$ when $0\leq\rho\leq1$. Indeed
$$
d(\rho)=\mathbb P(B\leq X<A,\ B\leq Y<A)
-\mathbb P(X\geq A,Y\geq A).
$$
Both univariate intervals have Gaussian measure $t=q/3$. The equal-measure positive-interval argument in subsection 3 bounds the first self-joint probability by the second. It extends to $\rho=1$ by continuity.

### 12. Entire star quadrant with the center of the opposite sign

Consider the star (P20) with $\beta,\gamma\in[-1,0]$. Write, for $z\geq C$,
$$
x=F_A(\beta,z),\quad y=F_B(\beta,z)-F_A(\beta,z),\quad
w=F_C(\beta,z)-F_B(\beta,z),
$$
and write $u,v,k$ for the corresponding three quantities for $\gamma$. Here $F_h(\lambda,z)=\overline\Phi((h-\lambda z)/\sqrt{1-\lambda^2})$ with its deterministic interpretation at $\lambda=\pm1$. These quantities are conditional probabilities of the three p-value bins of marginal length $t$.

Every one of these six probabilities is at most $t$. To prove this for $\lambda=-r$, $0\leq r<1$, divide the conditional density at a statistic value $s\geq C$ by its unconditional density:
$$
\frac{\phi((s+rz)/\sqrt{1-r^2})}{\sqrt{1-r^2}\phi(s)}
=\frac1{\sqrt{1-r^2}}
\exp\left\{-\frac{2rsz+r^2(s^2+z^2)}{2(1-r^2)}\right\}
\leq\frac{e^{-rC^2/(1-r)}}{\sqrt{1-r^2}}\leq1.
$$
The last majorant starts at 1 and has negative log derivative
$r/(1-r^2)-C^2/(1-r)^2$, since $C^2>1$. Integration over each of the three positive-statistic bins proves the assertion. At $r=1$ the conditional statistic is $-z<0$, so each probability is zero. Thus both the zero loading and the zero-residual boundary are explicitly included.

Condition (P7) on the center $T_1=Z$. Its integrand vanishes for $z<C$. Direct expansion in these bin probabilities gives, on its three other intervals, respectively,
$$
\begin{array}{c|c}
\text{center interval}&\text{conditional triple integrand}\\\hline
[C,B)&yk+wv+wk\\
[B,A)&wk-xv-yu-2yv\\
[A,+\infty)&xu-yv.
\end{array}
\tag{P25}
$$
For example the first polynomial before expansion is
$(x+y+w)(u+v+k)-x(u+v+k)-(x+y+w)u-(x+y)(u+v)+x(u+v)+(x+y)u$, which is exactly $yk+wv+wk$. The other two follow from the same full (P7), retaining all its positive and negative terms. Each polynomial is multiaffine; the retained short certificate checks these three identities and the upper bounds $3,1,1$ on every vertex of $[0,1]^6$ using exact rational arithmetic.

Because $x,y,w,u,v,k\in[0,t]$, the three upper bounds in (P25) are $3t^2,t^2,t^2$. Each of the three center intervals has probability $t$. Consequently
$$
\mathcal T\leq5t^3.
$$
The two negative edges are $\beta,\gamma$, while the positive edge $\beta\gamma$ has $d(\beta\gamma)\leq0$. Equations (P6) and (P24) therefore give the strict uniform bound for this entire closed quadrant:
$$
\begin{aligned}
H_{3,[3]}(q;0,C(1,\beta,\gamma))
&\leq q+2(0.00000344875897091133)+5/192^3\\
&<0.015632604<0.0156344,
\qquad -1\leq\beta,\gamma\leq0.
\end{aligned}
\tag{P26}
$$
The exact identities and strict rational comparison are retained in `/private/tmp/lihua_star_singleton_sign_certificate_20261104_v1.py`, SHA-256 `290408ce21fe121ce9b9139aeb31e98db221d52036f266ee76b5ec5f3130a7e1`, and its `.log`, SHA-256 `76ffab425cd3c53561e0af71527e5485ccb60a954835cac20c669c92ba65088c`. This short deterministic check took less than a second. Together with subsection 6, this leaves only $0\leq\beta\leq1$, $-1\leq\gamma\leq0$, and its coordinate-swapped copy, for a complete star upper bound. The duplicate family lies on $\beta=1$ and must still be covered.

### 13. A tighter branch formula, its current implementation status, and what remains

Formula (P25) is an algebraic identity for arbitrary loading signs, even where the bin bound by $t$ is unavailable. It suggests a tighter alternative to (P21): keep the single-coordinate baseline $q$ exactly in (P6), enclose the three pair corrections separately, and integrate only the triple remainder over $z\geq C$. This avoids inflating the single-coordinate marginal terms by separate parameter-CDF suprema.

For a parameter interval and a finite $z$ interval, enclose each of the three conditional CDFs by its extrema on that rectangle. For a sign-fixed loading interval the CDF is monotone in $z$, with the loading's sign. Its minimum over the loading interval is at an endpoint; its maximum is at an endpoint or at the critical point $\lambda=z/h$ when that point belongs to the interval. These are precisely the derivative and deterministic-endpoint facts in subsection 8. Subtract the CDF enclosures to obtain valid bin probability intervals, intersecting with $[0,1]$ and, for the negative-loading coordinate on $z\geq C$, with $[0,t]$. Evaluate each positive product in (P25) at the upper endpoints and each subtracted product at the lower endpoints. Multiply by the exact Gaussian mass of the $z$ cell and sum. This is a Darboux upper bound: it has no unproved smooth quadrature remainder and it remains valid for deterministic conditional coordinates and cells crossing their threshold levels. The omitted interval $z\geq L$ costs at most $2\overline\Phi(L)$ for this triple integrand, since $|xu-yv|\leq2$ even without using the negative-loading bound. Refining either the parameter boxes or the $z$ cells decreases the corresponding interval envelopes.

Pair correction extrema on a negative-correlation interval are its endpoints and the single maximum in subsection 11. On a positive-correlation interval, $f''>0$ and $f'(0)<0$, while $f(0)<\log2$ and $f(1-)=+\infty$. Thus $d'$ changes sign exactly once there, from negative to positive, and the maximum of $d$ on a positive interval is at one of its two endpoints. Endpoint values still require certified evaluation. These facts give a rigorous scalar-extremum rule for all three pair terms in each mixed-sign star box, rather than relying on a sampled pair grid.

A new exploratory floating-point implementation of these box formulas was written as `/private/tmp/lihua_star_box_prototype_20261104_v1.py`, 3717 bytes, SHA-256 `03d2f8d01b5ba400376458ad5692745704551fae29f29df7c859320b7e0bcd1e`. It uses SciPy CDFs and pair quadrature and explicitly labels its results exploratory. It has not been executed or certified. An attempted upload to the existing isolated UC Davis directory was rejected by automatic approval review for lack of visible authorization to export that specific unpublished-code payload. No alternative export or local substantial computation was attempted. This implementation and its proposed parameter search are not evidence for an upper bound.

At that point the decisive comparison was one-sided: (P23) is a strict full-model lower bound above $0.0156344$, and (P26) excludes a whole star quadrant below that threshold. The following analytic reductions subsequently removed the need to execute the two-dimensional branch search. Its unexecuted code remains a diagnostic artifact, not a certificate.

### 14. Removing the entire low and middle positive-loading strips analytically

It remains to consider $\beta=b\in[0,1]$ and $\gamma=c\in[-1,0]$, and its coordinate-swapped copy. First suppose $0<b\leq0.95$ and $-1<c<0$. Reorder the coordinates so that the single opposite-sign coordinate comes first. Its two negative edges have magnitudes $r=-c$, $s=-bc$, and its positive edge is $\zeta=b$. Keep $r,s$ fixed. The full factor-feasible positive-edge interval (P18) has lower endpoint $rs=bc^2$ and upper endpoint $b$. The strict negative derivative already proved in (P19) holds throughout this interval, since every $\zeta\leq0.95$. Hence the FDR at the upper endpoint is at most that at the lower endpoint. The lower endpoint is the star with loadings $(1,c,bc)$ after this reordering: both other loadings are nonpositive. Therefore (P26) proves
$$
H_{3,[3]}(q;0,C(1,b,c))<0.015632604
\quad(0\leq b\leq0.95,\ -1\leq c\leq0).
\tag{P27}
$$
Cases with a zero edge or a singular endpoint follow by continuity; no division by the vanishing edge is needed there. This uses the already established *strict outer derivative sign*, not merely the weaker conclusion that the maximum is at one of two endpoints.

The whole middle strip $0.95\leq b\leq0.97$ admits a much coarser but sufficient bound. In the notation of (P25), only the negative-loading coordinate is needed to have $u,v,k\leq t$; the other coordinate has $x,y,w\geq0$ and $x+y+w\leq1$. Thus its three triple integrands obey
$$
yk+wv+wk\leq t(y+2w)\leq2t,\qquad
wk-xv-yu-2yv\leq t,\qquad xu-yv\leq t.
$$
Each center interval still has probability $t$, so on this whole signed-star domain
$$
\mathcal T\leq4t^2.
\tag{P28}
$$
There is a large negative pair correction on the middle strip. Let $X,Y$ be centered standard normals of correlation $b$, $I=[B,A)$, and $J=[A,+\infty)$. The conditional normal density has maximum at most $K/\sqrt{1-b^2}$, where $K=1/\sqrt{2\pi}<0.4$. Since $A-B<0.251$ and $\sqrt{1-0.97^2}>0.243$,
$$
\mathbb P(X,Y\in I)
\leq t\frac{(A-B)K}{\sqrt{1-b^2}}
<\frac{251}{116640}.
$$
On the other hand, integrate the bivariate Plackett identity from $b$ to the singular endpoint 1:
$$
\begin{aligned}
\mathbb P(X,Y\in J)
&=t-\int_b^1\phi_2(A,A;\rho)\,d\rho\\
&\geq t-K\phi(A)\int_b^1\frac{d\rho}{\sqrt{1-\rho^2}}
=t-K\phi(A)\arccos b\\
&>t-(0.4)(0.015)(0.32)=\frac{1973}{600000}.
\end{aligned}
$$
Here $\phi(A)<0.015$ was already certified in (P11), and $\arccos(0.95)<0.32$: the alternating cosine series gives $\cos(0.32)\leq1-0.32^2/2+0.32^4/24<0.95$. Subtracting these two uniform bounds proves $d(b)<-0.001$ for every $b\in[0.95,0.97]$. The other two pair corrections have negative correlations $c,bc$ and are each below $0.000004$ by (P24). Equations (P6) and (P28) now give
$$
H_{3,[3]}(q;0,C(1,b,c))
<q-0.001+2(0.000004)+4t^2
=\frac{2122777}{144000000}<q
\quad(0.95\leq b\leq0.97,\ -1\leq c\leq0).
\tag{P29}
$$
These are deliberately loose analytic inequalities with a large margin. All their numerical comparisons are checked with exact fractions in `/private/tmp/lihua_star_middle_strip_certificate_20261104_v1.py`, SHA-256 `0b414ef3bdc7e14e21b0388e8ed82cf8dead72d0fbd03b9ed77a3beffa59f986`; its `.log` has SHA-256 `5f3905fc22eaf162205f92d148eaa3f5fa66804473d3c348a411e4c4254fa6ce`. The calculation took less than a second.

### 15. Removing the high positive-loading strip by monotonicity toward duplicates

For $0.97\leq b<1$ and $-1<c<0$, write $\mathcal B_{ij}$ for the *endpoint* covariance derivative with respect to edge $ij$, evaluated at the star covariance with edges $(b,c,bc)$. Differentiating this exact star path gives
$$
\frac{\partial}{\partial b}H_{3,[3]}(q;0,C(1,b,c))
=\mathcal B_{12}+c\mathcal B_{23}.
\tag{P30}
$$
The first edge is positive. Reordering coordinates as in subsection 14 makes its derivative precisely the positive-edge derivative in (P19), evaluated at a factor-feasible endpoint; the pointwise derivative formula remains valid since the covariance is positive definite. Its established outer bound gives
$$
\mathcal B_{12}>0.076\,\phi_2(B,B;b)>0.076(0.04)=0.00304.
$$
For the last inequality, $\phi_2(B,B;b)$ is increasing for positive $b$. At $b=0.97$, use
$$
B^2/(1.97)<2.75,\quad e^{2.75}<16,\quad
\sqrt{1-0.97^2}<0.244,\quad 2\pi<44/7
$$
to get $\phi_2(B,B;0.97)>1/\{(44/7)(0.244)(16)\}>0.04$. The exponential bound is certified by its positive series and a geometric tail.

For completeness, the negative-edge derivative in (P30) needs no conditional-tail smallness. The general Plackett expansion for any edge has positive terms only
$$
\phi_2(B,B;\rho)(1-H_C(B,B))
+\phi_2(C,C;\rho)(H_C-H_A)(C,C).
$$
Its $AB$ terms have coefficients $H_C-1\leq0$, and its $AC$ and $BC$ terms are negatives of positive conditional-CDF differences. All conditional probabilities are in $[0,1]$, at every conditional mean and variance. At $\rho=bc\leq0$, the negative-correlation copula bound already proved on positive thresholds therefore gives
$$
\mathcal B_{23}\leq\phi_2(B,B;bc)+\phi_2(C,C;bc)
\leq\phi(B)^2+\phi(C)^2
<(0.028)^2+(0.04)^2=0.002384.
$$
Since $c\in[-1,0]$, (P30) is consequently bounded below by
$$
0.00304-0.002384=\frac{41}{62500}>0.
$$
The full FDR strictly increases in $b$ on this strip. Integrating this inequality for interior parameters and using the established compactification continuity proves
$$
H_{3,[3]}(q;0,C(1,b,c))
\leq H_{3,[3]}(q;0,C(1,1,c))
=H_{\mathrm{dup}}(c)
\quad(0.97\leq b\leq1,\ -1\leq c\leq0).
\tag{P31}
$$
This explicitly includes $b=1$, $c=-1$, $c=0$, and their duplicate or zero-residual intersections by continuity. The new rational comparisons are retained in `/private/tmp/lihua_star_duplicate_strip_certificate_20261104_v1.py`, SHA-256 `6548d2e452daa33954be87732cc2bbc056c4034680995fa753562c5f2ce9c3c2`, and its `.log`, SHA-256 `da5f314d91682ad6996f2f6bf519565c9f685ff97c06ca07bf34757ea3787863`; its exact calculation took less than a second.

Subsections 12, 14, and 15, together with the same-sign bound, cover the entire closed star square and reduce its final upper-bound obligation to the single scalar family (P8), $-1\leq c\leq0$. The following certificate completes that obligation.

### 16. Certified duplicate supremum and the strict finite-array gap

Write $H_{\mathrm{dup}}(c)=q+g(c)$, with $g(c)=Q_c(q,q)-Q_c(q/3,q)-Q_c(2q/3,q)$ as in (P8). Its derivative is
$$
g'(c)=\phi_2(C,C;c)-\phi_2(A,C;c)-\phi_2(B,C;c).
$$
For $U\in\{A,B\}$, put
$$
R_U(c)=\frac{\phi_2(U,C;c)}{\phi_2(C,C;c)}
=\exp\left\{-\frac{(U-C)C}{1+c}
-\frac{(U-C)^2}{2(1-c^2)}\right\}.
$$
The negative of this exponent has strictly negative derivative for $-1<c<0$, by the same calculation as in subsection 11. Thus $R_A+R_B$ strictly increases from zero as $c\downarrow-1$. Exact rational exponential enclosures give
$$
R_A(-0.135856)+R_B(-0.135856)<1
<R_A(-0.135854)+R_B(-0.135854).
$$
There is exactly one zero of $g'$; it changes from positive to negative and lies in this bracket. Since $g(-1)=g(0)=0$, this is the global maximum on the entire closed interval, including its singular endpoint.

On $[-3/20,0]$ the certified quantile bounds give $\phi_{UV}<0.002$, $|(\log\phi_{UV})'|<14$, and $|(\log\phi_{UV})''|<32$ for the three required corners. Hence $|\phi_{UV}''|<0.46$ and $|g'''|<3/2$. The 32-cell composite midpoint enclosure of
$$
g(-0.135856)=-\int_{-0.135856}^0g'(c)\,dc
$$
has error at most $27/131072000$, since its length is less than $3/20$. Also $|g'|<0.006$, so the root bracket of width $2\cdot10^{-6}$ costs at most $1.2\cdot10^{-8}$. All quantiles, point evaluations, square roots, exponentials, and final comparisons are enclosed with exact `Fraction` arithmetic. The resulting outward-rounded bound is
$$
\sup_{-1\leq c\leq0}H_{\mathrm{dup}}(c)
\leq0.01563275411291622882<0.0156344.
\tag{P32}
$$
An independent worker produced the certificate; the executing worker read its complete code and saved log and checked the root-sign and quadrature normalizations. The files are `/private/tmp/lihua_duplicate_sup_certificate_20261104_v1.py`, SHA-256 `ed93775db1a41eb6163609ea4188711a0689302c89c0b98607e1d46074322f1e`, and its `.log`, SHA-256 `41ee0bbf062fa9da638aa1076de6921bc317a0e4666d8ba892f4ec7b51144a21`. Its short exact calculation took about 4.6 seconds.

Here is the complete upper coverage. Same-sign factor models have FDR at most $q$ by subsection 6. The other star quadrant is bounded by (P26). In the mixed-sign star quadrant, the low strip (P27) is bounded by the same constant, the middle strip (P29) is bounded by $q$, and the high strip (P31) is bounded by (P32). Interchanging the last two coordinates covers the other mixed-sign quadrant. Every endpoint, including duplicate coordinates, zero loadings, and zero residual variances, was included by the proved continuity and the explicit endpoint arguments. The star reduction (P20) and the complete label/mean reduction (P17) therefore imply the uniform bound for the whole factor optimization, not merely a fixed mean or fixed label case:
$$
\begin{aligned}
A_3(1/64)&\leq0.01563275411291622882\\
&<0.01563456094228375186
\leq H_{3,[3]}(1/64;0,\Sigma_{-1/10})
\leq M_3(1/64).
\end{aligned}
\tag{P33}
$$
Here $\Sigma_{-1/10}$ has diagonal entries 1 and every off-diagonal entry $-1/10$, and its admissibility and lower bound are proved in subsection 10. The strict gap in (P33) exceeds $1.8\cdot10^{-6}$. The two displayed finite decimal comparison endpoints are outward rational bounds. No Monte Carlo error, floating-point optimizer, or unverified quadrature tolerance enters this comparison.

The short aggregate check `/private/tmp/lihua_full_factor_gap_certificate_20261104_v1.py`, SHA-256 `343d2dd5eb74575187f0ea943707bcf05988f6be67fbae96c348e0d90e9f1b6a`, checks all six supporting source hashes and every final rational comparison. Its `.log` has SHA-256 `cc0ae67779cb925327a61ea469f4004b70818de543149600b773e21310172000`. It checks the assembly of the analytic coverage and the scalar certificates; it does not replace their written proofs. No remote computation was needed for this final analytic route, and the unexecuted branch prototype supplies no part of the certificate.

The complete six-certificate manifest is below. Each stem names a `.py` source and a `.log` file, both directly in `/private/tmp/`; the two columns give their SHA-256 hashes. The aggregate check independently verifies the source column. The parent executing agent also independently reconstructed (P27)--(P31), including the fixed-negative-edge comparison, both middle-strip pair bounds, the triple-bin bounds, the two positive terms of the negative-edge Plackett derivative, and the chain-rule sign in (P30).

| Certificate stem | Source SHA-256 | Log SHA-256 |
|---|---|---|
| `lihua_negative_triangle_certificate_20261104_v1` | `dc65165078a3ea2f69ce31bf01a964ec07a9af1dd9cfbfaba179ed0cc9ce5211` | `2a6d764ca4db2c1732325e075cb596fd09fd396839fdcd6d1afdea311aabe61c` |
| `lihua_negative_pair_sup_certificate_20261104_v1` | `e43339d30137344f0bd3f9dc5013a37b792779f659e0ad4489cdf0ae1a523f9d` | `939dbc75f4ac29bac31a6b4e63412771a3996ec41c86ff244eada0526b804efd` |
| `lihua_star_singleton_sign_certificate_20261104_v1` | `290408ce21fe121ce9b9139aeb31e98db221d52036f266ee76b5ec5f3130a7e1` | `76ffab425cd3c53561e0af71527e5485ccb60a954835cac20c669c92ba65088c` |
| `lihua_star_middle_strip_certificate_20261104_v1` | `0b414ef3bdc7e14e21b0388e8ed82cf8dead72d0fbd03b9ed77a3beffa59f986` | `5f3905fc22eaf162205f92d148eaa3f5fa66804473d3c348a411e4c4254fa6ce` |
| `lihua_star_duplicate_strip_certificate_20261104_v1` | `6548d2e452daa33954be87732cc2bbc056c4034680995fa753562c5f2ce9c3c2` | `da5f314d91682ad6996f2f6bf519565c9f685ff97c06ca07bf34757ea3787863` |
| `lihua_duplicate_sup_certificate_20261104_v1` | `ed93775db1a41eb6163609ea4188711a0689302c89c0b98607e1d46074322f1e` | `41ee0bbf062fa9da638aa1076de6921bc317a0e4666d8ba892f4ec7b51144a21` |

The rejected upload described in subsection 13 was not retried or replaced by another export mechanism. The purely analytic reduction and these short local exact certificates resolved the computation requirement without exporting the prototype. Thus the approval rejection left no mathematical obligation blocked and no upload pending for this route.

## Failure

The obstruction is checklist item 2's proposed exact joint extremal lemma (E). At its first required gate, $N=3,q=1/64$, (P33) proves $M_3(1/64)>A_3(1/64)$. The factor upper bound includes every permitted null and alternative label, every compactified mean, and every singular factor boundary through (P17), (P20), and the exhaustive analytic star coverage. The full-model lower bound is an admissible centered all-null positive-definite negative triangle. Thus a covariance-class comparison at only a fixed label or sampled factor point is not being mistaken for failure of the joint optimization.

The exact factor-replacement lemma required by this plan is false. Endpoint variations, an $N=4$ screen, or the terminal restricted-class estimate cannot repair that false equality. Any replacement allowing a quantitative slack would require a new proved lemma and a new plan. This failure concerns the stronger auxiliary principle (E), not the original asymptotic $q\sqrt{\log(1/q)}$ upper-bound target. The target asset is untouched and has no new proof or falsification verdict.

## Verification

The first decisive issue is the explicit finite-array extremal lemma (E), starting at $N=3,q=1/64$. Its optimizer comparison is not the target scalar budget: it compares two covariance classes after joint mean optimization and can be false even when both classes obey the target asymptotic upper bound. A certified failure of this stronger principle stops the plan. Finite successful cases are screening gates and cannot establish (E) for all $N$.

The potentially useful new tools are the compact labelled optimization and the endpoint joint mean/covariance calculus with the PSD-preserving variations (P) and (N). Their formulas can be checked directly, but the global replacement of maximizers is the entire new unresolved mechanism. It must be proved, with its boundary cases, before invoking a factor model. This plan makes no claim that KKT or second-order conditions already force the desired factor form.

The terminal calculation (K)--(F) is explicit and independently checkable. No unproved Gaussian regression jump bound, mean monotonicity, covariance completion, or null-only linking bound enters it. If (E) is established, step 7 obtains an $N$- and mean-uniform finite-level upper bound, so the required $q$-dependent dimensions and singular covariances are included. If (E) cannot be established, completing the terminal calculation does not complete the target.

## Assumed definitions

Use the approved definitions `gaussian_multiple_testing_model`, `gaussian_test_pvalues`, `benjamini_hochberg_step_up`, `false_discovery_rate`, and `gaussian_worst_case_bh_fdr` exactly as in the context pack. No draft definition or unproved asset is assumed. The compact labelled limits, $M_N,A_N$, $C(a)$, and the endpoint derivatives are local auxiliary notation in this plan. They do not revise the approved model or true-null definition. In particular (E), the global maximizer replacement, and all boundary extensions are pending proof obligations, not assumptions supplied to the final theorem.

## Adapted from

- `multifactor_radial_fdr_bounds`: adapt only its terminal conditioning, radial event, and strip-integration architecture to a single signed common factor. The transferable hypotheses are exactly independent residuals given the common factor, unit marginal variances, and the full composite null $\theta_i\leq0$; these hold for $C(a)$, including $a_i=0,\pm1$. The general covariance is not asserted to satisfy these hypotheses. Its new connection to this class is the independently required extremal lemma (E). Unlike using the source's cited statements as black boxes, step 6 reproves conditional leave-one-out directly and obtains the central integral by the displayed density-ratio completion of squares. Native reads of `lei2026_conditional_fdp_bound --section Proof` and `lei2026_integrated_conditional_tail_ratios --section Proof` supplied no Proof sections, so their proofs are not purportedly adapted or assumed here. The exact one-dimensional radial strip is $\log2$, and there is no growing-factor or directional-entropy hypothesis in the final reduction.

## Difference from failed plans

- `plan_gaussian_bh_one_sided_global_corner_budget_20261104`: replaces support over arbitrary PSD test matrices applied to a path-integrated corner matrix by a finite-dimensional optimization of the actual Gaussian FDR, including actual means. The endpoint matrix $B$ is used only in legitimate variations at its own candidate maximizer. No integrated diagonal completion is requested. The weak alternative-only correlation obstruction remains valid and is not dismissed by endpoint stationarity.
- `plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104`: uses no fixed-alternative Schur completion, row-absolute cost, or optimized block completion. The full alternative block is allowed to vary inside the actual global maximization, with its joint Gaussian law retained. The complete general-completion obstruction in `idea_ce4038795c70` excludes treating a better row recipe or a KKT slogan as a repair. The new, falsifiable requirement is instead (E), with negative means jointly optimized and singular boundaries explicitly retained.
