---
type: candidate
title: Zero-loading null at the central-contribution level endpoint
status: failed
target_asset: gaussian_bh_one_sided_free_central_window_core
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T22:40:10.866Z'
extension_version: 0.0.4
---

## Object

Take $N=d=1$, $\theta_1=0$, $a_1=0$, and $q=1/10$. Let $Z,\varepsilon_1$ be independent standard normal variables. Thus $T_1=\varepsilon_1$, $r_1=0$, $s_1=1$, $\gamma_1=1$, and $p_1=\overline\Phi(\varepsilon_1)$. Use the prescribed central-event convention $Y_1=-\infty$.

## Checks

### H1

The positive dimensions, deterministic mean and loading, norm bound, Gaussian factors, and independent Gaussian residual satisfy the multifactor definition exactly.

### H2

Use the one-sided track. The mean $\theta_1=0\le0$ makes $I_0=\{1\}$. The zero-loading central-event convention is exactly the convention in the statement.

### H3

The level $q=1/10$ satisfies both $0<q<1/2$ and the narrower range $0<q\le1/10$ of consequence (i). Here $U=\overline\Phi^{-1}(1/10)=1.2815515655446006$.

### NOT

For one test, ordinary BH rejects exactly when $p_1\le q$, equivalently $\varepsilon_1\ge U$. On rejection its count is one, and the central event holds surely. Hence $\mathrm{Ce}=q=0.1$. The proposed bound is

$$
q\left(\frac12+\frac{U}{\sqrt{2\pi}}\right)=0.10112651040103891>0.1.
$$

This is also an exact comparison: $U>\sqrt{\pi/2}$ since $\overline\Phi(\sqrt{\pi/2})>1/10$, as stated in the target. Thus the claimed consequence holds for this endpoint object.

## Failure

NOT fails: the zero-loading endpoint has central contribution $0.1$, below the claimed bound by approximately $0.00112651040103891$.
