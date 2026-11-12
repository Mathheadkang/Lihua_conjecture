---
type: lemma
title: >-
  Global averaged particle-potential certificate at regularized Gaussian BH
  maxima
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_private_cutoff_particle_mass_variation
  - gaussian_bh_averaged_signed_mean_level_complementarity
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_hybrid_particle_potential_convention
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_signed_near_active_gradient_cones
  - gaussian_bh_marked_exchangeable_parameter_array
tags:
  - gaussian_bh
  - particle_mass
  - global_potential
  - signed_complementarity
---

## Statement

Use the [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md), [signed near-active conventions](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), [marked-array conventions](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) and draft [hybrid particle-potential convention](../definitions/gaussian_bh_hybrid_particle_potential_convention.md). Fix $\sigma,s>0$, $\sigma^2+s^2<1$, $0<a<1/4$ and $\chi_a$. All tests are one-sided; $s$ denotes private smoothing. Write $S=\overline\Phi$, $m=S/\phi$ and $q_{\max}=S(1)$.

The [particle-mass variation](gaussian_bh_private_cutoff_particle_mass_variation.md), approved [averaged signed complementarity](gaussian_bh_averaged_signed_mean_level_complementarity.md), approved [complete signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) and approved [marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) are declared prerequisites. For $\eta,\delta>0$, fix a genuine deterministic canonical global maximizer $(\pi,q)$ of
$$
\frac{\mathcal F^a(\pi;q,\sigma,s)}{qU}-\eta M_2(\pi)-\delta\log(1/q),
\qquad U=S^{-1}(q),\qquad 0<q\le q_{\max}.
$$
Thus $\pi\{\theta=0,\ell=0\}=0$. Set $F^a=\mathcal F^a(\pi;q,\sigma,s)$, $\beta=1-m(U)/U$ and $E_0=\{(0,v,1)\}$. Laws and every competing lawful particle are fixed before Gaussian innovations, and may be embedded into a common larger separable Hilbert space. No optimum conditional on $X$ is asserted.

For $x=(\theta,v,\ell)$ let
$$
\tau_s=\sqrt{1-\sigma^2-s^2},\qquad
c_s(v)^2=s^2+\tau_s^2(1-\|v\|^2),\qquad
K_{X,x}(z)=S\!\left(\frac{z-\theta-\tau_sX(v)}{c_s(v)}\right).
$$
Use the approved actual rank $R$, full FDP $D$, tails $H_X,V_X$, densities $h_X,h_{0,X}$, quantile $Q_X$, $f_X(r)=V_X(Q_X(r))/r$, $g_X=\chi_af_X$, $w_X=g_X'$, $w_{X,\pm}=(\pm w_X)_+$, barrier $B_X$, suffix minimum $M_X$ and full active set $\mathcal A_X$.

1. **Actual-record geometry and hybrid selectors.** For $0<t<1$, prove
$$
B_X'(t)=\frac1\sigma\left\{\frac1{h_X(Q_X(t))}
-\frac{m(u_q(t))}{t}\right\}.
$$
For every active interior point $t>r$, prove $B_X'(t)=0$. At an active boundary $t=r$, prove $M_X'(r)=B_X'(r)\ge0$ for almost every such $r$. In particular, with the derivative interpreted almost everywhere,
$$
\int_a^1\phi(M_X(r))M_X'(r)\,dr\le1.
$$
Retain this geometry when controlling reciprocal density; no unrestricted uniform bound on $1/h_X$ is assumed.

Prove measurable almost-everywhere nonemptiness of the hybrid families $\mathcal S_j$ from the draft convention: either the exact boundary $t=r$ when $B_X(r)=M_X(r)$, or a rational $t>r$ with
$$
B_X(t)\le M_X(r)+1/j,\qquad |B_X'(t)|\le1/j.
$$
Prove approximation of every active minimum, including boundary and tied minima. Verify joint measurability and representative invariance for all kernels, selectors and expectations required below.

2. **Compact potential sets and all-active supports.** For either sign and each $t\in\mathcal S_j$ use the selector pair
$$
G_\pm^t(x)=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))
\frac{K_{X,x}(Q_X(t(X,r)))}{h_X(Q_X(t(X,r)))}\,dr,
$$
$$
c_\pm^t=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))m(u_q(t(X,r)))\,dr.
$$
Prove that the closed convex hulls $\mathscr C_j^\pm$ and nested intersections $\mathscr C^\pm$ defined in the convention are nonempty convex compact sets in its declared evaluation topology. Establish bounds on $c_\pm^t$ and the following bound, or a justified larger explicit bound, simultaneously for all selector potentials and their closed convex limits:
$$
0\le G_\pm(x)\le K_0,
\qquad K_0=\frac{T_a}{\sigma\sqrt{2\pi}}
\left(\frac{m(1)}a+\sigma\right)+W_a,
$$
where $T_a=1+\log(1/a)$ and $W_a=\|\chi_a'\|_\infty+1/a$. This bound is independent of $x,\pi,X$ (in particular the conditional selector estimates used to prove the averaged bound must be independent of $X$). The $\sigma$ term permits the near-stationarity tolerance for every $j\ge1$.

