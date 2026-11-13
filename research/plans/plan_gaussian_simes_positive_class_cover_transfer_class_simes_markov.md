---
type: plan
title: >-
  Positive-class cover transfer by a per-class Simes reduction, the positive
  Gaussian Simes inequality, and Markov's inequality on the hitting mass
status: succeeded
target_asset: gaussian_simes_positive_class_cover_transfer
origin: agent
inspired_by: []
proof_digest: 337a0254ed1d2e46ac3ebb465026ee0b39b15d41d835bb7e7ddfe5998098e9eb
statement_digest: 6f5e1db93cf32b89012029bd947a756bef6f729d9d2aea6b980ed9894daae7fb
dependency_digests:
  lib_chi2024_positive_gaussian_simes: ec28454a273facc776f366331e57e9607ec21259d9fb56b3c1a187d35b8007e9
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
verified_proof_digest: 337a0254ed1d2e46ac3ebb465026ee0b39b15d41d835bb7e7ddfe5998098e9eb
---

## Goal

Target: [Random positive-class cover transfer for the all-null Gaussian Simes event](../assets/gaussian_simes_positive_class_cover_transfer.md).

Prove the bound $\mathbb P_{N,0,\Sigma}(E_q\cap\{h(T)\ge c_*\})\le q/(c\,c_*)$ by showing deterministically that every class the BH rejection set hits at the stated proportion has its own Simes statistic at most $q/c$. Then apply [the positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) to each fixed class, and use Markov's inequality on the $\pi$-average of the per-class indicators. The only cited result is `lib_chi2024_positive_gaussian_simes`, already in `depends_on`. Its mixture extension (Remark 10) is not needed, because each class $S$ is deterministic and is handled separately.

## Plan

1. [x] **Finiteness and measurability.** The positive classes of $\Sigma$ are nonempty subsets of $[N]$, so there are finitely many of them, and $\pi$ is given by weights $\pi_S=\pi(\{S\})\ge0$ with $\sum_S\pi_S=1$. The BH quantities $\widehat k_q(p)$, $r$, $\mathcal A$ and the event $E_q$ are determined by finitely many comparisons $p_i\le qk/N$, and $p=\overline\Phi(T)$ is continuous in $T$, so they are Borel functions of $T$. Hence on $E_q$, $h(T)=\sum_S\pi_S\,\mathbf 1\{|\mathcal A\cap S|\ge\max(1,c|S|r/N)\}$ is a finite sum of Borel indicators, and $E_q\cap\{h\ge c_*\}$ is an event. Claim: $h$ is Borel and the probability in the statement is defined.

2. [x] **Deterministic per-class Simes reduction.** Fix $p\in[0,1]^N$ with $r=R_q(p)\ge1$, and fix a nonempty $S\subseteq[N]$ with $K=|S|$ and $m=|\mathcal A\cap S|\ge\max(1,cKr/N)$. Every $i\in\mathcal A$ has $p_i\le q\widehat k_q(p)/N$. In fact $r=\widehat k_q(p)$. The $\widehat k_q$ smallest p-values are $\le p_{(\widehat k_q)}\le q\widehat k_q/N$, so $r\ge\widehat k_q$. If $r>\widehat k_q$, then $p_{(\widehat k_q+1)}\le q\widehat k_q/N\le q(\widehat k_q+1)/N$, which contradicts maximality. Only $\widehat k_q\le r$ is needed: it gives $p_i\le qr/N$ for $i\in\mathcal A$. Thus $p_S=(p_i)_{i\in S}$ has at least $m$ coordinates $\le qr/N$, so its $m$-th order statistic, with multiplicities, satisfies $p^S_{(m)}\le qr/N$, and $1\le m\le K$. Hence
$$
S_K(p_S)\le\frac{K}{m}\,p^S_{(m)}\le\frac{qKr}{Nm}\le\frac qc,
$$
where the last step is $m\ge cKr/N$. Claim: on $E_q$, the set of classes in the definition of $h$ is contained in $\{S: S_{|S|}(p_S)\le q/c\}$. Hence $h(T)\le g(T):=\sum_S\pi_S\,\mathbf 1\{S_{|S|}(p_S)\le q/c\}$ on $E_q$.

3. [x] **Hypotheses of the library theorem for one fixed positive class.** Fix a positive class $S$ with $K=|S|$. Under $\theta=0$, $Y=T_S$ is jointly Gaussian with unit variances, and its correlation matrix is the principal submatrix $\Sigma_S$. This matrix is symmetric, positive semidefinite, and has unit diagonal, so it is a correlation matrix (it may be singular, which the library node explicitly allows). Put $f_i=\overline\Phi$ for all $i\in S$: measurable and all nonincreasing. So $p_S\in\mathcal G_{\Sigma_S}$ in the sense of `lib_chi2024_gaussian_dependence`. Each $T_i\sim\mathcal N(0,1)$, and $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$. So $\mathbb P(p_i\le u)=\mathbb P(T_i\ge\overline\Phi^{-1}(u))=u$ for $u\in(0,1)$, which gives $p_S\in\mathcal U^K$. The positive-class condition gives $\Sigma_{ij}\ge0$ for distinct $i,j\in S$. When $K=1$ the off-diagonal condition is vacuous, and $S_1(p_S)=p_i$ is uniform. The level $\alpha=q/c$ lies in $(0,1)$ because $0<q<c\le1$. Claim: $\mathbb P_{N,0,\Sigma}(S_K(p_S)\le q/c)\le q/c$ by `lib_chi2024_positive_gaussian_simes`. The mixture extension is not used.

