---
type: candidate
title: Equality delta = 1 - alpha_0 at the endpoint t = alpha_0/2
status: failed
target_asset: gaussian_simes_fixed_level_amplification
checks:
  H1: pass
  H2: pass
  H3: unknown
  H4: pass
  NOT: fail
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

Parameters at the boundary of every hypothesis: $\alpha_0=1/2$, $\delta=1-\alpha_0=1/2$ (largest $\delta$ compatible with $B(\alpha_0)\ge\alpha_0$), $t=\alpha_0/2=1/4$ (right endpoint, where $\lfloor\alpha_0/t\rfloor=2$ is smallest). The claimed bound is $\frac{2\log 2}{1/2}\cdot\frac14=\log2\approx0.693$. Witness $\Sigma\in\mathcal C_N$ arbitrary (any $N$, singular allowed).

## Checks

### H1

$\alpha_0=1/2\in(0,1)$: pass.

### H2

$\delta=1/2\in(0,1)$: pass.

### H3

$B(1/2)\le1/2$, i.e. the all-null Gaussian Simes test at level $1/2$ is exactly valid over all correlations. The lower bound $B(1/2)\ge1/2$ holds ($N=1$), but no upper bound is available here: negatively correlated pairs may push the rejection probability above $1/2$. Unknown.

### H4

$t=1/4\in(0,1/4]$: pass (endpoint).

### NOT

The conclusion cannot fail for any witness once H3 holds. Fix $\Sigma\in\mathcal C_N$ with $q=\mathbb P_{N,0,\Sigma}(E_t)$ and let $m\ge1$ be an integer with $mt\le\alpha_0$. Put $\Sigma^{(m)}=\mathrm{diag}(\Sigma,\ldots,\Sigma)\in\mathcal C_{mN}$ ($m$ independent blocks, singular allowed). If block $j$ has $p^{j}_{(k)}\le tk/N$, then the pooled order statistic satisfies $p_{(k)}\le p^j_{(k)}\le (mt)k/(mN)\le\alpha_0k/(mN)$, so $E_{\alpha_0}$ occurs for the pooled vector. Hence $1-\delta\ge B(\alpha_0)\ge1-(1-q)^m$, so $q\le1-\delta^{1/m}\le\log(1/\delta)/m$ (using $1-e^{-x}\le x$). Here $m=2$: $q\le\tfrac12\log2\approx0.347<\log2$. In general $m=\lfloor\alpha_0/t\rfloor\ge\alpha_0/(2t)$ for $t\le\alpha_0/2$ gives $q\le 2\log(1/\delta)t/\alpha_0$. So NOT fails (conditionally on H3; if H3 fails, the object fails H3).

## Failure

NOT fails: the independent block-diagonal replication of any witness $\Sigma$ (admissible in $\mathcal C_{mN}$) turns one rejection at level $t$ into one at level $\alpha_0$, giving $q\le\log(1/\delta)/m$ with slack factor $2$ even at the boundary $\delta=1-\alpha_0$, $t=\alpha_0/2$.