Prove uniform $C^1$ bounds in $\theta$, bounded second $\theta$ derivatives at fixed $s$, and equicontinuity of the potentials and their $\theta$ derivatives in the strong particle parameters, for the entire generating families and limits. Prove analytic extension in $\theta$ on either tag, including its preservation under the selected convex limits. Use a countable strong dense parameter set and these bounds to prove compactness; the infinite-dimensional strong Hilbert ball is not compact. Justify continuity of the integral pairings with $\pi$ used below.

For a finitely supported lawful probability law $\nu$, fixed $\rho\ge0$, $\zeta=\rho(\nu-\pi)$ and any finite level velocity $\lambda$, prove the exact all-active support formulas
$$
h_{\mathscr C^\pm}(\zeta,\lambda)
=\lim_{j\to\infty}h_{\mathscr C_j^\pm}(\zeta,\lambda)
$$
$$
=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))
\max_{t\in\mathcal A_X(r)}
\left\{\rho\frac{H_{\nu,X}(Q_X(t))-H_X(Q_X(t))}{h_X(Q_X(t))}
+\lambda m(u_q(t))\right\}\,dr.
$$
Here the support is the integral pairing in the convention; the formula may be proved for every finite $\lambda$ even when only one sign of level motion is lawful. Prove all nested-hull limits and Gaussian interchanges without identifying separate positive and negative optimizing selectors or assuming a linear derivative.

3. **Bulk potential and direct separation.** Define
$$
P_0(x)=\mathbb E_{X,Z}\left[
\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
\left\{\ell(x)-\frac{h_{0,X}(Q_X(R))}{h_X(Q_X(R))}\right\}
K_{X,x}(Q_X(R))\right].
$$
The integrand is zero on $R\le a$ and on the rank-one exceptional null set. Prove boundedness, strong continuity, and $C^1$ regularity in $\theta$, with
$$
\partial_\theta P_0(x)=\mathfrak b(x),
$$
where $\mathfrak b$ is the approved bulk mean density of averaged complementarity. The formula defines its extension to particles outside the support. With $\overline P_0=P_0-\int P_0d\pi$ and $\overline G_\pm=G_\pm-\int G_\pm d\pi$, prove for the lawful directions above
$$
\dot{\mathcal F}^a=\rho\int P_0\,d(\nu-\pi)
+h_{\mathscr C^+}(\rho(\nu-\pi),\lambda)
-h_{\mathscr C^-}(\rho(\nu-\pi),\lambda).
$$
Apply the particle-mass extremal inequality to every such $\nu$, every $\rho\ge0$ and every allowed $\lambda$. Center each mass potential before separation and retain the centered moment shift
$$
-\eta qU\{\theta^2-M_2(\pi)\}.
$$
Prove continuity of centering on the compact potential classes using their uniform bounds. Use the pointwise nonpositive cone in the product of real value coordinates indexed by lawful particles, together with the level endpoint cone; do not require $\pi$-integration to be continuous on an unrestricted product space. Prove the required product-space separation directly from the established compactness using finite-coordinate continuous separating functionals. Derivative coordinates, when used to enforce coherence, require the lawful mean variations and their justified support representation. Derive equality $\pi$-almost everywhere by integrating the centered inequality. Use countably additive averaged potentials and prove every needed closure or limiting step; no undeclared finite-dimensional quasidifferential theorem or finitely additive gradient may substitute for this argument.

4. **Matching global certificate and coherent mean flux.** Prove the existence of a matching pair $(G_+,c_+)\in\mathscr C^+$, $(G_-,c_-)\in\mathscr C^-$, with
$$
\mathcal P=P_0+G_+-G_-,\qquad
P(x)=\mathcal P(x)-\eta qU\theta^2,
\qquad \kappa=\int P\,d\pi,
$$
such that
$$
P(x)\le\kappa\quad\text{for every lawful }x\in E_{\rm ball},
\qquad P(x)=\kappa\quad\pi\text{-almost everywhere}.
$$
Retain the matching level coordinate $\Lambda=c_+-c_-$ and prove
$$
\Lambda=\beta F^a-\delta qU\quad(q<q_{\max}),\qquad
\Lambda\ge\beta F^a-\delta qU\quad(q=q_{\max}).
$$
For this same potential pair, set $\Psi=\partial_\theta\mathcal P$ and prove
$$
\Psi=2\eta qU\theta\quad\pi\text{-almost everywhere off }E_0,
\qquad \Psi\ge0\quad\pi\text{-almost everywhere on }E_0.
$$
Prove that its exact integral is the approved total flux,
$$
\int\Psi\,d\pi=\Gamma_a
=\frac1\sigma\mathbb E_X\int_a^1w_X(r)\phi(M_X(r))\,dr
=\frac1\sigma\mathbb E_{X,Z}[Z\chi_a(R)D].
$$
Justify the identity by the kernel posterior mass normalization and actual-rank survival integration. Coherence with the global potential certificate is part of the conclusion; independently choosing an unrelated mean-gradient certificate is insufficient. No single exact selector realizing every convexified limit is required.

