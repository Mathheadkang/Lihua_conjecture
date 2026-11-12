---
type: candidate
title: Antipodal rank-one Gaussian nulls do not violate the radial bounds
status: failed
target_asset: multifactor_radial_fdr_bounds
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 4
direction: known_counterexamples
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:39:44.119Z'
extension_version: 0.0.4
---

## Object

Take $m=2$, $d=1$, $q=1/100$, $\theta_1=\theta_2=0$, and scalar loadings $a_1=1$, $a_2=-1$. Let $Z,\varepsilon_1,\varepsilon_2$ be mutually independent standard normal variables and set $T_1=Z$, $T_2=-Z$. This is the singular, perfectly negatively correlated Gaussian design. Check both testing tracks separately on this same object.

The known finite-level Gaussian FDR inflation discussed in the cited paper is a reason to examine singular and oppositely oriented loading designs. This elementary endpoint design itself has FDR exactly $q$; strict inflation above $q$ would not suffice to refute the target either.

## Checks

### H1

Pass. The numbers $m=2$ and $d=1$ are positive integers, and the means and loadings are deterministic.

### H2

Pass. Both loading norms equal one, so the representation has independent residuals with zero coefficients and covariance

$$
\Sigma(A)=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$

This matrix is positive semidefinite with unit diagonal; singularity is explicitly allowed.

### H3

Pass. Both means are zero. Thus $I_0=\{1,2\}$ and $\pi_0=1$ under either track. Moreover $r_1=r_2=1$ and $\gamma_1=\gamma_2=0$.

### H4

Pass. The level $q=1/100$ lies in both required ranges: $0<q<1/2$ and $0<q\leq2\overline\Phi(1)$.

### H5

Pass. Apply ordinary BH, including its largest-rank rule and non-strict inequalities, to the stated Gaussian p-values. Since $d=1$, $b=\overline\Phi^{-1}(q/2)$, so $\Delta_1=\log2$ and $\Delta_2=0$.

### NOT

Fail. For one-sided tests the p-values are $p_1=\overline\Phi(Z)$ and $p_2=\overline\Phi(-Z)=1-p_1$. The second ordered p-value is at least $1/2>q$, so rank two cannot qualify. Rank one qualifies exactly when $p_1\leq q/2$ or $p_1\geq1-q/2$. Since $p_1$ is uniform, this event has probability $q$. All hypotheses are null, and hence the FDR is $q=0.01$, whereas the proposed bound equals

$$
q\left(\frac32+\log2\right)>q.
$$

For two-sided tests the p-values are identical: $p_1=p_2=2\overline\Phi(|Z|)$. BH rejects both exactly when this common uniform p-value is at most $q$. Its FDR is again $q=0.01$, whereas the proposed bound is $3q/2=0.015$. The cap at one is inactive in both calculations.

## Failure

NOT fails: both testing tracks have FDR exactly $q$, strictly below their finite-level radial bounds even though every null loading has norm one.
