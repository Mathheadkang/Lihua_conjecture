---
type: candidate
title: Opposite residual null atoms at zero and terminal BH rank
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:17:48.165Z'
extension_version: 0.0.4
---

## Object

For every sample size $m$, take $N=2$, $d=1$, $q=1/4$, $\sigma=1/2$, $\tau=\sqrt{3}/2$, directions $v_1=1$, $v_2=-1$, means $\theta_1=\theta_2=0$, and true tags $\ell_1=\ell_2=1$. Thus
$$
T_1=\tau G+\sigma Z,\qquad T_2=-\tau G+\sigma Z,
$$
where $G,Z$ are independent standard normals. Sample $m$ indices uniformly with replacement, using these exact scores.

This tests two distinct score atoms, disappearance of one atom from the sample, zero rejection, and the terminal rank one. It differs from the board's single-score families: the higher score can qualify alone, and its sampled mass changes its BH threshold.

## Checks

### H1

Pass. The fixed parameters satisfy $0<q=1/4<1/2$ and $0<\sigma=1/2<1$.

### H2

Pass. $N=2,d=1$ are positive integers and the deterministic directions $1,-1$ have unit norm. Their residual Gram matrix is singular, as expressly allowed.

### H3

Pass. Both tags are true and both means are zero, so the required implication $\ell_i=1\Rightarrow\theta_i\le0$ holds. The alternative-tag implication is vacuous.

### H4

Pass. The displayed jointly Gaussian scores have exactly the prescribed common-loading construction; each has variance $\tau^2+\sigma^2=1$.

### H5

Pass. The index sample is iid uniform and independent of $(G,Z)$, and repeated indices retain the original scores without extra Gaussian noise.

### H6

Pass. Use ordinary non-strict BH at level $q$ for both arrays and their actual largest ranks. Write
$$
B=\sigma Z+\tau|G|,\qquad C=\sigma Z-\tau|G|,\qquad u(r)=S^{-1}(qr).
$$
Let $P$ be the sampled fraction of the index with score $B$, choosing index 1 on the probability-zero event $G=0$. Conditional on $G$, $mP$ is $\operatorname{Binomial}(m,1/2)$ with a distribution independent of $G,Z$. In particular, $P$ is independent of $(|G|,Z)$.

On $\{C\ge u(1)\}$, all original and sampled scores have p-value at most $q$, so $\rho_N=\rho_m=1$. On its complement, exact finite-grid BH gives
$$
\rho_N=\tfrac12\mathbf1_{\{B\ge u(1/2)\}},\qquad
\rho_m=P\mathbf1_{\{B\ge u(P)\}},
$$
where the last expression is defined to be zero for $P=0$. Indeed, when the lower score has p-value greater than $q$, no rank containing that score qualifies; among copies of the higher score the largest possible qualifying normalized rank is precisely their total mass. This formula also includes $P=1$ and all equality cases. Because every tag is true, $D_j=\mathbf1_{\{\rho_j>0\}}$ for $j=N,m$.

### NOT

Fail. An explicit uniform-in-$m$ bound tends to zero. Put
$$
\delta=|P-1/2|,\quad J_N=\mathbf1_{\{B\ge u(1/2)\}},\quad
J_m=\begin{cases}\mathbf1_{\{B\ge u(P)\}},&P>0,\\0,&P=0.\end{cases}
$$
On the terminal-rank event both discrepancies vanish. On its complement the preceding formulas yield
$$
|D_m-D_N|+|\rho_m-\rho_N|
\le\delta+\tfrac32|J_m-J_N|.
$$
Let
$$
L=\sup_{1/4\le r\le3/4}\frac{q}{\phi(S^{-1}(qr))}<\infty,
\qquad c=\frac{L}{\sigma\sqrt{2\pi}}.
$$
Conditional on $|G|$ and $P$, the score $B$ has a Gaussian density bounded by $1/(\sigma\sqrt{2\pi})$. Thus, for $1/4\le P\le3/4$, the probability that $B$ lies between the two thresholds is at most $c\delta$. Markov's inequality gives
$$
\mathbb P\{P\notin[1/4,3/4]\}\le4\mathbb E\delta,
\qquad
\mathbb E|J_m-J_N|\le(c+4)\mathbb E\delta.
$$
Finally $\mathbb E\delta\le\sqrt{\operatorname{Var}P}=1/(2\sqrt m)$, so
$$
\mathbb E\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]
\le\frac{7+\tfrac32c}{2\sqrt m}\longrightarrow0.
$$
This bound covers missing atoms $P=0,1$ through the bad-frequency event. The argument uses no monotonicity of FDP. It rules out this fixed two-atom family only and does not establish compression for general models.

## Failure

NOT fails: common-shift Gaussian smoothing makes the distinct-atom threshold switch probability at most a constant times the binomial mass error, giving an explicit $O(m^{-1/2})$ discrepancy bound.
