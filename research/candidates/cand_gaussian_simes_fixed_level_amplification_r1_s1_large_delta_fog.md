---
type: candidate
title: Large delta with single-test witness (delta above 1 - alpha_0)
status: failed
target_asset: gaussian_simes_fixed_level_amplification
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  NOT: unknown
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:06:58.701Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Parameters $\alpha_0=1/2$, $\delta=9/10$, $t=1/4$. Witness for the left side $B(t)$: $N=1$, $\Sigma=(1)$, so $p_1=\overline\Phi(T_1)$ is uniform on $(0,1)$ and $\mathbb P(E_t)=\mathbb P(p_1\le t)=t$.

The claimed bound at $t$ is $\frac{2\log(1/\delta)}{\alpha_0}t=4\log(10/9)\cdot\tfrac14=\log(10/9)\approx0.1054<0.25$, so the conclusion would fail if the hypothesis held.

## Checks

### H1

$\alpha_0=1/2\in(0,1)$: pass.

### H2

$\delta=9/10\in(0,1)$: pass.

### H3

Hypothesis $B(\alpha_0)\le1-\delta=1/10$. The single-test model $N=1$, $\Sigma=(1)\in\mathcal C_1$ gives $\mathbb P_{1,0,\Sigma}(E_{1/2})=\mathbb P(p_1\le1/2)=1/2$, so $B(1/2)\ge1/2>1/10$: fail.

General form: $B(\alpha)\ge\alpha$ for every $\alpha$ (take $N=1$), so H3 forces $1-\delta\ge\alpha_0$, i.e. $\delta\le1-\alpha_0$. Then $\log(1/\delta)\ge\log(1/(1-\alpha_0))\ge\alpha_0$, so the constant $2\log(1/\delta)/\alpha_0$ is at least $2$. Every degenerate witness with $\mathbb P(E_t)=t$ (the case $N=1$; the all-ones $\Sigma$, where all $p_i$ coincide and $E_t=\{p_1\le t\}$; the antithetic pair $\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$ with $t<1/2$, where $E_t=\{\min(p_1,1-p_1)\le t/2\}$) therefore satisfies the conclusion whenever H3 holds.

### H4

$t\in(0,\alpha_0/2]$: $1/4=\alpha_0/2$ (endpoint). Not reached: unknown.

### NOT

Unknown (not reached).

## Failure

H3 fails: $B(\alpha)\ge\alpha$ via $N=1$, so $\delta=9/10>1-\alpha_0$ is not admissible; admissible $\delta\le1-\alpha_0$ makes the constant at least $2$.
