---
type: candidate
title: Singular antithetic Gaussian pair at a small BH level
status: failed
target_asset: gaussian_bh_conditional_subpoisson_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:22:44.063Z'
extension_version: 0.0.4
---

## Object

Let $Z\sim N(0,1)$, $N=2$, $I_0=\{1,2\}$, $q=1/100$, and let $\mathcal H$ be the trivial sigma-field. Set
$$
T_1=Z,\qquad T_2=-Z,\qquad U=\overline\Phi(Z),\qquad (P_1,P_2)=(U,1-U),\qquad K=1.
$$
Here $U$ is uniform on $(0,1)$. The object tests the permitted singular-covariance boundary while retaining a nontrivial claimed upper bound.

## Checks

### H1

Pass. $N=2$ is a positive integer, the original null set is deterministic, $q=1/100\in(0,1)$, and both p-values lie in $[0,1]$.

### H2

Pass. There are no alternatives, so the trivial conditioning sigma-field contains their complete empty p-value vector. Conditional expectations equal unconditional expectations.

### H3

Pass. Run the prescribed ordinary BH rule with non-strict comparisons and both original null labels. The second rank never qualifies because $\max(U,1-U)\ge1/2>q$. Thus $R=V=1$ exactly when $U\le q/2$ or $U\ge1-q/2$, and otherwise $R=V=0$. Both boundary events have probability zero, so these calculations also cover the non-strict convention.

### H4

Pass. The constant $K=1$ is $\mathcal H$-measurable and belongs to $[1,\infty]$.

### H5

Pass. For every $0<s\le q$, the events $\{U\le s\}$ and $\{U\ge1-s\}$ are disjoint. Hence $C(s)$ is Bernoulli with success probability $2s$. For every $\lambda\ge0$,
$$
\mathbb E e^{\lambda C(s)}=1+2s(e^\lambda-1)\le \exp\{2s(e^\lambda-1)\}=\exp\{NKs(e^\lambda-1)\}.
$$
The deterministic calculation holds simultaneously for all the required $s$ and $\lambda$ on one full-measure set.

### H6

Pass. This also meets the Gaussian sufficient-condition branch. The conditional score vector has finite mean zero and the singular PSD covariance
$$
Q=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},
$$
whose eigenvalues are $0$ and $2$ and whose distinct-null covariance is nonpositive. The p-values are the stated Gaussian tail transforms. Each marginal is uniform, so $F_{1,\mathcal H}(s)+F_{2,\mathcal H}(s)=2s$ and the prescribed supremum gives exactly $K=1$.

### NOT

Fail. By the actual BH counts in H3,
$$
\mathbb E[\operatorname{FDP}\mid\mathcal H]=\operatorname{FDR}=\mathbb P(U\le q/2\text{ or }U\ge1-q/2)=q=1/100.
$$
The proposed bound is $\min\{1,4eqK\}=e/25>1/100$. Thus this singular Gaussian boundary case satisfies the conclusion and is not a counterexample.

## Failure

NOT fails: the singular antithetic null pair has FDR exactly $q$, below the claimed $4eq$ bound.
