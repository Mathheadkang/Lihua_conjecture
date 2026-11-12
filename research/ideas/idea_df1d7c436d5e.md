---
type: idea
title: >-
  Independent replanning phase 1 — frozen three-architecture dossier before
  history comparison
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags: []
---

第一阶段原样冻结。独立CLI thread 01a1bfd5-570c-7a60-a77a-e6d12c071e02；仅公开arXiv:2607.14812v4原文与其普适阶问题，关闭记忆/文件工具，不继承本对话。输入SHA256 6d7681098b9da517a24ff6070e128cfc83805dc4846710fae9b9dcfa3383662d；完整输出SHA256 d6125175cd6509e0550c783d297ce49b09b74956f7237575aa85484204709223。输出自检未见项目旧摘要，事件记录无工具调用，turn completed。以下全文未由父任务改写；冻结时尚未开始第二阶段历史比较。三条均为待检验架构，不是证明或新颖性认定。

## Input audit

The system and developer input contains general operating instructions, a skill catalog, and environment metadata. It contains **no project-specific prior research summary, mathematical findings, earlier proof attempts, or private follow-up material**. I therefore find no contamination of the kind specified in the request.

I have used only the supplied public excerpt and standard mathematical knowledge. I have made no tool calls and accessed no files, applications, memories, previous sessions, or external sources. The source’s identity, version, date, and reported results are taken from the supplied excerpt; I have not independently verified them.

The three architectures below are **unproved research routes**, not proofs of the requested bound. Each has a precise mathematical gate at which it can fail.

## Common setup and established bridges

Write
\[
F_s(q)=\sup_{N,\theta,\Sigma}\operatorname{FDR}_{\theta,\Sigma}
(\operatorname{BH}_q),\qquad s\in\{\le,=\},
\]
with the null sets and \(p\)-values defined in the excerpt. The supremum is taken separately at every \(q\).

The desired conclusion is the existence of numerical constants
\[
C_s<\infty,\qquad q_s>0,
\]
such that
\[
F_s(q)\le C_s q\sqrt{\log(1/q)}
\quad(0<q\le q_s).
\]

All subsequent statements concern finite models, with constants uniform over their dimensions and parameters. That uniformity is what would permit the unrestricted supremum.

Two elementary facts will be used repeatedly.

**Exact leave-one-out identity.** Replace \(P_i\) by zero and let \(R_i^0\) be the resulting ordinary BH rejection count, using the largest nonstrict crossing. Then
\[
\{i\text{ rejected}\}
=\{P_i\le qR_i^0/N\},
\]
and on this event \(R=R_i^0\). Consequently,
\[
\operatorname{FDR}
=\sum_{i\in H_0}
\mathbb E\left[
\frac{\mathbf1\{P_i\le qR_i^0/N\}}{R_i^0}
\right].
\tag{1}
\]
This is deterministic BH algebra and needs no dependence assumption.

**Continuity at singular covariance matrices.** For fixed finite \(N,\theta,q\), the FDP is locally constant as a function of \(T\), except possibly where
\[
P_i=qk/N
\]
for some \(i,k\). Each such equality has probability zero because every \(T_i\) has variance one. This remains true when \(\Sigma\) is singular. Thus covariance regularization can be removed by bounded convergence, provided the preceding estimates are uniform in the regularization parameter.

Neither fact replaces the selected rank by a freely chosen rank.

## Architecture 1: Gaussian regression sections and signed boundary cancellation

This route resolves each null contribution along its own Gaussian coordinate. Its central difficulty is to control the **signed recycling of rejection boundaries** created by the other hypotheses.

### 1. Essential Gaussian property

For every coordinate \(i\), including in singular models, write
\[
X_i=T_i-\theta_i,\qquad
T_j=\theta_j+\rho_{ij}X_i+W_j^{(i)},
\]
where \(X_i\sim N(0,1)\) and the residual vector \(W^{(i)}\) is independent of \(X_i\).

Conditional on \(W^{(i)}=w\), all statistics are affine functions of one scalar \(x\). Ordinary BH therefore has finitely many changes along that section:

- one-sided changes occur at affine threshold crossings;
- two-sided changes occur at crossings of absolute affine functions.