4. [x] **Markov's inequality.** Since $c_*>0$ and $h=0$ off $E_q$, step 2 gives $E_q\cap\{h\ge c_*\}\subseteq\{g\ge c_*\}$. Here $g\ge0$ is a finite combination of indicators. Markov's inequality, linearity of expectation, and step 3 give
$$
\mathbb P(E_q\cap\{h\ge c_*\})\le\frac{\mathbb E g}{c_*}=\frac1{c_*}\sum_S\pi_S\,\mathbb P\bigl(S_{|S|}(p_S)\le q/c\bigr)\le\frac1{c_*}\sum_S\pi_S\frac qc=\frac{q}{c\,c_*}.
$$
Claim: the stated bound.

## Verification

Step 1 makes the event measurable and reduces $\pi$ to finite weights. Step 2 is a pathwise inclusion valid for every realization on $E_q$. It uses only the BH definition (rejected p-values lie below $q\widehat k_q/N\le qr/N$) and the hitting proportion $m\ge c|S|r/N$ with $m\ge1$. Step 3 checks every hypothesis of `lib_chi2024_positive_gaussian_simes` for each fixed class: Gaussian dependence with latent correlation $\Sigma_S$ through one common nonincreasing transform, uniform marginals under $\theta=0$, nonnegative off-diagonal entries, finite $K\ge1$, and $\alpha\in(0,1)$. Step 4 combines these by Markov's inequality, which gives exactly $q/(c\,c_*)$ for every $c_*\in(0,1]$. Determinism of $\pi$ is used in step 4: the weights $\pi_S$ do not depend on $T$, so $\mathbb E g=\sum_S\pi_S\mathbb P(\cdot)$. No assumption on singularity of $\Sigma$, on $N$, or on the sign pattern outside the support of $\pi$ is needed.

## Assumed definitions

None beyond approved nodes. `gaussian_multiple_testing_model`, `gaussian_test_pvalues`, and `benjamini_hochberg_step_up` are approved. The library theorem `lib_chi2024_positive_gaussian_simes` and its definitions `lib_chi2024_gaussian_dependence` and `lib_chi2024_simes_function_uniform_pvalues` are approved library nodes and are used as black boxes.

## Outcome

Succeeded. The complete proof is under `## Proof` in [Random positive-class cover transfer for the all-null Gaussian Simes event](../assets/gaussian_simes_positive_class_cover_transfer.md). It follows steps 1-4 as planned. The proof also checks the identity $E_q=\{r\ge1\}$, using $r\ge\widehat k_q$. The only cited result is Theorem 8(I) of [the positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md), applied to each fixed positive class $S$ with latent correlation $\Sigma_S$; its mixture extension is not used. No draft definitions are assumed: `gaussian_multiple_testing_model`, `gaussian_test_pvalues`, `benjamini_hochberg_step_up` and the two library definitions are approved.

## Verdict

confirmed

Checked step by step against the statement and the exact statement of `lib_chi2024_positive_gaussian_simes` (Theorem 8(I)) with its definitions `lib_chi2024_gaussian_dependence` and `lib_chi2024_simes_function_uniform_pvalues`.

- Step 1: there are finitely many classes and $\pi$ is a deterministic weight vector; $\widehat k$, $\mathcal A$, $r$, $E_q$ and $h$ are Borel. The identity $E_q=\{r\ge1\}$ holds because $r\ge\widehat k$: the indices of $p_{(1)},\dots,p_{(\widehat k)}$ are all rejected.
- Step 2: on $E_q$ every rejected $p_i\le q\widehat k/N\le qr/N$. A charged class has $m=|\mathcal A\cap S|\in[1,K]$ with $m\ge cKr/N>0$, so $p^S_{(m)}\le qr/N$ and $S_K(p_S)\le (K/m)\,qr/N\le q/c$. The inequalities go the right way, and the only division is by $m\ge1$ and by $cKr/N>0$. Hence $h\le g$ on $E_q$.
- Step 3: every hypothesis of Theorem 8(I) holds for each fixed class. $T_S$ is centered jointly Gaussian with covariance $\Sigma_S$, which has unit diagonal, so the variances are positive and $\Sigma_S$ is a correlation matrix; the library node explicitly allows a singular one. All $f_i=\overline\Phi$ are measurable and nonincreasing, so $p_S\in\mathcal G_{\Sigma_S}$. Uniform marginals are verified directly, the off-diagonal entries of $\Sigma_S$ are nonnegative by the definition of a positive class (vacuous when $K=1$), and $\alpha=q/c\in(0,1)$ because $q<c\le1$. The proof does not use the mixture extension.
- Step 4: since $c_*>0$ and $h=0$ off $E_q$, we get $E_q\cap\{h\ge c_*\}\subseteq\{g\ge c_*\}$. Markov's inequality and linearity, using the deterministic weights $\pi_S$, give $q/(c\,c_*)$.

No gaps needed closing.
