---
type: candidate
title: Two antipodal unit-loading nulls
status: failed
target_asset: gaussian_bh_radial_strip_refinement_defined_entropy
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 582355e827b2c8daf9f48064719117ca7fdba4dbdf5b11f0c912cc329dca2dad
performed_by: unknown
created_at: '2026-11-06T23:19:24.051Z'
extension_version: 0.0.4
---

## Object

The search board contains no prior obstruction or near-miss. Take the smallest model with opposite nonzero null directions: $N=2$, $d=1$, $\theta_1=\theta_2=0$, $a_1=1$, $a_2=-1$, and $Z,\varepsilon_1,\varepsilon_2$ independent standard normals. Thus $T_1=Z$, $T_2=-Z$, $r_1=r_2=1$, and $s_1=s_2=0$. Use $G_1=\{1\}$, $G_2=\{2\}$, $v_1=1$, $v_2=-1$. Let $q$ range over the entire allowed interval $(0,1/2)$; the same fixed model supplies a sequence as $q\downarrow0$.

## Checks

### H1

Pass. The positive integers are $N=2,d=1$, the means and loadings are deterministic, and both loading norms equal one, as permitted.

### H2

Pass. The stipulated independent Gaussian variables give exactly the required representation. Its singular covariance has diagonal entries one and off-diagonal entries minus one.

### H3

Pass. For every $0<q<1/2$, both means are true nulls, so $m_0=N=2>0$ and $\pi_0=1$. Apply precisely the ordinary BH rule in the target.

### H4

Pass. The displayed sets partition the nulls, the two vectors are unit vectors, and $a_i=r_i v_i$. The masses normalized by $N$ are $\pi_1=\pi_2=1/2$. Consequently $\mathcal E_0=\log 2$, $\overline\gamma_0=0$, and $b_1=b_2=\overline\Phi^{-1}(q/2)>U=\overline\Phi^{-1}(q)>0$.

### H5

Pass. The target's extended conventions give $C_{11}=C_{22}=+\infty$ and $A(1/2,0)=+\infty$. Therefore $\mathcal E_{\min}=\log 2$ and $\mathcal E_s=+\infty$; no undefined quotient occurs.

### NOT

Fail. Write $P=\overline\Phi(Z)$, which is uniform on $(0,1)$. The p-values are $P,1-P$. Rank two cannot qualify because their maximum is at least $1/2>q$. Rank one qualifies exactly when $P\le q/2$ or $P\ge1-q/2$, disjoint events of total probability $q$. Both hypotheses are null, hence $\operatorname{FDR}=q$.

The proposed finite RS bound becomes $q\le q(3/2+\log 2)$ and holds strictly for every allowed $q$. Both entropy comparison expressions equal $\log2$ before the final upper bound $+\infty$, so the comparisons hold. The threshold comparison holds because, with $h(x)=\phi(x)/\overline\Phi(x)>x$ for $x>0$,
$$
\log2=\int_U^{b_1}h(x)\,dx\ge U(b_1-U).
$$
For the fixed-model sequence $q\downarrow0$, $\mathcal E_{\min}=\mathcal E_0=\log2=o(\sqrt{\log(1/q)})$ and $\operatorname{FDR}/(q\sqrt{\log(1/q)})=1/\sqrt{\log(1/q)}\to0$. The corollary and its applicable sufficient condition therefore hold. The alternative sufficient condition using $\mathcal E_s$ is not met.

## Failure

NOT fails: exact antipodal dependence gives FDR $q$, while the finite bound, entropy comparisons, and applicable asymptotic corollary all hold.
