---
type: candidate
title: Irrational mixed tags on a single zero-mean score at the zero-moment boundary
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:46:24.649Z'
extension_version: 0.0.4
---

## Object

Take $q=1/4$, $\sigma=1/2$, $d=1$, $v=1$, $a=1/\sqrt{2}$, and the deterministic completed law
$$
\pi=a\delta_{(0,1,1)}+(1-a)\delta_{(0,1,0)}.
$$
This tests the canonical approximation conclusion at $C=M_2(\pi)=0$, simultaneously with an alternative-tagged zero and irrational tag masses. Both atoms have score $Y=(\sqrt{3}/2)\xi+(1/2)Z$, where $\xi,Z$ are independent standard normals.

## Checks

### H1

Pass. The fixed parameters satisfy $0<q<1/2$, $0<\sigma<1$, and $d$ is a positive finite integer.

### H2

Pass. The law is deterministic and independent of the Gaussian randomness. Both directions have unit norm. The true-tagged mean is nonpositive and the alternative-tagged mean is nonnegative, so both atoms lie in the prescribed closed tagged domain. Moreover $M_2(\pi)=0$, hence $\pi\in\mathcal P_2(\mathcal E)$.

### H3

Pass. Use exactly the full population BH functional. Since both p-values equal $S(Y)$, its largest crossing is $1$ when $S(Y)\le q$, and $0$ otherwise. Therefore
$$
D_\pi=a\mathbf1_{\{S(Y)\le q\}},\qquad F(\pi)=aq.
$$
No rank or crossing is discarded.

### NOT

Fail: canonical approximation, FDR convergence and second-moment convergence all hold explicitly. For every integer $n\ge2$, put $k_n=\lfloor na\rfloor$, $a_n=k_n/n$, and
$$
\nu_n=a_n\delta_{(0,1,1)}+(1-a_n)\delta_{(1/n,1,0)}.
$$
Both multiplicities $k_n,n-k_n$ are positive integers, and both labels are canonical. Couple the tag masses at zero, then move the alternative means to $1/n$. This gives
$$
W_1(\nu_n,\pi)\le |a_n-a|+(1-a_n)/n\longrightarrow0,
\qquad M_2(\nu_n)=(1-a_n)/n^2\longrightarrow0.
$$
For the finite realization, all true nulls have p-value $S(Y)$ and all alternatives have p-value $S(Y+1/n)\le S(Y)$. If $S(Y)\le q$, the actual largest crossing is $1$ and the FDP is $a_n$. If $S(Y)>q$, no true null can be rejected at any BH threshold $q\rho\le q$; any alternative-only crossing contributes zero FDP. Consequently
$$
F(\nu_n)=a_nq\longrightarrow aq=F(\pi).
$$
For each fixed $\eta>0$, also $J_\eta(\nu_n)=a_nq-\eta(1-a_n)/n^2\to aq=J_\eta(\pi)$.

## Failure

NOT fails: the alternative-tagged zero, irrational mixing weights and zero second moment are compatible with explicit canonical finite approximation preserving all three required limits.
