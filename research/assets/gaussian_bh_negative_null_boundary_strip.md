---
type: lemma
title: Shrinking null-mean boundary strip for the actual Gaussian BH FDR
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags: []
---

## Statement

For every finite positive integer N, every theta in R^N, every positive-semidefinite unit-diagonal covariance Sigma (including singular matrices), and 0<q<=barPhi(1), apply the original one-sided ordinary Benjamini-Hochberg procedure to p_i=barPhi(T_i), T~N_N(theta,Sigma). Keep the original true-null set I_0={i:theta_i<=0}, largest qualifying rank, multiplicities and non-strict comparisons. Let R be its actual rejection count and set U=barPhi^{-1}(q)>=1.

For any a>0 define D_a={i:theta_i<=-a} and V_{D_a}=|D_a intersect R_q|. Then
$$
E[V_{D_a}/(R vee 1)] <= (q|D_a|/N) exp(-a^2/2-aU) [(U+1)/a+1/a^2].
$$
All displayed bounds are uniform over the finite model; a and every model parameter may depend on q.

In particular, for 0<q<=barPhi(e), put a_q=2 log(U)/U and D_q=D_{a_q}. Then
$$
E[V_{D_q}/(R vee 1)] <= (3/4+1/(2e)) q|D_q|/N <= q.
$$
Consequently, with B_q={i:-a_q<theta_i<=0} and V_{B_q}=|B_q intersect R_q|,
$$
FDR_BH(q;N,theta,Sigma) <= q+E[V_{B_q}/(R vee 1)].
$$
The counts and denominator always refer to the same unmodified full BH procedure. No coordinate is deleted, relabeled, recentered or given a new covariance. This statement supplies a contribution decomposition only; it does not assert a bound for the remaining near-boundary contribution or prove either universal order target. Here barPhi is the standard normal survival function, e is the base of the natural logarithm, log is natural, and R vee 1=max(R,1).

## Proof

Fix an admissible finite model and $0<q\leq\overline\Phi(1)$. Use the one-sided $p$-values and true-null set of [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md): $p_i=\overline\Phi(T_i)$ and $I_0=\{i:\theta_i\leq0\}$. Throughout, $\mathcal R_q=\mathcal R_q(p)$ and $R=|\mathcal R_q|$ are the rejection set and count of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) on the full vector. Put $U=\overline\Phi^{-1}(q)\geq1$ and $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$.

Let $k=\widehat k_q(p)$ be the largest qualifying rank. If $k=0$, then $R=0$. If $k>0$, at least $k$ $p$-values are at most $qk/N$. Write $m$ for their number. If $m>k$, then $p_{(m)}\leq qk/N\leq qm/N$, contradicting maximality of $k$. Thus $m=k$ and $R=k$, including all multiplicities and ties. Every coordinate is finite almost surely; since $N$ is finite, $0<p_i<1$ holds simultaneously almost surely. On rejection of label $i$, we have $R>0$, $p_i\leq qR/N\leq q$, and $1/R\leq q/(Np_i)$. Off that event the left side below is zero. Hence, also when $R=0$,
$$
\frac{\mathbf 1\{i\in\mathcal R_q\}}{R\vee1}
\leq\frac qN\frac{\mathbf 1\{p_i\leq q\}}{p_i}
\quad\text{almost surely}.
$$

Fix $a>0$ and $i\in D_a$, and write $b=-\theta_i\geq a>0$. The [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) gives $T_i\sim\mathcal N(-b,1)$ because $\Sigma_{ii}=1$, including singular $\Sigma$. Strict monotonicity of the survival function gives $\{p_i\leq q\}=\{T_i\geq U\}$. The one-dimensional density therefore yields, as integrals of nonnegative functions,
$$
J_b(U):=\mathbb E\!\left[\frac{\mathbf 1\{p_i\leq q\}}{p_i}\right]
=\int_U^\infty\frac{\phi(t+b)}{\overline\Phi(t)}\,dt
=e^{-b^2/2}\int_U^\infty e^{-bt}\frac{\phi(t)}{\overline\Phi(t)}\,dt,
$$
using $\phi(t+b)=e^{-b^2/2-bt}\phi(t)$.