The residual vector may be degenerate. No inverse covariance matrix is needed.

### 2. Rigorous bridge to mixed-null BH

Let \(r_i(x,w)\) denote the actual largest BH crossing after forcing \(P_i=0\), evaluated on this section. Define
\[
g_i(x,w)=
\frac{\mathbf1\{p_+(\theta_i+x)\le qr_i(x,w)/N\}}
{r_i(x,w)}
\]
for a one-sided true null.

Equation (1) gives exactly
\[
\operatorname{FDR}_{\le}
=\sum_{i\in H_0}
\mathbb E_{W^{(i)}}\int_{\mathbb R}\phi(x)g_i(x,W^{(i)})\,dx.
\tag{2}
\]

For almost every residual realization, \(g_i\) is piecewise constant. If its distinct jump locations are \(b\), with all simultaneous changes combined into a single jump,
\[
\int\phi(x)g_i(x,w)\,dx
=\sum_b\bar\Phi(b)\,\Delta g_i(b,w).
\tag{3}
\]
Here \(g_i(-\infty,w)=0\). The formula follows by integration by parts for a step function.

Let \(b_i^\star\) be the first jump making \(g_i\) positive. Its contribution is at most \(q/N\). Indeed, if the post-jump rank is \(r\), activation implies
\[
\bar\Phi(\theta_i+b_i^\star)\le qr/N.
\]
Because \(\theta_i\le0\),
\[
\bar\Phi(b_i^\star)\le
\bar\Phi(\theta_i+b_i^\star)\le qr/N.
\]
This explicitly handles negative null means.

All remaining signed jumps form a remainder \(\mathcal B_{\le}(q)\), giving
\[
\operatorname{FDR}_{\le}
\le q\,|H_0|/N+\mathcal B_{\le}(q).
\tag{4}
\]

### 3. First essential unproved proposition

A useful gate is the following **signed section-cancellation inequality**:

> There are numerical \(A,B,q_0>0\) such that, for every finite unit-diagonal PSD Gaussian model, every one-sided null configuration, every \(0<q\le q_0\), and every \(L\ge1\),
> \[
> \mathcal B_{\le}(q)
> \le A qL+B\bar\Phi(L).
> \tag{5}
> \]

Taking
\[
L=\sqrt{2\log(1/q)}
\]
would establish the required order.

This proposition is not established here. Its content is that the aggregate signed boundary charge has a dimension-free Gaussian truncation estimate. It is stronger than merely bounding the final integral at one selected \(L\), and can be tested independently at other scales.

A proof would have to exploit the shared Gaussian regression structure across the sections. Bounding each jump separately is unlikely to suffice.

### 4. Decisive tests

**Analytic obstruction to a tempting shortcut.** A bound of the form
\[
\mathbb E\left[
\frac{\mathbf1\{P_i\le qR_i^0/N\}}{R_i^0}
\right]
\le Cq/N
\tag{6}
\]
uniformly in \(N\) is false.

To see the mechanism, take one null \(T_0=X\), and \(n\) nonnulls
\[
T_j=2z(qj/N)-X,\qquad
z(t)=\Phi^{-1}(1-t),\quad N=n+1.
\]
Their ordering is fixed. After forcing the null \(p\)-value to zero, the rank approximately tracks
\[
R_0^0(X)\asymp N\bar\Phi(X)/q
\]
over a long range. The null contribution has harmonic accumulation of order
\[
(q/N)\log N.
\]
Thus this route must aggregate across nulls and retain cancellation; a constant bound for each null separately cannot carry it.

**Degenerate cancellation test.** Use a rank-one model with a block of identical nulls \(T_i=X\) and alternatives \(T_j=\mu_j\pm X\). Choose the \(\mu_j\)'s so that many rank switches occur near null activation boundaries. Enumerate all section jumps exactly and test (5), especially when several jumps coalesce.

This directly tests whether signed cancellation survives arbitrarily many alternative-induced changes.

### 5. Two-sided justification and constants

For a two-sided true null, \(\theta_i=0\). Split the section integral into \(x\ge0\) and \(x\le0\), and parameterize each by \(y=|x|\). On either branch, activation requires
\[
\bar\Phi(y)\le qr/(2N).
\]
The first activation charge is therefore at most \(q/(2N)\) per branch. Together, their anchor contribution is at most \(q/N\).

