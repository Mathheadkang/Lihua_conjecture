---
type: idea
title: >-
  Independent architecture 2 before history comparison: Covariance interpolation
  and reduction to one common factor
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags: []
---

阶段1独立方案，从已冻结原文 idea_df1d7c436d5e 逐字提取；未依据旧路线修改。原输出SHA256 d6125175cd6509e0550c783d297ce49b09b74956f7237575aa85484204709223。以下含原始共同设置与该路线全部五项义务、具体检验和停止条件。待第二阶段核对历史与数学筛选，不代表已验证或新颖。

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
