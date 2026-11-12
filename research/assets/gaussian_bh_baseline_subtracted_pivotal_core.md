---
type: lemma
title: Baseline-subtracted pivotal identity for arbitrary Gaussian covariance
status: approved
source:
  kind: original
  location: >-
    plan_two_sided_baseline_subtracted_pivotal_probe_20261105, Progress Step 3,
    BH0, BH2, A1c and BSP-i
depends_on:
  - gaussian_bh_two_sided_exact_pivotal_identity
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - two_sided
  - baseline_subtracted
  - extracted_unverified
---

## Statement

### Source notation and scope

For every $q\in(0,1)$ and every admissible [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) $(N,\theta,\Sigma)$, including singular covariance matrices, use the two-sided testing track and a true null $i$ with $\theta_i=0$. There is no restriction on finite $N$ or on its dependence on $q$.

Setting. $p(u)=2\overline\Phi(u)$, $t_k=qk/N$, $b\in[0,1]^N$, $\widehat k_q(b)=\max\{k\in\{0,\dots,N\}:\#\{j:b_j\le t_k\}\ge k\}$ ($\widehat k=0$ if none; $\max\emptyset=0$). Null $i$, $\theta_i=0$, so $T_i\sim N(0,1)$ and $P_i=p(|T_i|)$ is $U(0,1)$.

Let $b^0$ be the p-value vector with $b^0_i=0$ and $R_i=\widehat k_q(b^0)$; $R_i\ge1$ since $b^0_i=0\le t_1$ gives $\#\{j:b^0_j\le t_1\}\ge1$. Let $b$ be the actual vector ($b_i=P_i$), $R=\widehat k_q(b)$. 

$Y_i:=T_{-i}-\theta_{-i}-c_iT_i$, $c_i=\Sigma_{-i,i}$. 

Movers $\mathcal M_i=\{j\ne i:c_{ij}\neq0\}$, $b^\flat=b^0$ with $b^\flat_j=1$ ($j\in\mathcal M_i$), $R^\flat_i=\widehat k_q(b^\flat)$, $\tau^\flat_i=qR^\flat_i/N$.

Local notation from source BH0: $a(x;t)=\frac{\mathbf 1\{p(|x|)\le t\}}t,\ \tau_i=\frac{qR_i}N$. Write $I_0=I_0^{(2)}(\theta)$ and $\pi_0=|I_0|/N$ as in the [exact pivotal identity](./gaussian_bh_two_sided_exact_pivotal_identity.md).

### Claim

$\Delta_i:=\mathbb E\,a(T_i;\tau_i)-1=\mathbb E[a(T_i;\tau_i)-a(T_i;\tau^\flat_i)]$.

With $p=p(|T_i|)$, $\Delta_i\le\mathbb E[\mathbf 1\{\tau^\flat_i<p\le\tau_i\}/\tau_i]$.

if $\mathcal M_i=\emptyset$ then $b^\flat=b^0$, $\Delta_i=0$ exactly (e.g. $\Sigma=I$, each null: $\Delta_i=0$, $\operatorname{FDR}=q\pi_0$ exactly).

## Proof

Fix the model and null coordinate as in the Statement. The following argument holds for every finite $N\ge1$ and every $q\in(0,1)$.

### Step 1: deterministic ranks and integrability

Fix any finite $N\ge1$, $q\in(0,1)$ and the model in the Statement. For $k\in[N]$, let $C_k(b)=\sum_{j=1}^N\mathbf1\{b_j\le t_k\}$. Each $C_k$ is Borel, so the maximum of the finite set of qualifying indices, together with $0$, is Borel. If $b\le b'$, then $C_k(b)\ge C_k(b')$ for each $k$, so every qualifying index for $b'$ qualifies for $b$ and $\widehat k_q(b)\ge\widehat k_q(b')$. Since $b_i^0=b_i^\flat=0\le t_1$ and $b^0\le b^\flat$, this yields $1\le R_i^\flat\le R_i\le N$, hence $q/N\le\tau_i^\flat\le\tau_i\le q<1$. P-values are continuous functions of the Gaussian coordinates and all ranks and thresholds are therefore measurable. Each normalized indicator is between $0$ and $N/q$, proving integrability. Weak count inequalities keep every tie and threshold equality; when $N=1$ both forced-zero ranks are $1$.

### Step 2: match the pivotal notation, including zero actual rejections

For every $j\ne i$, the residual definition gives $\theta_j+c_{ij}T_i+(Y_i)_j=T_j$. Thus the forced-zero vector defining $\rho_i(T_i,Y_i)$ is exactly $b^0$, and $R_i=\rho_i(T_i,Y_i)$, so both definitions of $\tau_i$ coincide. The dependency's A1 clauses explicitly quantify over every $q\in(0,1)$, independently of its earlier small-$q$ auxiliary notation.

For completeness, if a vector has maximal rank $r>0$ and $m=C_r(b)>r$, then $m\le N$ and $t_m\ge t_r$ imply $C_m(b)\ge m$, contradicting maximality of $r$. Hence $C_r(b)=r$ and the BH rejection count equals its maximal rank; at rank zero its rejection set is empty. Monotonicity gives $R\le R_i$. If $P_i\le t_{R_i}$, the actual and forced-zero counts at $R_i$ coincide, so $R\ge R_i$, giving $R=R_i$ and rejection of $i$. Conversely, if $i$ is rejected, $P_i\le t_R\le t_{R_i}$ and the same equality-of-counts argument gives $R=R_i$. Therefore, including $R=0$ and ties,