The two-sided obligation is a **separate** version of (5) for the sum of the two signed branch remainders:
\[
\mathcal B_{=}(q)
\le A_=qL+B_=\bar\Phi(L).
\tag{7}
\]
Absolute values change the alternative crossing geometry; the one-sided inequality does not automatically imply (7).

Dimension disappears only if (5) and (7) hold after summing all null sections. Singular models are already included in the regression representation.

**Stop condition.** Abandon this architecture if either signed remainder violates its uniform truncation inequality. Also stop any version that requires absolute summation of all jump charges or the false per-null estimate (6). Failure of those stronger estimates would not disprove the original conjecture.

## Architecture 2: Covariance interpolation and reduction to one common factor

This route seeks a comparison theorem that reduces the unrestricted covariance problem to the class for which the excerpt reports uniform sharp bounds.

### 1. Essential Gaussian property

For a smooth bounded function \(f\), Gaussian covariance interpolation gives
\[
\frac{d}{dt}\mathbb E f(T_t)
=
\frac12\sum_{j,k}\dot\Sigma_{jk}(t)
\,\mathbb E[\partial_{jk}f(T_t)],
\tag{8}
\]
along a suitable positive-definite covariance path.

For BH, \(f\) is the actual mixed-null FDP. Its derivatives must be interpreted through smoothing or boundary measures. Their signs encode rank changes, dilution by alternatives, and null rejections.

This is a covariance comparison problem, rather than a section-by-section tail estimate.

### 2. Rigorous bridge to mixed-null BH

Define the one-common-factor class explicitly by
\[
T_i=\theta_i+a_iZ+\sqrt{1-a_i^2}\,\varepsilon_i,
\qquad a_i\in[-1,1],
\tag{9}
\]
with independent standard normal \(Z,\varepsilon_1,\ldots,\varepsilon_N\).

Let \(M_s(q)\) be the supremum of ordinary BH FDR in this class, with the corresponding original null definition.

The excerpt reports
\[
M_s(q)=\{c_s+o(1)\}q\sqrt{\log(1/q)}
\]
uniformly over dimension, means, and loadings. Consequently, taking that reported result as an input, there exist finite \(D_s\) and positive \(q_s^\star\) such that
\[
M_s(q)\le D_sq\sqrt{\log(1/q)}
\quad(0<q\le q_s^\star).
\tag{10}
\]

A comparison to \(M_s\) would preserve the mixed-null problem and the actual BH crossing.

### 3. First essential unproved proposition

The architectural gate is a **factor-envelope comparison**:

> For each formulation \(s\), there are numerical \(K_s,B_s,q_0>0\) such that every finite unit-diagonal PSD Gaussian model satisfies
> \[
> \operatorname{FDR}_{\theta,\Sigma}(\operatorname{BH}_q)
> \le K_s M_s(q)+B_sq,
> \qquad 0<q\le q_0.
> \tag{11}
> \]

This need not assert that a one-factor model is an exact extremizer. Constant-factor domination suffices.

An interpolation proof must specify:

1. a path or decomposition connecting the general model to factor models;
2. the boundary terms produced by the actual FDP;
3. a dimension-free bound on their net contribution.

Equation (8) supplies an analytic language for those obligations, but supplies no favorable sign by itself.

### 4. Decisive tests

**Frustrated rank-two test.** Start with
\[
\Sigma=
\begin{pmatrix}
1&-1/2&-1/2\\
-1/2&1&-1/2\\
-1/2&-1/2&1
\end{pmatrix}.
\tag{12}
\]
This is the Gram matrix of three unit vectors separated by \(120^\circ\). Its three negative off-diagonal entries cannot equal \(a_ia_j\) simultaneously.

Use two true nulls and one alternative, then vary the alternative mean. The model has an explicit two-dimensional Gaussian representation. It tests the sign of any proposed local interpolation inequality without requiring high dimension.

**Amplified obstruction test.** Replicate groups loading on the three directions, with unequal group sizes and adjustable alternative means. This tests whether a comparison loss accumulates with the number of groups or hypotheses.

