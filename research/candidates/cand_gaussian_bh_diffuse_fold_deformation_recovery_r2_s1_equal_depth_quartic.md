---
type: candidate
title: Equal-depth quartic competing folds fail the isolated-minimum hypothesis
status: failed
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: fail
  H6: unknown
  NOT: unknown
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:44:55.665Z'
extension_version: 0.0.4
---

## Object

Test the equal-depth competing-well mechanism: a distant second fold can prevent a deformation of the first fold from removing the largest forced-true crossing. This is a nonlinear quartic barrier, rather than a parameter change of the previously checked linear quantile.

Take $q=1/4$, $p=1/2$, $\sigma=1/2$, $\mathcal H=\mathbb R^2$, $v_0=e_1$ and $v_1=e_2$. For $c\in[0,1]$ put
$$
r(c)=\frac{1+c}{2},\qquad u(r)=S^{-1}(r/4),\qquad h(c)=(c-1/3)^2(c-2/3)^2,
$$
$$
\vartheta(c)=u(r(c))+2-\frac{h(c)}{100}.
$$
Use independent standard normals $\xi_1,\xi_2,Z$, with $X_0=(\sqrt3/2)\xi_1+Z/2$ and $Y=(\sqrt3/2)\xi_2+Z/2$, and the deterministic tagged law prescribed by this quantile and these two directions.

## Checks

### H1

Pass: $q\in(0,1/2)$ and $p,\sigma\in(0,1)$.

### H2

Pass: $e_1,e_2$ are distinct unit vectors. The displayed scores have unit variances and correlation $\rho=1/4\in(-1,1)$, with the required common loading $\sigma=1/2$.

### H3

Pass: the law is exactly
$$
\pi=\frac12\delta_{(0,e_1,1)}+\frac12\int_0^1\delta_{(\vartheta(c),e_2,0)}\,dc.
$$
Its parameters are deterministic, its true atom has mean zero, and its alternative means are positive by H4 below. All means are bounded, so it is in the prescribed first-moment tagged space.

### H4

Pass: $u(r(c))$ is smooth on this compact rank interval, so $\vartheta\in C^3([0,1])$. Since $r(c)/4\le1/4<1/2$, $u(r(c))>0$. Also $0\le h(c)\le16/81$, hence $\vartheta(c)>2-16/8100>0$.

The derivative is
$$
\vartheta'(c)=-\frac{1}{8\phi(u(r(c)))}-\frac{h'(c)}{100},\qquad
h'(c)=2(c-1/3)(c-2/3)(2c-1).
$$
On $[0,1]$, $|h'|\le8/9$. Since $\phi\le1/\sqrt{2\pi}$,
$$
\vartheta'(c)\le-\frac{\sqrt{2\pi}}8+\frac{8}{900}<0.
$$
Thus the quantile is strictly decreasing and $\vartheta(1)>0$.

### H5

Fail: the barrier is exactly
$$
g(c)=u(r(c))-\vartheta(c)=-2+\frac{(c-1/3)^2(c-2/3)^2}{100}.
$$
Its global minimum $-2$ is attained at both $c=1/3$ and $c=2/3$, so it has no unique global minimizer. This is the first failed hypothesis. The second fold supplies the competing-crossing mechanism only after violating the target's uniqueness requirement.

### H6

Unknown after the first failure: the nondegeneracy condition at the required unique interior global minimizer is not checked.

### NOT

Unknown after the first failure. No FDR-variation or finite-recovery contradiction is asserted for this inadmissible two-well object.

## Failure

H5 fails: the equal-depth quartic has two global minimizers, whereas the target requires a unique global minimum.
