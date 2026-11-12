---
type: candidate
title: Zero-mean coincident-kernel tag swap at the maximal level
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:02:24.062Z'
extension_version: 0.0.4
---

## Object

Take the real Hilbert space, $\sigma=s=1/2$, $a=1/8$, and $q=S(1)$. Set
$$
\pi=\delta_{(0,0,1)},\qquad \nu=\delta_{(0,0,0)},\qquad \rho=1,\quad\lambda=0.
$$
Use the cutoff equal to zero up to $a$, equal to one from $2a$ onward, and equal to $3t^2-2t^3$ between them, where $t=(r-a)/a$. For $0<\epsilon<1/16$, the perturbed law transfers mass $\epsilon$ from a true-tagged zero mean to a false-tagged zero mean while preserving every score kernel. This tests whether the closed-tag boundary loses the signed bulk response when all quantile and rank responses vanish.

## Checks

### H1

Both smoothing parameters are positive and $\sigma^2+s^2=1/2<1$.

### H2

The specified cutoff is nondecreasing and $C^1$, has the prescribed endpoint plateaus, and $0<a<1/4$. The level equals the allowed upper endpoint.

### H3

Use the approved private-smoothed directing population and marked-array conventions supplied in the pack, and its two approved prerequisite statements. In particular, a false-tagged zero is allowed in this analytic completion; canonical finite recovery must shift it to a positive mean.

### H4

Both laws are deterministic Borel probabilities fixed before innovations. Their loading vectors have norm zero. Both implications defining lawful marks hold at mean zero, and both second mean moments vanish. The background $X$ has no effect here.

### H5

The direction has finite fixed coefficients $\rho=1$, $\lambda=0$. For the indicated $\epsilon$, $\epsilon\rho<a/2$, $\epsilon|\lambda|=0$, and $q_\epsilon=q$. The upper-level boundary condition on $\lambda$ holds with equality.

### NOT

Fail: the proposed lost-bulk-response violation is absent. Put $c=\sqrt{3}/2$. Directly from the kernels,
$$
H_{\epsilon,X}(z)=H_X(z)=S(z/c),\qquad
V_{\epsilon,X}(z)=(1-\epsilon)S(z/c),\qquad
Q_{\epsilon,X}(r)=cS^{-1}(r).
$$
Consequently $f_{\epsilon,X}(r)=1-\epsilon$ at every positive rank, including the continuous rank-one convention. The true-mass fixed-rank difference is $\epsilon r\le\epsilon$, and the displayed derivatives in the target give
$$
\dot Q_X(r)=0,\qquad \dot f_X(r)=-1.
$$
The same derivative $-1$ holds at rank one. The actual rank is unchanged for every $X,Z$, since its total kernel and level are unchanged. Every suffix minimum is unchanged, so $\dot M_X(r)=0$ even if active minima compete. Thus, writing $C=\mathbb E\chi_a(R)$,
$$
\mathcal F^a(\pi_\epsilon;q,\sigma,s)=(1-\epsilon)C,
\qquad \dot{\mathcal F}^a=-C.
$$
This is exactly the target's bulk term; its rank term is zero. The entire payoff difference quotient has absolute value at most one. Both moments remain zero. No global-maximality antecedent is asserted for this object, so no extremal inequality is inferred from it.

The survival brackets also hold: here $R_\epsilon=R_0$, $\Delta_z\ge0$, and $R_0$ is nondecreasing in $Z$, making both indicator inequalities immediate, including the prescribed zero extension above rank one. The unperturbed survival is $S(M(r))$, with
$$
B(r)=2\{S^{-1}(qr)-cS^{-1}(r)\}.
$$
This is smooth locally below one and tends to $+\infty$ at one. On every compact rank interval below one, all suffix minimizers lie in a larger compact interval below one, so their running minimum is locally Lipschitz. Its survival is nonincreasing and tends to zero at one; its local absolute-continuity identities pass to one by monotone integration of the nonnegative negative derivative. It is therefore absolutely continuous on $[a/2,1]$, as required. The survival perturbation difference quotient itself is identically zero. False-zero canonical endpoint recovery is covered by the approved endpoint-recovery prerequisite after each endpoint is fixed; this example exposes no violation there.

## Failure

NOT fails: coincident score kernels suppress the rank response but retain exactly the signed true-mass response $-\mathbb E\chi_a(R)$.