**Algebraic screening test.** Reject any argument claiming that every correlation matrix is a convex combination of sign rank-one matrices. Correlation matrices are not exhausted by that convex hull. Moreover, even a valid covariance mixture would not make Gaussian BH FDR linear in covariance.

### 5. Two-sided justification and constants

The two formulations require separate comparison theorems.

For one-sided tests, the troublesome correlations include negative null–alternative correlations. A comparison that makes all such correlations nonnegative would remove the lower-bound mechanism described in the excerpt and cannot simply be presumed to increase FDR.

For two-sided tests, reflection symmetry of null coordinates does not restore monotonicity of the full \(p\)-value vector in the presence of nonzero means. The Hessian boundary terms differ from the one-sided terms.

If (11) holds, dimension-free constants follow immediately from (10). If smoothing or covariance regularization is used, the comparison constants must be uniform before those parameters are removed. Fixed-dimensional continuity then includes singular models.

**Stop condition.** Stop this route if the comparison requires a loss growing with rank, number of factors, \(N\), or a covariance condition number. A failed monotonicity claim invalidates that comparison argument; it does not invalidate every possible factor-envelope comparison.

## Architecture 3: Moving Gaussian hyperplanes and weighted positive boundary flux

This route treats \(q\) as the moving parameter and seeks a dimension-free bound on the positive changes of the actual FDP. It uses the geometry of a Gaussian hyperplane arrangement.

### 1. Essential Gaussian property

Represent every allowed model as
\[
T_i=\theta_i+\langle a_i,Z\rangle,
\qquad Z\sim N(0,I_d),\qquad \|a_i\|=1,
\tag{13}
\]
where \(d=\operatorname{rank}(\Sigma)\).

For one-sided testing, the BH decisions are determined by the hyperplanes
\[
\theta_i+\langle a_i,z\rangle
=z(uk/N),\qquad 1\le i,k\le N,
\tag{14}
\]
at level \(u\).

These planes partition Gaussian space into cells on which the actual largest BH crossing and FDP are constant. Their Gaussian surface measures are well defined even when \(d<N\).

The relevant property is Gaussian surface integration, together with the normal hazard scale
\[
\lambda(z(u))\asymp \sqrt{\log(1/u)}.
\]

### 2. Rigorous bridge to mixed-null BH

As \(u\) increases, each interface moves with normal speed
\[
v_{ik}(u)=\frac{k}{N\phi(z(uk/N))}.
\tag{15}
\]

On an interface piece \(F\), let \(\Delta_F\mathrm{FDP}\) be the full change in FDP when the moving interface passes a point. This includes all changes in the largest crossing; it is not merely the contribution of coordinate \(i\).

Formally, and rigorously under the usual finite-arrangement transport formulation away from exceptional parameter values,
\[
\frac{d}{du}\operatorname{FDR}(u)
=
\sum_F v_F(u)\,
\Delta_F\mathrm{FDP}\,
\gamma_{d-1}(F),
\tag{16}
\]
where \(\gamma_{d-1}\) denotes Gaussian surface measure.

Define the positive flux
\[
\mathcal S_{\le}(u)=
\sum_F v_F(u)\,
(\Delta_F\mathrm{FDP})_+
\,\gamma_{d-1}(F).
\tag{17}
\]
Then
\[
\operatorname{FDR}(q)\le\int_0^q\mathcal S_{\le}(u)\,du.
\tag{18}
\]

For every fixed finite model, \(\operatorname{FDR}(u)\to0\) as \(u\downarrow0\): a false rejection requires some true-null \(P_i\le u\), whose probability is at most \(|H_0|u\). This observation supplies the integration boundary condition, not the uniform bound.

Coincident interfaces must be grouped and assigned their full FDP jump once.

### 3. First essential unproved proposition

The gate is a **weighted Gaussian surface-flux inequality**:

> There are numerical \(K,q_0>0\) such that, for every finite one-sided Gaussian model with arbitrary alternative means and null means \(\theta_i\le0\),
> \[
> \mathcal S_{\le}(u)
> \le K\{1+\sqrt{\log(1/u)}\}
> \tag{19}
> \]
> for almost every \(0<u\le q_0\).

It would imply the target because
\[
\int_0^q\{1+\sqrt{\log(1/u)}\}\,du
\le Cq\sqrt{\log(1/q)}
\]
on a universal small-\(q\) interval.