For $t>0$, the identity $\phi'(s)=-s\phi(s)$ and integration by parts on $[t,M]$ give
$$
\int_t^M\phi(s)\,ds
=\frac{\phi(t)}t-\frac{\phi(M)}M-\int_t^M\frac{\phi(s)}{s^2}\,ds.
$$
The boundary term $\phi(M)/M$ tends to zero because the Gaussian exponential tends to zero and $1/M\leq1$ for $M\geq1$. The last integral converges, being bounded by $t^{-2}\overline\Phi(t)$. Sending $M$ to infinity gives
$$
\overline\Phi(t)=\frac{\phi(t)}t-\int_t^\infty\frac{\phi(s)}{s^2}\,ds
\geq\frac{\phi(t)}t-\frac{\overline\Phi(t)}{t^2}.
$$
Since $\overline\Phi(t)>0$, rearrangement shows
$$
\frac{\phi(t)}{\overline\Phi(t)}\leq t+\frac1t\leq t+1\qquad(t\geq1).
$$
Consequently,
$$
J_b(U)\leq e^{-b^2/2}\int_U^\infty(t+1)e^{-bt}\,dt
=e^{-b^2/2-bU}\left(\frac{U+1}{b}+\frac1{b^2}\right).
$$
Indeed, an antiderivative is $-e^{-bt}((t+1)/b+1/b^2)$, whose value tends to zero at infinity because $b>0$. This also proves finiteness. For fixed $U\geq1$, both positive factors $e^{-b^2/2-bU}$ and $(U+1)/b+1/b^2$ decrease as $b>0$ increases. Their product is therefore at most its value at $a$ when $b\geq a$. Summing the pathwise bound over the deterministic finite set $D_a$ and taking expectations gives
$$
\mathbb E\!\left[\frac{V_{D_a}}{R\vee1}\right]
\leq\frac qN\sum_{i\in D_a}J_{-\theta_i}(U)
\leq\frac{q|D_a|}{N}e^{-a^2/2-aU}
\left(\frac{U+1}{a}+\frac1{a^2}\right).
$$
When $D_a$ is empty both sides are zero, so this proves the first bound in every case.

Now let $q\leq\overline\Phi(e)$, so $U\geq e$. Write $L=\log U\geq1$ and $a=a_q=2L/U>0$. Since $e^{-aU}=U^{-2}$,
$$
e^{-a^2/2-aU}\left(\frac{U+1}{a}+\frac1{a^2}\right)
\leq U^{-2}\left(\frac{U(U+1)}{2L}+\frac{U^2}{4L^2}\right)
=\frac{1+1/U}{2L}+\frac1{4L^2}
\leq\frac{1+1/e}{2}+\frac14
=\frac34+\frac1{2e}<1.
$$
The last strict inequality uses $e>2$; all preceding inequalities include $U=e$. Applying the first bound and $|D_q|\leq N$ therefore yields
$$
\mathbb E\!\left[\frac{V_{D_q}}{R\vee1}\right]
\leq\left(\frac34+\frac1{2e}\right)\frac{q|D_q|}{N}\leq q.
$$

Finally, because $a_q>0$, the original true-null set has the exact disjoint partition
$$
I_0=D_q\,\dot\cup\,B_q,
\qquad B_q=\{i:-a_q<\theta_i\leq0\}.
$$
The equality $\theta_i=-a_q$ is assigned to $D_q$ and $\theta_i=0$ to $B_q$. Thus $V=V_{D_q}+V_{B_q}$ for the same full rejection set. By the definition of [false discovery rate](../definitions/false_discovery_rate.md),
$$
\operatorname{FDR}_{\mathrm{BH}}(q;N,\theta,\Sigma)
=\mathbb E\!\left[\frac{V_{D_q}}{R\vee1}\right]
+\mathbb E\!\left[\frac{V_{B_q}}{R\vee1}\right]
\leq q+\mathbb E\!\left[\frac{V_{B_q}}{R\vee1}\right].
$$
This identity also holds when $R=0$, since all three counts vanish then. Each calculation is valid at every fixed admissible $q$ with the displayed constants independent of $N$, $\theta$, $\Sigma$, and $a$. Arbitrary deterministic dependence of those parameters on $q$ is consequently allowed. Only unit-variance marginal laws were used, so singular covariance requires no limiting argument. The argument supplies the stated contribution decomposition and no further estimate of the $B_q$ contribution.
