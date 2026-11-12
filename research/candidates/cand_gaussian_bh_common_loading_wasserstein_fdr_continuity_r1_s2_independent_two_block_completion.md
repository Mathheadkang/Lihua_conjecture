---
type: candidate
title: Independent opposing residual blocks at an alternative-tagged zero limit
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:42:21.565Z'
extension_version: 0.0.4
---

## Object

Take $q=1/4$, $\sigma=\tau=1/\sqrt2$, $\mathcal H=\mathbb R$ and independent standard normals $\xi,Z$, with $X(v)=v\xi$.
For $0<w<1$ and $\epsilon\ge0$ set
$$
\pi_{w,\epsilon}=w\delta_{(0,1,1)}+(1-w)\delta_{(\epsilon,-1,0)}.
$$
The proposed limit is $\pi=\pi_{1/2,0}$, and the explicit approximating sequence is
$$
w_n=\frac12+\frac1{n+3},\qquad \epsilon_n=\frac1n,\qquad
\pi_n=\pi_{w_n,\epsilon_n}\quad(n\ge1).
$$
The two distinct scores are $T_0=(\xi+Z)/\sqrt2$ and $T_A=\epsilon+(-\xi+Z)/\sqrt2$. This smallest mixed-label example tests the completed alternative zero, two competing block ranks, rank zero, and rank one. The checks below establish the four conclusions on this explicit family and sequence, not continuity for arbitrary population laws.

## Checks

### H1

The fixed constants satisfy $q\in(0,1/2)$ and $\sigma\in(0,1)$; $\mathbb R$ is nonzero, separable and real.

### H2

Both directions have norm one. The true point has mean zero and the alternative point has nonnegative mean. Both laws are deterministic probability measures with finite first mean moment. The alternative zero in $\pi$ is used only in the permitted completion; every $\pi_n$ has strictly positive alternative mean.

### H3

$X(v)=v\xi$ is the prescribed finite series representative, and $Z$ is independent of $\xi$. Each score has variance one. Their covariance is $(-1+1)/2=0$, so the two scores, and their p-values $U=S(T_0)$ and $P=S(T_A)$, are independent. Here $U$ is uniform and
$$
G_\epsilon(t):=\mathbb P(P\le t)=S(S^{-1}(t)-\epsilon).
$$

### H4

Move the alternative mean by $\epsilon_n$, costing at most $\epsilon_n$, and move excess mass $w_n-1/2$ between the two zero-mean tagged points, costing $3(w_n-1/2)$ because their direction distance is two and tag distance is one. The triangle inequality gives
$$
W_1(\pi_n,\pi)\le\frac1n+\frac3{n+3}\longrightarrow0.
$$

### NOT

**Conclusion 1.** The two-point sums defining $H,V$ are measurable. Every positive largest rank belongs to $\{w,1-w,1\}$: if $H(r)\ge r>0$, put $s=H(r)$; monotonicity gives $H(s)\ge s$, and $s$ is one of those three values. At a largest positive rank, $H(\rho)>\rho$ would give the larger qualifying rank $H(\rho)$, a contradiction. Thus $H(\rho)=\rho$, the rank is attained, and $0\le V(\rho)/\rho\le1$. Rank one occurs exactly when $U,P\le q$; rank zero includes $U,P>q$. All finite sums and the maximum over three measurable candidate ranks are measurable. The finite series is defined everywhere. A representative change on a product-null set changes neither score on any positive-mass atom outside one Gaussian-null set; taking a countable union proves the same assertion simultaneously for this sequence and its limit. Hence all well-definedness and representative assertions hold on the tested countable family, including endpoints and competing ranks.

**Conclusion 2.** The only true score has mean zero, so its conditional marginal is exactly $F_z(t)$, and the requested comparison holds with equality. To check integrability for every fixed $z,b$, change variables $u=S^{-1}(t)$:
$$
\int_{(0,b]}\frac{dF_z(t)}t
=\int_{S^{-1}(b)}^\infty
\frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du.
$$
On the finite portion the integrand is continuous. For large positive $u$, a Gaussian Mills bound bounds it by a constant depending on $z$ times $(1+u)\exp(-u^2/2+\sqrt2zu)$, which is integrable. For $E_a=\{0<\rho\le a\}$, rejection of the true block implies $U\le q\rho\le qa$ and $1/\rho\le q/U$. Consequently, for every $a\in(0,1)$,
$$
D\mathbf1_{E_a}\le\frac{qw}{U}\mathbf1_{\{U\le qa\}},\qquad
\mathbb E[D\mathbf1_{E_a}\mid Z=z]
\le\min\left\{1,qw\int_{(0,qa]}\frac{dF_z(t)}t\right\}
\le\min\left\{1,q\int_{(0,qa]}\frac{dF_z(t)}t\right\}.
$$
The last bound is common to every member of this family, including all $n$. Its integral tends to zero for each $z$ by the established integrability, and dominated convergence applies after the minimum with one. Thus the microscopic estimate and its limit hold on the entire tested family. This verifies the object against this clause without asserting that a two-block calculation proves the target's supremum over all laws.

**Conclusion 3.** The exact FDP formula, retaining the largest rank, is
$$
D=\mathbf1_{\{U\le qw,\ P>q\}}+
w\mathbf1_{\{U\le q,\ P\le q\}}.
$$
The first event rejects the true block alone at rank $w$, and the second rejects both blocks at rank one. On all other events the true rejection count is zero. Independence therefore gives, for every $w,\epsilon$ in the family,
$$
F_{\pi_{w,\epsilon}}=qw(1-G_\epsilon(q))+wqG_\epsilon(q)=qw.
$$
In particular $F_\pi=q/2$ and $F_{\pi_n}=qw_n\to q/2$. This directly verifies continuity on the constructed sequence and, more generally, any sequence within this family with $w_n\to w$; it makes no assertion about other convergent sequences.

**Conclusion 4.** Write $w_n=(n+5)/(2n+6)$. Realize $\pi_n$ by $n+5$ identical true-score copies and $n+1$ identical alternative-score copies, with $N_n=2n+6$. Every copy has variance one; the covariance matrix is the positive semidefinite block matrix with all-ones diagonal blocks and zero off-diagonal blocks. The alternative mean $1/n>0$ gives the canonical labels. For an empirical law with denominator $N_n$, a qualifying population rank can be increased to its count $j/N_n$; hence the largest population rank is exactly the largest qualifying ordinary BH rank divided by $N_n$. Rejection counts and true counts are the same multiples of $1/N_n$, so the finite BH FDP equals $D_{\pi_n}$ samplewise. Its FDR is $qw_n\to q/2$. Replication by any positive integer preserves the empirical law, so it preserves rank fraction, FDP and FDR samplewise. Thus the analytic-zero value in this object is a limit of canonical finite-model values and creates no larger supremum within this tested family.

All four clauses tested on the proposed object and sequence are consistent with the target; there is no violated conclusion.

## Failure

NOT fails: the mixed two-block FDR is exactly $qw$, and the completed limit is obtained by canonical rational finite arrays with $F_{\pi_n}\to F_\pi=q/2$; the other conclusion clauses also hold for this explicit family.