The weights in (17) are essential. An unweighted surface-area bound for an arrangement of \(N^2\) planes generally cannot give the desired dimension-free result.

### 4. Decisive tests

**Identical-null degeneracy.** Set all \(T_i=X\), with all hypotheses null. BH rejects all hypotheses exactly when \(\bar\Phi(X)\le u\), so
\[
\operatorname{FDR}(u)=u.
\]
A correct grouped flux calculation gives \(1\), independent of \(N\). Counting coincident coordinate interfaces separately produces a spurious dimension factor and immediately falsifies that implementation.

**Rank-jump dilution test.** Use one null and a large identical alternative block:
\[
T_0=X,\qquad T_j=\mu-X.
\]
At an alternative interface, the selected rank can jump by the block size. Compute the full change of
\[
V/(R\vee1)
\]
on both sides. This checks whether the flux accounting retains dilution and changes in null rejection status.

**Oscillation test.** Combine several alternative blocks with opposite loadings and separated means. Test whether the positive flux itself becomes large while signed FDR changes cancel. That would defeat (19), even if the original FDR bound remains true.

### 5. Two-sided justification and constants

For two-sided testing, replace (14) by both families
\[
\theta_i+\langle a_i,z\rangle
=\pm z(uk/(2N)).
\tag{20}
\]
Their speed magnitude is
\[
\frac{k}{2N\phi(z(uk/(2N)))}.
\tag{21}
\]

Define \(\mathcal S_{=}\) using the actual two-sided FDP and these interfaces. The separate required proposition is
\[
\mathcal S_{=}(u)
\le K_=\{1+\sqrt{\log(1/u)}\}.
\tag{22}
\]
Counting two branches is insufficient to prove it: nonzero alternative means change the arrangement and its FDP jumps.

Negative one-sided null means enter as offsets in (14); the proposed inequality must hold with those offsets, rather than replacing them by zero through an unjustified FDR monotonicity argument.

This architecture needs no covariance regularization: (13) works directly in the support dimension. Dimension independence must come from the FDP-weighted flux inequality itself.

**Stop condition.** Stop the positive-flux version if grouped examples produce unbounded positive variation relative to \(\sqrt{\log(1/u)}\). A signed-flux argument might survive, but would be a materially different obligation. Also stop any derivation that counts interfaces without their full BH jump or introduces a surface-area factor depending on \(N\).

## What is established and what remains open in these architectures

The regression representation, exact leave-one-out identity, finite section decomposition, Gaussian interpolation identity under smoothing, support-space representation, and fixed-model continuity at singular covariances are standard mathematical tools.

The load-bearing claims remain unproved:

| Architecture | Essential unresolved claim |
|---|---|
| Regression sections | Dimension-free signed boundary cancellation, (5) and (7) |
| Covariance comparison | Constant-factor reduction to the one-common-factor envelope, (11) |
| Moving interfaces | Dimension-free weighted positive surface flux, (19) and (22) |

These are structurally different obligations: cancellation along null-conditioned lines, comparison across covariance models, and control of the variation generated by moving rejection boundaries.

None establishes the requested universal-order consequence at present. Each preserves ordinary BH’s largest nonstrict crossing, allows the model to vary with \(q\), and identifies where uniformity over dimension and degeneracy must actually be proved.

## Public-source whitelist and provenance

Only the following inputs were used:

1. **The user-supplied excerpt attributed to Lihua Lei**, *How Much Can Gaussian Dependence Inflate the Benjamini–Hochberg Procedure’s FDR?*, identified by the user as [arXiv:2607.14812v4](https://arxiv.org/abs/2607.14812v4), revision dated 9 October 2026. Definitions, reported lower bounds, reported one-common-factor asymptotics, and the conjecture were taken from that excerpt.
2. **Standard mathematical knowledge:** deterministic BH leave-one-out algebra; Gaussian regression and Gram representations; one-dimensional Gaussian integration by parts; Gaussian covariance interpolation for smooth functions; Gaussian tail asymptotics; and integration over moving piecewise-smooth boundaries.

No claims from the papers cited inside the excerpt were independently consulted. No novelty claim, literature-search claim, or proof of the universal bound is made.