$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
=\frac{\mathbf1\{P_i\le t_{R_i}\}}{R_i}
=\frac qN a(T_i;\tau_i).
$$

In particular the target's $\Delta_i$ agrees with the quantity in approved A1(d).

### Step 3: singular Gaussian residual and frozen nonmovers

The vector $(T_i,Y_i)$ is a centered joint Gaussian linear image of $T-\theta$, with $\operatorname{Var}T_i=1$, $\operatorname{Cov}(Y_i,T_i)=c_i-c_i=0$, and residual covariance $S_i:=\Sigma_{-i,-i}-c_ic_i^{\mathsf T}\succeq0$ because it is a covariance matrix. For any $s\in\mathbb R$ and $v\in\mathbb R^{N-1}$, joint Gaussianity gives

$$
\mathbb E e^{\mathrm i(sT_i+v^{\mathsf T}Y_i)}
=e^{-s^2/2-v^{\mathsf T}S_iv/2}
=\mathbb E e^{\mathrm i sT_i}\,\mathbb E e^{\mathrm i v^{\mathsf T}Y_i}.
$$

Factorization proves independence of $T_i$ and the entire residual vector, with no invertibility hypothesis and including degenerate Gaussian components. This also recovers the dependency's A1(a). For a nonmover $j\ne i$, $T_j=\theta_j+(Y_i)_j$. Define $h_i(y)$ to have entry $0$ at $i$, entry $1$ on movers, and entry $p(|\theta_j+y_j|)$ on each nonmover. It is Borel and $b^\flat=h_i(Y_i)$. Step 1 shows $g_i(y):=(q/N)\widehat k_q(h_i(y))$ is Borel with values in $\{t_1,\ldots,t_N\}$. Consequently $\tau_i^\flat=g_i(Y_i)$ is independent of $T_i$ and its p-value. No independence among the nonmovers is asserted or needed. When $N=1$ the residual lives in $\mathbb R^0$; when no nonmovers remain, $h_i$ is constant; both arguments still apply.

### Step 4: exact mean-one baseline

For $t\in(0,1)$ let $u_t\ge0$ be the unique value satisfying $2\overline\Phi(u_t)=t$. Since $T_i\sim N(0,1)$, continuity and symmetry give $\mathbb P(P_i\le t)=\mathbb P(|T_i|\ge u_t)=t$. Independence from Step 3 and the finite-valued positive threshold give, almost surely,

$$
\mathbb E[a(T_i;\tau_i^\flat)\mid Y_i]
=\sum_{k=1}^N\mathbf1\{g_i(Y_i)=t_k\}\frac{\mathbb P(P_i\le t_k)}{t_k}
=\sum_{k=1}^N\mathbf1\{g_i(Y_i)=t_k\}=1.
$$

Therefore $\mathbb E a(T_i;\tau_i^\flat)=1$. This is also an application of approved A1(c), with its Borel and range hypotheses verified. The bound $N/q$ from Step 1 justifies conditioning and all subsequent expectation differences for each fixed finite $N,q$.

### Step 5: exact subtraction and three-case upper bound

The baseline mean gives, by integrability,

$$
\Delta_i=\mathbb E a(T_i;\tau_i)-1
=\mathbb E[a(T_i;\tau_i)-a(T_i;\tau_i^\flat)].
$$

Write $p=p(|T_i|)$. Since $0<\tau_i^\flat\le\tau_i$, the difference inside this expectation is exactly $1/\tau_i-1/\tau_i^\flat\le0$ on $p\le\tau_i^\flat$, exactly $1/\tau_i$ on $\tau_i^\flat<p\le\tau_i$, and zero on $p>\tau_i$. The cases exhaust every outcome, retain the weak endpoint comparisons, and remain valid when the two thresholds coincide. Thus pointwise the difference is at most $\mathbf1\{\tau_i^\flat<p\le\tau_i\}/\tau_i$, and taking expectations proves exactly the claimed upper bound.

### Step 6: empty movers and the independent-coordinate consequence

If $\mathcal M_i=\emptyset$, the construction changes no coordinate of $b^0$, so $b^\flat=b^0$ and $\tau_i^\flat=\tau_i$. Step 5 gives $\Delta_i=0$ exactly. If $\Sigma=I$, every true null has empty movers regardless of alternative means. The approved dependency's all-$q$ A1(d), with its $\Delta_i$ identified in Step 2, gives

$$
\operatorname{FDR}^{(2)}_{\mathrm{BH}}
=q\pi_0+\frac qN\sum_{i\in I_0}\Delta_i=q\pi_0.
$$

For $I_0=\emptyset$ both the sum and the false discovery proportion are zero. The proof fixed arbitrary finite $N$, $q\in(0,1)$ and admissible covariance, never imposed a small-$q$ or nonsingularity condition, and permits arbitrary dependence of model parameters on $q$. All six planned steps are established; none uses a block-baseline or two-copy assertion.

## Provenance

Selected verbatim from [the baseline-subtracted pivotal probe plan](../plans/plan_two_sided_baseline_subtracted_pivotal_probe_20261105.md), Progress Step 3: general-covariance BSP-i, with its BH0, BH2 and A1c proof. Statement excerpts are the BSP-i exact identity, upper bound, and no-movers consequence. Local notation is copied from the same source setting and setup. This core selection makes no BSP-ii block-baseline independence claim and no BSP-iii two-copy claim; the original compound draft remains preserved under its original ID. Only display-math line breaks are normalized. No independent verification verdict is asserted.
