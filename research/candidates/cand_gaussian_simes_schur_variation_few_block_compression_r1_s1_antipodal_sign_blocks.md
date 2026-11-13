---
type: candidate
title: >-
  Many independent antipodal sign blocks (entries in {0,+1,-1}, rank n, 2n
  directions)
status: failed
target_asset: gaussian_simes_schur_variation_few_block_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: ae49babfdb545830e8ad7375a17d918e1fb1ba20e49b625bd07dbdd7738fee3a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:45:35.188Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

For $n\ge1$ put $N=2n$ and let $\Sigma=\mathrm{diag}(B,\ldots,B)$ with $n$ copies of $B=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$. So $\Sigma$ is singular of rank $n$, has entries in $\{0,\pm1\}$, and has $2n$ distinct row directions (no clone-block compression with fewer than $2n$ blocks, since distinct rows of $\Sigma$ are distinct). Here $\Sigma\circ\Sigma=\mathrm{diag}(J_2,\ldots,J_2)$ and
$$
R(t)=(1-t)\Sigma+t(\Sigma\circ\Sigma)=\mathrm{diag}\Bigl(\begin{pmatrix}1&r\\r&1\end{pmatrix},\ldots\Bigr),\qquad r=2t-1 .
$$
Thus $Z=(X_1,\ldots,X_n,Y_1,\ldots,Y_n)$ with independent pairs $(X_j,Y_j)$ of correlation $r$. This is the equality/degenerate case "entries of modulus one or zero" of the Schur square, pushed to many directions. Tested at levels $q\to0$ ($q=0.05,0.02,0.005,0.001$, and exactly for $n=1$ down to $q=10^{-4}$) and $n\in\{1,10,30,100,300,1000,3000\}$. Unbalanced versions (sign classes of sizes $a,b$ inside each block) were checked exactly for $n=1$.

## Checks

### H1

$q\in(0,q_2]$: the family is taken along a sequence $q\to0$, so it meets every candidate $q_2$.

### H2

$N=2n$ is a positive integer.

### H3

$\Sigma$ is symmetric, PSD (block diagonal with PSD blocks $B=uu^{\mathsf T}$, $u=(1,-1)$), unit diagonal: $\Sigma\in\mathcal C_N$, singular, as the statement allows.

### NOT

Since $\mathcal M(q)\ge0$ (a supremum of nonnegative variations over a nonempty set), NOT requires $\mathcal V_-(f_{q,\Sigma})>1/8$.

Exact endpoint values. At $t=1$ ($r=1$) each value is duplicated: $p_{(2j-1)}=p_{(2j)}=u_{(j)}$ for $n$ independent uniforms, and $u_{(j)}\le q(2j)/(2n)$ is the Simes event for $n$ independent p-values, so $f(1)=q$. At $t=0$ ($r=-1$) the pair p-values are $(u,1-u)$; thresholds $qk/N\le q<1/2$ only see the $n$ values $v_j=\min(u_j,1-u_j)=w_j/2$ with $w_j$ i.i.d. uniform, and $v_{(k)}\le qk/(2n)$ iff $w_{(k)}\le qk/n$, so $f(0)=q$. For $t\in[1/2,1]$ all correlations are $\ge0$, so $f(t)\le q$ by [the positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md); for every $t$, Hommel's bound gives $f(t)\le qH_N$.

Exact computation for $n=1$ (two clone classes of weights $\alpha,1-\alpha$, bivariate normal integrals): the Simes size is
$$
f=q+\mathbb P\bigl(q\alpha<p_A\le q,\ q(1-\alpha)<p_B\le q\bigr)-\mathbb P\bigl(p_A\le q\alpha,\ p_B\le q(1-\alpha)\bigr).
$$
On a 100-point grid in $r$ (refined near $r=1$), $\mathcal V_-/q=0.179,0.184,0.188,0.190$ for $\alpha=1/2$ and $q=0.05,0.01,10^{-3},10^{-4}$, and about $0.06$ for $\alpha=0.1$. The only dip is near $r\to1$ (min $f/q\approx0.81$).

Numerical (Monte Carlo, common random numbers across a 26-point $t$-grid, so the grid value of $\mathcal V_-$ includes upward-biased noise): $\mathcal V_-/q\approx0.18$ ($n=1$), $0.20$ ($n=10$), $0.24$ ($n=300$) at $q=0.05$; $0.24$ ($n=30$, $q=10^{-3}$, $10^6$ reps); $0.23$ ($n=100$, $q=0.005$); $0.24$ ($n=1000$, $q=0.005$); $0.27$ ($n=3000$, $q=0.02$, 30000 reps). The profile has a single dip (min $f/q\approx0.87$–$0.91$, near $t\approx0.96$) and a bump $\le1.05q$ on the negative side. So $\mathcal V_-\approx0.25q\ll1/8$, with no visible growth in $n$.

NOT fails (numerically for $n\ge2$; exactly for $n=1$).

## Failure

NOT fails: the profile is $q$ at both ends with one shallow dip, so $\mathcal V_-\approx0.2$–$0.27\,q$, independent of the number $2n$ of directions.
