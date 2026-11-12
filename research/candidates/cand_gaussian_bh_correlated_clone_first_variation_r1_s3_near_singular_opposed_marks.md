---
type: candidate
title: Near-singular positive correlation with opposite tangent clone marks
status: failed
target_asset: gaussian_bh_correlated_clone_first_variation
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
  H10: pass
  H11: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:10:17.525Z'
extension_version: 0.0.4
---

## Object

Take $N=K=d=2$, $q=1/4$, $i=1$, $\theta=(0,0)$, $\rho=9999/10000$, and $s=\sqrt{1-\rho^2}$. Let $G=(Z,Y)$ have independent standard normal coordinates and take $v_1=(1,0)$, $v_2=(\rho,s)$, $w_1=(0,1)$, $w_2=(0,-1)$, and $c_1=c_2=0$. Thus $T_1=Z$, $T_2=\rho Z+sY$, and the two perturbed scores are $(Z\pm\varepsilon Y)/\sqrt{1+\varepsilon^2}$. Use exactly the prescribed one-sided p-values, actual null labels, and ordinary largest-rank BH procedures. This pushes positive definiteness close to its singular boundary, with nontrivial opposite marks at the null-mean boundary.

## Checks

### H1

Pass: $N=2$ is an integer at least one.

### H2

Pass: $K=2$ is an integer at least one.

### H3

Pass: $q=1/4\in(0,1/2)$.

### H4

Pass: $\theta=(0,0)\in\mathbb R^2$.

### H5

Pass: $\Sigma=\left(\begin{smallmatrix}1&\rho\\\rho&1\end{smallmatrix}\right)$ is unit diagonal and positive definite, with eigenvalues $1\pm\rho>0$ and determinant $1-\rho^2>0$.

### H6

Pass: $G\sim\mathcal N_2(0,I_2)$ and the displayed $v_1,v_2$ are unit rows with Gram matrix $\Sigma$. Hence this is the required finite jointly Gaussian representation.

### H7

Pass: $p_j=\overline\Phi(T_j)$ and $I_0=\{1,2\}$. Both original and expanded procedures use ordinary BH with largest qualifying rank and non-strict inequalities; all four expanded coordinates are nulls.

### H8

Pass: $i=1\in[2]$, $E_i=\{(0,y):y\in\mathbb R\}$, and $w_1,w_2\in E_i$.

### H9

Pass: $c_1=c_2=0\le0$, as required at $\theta_i=0$.

### H10

Pass: every expanded score is exactly the displayed normalized perturbation of group 1 or an exact copy of $T_2$. Its variance is one, its mean is zero, and its actual one-sided null label is preserved for every $\varepsilon\ge0$. The nonzero-mean sign condition is vacuous.

### H11

Pass: face values, jumps, measures, and $g$ are formed with the original two-coordinate grid and fixed labels as prescribed. Here $g(y)=-|y|$, and the formulas below compute the actual jumps, rather than a free rank selector.

### NOT

Fail: this object satisfies all four conclusions. Write $u_1=\overline\Phi^{-1}(1/8)>u_2=\overline\Phi^{-1}(1/4)$.

For exact copies, each qualifying odd rank $2r-1$ forces the following even rank $2r$ to qualify, since its p-value is identical and its BH bound is larger. The largest rank is therefore twice the original largest rank, including ties. This proves conclusion 1 pointwise.

Because all original labels are null,
$$
f(t)=\mathbf1\{\max(t_1,t_2)\ge u_1\text{ or }\min(t_1,t_2)\ge u_2\}.
$$
Consequently, outside finitely many $y$-values,
$$
\Delta_{1,1}(y)=\mathbf1\{\rho u_1+sy<u_2\},\qquad
\Delta_{1,2}(y)=\mathbf1\{u_2<\rho u_2+sy<u_1\}.
$$
Both jumps have magnitude at most one. Therefore the total-variation first-moment bound in conclusion 2 holds, with right side $\phi(u_r)(1+\mathbb E|Y|)<\infty$.

For conclusion 3, put $U_\ell=\overline\Phi^{-1}(\ell/16)$ for $1\le\ell\le4$, and $\delta=\min_{1\le\ell<4}(U_\ell-U_{\ell+1})>0$. If BH partially rejects group 1 at its largest rank $\ell$, one rejected group-1 score is at least $U_\ell$, while an unrejected group-1 score must be strictly below $U_{\ell+1}$: otherwise rank $\ell+1$ would qualify. The clone spread must exceed $\delta$. The spread here is $2\varepsilon|Y|/\sqrt{1+\varepsilon^2}\le2\varepsilon|Y|$, so partial rejection has probability at most
$$
2\exp\{-\delta^2/(8\varepsilon^2)\}.
$$
Group 2 cannot be partly rejected because its scores are identical. If every group is all or none, the selected number of groups is exactly the largest qualifying rank for their minimum scores: any qualifying group rank lifts to a qualifying expanded even rank, and the actual all-or-none expanded rank projects back. Thus the displayed bound also bounds the rejection-set disagreement in conclusion 3.

The reduced scores are $H_1^\varepsilon=(Z-\varepsilon|Y|)/\sqrt{1+\varepsilon^2}$ and $H_2^\varepsilon=\rho Z+sY$. For fixed $y$, define
$$
b_r^\varepsilon(y)=\sqrt{1+\varepsilon^2}\,u_r+\varepsilon|y|,\qquad
d_r(y)=(u_r-sy)/\rho,
$$
$$
m_\varepsilon(y)=\min\{b_1^\varepsilon(y),d_1(y),\max(b_2^\varepsilon(y),d_2(y))\}.
$$
The actual reduced BH event of any rejection is exactly $Z\ge m_\varepsilon(y)$, so its conditional FDP expectation is $\overline\Phi(m_\varepsilon(y))$. At $\varepsilon=0$, the active branch has derivative $|y|$ exactly when either $y<a$ or $b<y<c$, with
$$
a=(u_2-\rho u_1)/s<0,\qquad b=(u_2-\rho u_2)/s>0,\qquad c=(u_1-\rho u_2)/s>b.
$$
The other active branches have derivative zero. Ties between branches lie in a finite set of $y$-values, of Gaussian measure zero. Min and max are Lipschitz in their inputs, and for $0<\varepsilon\le1$,
$$
|m_\varepsilon(y)-m_0(y)|/\varepsilon\le |y|+\max_r|u_r|.
$$
The bounded derivative of $\overline\Phi$ gives an integrable dominating function, justifying differentiation under the $Y$ integral. The exponentially small expanded-versus-reduced error has zero first variation. Hence the actual expanded derivative equals
$$
D=-\phi(u_1)\int_{-\infty}^{a}|y|\phi(y)\,dy
   -\phi(u_2)\int_b^c y\phi(y)\,dy
 =-\phi(u_1)\phi(a)-\phi(u_2)(\phi(b)-\phi(c)).
$$
Using the computed actual jumps and $g=-|y|$ in the proposed signed-face formula gives exactly the same $D$. Numerically, $a\approx-33.641064$, $b\approx0.004769482$, $c\approx33.653968$, and $D\approx-0.126773069$. Thus proximity to singular covariance does not violate conclusion 4 for this fixed positive-definite model.

## Failure

NOT fails: explicit largest-rank BH calculations and a dominated conditional-threshold derivative verify all four conclusions for the nearly singular model.
