---
type: candidate
title: Empty original null set in a three-group compensated-clone model
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:05:52.404Z'
extension_version: 0.0.4
---

## Object

Take $N=3$, $\theta=(1,2,3)$, $\Sigma=I_3$, $q=1/4$, and $i=1$. Let $d=3$, $G\sim\mathcal N_3(0,I_3)$, and $v_j=e_j$. Thus $T_j=j+G_j$. All original hypotheses are alternatives, so $I_0=\varnothing$. Use the target's exact compensated private-clone construction with independent standard normal $\xi_b$, and restrict to $0<\varepsilon<1/4$.

This tests the empty-null-set boundary, rather than a parameter refinement of the board's negative-null singleton or its two-group mixed-label example. Their saddle and fractional-null calculations do not cover this structural case: here the entire FDP function, and therefore every signed face jump, vanishes. The object has three original groups so its population crossing still includes two distinct exact-copy steps.

## Checks

### H1

The original model is finite, $N=3\ge1$, and $\theta=(1,2,3)\in\mathbb R^3$.

### H2

The covariance $I_3$ has unit diagonal and is positive definite, since $x^{\mathsf T}I_3x=\|x\|^2>0$ for every nonzero $x\in\mathbb R^3$.

### H3

The level satisfies $q=1/4\in(0,1/2)$.

### H4

The chosen index is $i=1\in[3]$, and $\theta_1=1\ne0$.

### H5

The representation $v_j=e_j$ is finite dimensional, its rows have norm one, and $v_j\cdot v_k=\delta_{jk}=\Sigma_{jk}$. The displayed Gaussian scores therefore have exactly the required joint law. For the signed-measure coordinates one may take $U_1(y_1,y_2)=(0,y_1,y_2)$.

### H6

Use the one-sided p-values $S(T_j)$, labels $I_0=\{j:\theta_j\le0\}=\varnothing$, and ordinary largest-rank BH with its non-strict thresholds, both before and after cloning.

### H7

For every positive integer $K$, groups 2 and 3 each have $K$ exact copies. Group 1 has exactly the required scores
$$
T_{1b}^{K,\varepsilon}=1+d_\varepsilon+\frac{G_1+\varepsilon\xi_b}{\sqrt{1+\varepsilon^2}},
\qquad
s=\frac{\varepsilon}{\sqrt{1+\varepsilon^2}},\quad
\phi(t_s)=s,\quad d_\varepsilon=s(t_s+t_s^{-1}),
$$
where all $\xi_b$ are independent standard normals independent of $G$. Each marginal has variance one and all expanded scores are jointly Gaussian.

### H8

For $0<\varepsilon<1/4$, one has $0<s<1/4<\phi(0)$, so $t_s>0$ exists. Since $d_\varepsilon>0$, the chosen mean remains positive. All expanded means are positive, and the actual expanded null set is exactly $I_0\times[K]=\varnothing$.

### H9

The original $N,\theta,\Sigma,q,i$ and representation are fixed independently of $K$ and $\varepsilon$. The limits are tested in the required order: $K\to\infty$ for each fixed positive $\varepsilon$, then $\varepsilon\downarrow0$.

### NOT

Both conclusions hold, so this check fails. First, the empty actual null set gives $F_{K,\varepsilon}=0$ for every $K$ and admissible $\varepsilon$, and $F=0$. Consequently the finite-copy limit exists. The definition gives $J_\varepsilon(x,G)=0$ for every $x,G$, hence $D_\varepsilon(G)=0$ and
$$
F_{\infty,\varepsilon}=0=\mathbb E_G D_\varepsilon(G).
$$

The required equality at the population crossing also holds pointwise. Fix $G\in\mathbb R^3$ and an admissible $\varepsilon$. Set $x_j=12S(T_j)>0$ for $j=2,3$. On $[0,3]$,
$$
H_\varepsilon(x,G)=\mathbf1\{x\ge x_2\}+\mathbf1\{x\ge x_3\}+b_\varepsilon(x,G),
$$
with the exact-group indicators zero at $x=0$. The function $b_\varepsilon$ is continuous on $[0,3]$, vanishes at zero, and lies strictly between zero and one on $(0,3]$. Therefore $H_\varepsilon$ is upper semicontinuous and right continuous, with only upward jumps. The set $\{x\in[0,3]:H_\varepsilon(x,G)\ge x\}$ is closed and nonempty. Its maximum is $\rho_\varepsilon(G)$. Since $H_\varepsilon(3,G)\le2+b_\varepsilon(3,G)<3$, this maximum is less than 3. If it is positive and $H_\varepsilon(\rho_\varepsilon,G)>\rho_\varepsilon$, right continuity would preserve the strict positive difference at some slightly larger $x<3$, contradicting maximality. Hence $H_\varepsilon(\rho_\varepsilon,G)=\rho_\varepsilon$ whenever $\rho_\varepsilon>0$.

Finally, with the original labels fixed at $I_0=\varnothing$, the original FDP $f(t)$ is identically zero for every score vector, regardless of BH rank cascades. Thus $\Delta_{1,r}(y)=0$ and $\mu_{1,r}=0$ for each $r=1,2,3$. Both sides of the compensated variation formula are exactly zero:
$$
\lim_{\varepsilon\downarrow0}\frac{F_{\infty,\varepsilon}-F}{s/t_s}=0
=\sum_{r=1}^3\log\{r h(u_r)\}\,\mu_{1,r}(\mathbb R^2).
$$

## Failure

NOT fails: the empty actual null set forces both finite-copy FDR and every signed face measure to vanish, while the population crossing satisfies the stated equality.