5. **Explicit tag price and finite false-particle comparison.** Write $K_{X,\theta,v}=K_{X,(\theta,v,\ell)}$, which does not depend on $\ell$. Prove that $G_+$ and $G_-$ are independent of the tag, and for the analytic extensions of either tag at the same $(\theta,v)$ prove
$$
P(\theta,v,1)-P(\theta,v,0)=T(\theta,v),
$$
$$
T(\theta,v)=\mathbb E_{X,Z}\left[
\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
K_{X,\theta,v}(Q_X(R))\right]\ge0.
$$
The global comparison remains asserted only for lawful particles. For $\pi$-almost every $(0,v,1)\in E_0$ and every fixed $h>0$, the new particle $(h,v,0)$ is lawful and must satisfy
$$
\mathcal P(h,v,0)-\mathcal P(0,v,0)
\le T(0,v)+\eta qU h^2.
$$
Prove
$$
\int_{E_0}T(0,v)d\pi\le F^a,
$$
and therefore
$$
\int_{E_0}[\mathcal P(h,v,0)-\mathcal P(0,v,0)]d\pi
\le F^a+\eta qU h^2\pi(E_0).
$$
This is a finite pre-noise particle comparison, including the explicit cost of changing the true-null tag.

## Scope and provenance

New draft original supporting goal from the leading tenth resumed reassessment in `research/project.md`, Intended Contribution. The hybrid selector and topology definition is a draft convention, not a compactness or stationarity assumption. A uniform estimate for the zero-true-mean normal flux, removal of regularizers, and both unrestricted Gaussian BH main bounds remain separate obligations even if this lemma and its particle-mass prerequisite are proved. No derivative passes through the finite-model, private-noise or cutoff limits. Every conclusion requires native falsification, proof execution and fresh independent verification.

## Proof

All parameters, laws and inserted particles in this proof are deterministic before the Gaussian innovations. We use precisely the four declared prerequisites. In particular, the [complete signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) supplies the actual-rank and endpoint identities and positive smooth conditional densities; [particle-mass variation](gaussian_bh_private_cutoff_particle_mass_variation.md) supplies its complete all-active derivative and normalized extremal inequality. No conditional-on-background extremum is used.

**1. Versions and record geometry.** Use the jointly measurable Gaussian series representative in the definitions. For each fixed loading its series converges almost surely. Fubini therefore gives almost-sure validity for almost every particle of the fixed law, and intersecting countably many such events also covers any specified countable family of laws and deterministic particles. Additional fixed particles or finite competitors use the corresponding Fubini event. A different representative agrees for each such law and particle; hence their conditional kernels and population objects agree almost surely. Below, conditional assertions are made on the population event supplied by the prerequisites, and extensions to every deterministic particle will be obtained after averaging, not by asserting samplewise continuity of the isonormal field.

