---
type: candidate
title: Critical two-atom BH branch under random composition
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:17:48.165Z'
extension_version: 0.0.4
---

## Object

Fix any admissible q and sigma. Take N=2, d=1, v_1=v_2=1, theta_1=0, theta_2=c>0, and tags ell_1=1, ell_2=0. Let tau=sqrt(1-sigma^2) and Y=tau G+sigma Z. Thus the scores are Y and Y+c, with Y standard normal. Sample the two indices independently with replacement, and let P be the sampled true-tag proportion, so mP has distribution Binomial(m,1/2), independently of Y.

This tests the critical-atom mechanism: a half-mass alternative atom lies on its own BH boundary when S(Y+c)=q/2, and sampling moves that boundary to q(1-P). Unlike the previously excluded single-score family, the two scores are distinct for every realization. The parameter c may depend on m; the estimate below is uniform over c>0.

## Checks

### H1

Pass: q lies in (0,1/2), and sigma lies in (0,1), fixed independently of m.

### H2

Pass: N=2 and d=1 are positive integers. The sampled size m is any positive integer.

### H3

Pass: both deterministic directions are the unit vector 1 in R. Their residual Gram matrix is singular, as permitted.

### H4

Pass: theta_1=0 with true tag 1, and theta_2=c>0 with alternative tag 0, satisfy the required sign conditions.

### H5

Pass: G and Z are independent standard normals and T_1=tau G+sigma Z, T_2=c+tau G+sigma Z have exactly the prescribed common-loading representation.

### H6

Pass: the indices are iid uniform on {1,2}, independently of G and Z. Repeated indices give exact copies. The resulting true-tag proportion P is independent of Y.

### H7

Pass: use ordinary non-strict largest-rank BH at the original level q. Write p_0=S(Y) and p_c=S(Y+c), so p_c<p_0. For an empirical true-tag proportion p, its exact normalized rank and FDP are

$$
\rho(p)=\begin{cases}1,&p_0\le q,\\(1-p)\mathbf1_{\{p_c\le q(1-p)\}},&p_0>q,\end{cases}
\qquad D(p)=p\mathbf1_{\{p_0\le q\}}.
$$

These formulas include p=0 and p=1. If p_0<=q, all sampled tests qualify at terminal rank one. If p_0>q and any true-tag tests are present, no true-tag test can be rejected, because every BH threshold is at most q; all alternative copies qualify exactly at their own largest possible rank 1-p when p_c<=q(1-p). Consequently the full model uses p=1/2 and the sampled model uses p=P. All threshold equalities use the required non-strict convention.

### NOT

Fail: both expected discrepancies converge uniformly over c>0. Put delta=P-1/2 and E={|delta|<=1/4}. Independence and the uniformity of p_0 give

$$
\mathbb E|D(P)-D(1/2)|=q\mathbb E|\delta|\le\frac{q}{2\sqrt m}.
$$

Let u(t)=S^{-1}(t) and

$$
L_q=\sup_{q/4\le t\le3q/4}|u'(t)|<\infty,
\qquad C_q=\frac{qL_q}{\sqrt{2\pi}}.
$$

On E, for each fixed P, the indicators at the two alternative-only boundaries can differ only when p_c lies between q(1-P) and q/2. In terms of Y this is an interval of length at most qL_q|delta|, translated by -c. Its standard normal probability is at most C_q|delta|, uniformly over c. For x=1-P, the elementary inequality

$$
\left|x\mathbf1_{\{p_c\le qx\}}-\frac12\mathbf1_{\{p_c\le q/2\}}\right|
\le |\delta|+\frac12\left|\mathbf1_{\{p_c\le qx\}}-\mathbf1_{\{p_c\le q/2\}}\right|
$$

therefore bounds the conditional expected rank difference by (1+C_q/2)|delta| on E. Restricting additionally to p_0>q can only decrease this bound; on p_0<=q the rank difference is zero. On the complement of E the difference is at most one. Since Var(P)=1/(4m), Chebyshev's inequality gives P(E^c)<=4/m. Hence

$$
\mathbb E\bigl[|D(P)-D(1/2)|+|\rho(P)-\rho(1/2)|\bigr]
\le\frac{1+q+C_q/2}{2\sqrt m}+\frac4m\longrightarrow0.
$$

For q in any compact subset of (0,1/2), C_q is uniformly bounded. The boundary composition instability is thus averaged away even with distinct scores and an alternative-only competing crossing. This family does not refute the asserted uniform approximation.

## Failure

NOT fails: the two distinct score atoms produce at most order m^{-1/2} expected FDP and rank error, uniformly over their positive mean separation.