Suppress the background subscript temporarily. Implicit differentiation and the inverse Gaussian-tail derivative give
$$
Q'(t)=-\frac1{h(Q(t))},\qquad
u_q'(t)=-\frac{q}{\phi(u_q(t))}=-\frac{m(u_q(t))}{t},
$$
Thus
$$
B'(t)=\frac1\sigma\left(\frac1{h(Q(t))}-\frac{m(u_q(t))}{t}\right).
$$
Every active $t>r$ lies below one and is a local minimum of the smooth function $B$, so $B'(t)=0$. To treat the boundary, fix a compact rank interval inside $(0,1)$. Since $B(t)\to+\infty$ as $t\uparrow1$, all suffix minima for this interval occur in one larger compact rank interval. On it $B$ has a finite Lipschitz constant. If $r<r'$ are in the original interval, a minimizer for $r$ either remains feasible at $r'$, in which case $M(r')=M(r)$, or lies between $r$ and $r'$, in which case comparison with $B(r')$ bounds $M(r')-M(r)$ by that Lipschitz constant times $r'-r$. Hence $M$ is locally Lipschitz and nondecreasing. Where $B(r)>M(r)$ its minimizers stay strictly above $r$ locally, and $M$ is locally constant. At almost every contact point both functions are differentiable; the nonnegative differentiable function $B-M$, vanishing there, has derivative zero. Consequently
$$
M'(r)=B'(r)\ge0\quad\text{almost everywhere on }\{B=M\},
\qquad M'=0\quad\text{almost everywhere on }\{B>M\}.
$$
The chain rule on compact intervals and the actual-rank survival endpoint from particle-mass variation give
$$
\int_a^1\phi(M(r))M'(r)\,dr
=S(M(a))-\lim_{b\uparrow1}S(M(b))=S(M(a))\le1.
$$
Here the last limit is zero: equivalently, $M(b)\to+\infty$, by $B(t)\to+\infty$. In particular no singular endpoint contribution was omitted.

The contact set is measurable. At each of its points use $t=r$ as candidate number zero. Enumerate the rationals in $(0,1)$ for all other candidates, retaining exactly those with $t>r$, $B(t)\le M(r)+1/j$ and $|B'(t)|\le1/j$. The tests are jointly measurable. An interior active point has $B'=0$, so continuity supplies retained rationals arbitrarily close to it, for every $j$. At a boundary active point candidate zero is exact. Thus the list is nonempty, and every active point, including each of several tied minima, is approximable as $j\to\infty$. Taking the first admissible candidate proves measurable nonemptiness of $\mathcal S_j$; taking first candidates within any prescribed positive error of a measurable candidate supremum will also be permitted. This uses only countable lists, not a selection theorem. All population functions involved are jointly measurable: quantiles can be defined by rational inequalities, minima by rational infima and the boundary value, and ordinary derivatives by measurable difference quotients. These observations also give measurable versions of $M'$ on its differentiability set.

**2. The entire conditional weight.** The approved bounds $0\le f\le1$ and $|f'|\le1/r$, together with the nonnegative cutoff derivative, give
$$
\int_a^1|w_X(r)|\,dr\le 1+\log(1/a)=T_a,
\qquad |w_X(r)|\le W_a.
$$
Since $u_q(t)\ge U\ge1$ and the Gaussian inverse Mills ratio $m$ is decreasing on $[1,\infty)$, $m(u_q(t))\le m(1)$. For clarity, monotonicity follows from $m'(z)=zm(z)-1<0$, using $S(z)<\phi(z)/z$ for $z>0$, which is obtained by integrating $u\phi(u)/z$ instead of $\phi(u)$ on $(z,\infty)$.

For a rational hybrid candidate, the derivative formula yields
$$
\frac1{h_X(Q_X(t))}\le \frac{m(1)}a+\frac\sigma j.
$$
For an exact boundary candidate, at almost every contact rank it instead yields
$$
\frac1{h_X(Q_X(r))}=\frac{m(u_q(r))}{r}+\sigma M_X'(r).
$$
Consequently every selector, on the same conditional full-measure set, satisfies
$$
\begin{split}
A_{\pm,j}^t(X)&:=\frac1\sigma\int_a^1
 \frac{w_{X,\pm}(r)\phi(M_X(r))}{h_X(Q_X(t(X,r)))}\,dr\\
&\le \frac{T_a}{\sigma\sqrt{2\pi}}
       \left(\frac{m(1)}a+\sigma\right)
 +W_a\int_a^1\phi(M_X(r))M_X'(r)\,dr\le K_0.
\end{split}
$$
This is a conditional bound independent of the background, the law, $j$ and the selector. It does not bound the reciprocal density at unrestricted ranks. Since $0\le K_{X,x}\le1$, it proves $0\le G_\pm^t(x)\le K_0$ for every fixed particle. Also
$$
0\le c_\pm^t\le \frac{T_am(1)}{\sigma\sqrt{2\pi}}.
$$
All these integrals are absolutely defined.

**3. Smooth averaged versions and analytic bounds.** The following estimates explain why averaging permits strong continuity despite the infinite-dimensional isonormal field. Write
$$
C_0=\sup_y\phi(y)=\frac1{\sqrt{2\pi}},\quad
C_1=\sup_y|y|\phi(y)=\frac1{\sqrt{2\pi e}},\quad
C_2=\sup_y|y^2-1|\phi(y)<\infty.
$$
For a real center $A$ and $c\ge s$, the kernel $S((z-A)/c)$, uniformly in real $z$, has center derivative bounded by $C_0/s$, second center derivative bounded by $C_1/s^2$, and variance-scale derivative bounded by $C_1/s$. The center derivative's derivatives in $A$ and $c$ are bounded by $C_1/s^2$ and $C_2/s^2$, respectively. These follow by direct differentiation of the Gaussian density. For loadings in the unit ball,
$$
|c_s(v)-c_s(v')|\le\frac{\tau_s^2}s\|v-v'\|,
\qquad \mathbb E|X(v)-X(v')|\le\|v-v'\|.
$$
The first bound follows by factoring the difference of the squared scales and using $c_s(v)+c_s(v')\ge2s$; the second is the Gaussian second-moment bound. With
$$
d_A=|\theta-\theta'|+\tau_s\|v-v'\|,
\qquad d_c=\frac{\tau_s^2}s\|v-v'\|,
$$
multiply the kernel increment estimates by the conditional total weight $A_{\pm,j}^t(X)\le K_0$ before averaging. This gives, on either tag,
$$
|G_\pm^t(x)-G_\pm^t(x')|
 \le K_0\left(\frac{C_0}s d_A+\frac{C_1}s d_c\right),
$$
$$
|\partial_\theta G_\pm^t(x)-\partial_\theta G_\pm^t(x')|
 \le K_0\left(\frac{C_1}{s^2}d_A+\frac{C_2}{s^2}d_c\right),
$$
$$
|\partial_\theta G_\pm^t|\le K_0C_0/s,
\qquad |\partial_\theta^2G_\pm^t|\le K_0C_1/s^2.
$$
Difference quotients are dominated by the same conditional total weight times the indicated Gaussian derivative bounds, which justifies the derivatives. The kernels, and hence these potentials, are tag independent. A dense countable particle set can first be used to fix common versions; these common moduli extend the averaged functions uniquely, and the same Gaussian increment bounds show that their extension agrees with the expectation at every other fixed particle. Representative changes therefore leave this continuous averaged version unchanged. Increments of $X$ here are Gaussian increments at fixed deterministic points; there is no assertion of a common samplewise continuous version.

We also record the analytic control needed for closed convex limits. Regard $\theta$ as complex. The Gaussian tail is entire, defined by its real value followed by integration of its entire derivative. For $|\operatorname{Im}\theta|\le b$, integrating along a vertical segment shows
$$
|K_{X,\theta,v}(z)|\le 1+\frac{bC_0}s e^{b^2/(2s^2)}.
$$
Indeed the modulus of the complex Gaussian density at $y+i d$ is $\phi(y)e^{d^2/2}$ and $|d|\le b/s$. Its complex derivatives have uniform strip bounds as well: differentiating gives a polynomial in $y+i d$ times that density, divided by a power of $c\ge s$; a polynomial times $e^{-y^2/2}$ is bounded for real $y$ and bounded $d$. Multiplication by $A_{\pm,j}^t(X)$ proves entire averaged extensions and corresponding uniform bounds on every strip. Differentiation or integration of their local power series is justified by these bounds. They hold for every generating potential and every finite convex combination.

**4. Compactness in the specified evaluation topology.** Let $\mathscr D$ be countable and strongly dense in $\widetilde E$, using dense real means on either tag and dense loadings in the separable unit ball. For all finite convex combinations, the value and derivative coordinates on $\mathscr D$, and the scalar coordinate $c$, lie in fixed bounded intervals. From any sequence extract a subsequence on which all these coordinates converge, by successive real-coordinate extractions and diagonalization. The common moduli in Step 3 imply Cauchy convergence at every other fixed particle; they define continuous limiting functions $G,J$ with those same moduli. On each finite real mean interval, equicontinuity and pointwise convergence give uniform convergence, by a finite net on that interval. Passing to the limit in
$$
G_n(\theta',v,\ell)-G_n(\theta,v,\ell)
 =\int_\theta^{\theta'}\partial_\theta G_n(u,v,\ell)\,du
$$
therefore proves $\partial_\theta G=J$.

For completeness analytic extension also survives. At each fixed $v,\ell$ the strip bounds give bounded Taylor coefficients on every disk, by the Cauchy integral formula. Extracting those coefficients on an increasing sequence of disks, or extracting values on countable disk nets and using the derivative strip bounds, gives a subsequence converging uniformly on compact complex disks to an entire function. Its real restriction must be the already identified $G$; uniqueness follows because an analytic function vanishing on a real interval has all Taylor coefficients zero. Thus the extension is unique and retains the strip bounds. Its first two real derivatives retain the bounds above, either by the Cauchy formula or by the real difference-quotient bounds followed by analyticity. This argument applies to any limit of convex combinations.

On the resulting common bounded family, convergence of the countable coordinates on $\mathscr D$ is equivalent, by the common moduli, to convergence of all the evaluations prescribed in the convention. A metric is obtained by enumerating these countable coordinates and summing $2^{-n}\min(1,|\Delta_n|)$. The diagonal argument proves sequential compactness for the closure of the whole convex generating family in this metric, hence compactness: if a metric space with that extraction property had an open cover with no finite subcover, finite-radius covers and a subsequence with shrinking distances would contradict either total boundedness or the convergent-subsequence property. Equivalently the usual finite-net argument proves total boundedness and completeness directly. This establishes compactness in the declared topology, without compactness of the Hilbert ball. To include ambient closure points explicitly, the real bounds and common moduli are closed conditions involving finitely many value or derivative coordinates, so each such point retains them. Approximate its first $n$ dense value, derivative and scalar coordinates within $1/n$ by convex combinations. The common moduli extend this approximation to every real coordinate; the preceding complex-disk extraction then gives that closure point its unique analytic extension with the same strip bounds. Thus the diagonal extraction applies to sequences of closure points as well, and its limits belong to the ambient continuous-$C^1$ space. The topology is Hausdorff, so each closed convex hull $\mathscr C_j^\pm$ is a closed subset of this compact family and is compact. It is nonempty and convex. Since $\mathcal S_{j+1}\subseteq\mathcal S_j$, these hulls are nested; their finite-intersection property proves that $\mathscr C^\pm$ are nonempty compact convex sets.

Pointwise convergence and the uniform bounds for $G$ and $\partial_\theta G$ imply, by dominated convergence against the fixed probability $\pi$,
$$
\int G_n\,d\pi\longrightarrow\int G\,d\pi,
\qquad
\int\partial_\theta G_n\,d\pi\longrightarrow\int\partial_\theta G\,d\pi.
$$
On these metrizable compact families this is continuity, including for nets. Consequently centering and every pairing $\int G\,d[\rho(\nu-\pi)]+\lambda c$ with finitely supported $\nu$ are continuous there. All limiting potentials are actual bounded continuous functions, integrated against the countably additive measure $\pi$; no finitely additive substitute is involved.

**5. All-active support formulas.** Fix one finitely supported lawful probability $\nu$, $\rho\ge0$ and finite $\lambda$, with no restriction on its sign for the moment. At a background where all its finitely many kernels are valid put
$$
J_X(t)=\rho\frac{H_{\nu,X}(Q_X(t))-H_X(Q_X(t))}{h_X(Q_X(t))}
       +\lambda m(u_q(t)).
$$
It is continuous on $(0,1)$. Fubini and the bound of Step 2 rewrite a generator's pairing as
$$
\frac1\sigma\mathbb E_X\int_a^1
       w_{X,\pm}(r)\phi(M_X(r))J_X(t(X,r))\,dr.
$$
Let $b_j(X,r)$ be the supremum of $J_X$ on the countable hybrid candidate list, including the available boundary candidate. The list is nonempty almost everywhere and its supremum is measurable. Choosing its first candidate within an error $\epsilon>0$ of that supremum shows that the supremum over measurable selectors equals the integral of $b_j$ against this nonnegative weight. All pairings are integrable, as can also be seen from the following common majorant.

At rational candidates $1/h\le m(1)/a+\sigma$; at boundary candidates $1/h\le m(1)/a+\sigma M'$. Since $|H_\nu-H|\le1$, an integrable majorant for the absolute value of the weighted candidate supremum, and for every weighted candidate value, is
$$
\frac{1}{\sigma}|w_X(r)|\phi(M_X(r))
 \left[\rho\left(\frac{m(1)}a+\sigma\right)+|\lambda|m(1)\right]
 +\rho W_a\phi(M_X(r))M_X'(r)
       \mathbf1_{\{B_X(r)=M_X(r)\}}.
$$
Its conditional rank integral is bounded by a deterministic constant, by Steps 1--2. It is therefore integrable also in $X$.

For each fixed good $(X,r)$, the candidates for all $j$ lie in a compact subset of $[r,1)$: their barriers are at most $M_X(r)+1$, whereas $B_X(t)\to+\infty$ at one. Every cluster point as $j\to\infty$ is active. Conversely each interior active point has admissible rational approximations at every accuracy, and an active boundary is available exactly. Continuity of $J_X$ consequently proves
$$
\lim_{j\to\infty} b_j(X,r)
 =\max_{t\in\mathcal A_X(r)}J_X(t).
$$
To see the upper inequality, choose almost-maximizing candidates and extract a compact subsequence; for the lower inequality approximate a maximizing active point. This also covers ties. Dominated convergence with the displayed majorant proves the limit after rank integration and Gaussian expectation. The positive and negative signs have their own maximizing selectors; none are identified with one another.

Closure and convexification do not change the support, since the pairing is continuous on the compact family just proved. For a continuous functional $L_*$ on nested nonempty compact sets, $\lim_j\max_{\mathscr C_j^\pm}L_*=\max_{\mathscr C^\pm}L_*$: extract a convergent subsequence of maximizers in $\mathscr C_1^\pm$; nested closedness places its limit in every hull. Applying this to the pairing proves both support identities in the statement, for every finite $\lambda$.

**6. Bulk potential and the mass extremal inequality.** The coefficient multiplying the kernel in $P_0$ has absolute value at most $1/a$, since $0\le h_{0,X}/h_X\le1$. Thus $|P_0|\le1/a$. The kernel derivative and increment bounds in Step 3, now with the bounded coefficient $1/a$ in place of the conditional selector weight, prove strong continuity on each tag, continuous differentiability in $\theta$, bounded second derivatives, and the same type of analytic extension. The coefficient and the actual base rank are held fixed when the new particle parameter is differentiated. Consequently
$$
\partial_\theta P_0(x)=\mathbb E_{X,Z}\left[
\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
 \left(\ell(x)-\frac{h_{0,X}(Q_X(R))}{h_X(Q_X(R))}\right)
 k_{X,x}(Q_X(R))\right]=\mathfrak b(x),
$$
where the last expression is exactly the bulk density in [averaged signed complementarity](gaussian_bh_averaged_signed_mean_level_complementarity.md). Zero-rank and rank-one exceptional cases use the stipulated zero conventions.

The fixed-rank derivative in particle-mass variation, followed by Fubini, gives
$$
\mathbb E_{X,Z}[\chi_a(R)\dot f_X(R)]
       =\rho\int P_0\,d(\nu-\pi).
$$
Indeed the integrand of the right side is precisely the difference of true tails minus $h_0/h$ times the difference of total tails, divided by $R$, as in that derivative. Its boundedness justifies the interchange. The same prerequisite gives $-\dot M_X(r)=\sigma^{-1}\max_{t\in\mathcal A_X(r)}J_X(t)$. Splitting the signed $w_X$ into its two parts and applying Step 5 therefore proves
$$
\dot{\mathcal F}^a=\rho\int P_0\,d(\nu-\pi)
  +h_{\mathscr C^+}(\rho(\nu-\pi),\lambda)
  -h_{\mathscr C^-}(\rho(\nu-\pi),\lambda).
$$
Only here and below require the level direction to be lawful: $\lambda$ is arbitrary if $q<q_{\max}$ and $\lambda\le0$ if $q=q_{\max}$. Set $L=\beta F^a-\delta qU$. Multiplying the approved normalized extremal inequality by $qU>0$ and using the moment derivative yields
$$
\begin{split}
&\rho\int\overline P_0\,d\nu
 -\eta qU\rho\int(\theta^2-M_2(\pi))\,d\nu\\
&\quad+h_{\mathscr C^+}(\rho(\nu-\pi),\lambda)
 -h_{\mathscr C^-}(\rho(\nu-\pi),\lambda)-\lambda L\le0.
\end{split}
$$
The centered moment shift is essential. Centering the bounded potential terms is continuous on our compact classes by Step 4. No continuity of $\pi$-integration on an unrestricted product space is asserted.

**7. Direct finite-coordinate separation.** Fix any $(G_+,c_+)\in\mathscr C^+$. For $(G_-,c_-)\in\mathscr C^-$ form the particle coordinates, indexed by every lawful particle $x$,
$$
z_-(x)=\overline P_0(x)+\overline G_+(x)-\overline G_-(x)
              -\eta qU(\theta(x)^2-M_2(\pi)),
$$
and the single level coordinate $z_-^{\rm lev}=c_+-c_--L$. Their image is compact and convex: every coordinate is continuous on $\mathscr C^-$ by Step 4. We seek all particle coordinates nonpositive, and level coordinate zero in the interior or nonnegative at the endpoint.

If there were no such image point, the closed subsets of $\mathscr C^-$ given by these individual constraints would have empty intersection. Compactness supplies finitely many already infeasible constraints. Include the level constraint, and project onto the resulting finitely many particle coordinates and the level coordinate. The projected compact convex set $A$ misses the closed convex cone
$$
C=(-\infty,0]^n\times C_{\rm lev},\qquad
C_{\rm lev}=\{0\}\ (q<q_{\max}),\quad
C_{\rm lev}=[0,\infty)\ (q=q_{\max}).
$$
Here is the separation argument in this finite space. Minimize the distance between $A$ and $C$; a minimizing pair $(a_0,c_0)$ exists because $A$ is compact and the relevant part of $C$ can be restricted to a bounded ball. The distance is positive. With $f=a_0-c_0$, first variations along segments in these convex sets give $f\cdot(a-a_0)\ge0$ and $f\cdot(c-c_0)\le0$. The cone property gives $f\cdot c_0=0$ and $\sup_C f\cdot c=0$. Therefore
$$
\inf_{a\in A}f\cdot a\ge\|f\|^2>0.
$$
Finiteness of that cone supremum forces particle coefficients $\alpha_i\ge0$. Its level coefficient $\lambda$ is arbitrary in the interior and satisfies $\lambda\le0$ at the endpoint. Put $\rho=\sum_i\alpha_i$. If $\rho>0$, let $\nu=\rho^{-1}\sum_i\alpha_i\delta_{x_i}$; if $\rho=0$, choose any finitely supported lawful probability, whose mass term then vanishes. The strict inequality reads
$$
\begin{split}
0<&\rho\int\overline P_0\,d\nu
 -\eta qU\rho\int(\theta^2-M_2(\pi))\,d\nu\\
&+\left\{\rho\int\overline G_+\,d\nu+\lambda c_+\right\}
 -h_{\mathscr C^-}(\rho(\nu-\pi),\lambda)-\lambda L.
\end{split}
$$
The braces are at most the positive support. This contradicts Step 6, also when $\rho=0$ is a pure level direction. Thus a matching negative pair exists and satisfies all constraints simultaneously. The argument used finitely many continuous value coordinates only; the unbounded fixed quadratic penalty was merely a prescribed coordinate offset.

**8. Contact and mean normals for this matching pair.** Define $\mathcal P,P,\kappa$ as in the statement. The resulting particle constraints are exactly $P(x)\le\kappa$ at every lawful particle. All terms are integrable against $\pi$, because the potentials are bounded and $M_2(\pi)<\infty$. Their centered inequality integrates to zero, so its nonpositive integrand must be zero $\pi$-almost everywhere. Hence $P=\kappa$ almost everywhere. The level constraint gives
$$
c_+-c_-=L\quad(q<q_{\max}),\qquad
c_+-c_-\ge L\quad(q=q_{\max}).
$$
At a contact point with true tag and negative mean, or false tag and positive mean, the $C^1$ function $P(\theta,v,\ell)$ has a local maximum on an open lawful mean interval. Its mean derivative vanishes. At a true-zero contact point its restriction to $\theta\le0$ has its maximum at zero, so its derivative there is nonnegative, since $[P(0)-P(-h)]/h\ge0$ for $h>0$. Canonicality removes false-tagged zeros from the almost-everywhere assertion. Thus with this very same pair,
$$
\Psi=\partial_\theta\mathcal P=2\eta qU\theta
      \quad\pi\text{-almost everywhere off }E_0,
\qquad \Psi\ge0\quad\pi\text{-almost everywhere on }E_0.
$$
This conclusion comes from deterministic lawful particle comparisons. No separate mean-gradient selection was made.

**9. Its exact total flux.** For every generating potential, $\partial_\theta K_{X,x}=k_{X,x}$. Fubini is justified by the nonnegative kernel and the conditional weight bound (or its derivative bound). Posterior mass normalization gives
$$
\begin{split}
\int\partial_\theta G_\pm^t\,d\pi
 &=\frac1\sigma\mathbb E_X\int_a^1w_{X,\pm}(r)\phi(M_X(r))
       \frac{\int k_{X,x}(Q_X(t))d\pi(x)}{h_X(Q_X(t))}\,dr\\
 &=\frac1\sigma\mathbb E_X\int_a^1w_{X,\pm}(r)\phi(M_X(r))\,dr.
\end{split}
$$
The right side is selector independent. Convexification and the derivative-integral continuity from Step 4 carry this identity to every pair in the compact hulls and intersections. Likewise $\int\partial_\theta P_0\,d\pi=0$: conditionally at the fixed actual rank the inner integral is $h_{0,X}-(h_{0,X}/h_X)h_X=0$. Its absolute integrability follows from the bounded Gaussian kernel derivatives. Subtracting gives
$$
\int\Psi\,d\pi=\frac1\sigma\mathbb E_X\int_a^1w_X(r)\phi(M_X(r))\,dr.
$$
To identify its survival form, $g_X(a)=0$, absolute continuity and $\int_a^1|w_X|\le T_a$ imply
$$
g_X(R)=\int_a^1w_X(r)\mathbf1_{\{R\ge r\}}\,dr.
$$
It also holds at rank zero and with the continuous endpoint convention. The actual-rank identity gives $\mathbf1_{\{R\ge r\}}=\mathbf1_{\{Z\ge M_X(r)\}}$, and direct Gaussian integration gives $\mathbb E_Z[Z\mathbf1_{\{Z\ge M\}}]=\phi(M)$. Signed Fubini is permitted because $\mathbb E|Z|\int|w_X|\le T_a\mathbb E|Z|<\infty$. Since $g_X(R)=\chi_a(R)D$, this proves exactly
$$
\int\Psi\,d\pi=\Gamma_a
 =\frac1\sigma\mathbb E_X\int_a^1w_X(r)\phi(M_X(r))\,dr
 =\frac1\sigma\mathbb E_{X,Z}[Z\chi_a(R)D].
$$

**10. Tags and the finite comparison.** Each generating $G_\pm^t$ is independent of the tag, and equality of its two tag evaluations survives convex combinations and evaluation limits. Subtract the two bulk formulas at the same $(\theta,v)$; their only difference is the particle tag. The quadratic penalty also cancels. The analytic extensions on both tags therefore satisfy
$$
P(\theta,v,1)-P(\theta,v,0)
 =T(\theta,v)
 =\mathbb E_{X,Z}\left[\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
      K_{X,\theta,v}(Q_X(R))\right]\ge0.
$$
For a true-zero contact particle $(0,v,1)$ and any fixed $h>0$, the particle $(h,v,0)$ is lawful. Applying its global comparison to this contact value gives
$$
\mathcal P(h,v,0)-\eta qUh^2
 \le\mathcal P(0,v,1)
 =\mathcal P(0,v,0)+T(0,v),
$$
which is the required finite comparison. At each good background and rank,
$$
\int_{E_0}K_{X,0,v}(Q_X(R))\,d\pi
 \le\int\ell(x)K_{X,x}(Q_X(R))\,d\pi(x)
 =V_X(Q_X(R)).
$$
Multiply by the nonnegative cutoff/rank coefficient and take expectations. Tonelli applies, and the actual full-FDP identity yields $\int_{E_0}T(0,v)d\pi\le F^a$. Integrating the preceding finite comparison consequently proves
$$
\int_{E_0}[\mathcal P(h,v,0)-\mathcal P(0,v,0)]\,d\pi
 \le F^a+\eta qUh^2\pi(E_0).
$$
All these comparisons concern particles fixed before noise. The proof has kept the target's regularizers fixed throughout and uses none of the separate unresolved uniform-flux or limiting bounds.
