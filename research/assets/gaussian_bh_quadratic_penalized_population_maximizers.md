---
type: lemma
title: >-
  Quadratic mean-penalized maximizers and deterministic transport comparisons
  for finite-dimensional Gaussian BH populations
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
uses_definitions:
  - gaussian_bh_quadratic_population_penalty
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - quadratic_mean_penalty
  - population_maximizer
  - deterministic_transport
  - finite_competitors
---

## Statement

Fix $q\in(0,1/2)$, $\sigma\in(0,1)$ and a positive integer $d$. Use exactly the [common-loading tagged Gaussian population](../definitions/gaussian_bh_common_loading_tagged_population.md) on $\mathbb R^d$ and the [quadratic mean-penalty notation](../definitions/gaussian_bh_quadratic_population_penalty.md): $\mathcal E$, $\mathcal P_1(\mathcal E)$, $\mathcal P_2(\mathcal E)$, $W_1$, $M_2$, $J_\eta$, $A_\eta$ and $W$. The functional $F(\pi)$ is the expectation of the original full mixed-label FDP at the actual globally largest non-strict BH crossing, including competing crossings, rank zero and rank one. All parameter laws and transports are deterministic and independent of the Gaussian randomness. Alternative-tagged zero means occur only in the analytic completion.

The following conclusions hold, using the approved [Wasserstein continuity of full population Gaussian BH FDR](gaussian_bh_common_loading_wasserstein_fdr_continuity.md) with its exact fixed-loading hypotheses.

1. **Compactness and attainment.** For each finite $C\ge0$, the set
$$
\mathcal K_C=\{\pi\in\mathcal P_2(\mathcal E):M_2(\pi)\le C\}
$$
is tight and compact in $W_1$. The moment $M_2$ is lower semicontinuous under $W_1$ convergence. These assertions include preservation of the closed tagged domain and follow from the bounded second moments and compact unit sphere and tag space in this finite ambient dimension. For every $\eta>0$, there exists a completed law $\pi_\eta\in\mathcal P_2(\mathcal E)$ such that
$$
J_\eta(\pi_\eta)=A_\eta,\qquad q\le A_\eta\le W\le1,\qquad
\eta M_2(\pi_\eta)\le1.
$$
The compactness, lower semicontinuity, maximizing-sequence moment bounds and applicability of the approved FDR continuity theorem must be established, rather than assumed in a formal extremum calculation.

2. **Canonical approximation with convergent moments.** For every $\pi\in\mathcal P_2(\mathcal E)$ there are finite rational parameter laws
$$
\nu_n=\sum_{j=1}^{m_n}\frac{k_{nj}}{N_n}\,
\delta_{(\theta_{nj},v_{nj},\ell_{nj})},\qquad
N_n=\sum_{j=1}^{m_n}k_{nj},\qquad m_n,k_{nj}\in\{1,2,\ldots\},
$$
where $\delta_x$ is unit point mass at $x$, every $v_{nj}\in\mathbb R^d$ has norm one and
$$
\ell_{nj}=\mathbf1_{\{\theta_{nj}\le0\}},\qquad
\ell_{nj}=0\Longrightarrow\theta_{nj}>0,
$$
such that
$$
W_1(\nu_n,\pi)\longrightarrow0,\qquad
F(\nu_n)\longrightarrow F(\pi),\qquad
M_2(\nu_n)\longrightarrow M_2(\pi).
$$
Each law is realized by $k_{nj}$ identical copies of the scores
$$
\theta_{nj}+\sqrt{1-\sigma^2}\,X(v_{nj})+\sigma Z.
$$
This is an admissible [finite Gaussian testing model](../definitions/gaussian_multiple_testing_model.md), with its canonical [one-sided p-values and true-null labels](../definitions/gaussian_test_pvalues.md), whose [ordinary BH procedure](../definitions/benjamini_hochberg_step_up.md) has [false discovery rate](../definitions/false_discovery_rate.md) exactly $F(\nu_n)$. In particular, $J_\eta(\nu_n)\to J_\eta(\pi)$ for fixed $\eta$. Moment convergence must be obtained through truncation and finite quantization with controlled rationalization; it is not a consequence of $W_1$ continuity alone.

3. **The unpenalized supremum and vanishing penalty.** The number $W$ equals the supremum of ordinary finite canonical Gaussian BH FDRs admitting the displayed realization at these same fixed $q,\sigma,d$. For every choice of maximizing laws $\pi_\eta$ in part 1, as $\eta\downarrow0$,
$$
A_\eta\longrightarrow W,\qquad
F(\pi_\eta)\longrightarrow W,\qquad
\eta M_2(\pi_\eta)\longrightarrow0.
$$
No convergence of the laws $\pi_\eta$ themselves, or unpenalized attained maximizer, is claimed. In particular, each penalized maximizer has ordinary finite competitors arbitrarily close to its penalized value.

4. **Exact deterministic transport comparison.** Fix $\eta>0$ and any maximizing law $\pi_\eta$. Let $K\ge0$ be finite and let $T_\epsilon:\mathcal E\to\mathcal E$ be any deterministic Borel transport with mean displacement bounded by $\epsilon K$ for $\pi_\eta$-almost every parameter, where $\epsilon>0$. Then $(T_\epsilon)_\#\pi_\eta\in\mathcal P_2(\mathcal E)$ and
$$
F((T_\epsilon)_\#\pi_\eta)-F(\pi_\eta)
\le\eta\{M_2((T_\epsilon)_\#\pi_\eta)-M_2(\pi_\eta)\}
\le2\epsilon K\eta\sqrt{M_2(\pi_\eta)}+\eta\epsilon^2K^2.
$$
The first comparison retains the signed moment increment. For any such family of transports defined for all sufficiently small positive $\epsilon$, the upper right difference quotient satisfies
$$
\limsup_{\epsilon\downarrow0}
\frac{F((T_\epsilon)_\#\pi_\eta)-F(\pi_\eta)}{\epsilon}
\le2K\eta\sqrt{M_2(\pi_\eta)}
\le2K\sqrt\eta.
$$
The final bound is independent of $d$ for a fixed speed $K$. More precisely its first upper bound is $2K\sqrt\eta\sqrt{\eta M_2(\pi_\eta)}$, whose last square-root factor tends to zero for any maximizing selection as $\eta\downarrow0$.

5. **Signed mean velocity and direction changes.** If a lawful transport family has mean $\theta+\epsilon b(x)$ for a fixed deterministic Borel velocity $b$ with $|b|\le K$ $\pi_\eta$-almost everywhere, then
$$
\eta\{M_2((T_\epsilon)_\#\pi_\eta)-M_2(\pi_\eta)\}
=2\eta\epsilon\int_{\mathcal E}\theta b\,d\pi_\eta
+\eta\epsilon^2\int_{\mathcal E}b^2\,d\pi_\eta,
$$
and consequently
$$
\limsup_{\epsilon\downarrow0}
\frac{F((T_\epsilon)_\#\pi_\eta)-F(\pi_\eta)}{\epsilon}
\le2\eta\int_{\mathcal E}\theta b\,d\pi_\eta.
$$
For pure direction transports, the moment increment is exactly zero, and therefore $F((T_\epsilon)_\#\pi_\eta)\le F(\pi_\eta)$. All output directions must remain unit and all output parameters must remain in the tagged domain. An upward displacement of a zero-mean point retaining a true-null tag is inadmissible. No reclassification of a true null is used to assert an ordinary finite-model variation.

6. **Finite endpoint recovery after choosing the perturbation.** For fixed $\eta$ and any lawful family in part 4, choose the finite canonical competitors after each positive $\epsilon$. They can be selected with parameter laws $\mu_\epsilon$ and $\nu_\epsilon$ approximating $\pi_\eta$ and $(T_\epsilon)_\#\pi_\eta$, respectively, so that the sum of their two $W_1$ errors, two absolute FDR errors and two absolute second-moment errors is $o(\epsilon)$ as $\epsilon\downarrow0$. Here $o(\epsilon)$ denotes a quantity divided by $\epsilon$ tending to zero. In particular,
$$
F(\nu_\epsilon)-F(\mu_\epsilon)
\le\eta\{M_2(\nu_\epsilon)-M_2(\mu_\epsilon)\}+o(\epsilon),
$$
and the difference quotients of these finite FDR increments have the same upper limits as those of the completed endpoints. Their multiplicities and test counts may depend arbitrarily on $\epsilon$. This recovers endpoint values and signed comparison bounds; it asserts no interchange of atomization and a finite-model derivative.

## Scope

This original draft is an existence, approximation and comparison target, without a candidate proof asserted. Attainment is restricted to fixed $q$, fixed strictly positive common loading $\sigma$, and fixed positive finite ambient dimension $d$. Maximizers are completed parameter laws; no finite or positive-definite maximizer is asserted. The full actual largest-crossing functional is retained throughout. No background-dependent parameter law, differentiability of $F$, upward motion of a retained zero-mean true null, transfer of finite-copy derivatives, complete random-fold response, normalized $q$-variation, $q$-scaled zero-null flux payment, or unrestricted Gaussian BH order bound is supplied. Native falsification, proof execution and fresh independent verification remain required.

## Proof

Throughout this proof $q,\sigma,d$ have the fixed values in the statement, and $\tau=\sqrt{1-\sigma^2}$. All laws and parameter maps constructed below are deterministic. We use clauses 1, 3 and 4 of [Wasserstein continuity of full population Gaussian BH FDR with a fixed common loading](gaussian_bh_common_loading_wasserstein_fdr_continuity.md). Thus $0\le F\le1$ and every use of continuity concerns the full mixed-label FDP at the actual largest non-strict crossing, including both rank endpoints and competing crossings.

**1. The domain, moment lower semicontinuity and tail bounds.** The product $\mathbb R\times\mathbb S^{d-1}\times\{0,1\}$ with the sum metric defining $c$ is complete and separable. The sign constraints define a closed subset: in a convergent sequence the discrete tag is eventually constant, and the corresponding closed half-line contains the limiting mean. Consequently $\mathcal E$ is complete and separable. In particular the two tags at mean zero remain distinct. For $R\ge0$ put
$$
\mathcal E_R=\{(\theta,v,\ell)\in\mathcal E:|\theta|\le R\}.
$$
This is a closed subset of the compact product $[-R,R]\times\mathbb S^{d-1}\times\{0,1\}$, hence compact. Here the compactness of the sphere uses finite $d$; it also holds for $d=1$, when the sphere consists of two points.

For $L>0$ define $f_L(\theta,v,\ell)=\min\{\theta^2,L\}$. The scalar map $t\mapsto\min\{t^2,L\}$ is $2\sqrt L$-Lipschitz, so $f_L$ is bounded and $2\sqrt L$-Lipschitz with respect to $c$. Integrating against any coupling and then taking the infimum shows
$$
\left|\int f_L\,d\alpha-\int f_L\,d\beta\right|
\le2\sqrt L\,W_1(\alpha,\beta).
$$
If $W_1(\pi_n,\pi)\to0$, then for every $L$,
$$
\int f_L\,d\pi=\lim_n\int f_L\,d\pi_n
\le\liminf_n M_2(\pi_n).
$$
Monotone convergence as $L\uparrow\infty$ gives
$$
M_2(\pi)\le\liminf_n M_2(\pi_n).
$$
Thus $\mathcal K_C$ is closed in $\mathcal P_1(\mathcal E)$. For every $R>0$ and $\pi\in\mathcal K_C$, pointwise comparison with $\theta^2$ gives
$$
\pi(|\theta|>R)\le\frac C{R^2},\qquad
\int_{\{|\theta|>R\}}|\theta|\,d\pi\le\frac C R.
$$
The first estimate and compactness of $\mathcal E_R$ prove tightness, including $C=0$.

**2. Compactness in the stated Wasserstein metric.** For $R>0$ let $Q_R$ replace $\theta$ by $\max\{-R,\min\{\theta,R\}\}$ and retain direction and tag. This is a Borel map from $\mathcal E$ into $\mathcal E_R$, since clamping preserves both sign constraints. Its deterministic coupling yields, uniformly on $\mathcal K_C$,
$$
W_1(\pi,(Q_R)_\#\pi)
\le\int (|\theta|-R)_+\,d\pi\le C/R.
$$
Fix $h>0$. A finite $h$-net of $\mathcal E_R$ gives a Borel map to its centers at distance at most $h$: assign each point to the first admissible center in a fixed enumeration. Hence every clamped law is within $h$ of a law on this finite set. If its centers are $a_1,\ldots,a_m$ and its diameter is $D$, the laws with weights $w,w'$ satisfy
$$
W_1\left(\sum_jw_j\delta_{a_j},\sum_jw'_j\delta_{a_j}\right)
\le\frac D2\sum_j|w_j-w'_j|.
$$
Indeed, couple the common mass $\min\{w_j,w'_j\}$ identically and couple the remaining masses, of total size $\frac12\sum_j|w_j-w'_j|$, at cost at most $D$ per unit mass. The finite weight simplex is compact, so its laws have a finite net at every positive accuracy. First choosing $R$ large and then $h$ small proves total boundedness of $\mathcal K_C$ in the ambient Wasserstein metric. If centers are required to lie in $\mathcal K_C$, discard covering balls missing that set and choose a point of the set in each remaining ball; doubling the radii gives such a net.

For completeness, we supply the needed completeness argument for $\mathcal P_1(\mathcal E)$. Fix $x_0\in\mathcal E$ with zero mean. Since directions have distance at most two and tags at most one,
$$
|\theta(x)|\le c(x,x_0)\le |\theta(x)|+3.
$$
Thus the definition of $\mathcal P_1$ is exactly finiteness of the first metric moment. From a $W_1$-Cauchy sequence choose a subsequence $(\alpha_j)$ whose successive distances are less than $2^{-j-1}$. By the definition of the infimum choose couplings $\gamma_j\in\Gamma(\alpha_j,\alpha_{j+1})$ with expected cost at most $2^{-j}$. On the complete separable space $\mathcal E$, these Borel couplings have regular conditional probability kernels given their first coordinates. Starting with law $\alpha_1$ and successively using those kernels constructs a countable sequence $(Y_j)$ having adjacent joint laws $\gamma_j$. This is the usual countable product construction from probability kernels; each new marginal is $\alpha_{j+1}$ by the coupling identity. In particular,
$$
\mathbb E\sum_{j\ge1}c(Y_j,Y_{j+1})\le\sum_{j\ge1}2^{-j}<\infty.
$$
The sum is finite almost surely. Thus $(Y_j)$ is almost surely Cauchy and converges in the complete space $\mathcal E$ to a measurable random point $Y$. On the exceptional null event assign $Y=x_0$. The triangle inequality, followed by the limit, gives
$$
\mathbb E c(Y_j,Y)\le\sum_{k\ge j}2^{-k}\longrightarrow0,
\qquad
\mathbb E c(Y,x_0)\le\mathbb E c(Y_1,x_0)+\sum_{k\ge1}2^{-k}<\infty.
$$
The law $\alpha$ of $Y$ therefore belongs to $\mathcal P_1(\mathcal E)$ and $W_1(\alpha_j,\alpha)\to0$. The whole original Cauchy sequence converges to $\alpha$ by its Cauchy property and the triangle inequality for $W_1$ (the latter follows by gluing two couplings through their shared marginal and integrating the triangle inequality for $c$). This proves completeness. The closed set $\mathcal K_C$ is therefore complete; complete and totally bounded metric spaces are compact. When $C=0$, all means are zero almost surely and the same argument applies directly; no positive lower bound on $C$ was used. Since all the limits above take values in $\mathcal E$, the completed sign and tag constraints are preserved.

**3. Attainment of the penalized supremum.** Choose a unit $v$ and let $\pi^0=\delta_{(0,v,1)}$. Its score $\tau X(v)+\sigma Z$ is standard normal. For this one-point law the largest rank is one if its p-value is at most $q$, and zero otherwise: if $p>q$, no positive rank can qualify, whereas if $p\le q$, rank one qualifies. Its full FDP is therefore $\mathbf1_{\{p\le q\}}$, and $F(\pi^0)=q$, $M_2(\pi^0)=0$. It follows that
$$
q\le A_\eta\le W\le1.
$$
Fix $\eta>0$. Choose a maximizing sequence $(\pi_n)\subset\mathcal P_2(\mathcal E)$. Discard finitely many terms so that $J_\eta(\pi_n)\ge q/2$. Then
$$
\eta M_2(\pi_n)=F(\pi_n)-J_\eta(\pi_n)\le1-q/2.
$$
Compactness of $\mathcal K_{(1-q/2)/\eta}$ gives a subsequence converging in $W_1$ to some $\pi_\eta$ in that set. The exact hypotheses of the approved continuity theorem hold: these are deterministic laws in the same $\mathcal P_1(\mathcal E)$, the directions are unit vectors in the fixed nonzero Hilbert space $\mathbb R^d$, the tags satisfy the completed sign constraints, and $q$ and the strictly positive common loading $\sigma$ are unchanged. Its clause 3 therefore gives $F(\pi_n)\to F(\pi_\eta)$ along the subsequence, for the full functional specified here. The moment lower semicontinuity from step 1 gives
$$
A_\eta=\lim_n J_\eta(\pi_n)
\le F(\pi_\eta)-\eta M_2(\pi_\eta)=J_\eta(\pi_\eta)\le A_\eta.
$$
This proves attainment without asserting convergence of the maximizing sequence's moments. Finally,
$$
0\le\eta M_2(\pi_\eta)=F(\pi_\eta)-A_\eta\le1-q\le1.
$$

**4. Canonical approximation retaining the second moment.** Fix $\pi\in\mathcal P_2(\mathcal E)$. For an integer $n\ge1$ put $R_n=n$ and $h_n=1/n$, and clamp the mean to $t_n=\max\{-n,\min\{\theta,n\}\}$. Under $\pi$,
$$
\int|t_n-\theta|^2\,d\pi
\le\int\theta^2\mathbf1_{\{|\theta|>n\}}\,d\pi\longrightarrow0.
$$
Quantize $t_n$ separately for the two tags. For tag one use
$$
\widehat\theta_n=-h_n\lfloor -t_n/h_n\rfloor\quad(t_n\le0),
$$
which belongs to the finite grid $\{-jh_n:0\le j\le n^2\}$. For tag zero use
$$
\widehat\theta_n=h_n(\lfloor t_n/h_n\rfloor+1)\quad(t_n\ge0),
$$
which belongs to $\{jh_n:1\le j\le n^2+1\}$. Both errors are at most $h_n$, and all alternative output means are strictly positive, including the images of alternative-tagged zero means. True tags, including true-tagged zero means, are unchanged. Thus every output label is exactly $\mathbf1_{\{\widehat\theta_n\le0\}}$.

Choose a finite unit-sphere net of radius at most $h_n$ and quantize $v$ to a unit representative $\widehat v_n$ by the first-center Borel rule used above. The mean and direction quantizers, retaining $\ell$, define a finite-valued Borel map. Let $\lambda_n$ be its pushforward law. The deterministic coupling with $\pi$ gives
$$
\|\widehat\theta_n-\theta\|_{L^2(\pi)}
\le\|t_n-\theta\|_{L^2(\pi)}+h_n\longrightarrow0,
$$
$$
W_1(\lambda_n,\pi)
\le\|\widehat\theta_n-\theta\|_{L^2(\pi)}+h_n\longrightarrow0.
$$
The tag cost is zero. The reverse triangle inequality for the $L^2$ norm gives
$$
\left|\sqrt{M_2(\lambda_n)}-\sqrt{M_2(\pi)}\right|
\le\|\widehat\theta_n-\theta\|_{L^2(\pi)}\longrightarrow0,
$$
and hence $M_2(\lambda_n)\to M_2(\pi)$.

Write only the positive-mass points of $\lambda_n$ as $a_{n1},\ldots,a_{nm_n}$, with weights $w_{nj}>0$. Set $B_n=n+h_n$, which bounds their mean magnitudes. Choose positive rational weights $r_{nj}$ summing to one and so close to $w_{nj}$ that
$$
e_n=\sum_{j=1}^{m_n}|r_{nj}-w_{nj}|,
\qquad e_n(1+B_n^2)\le1/n.
$$
Such weights exist: for $m_n>1$ approximate the first $m_n-1$ weights by positive rationals with the sum of their errors arbitrarily small relative to the final positive weight, and define the final rational weight by subtracting their sum from one. For $m_n=1$ use weight one. Let $\nu_n=\sum_jr_{nj}\delta_{a_{nj}}$. The support has $c$-diameter at most $2B_n+3$, so the common-mass coupling from step 2 yields
$$
W_1(\nu_n,\lambda_n)\le\frac{2B_n+3}{2}e_n\longrightarrow0,
\qquad
|M_2(\nu_n)-M_2(\lambda_n)|\le B_n^2e_n\longrightarrow0.
$$
Consequently $W_1(\nu_n,\pi)\to0$ and $M_2(\nu_n)\to M_2(\pi)$. All these laws have unit directions, lawful canonical tags and finite first moments in the same fixed space, so clause 3 of the approved continuity theorem applies and gives $F(\nu_n)\to F(\pi)$. For each fixed $\eta$, subtraction now also gives $J_\eta(\nu_n)\to J_\eta(\pi)$. Second-moment convergence has been proved by the $L^2$ construction and the rationalization bounds, rather than inferred from $W_1$ convergence.

**5. Exact finite realization and equality of suprema.** Choose a common denominator $N_n$ for the positive rational weights, writing $r_{nj}=k_{nj}/N_n$ with positive integers $k_{nj}$ and $\sum_jk_{nj}=N_n$. Use $k_{nj}$ identical copies of $\theta_{nj}+\tau X(v_{nj})+\sigma Z$, where $a_{nj}=(\theta_{nj},v_{nj},\ell_{nj})$. This is a jointly Gaussian finite vector with covariance entries
$$
\Sigma_{ab}=\tau^2\langle v_a,v_b\rangle+\sigma^2.
$$
Its diagonal entries are one, and for any real coefficients $s_a$,
$$
\sum_{a,b}s_as_b\Sigma_{ab}
=\tau^2\left\|\sum_a s_av_a\right\|^2+\sigma^2\left(\sum_a s_a\right)^2\ge0.
$$
It is therefore an admissible [finite Gaussian testing model](../definitions/gaussian_multiple_testing_model.md), allowing duplicated coordinates and singular covariance. The [one-sided p-values and true-null convention](../definitions/gaussian_test_pvalues.md) give exactly the canonical labels already constructed.

We also verify the exact [ordinary BH](../definitions/benjamini_hochberg_step_up.md) identification directly. For any one of these $N=N_n$-coordinate arrays and each realization, write $k$ for its largest qualifying integer rank. At a positive population rank $r$, the empirical count is $j/N$, where $j=\#\{a:p_a\le qr\}$. If $r$ qualifies, then $j/N\ge r$, so $j\ge1$ and
$$
p_{(j)}\le qr\le qj/N.
$$
Thus $j$ is a qualifying integer rank and $r\le j/N\le k/N$. Conversely, if $k>0$, rank $k/N$ qualifies in the population definition. Hence $\rho_{\nu_n}=k/N$ when $k>0$, and $\rho_{\nu_n}=0$ when $k=0$. For $k>0$, the rejection count at cutoff $qk/N$ is exactly $k$: a count $j>k$ would make $j$ a larger qualifying integer rank by the same inequality. The population numerator is the number of rejected true nulls divided by $N$, so its fractional FDP is exactly $V/k$. At rank zero both FDP conventions are zero. This argument includes rank one, all ties and competing crossings, with the non-strict inequalities unchanged. Taking expectations gives precisely $F(\nu_n)$ as the ordinary [FDR](../definitions/false_discovery_rate.md).

Let $B$ denote the supremum of FDRs of ordinary finite canonical models with the displayed realization at these fixed $q,\sigma,d$. Every such array has a canonical empirical parameter law in $\mathcal P_2(\mathcal E)$ and the preceding identification gives its FDR as $F$ of that law. Therefore $B\le W$. Conversely, for any $\pi\in\mathcal P_1(\mathcal E)$, clause 4 of the approved continuity theorem supplies canonical rational laws in this same fixed $\mathbb R^d$, realized by exactly the same finite score formula, whose FDRs tend to $F(\pi)$. This use of the theorem requires only its first-moment assumption, and so also covers $M_2(\pi)=\infty$. It follows that $F(\pi)\le B$ for every such law, proving $W\le B$ and hence $B=W$. Step 4 applied to each $\pi_\eta$ additionally gives ordinary finite competitors with penalized values arbitrarily close to $J_\eta(\pi_\eta)$.

**6. Vanishing penalty for every maximizing selection.** Fix $\delta>0$. Since $B=W$, choose one finite canonical law $\nu$ such that $F(\nu)>W-\delta$. Its moment is finite. For every $\eta>0$,
$$
W\ge A_\eta\ge F(\nu)-\eta M_2(\nu)>W-\delta-\eta M_2(\nu).
$$
Letting $\eta\downarrow0$ and then $\delta\downarrow0$ proves $A_\eta\to W$. For every choice of maximizing law, regardless of how the choice depends on $\eta$,
$$
A_\eta\le F(\pi_\eta)\le W,
\qquad
0\le\eta M_2(\pi_\eta)=F(\pi_\eta)-A_\eta\le W-A_\eta.
$$
These inequalities prove both $F(\pi_\eta)\to W$ and $\eta M_2(\pi_\eta)\to0$. No compactness of these laws across changing $\eta$ or unpenalized attainment is needed.

**7. Exact signed transport comparison.** Fix $\eta>0$, a maximizing law $\pi_\eta$, and a lawful deterministic Borel transport as in part 4. Write $\beta_\epsilon=(T_\epsilon)_\#\pi_\eta$ and $u_\epsilon(x)=\theta_\epsilon(x)-\theta(x)$. Since $|u_\epsilon|\le\epsilon K$ almost everywhere and the image lies in $\mathcal E$,
$$
\int\theta_\epsilon^2\,d\pi_\eta
\le2M_2(\pi_\eta)+2\epsilon^2K^2<\infty.
$$
Thus $\beta_\epsilon\in\mathcal P_2(\mathcal E)$ (finite first moment also follows by Cauchy--Schwarz). It is a deterministic law independent of Gaussian randomness, so maximality applies without any continuity or differentiability assumption on the family:
$$
F(\beta_\epsilon)-F(\pi_\eta)
\le\eta\{M_2(\beta_\epsilon)-M_2(\pi_\eta)\}.
$$
The signed moment increment is exactly
$$
M_2(\beta_\epsilon)-M_2(\pi_\eta)
=\int(2\theta u_\epsilon+u_\epsilon^2)\,d\pi_\eta
\le2\epsilon K\sqrt{M_2(\pi_\eta)}+\epsilon^2K^2,
$$
where the final inequality uses $\int|\theta|\,d\pi_\eta\le\sqrt{M_2(\pi_\eta)}$. Multiplying by $\eta$ proves the displayed comparisons in part 4, retaining the signed increment in the first comparison. For a family defined at all sufficiently small positive $\epsilon$, division by $\epsilon$ and the upper limit give
$$
\limsup_{\epsilon\downarrow0}
\frac{F(\beta_\epsilon)-F(\pi_\eta)}{\epsilon}
\le2K\eta\sqrt{M_2(\pi_\eta)}
=2K\sqrt\eta\sqrt{\eta M_2(\pi_\eta)}\le2K\sqrt\eta.
$$
The last inequality uses step 3, and step 6 shows that the extra square-root factor tends to zero for every maximizing selection as $\eta\downarrow0$. The coefficient for fixed $K$ contains no $d$; existence and compactness remain statements at fixed finite $d$. The reasoning also covers $K=0$, with no division by $K$.

**8. Fixed signed velocities and direction changes.** If $u_\epsilon=\epsilon b$ with fixed Borel $|b|\le K$ almost everywhere, then $\theta b$ is integrable by Cauchy--Schwarz and $b^2$ is integrable by boundedness. The exact expansion is
$$
\eta\{M_2(\beta_\epsilon)-M_2(\pi_\eta)\}
=2\eta\epsilon\int\theta b\,d\pi_\eta
+\eta\epsilon^2\int b^2\,d\pi_\eta.
$$
Insert it into the first comparison in step 7, divide by $\epsilon$ and take the upper limit. This gives the signed bound $2\eta\int\theta b\,d\pi_\eta$ claimed in part 5. A pure direction transport retains mean and tag and maps every direction to a unit direction. Its moment increment is identically zero, so the same comparison gives $F(\beta_\epsilon)\le F(\pi_\eta)$ for each lawful transport. Domain preservation has been imposed throughout. In particular a point with mean zero and retained tag one must have output mean at most zero; upward motion there is inadmissible. Neither this argument nor the finite recovery below uses a reclassification of a true null to assert an ordinary finite-model variation.

**9. Finite recovery of both endpoints after fixing the perturbation.** Fix $\eta$ and any lawful family from part 4. For each sufficiently small positive $\epsilon$, step 7 gives a deterministic law $\beta_\epsilon\in\mathcal P_2(\mathcal E)$. Apply step 4 separately to $\pi_\eta$ and $\beta_\epsilon$. Since each of its three errors tends to zero, choose one finite canonical approximation $\mu_\epsilon$ of $\pi_\eta$ and one $\nu_\epsilon$ of $\beta_\epsilon$ such that
$$
\begin{aligned}
&W_1(\mu_\epsilon,\pi_\eta)+W_1(\nu_\epsilon,\beta_\epsilon)
+|F(\mu_\epsilon)-F(\pi_\eta)|+|F(\nu_\epsilon)-F(\beta_\epsilon)|\\
&\quad+|M_2(\mu_\epsilon)-M_2(\pi_\eta)|
+|M_2(\nu_\epsilon)-M_2(\beta_\epsilon)|
\le\frac{\epsilon^2}{1+\eta}.
\end{aligned}
$$
For example, fix the deterministic approximation sequences from step 4 and choose at each endpoint the first integer index for which its three-error sum is less than $\epsilon^2/[2(1+\eta)]$. These are choices from deterministic parameter laws, with no dependence on Gaussian realizations. No measurability in $\epsilon$ or uniform continuity modulus is required.

The error in replacing the completed FDR increment by the finite one is bounded by the sum of the two absolute FDR errors. The error in the signed moment increment is bounded by the sum of the two absolute moment errors. Substitution into step 7 therefore yields
$$
F(\nu_\epsilon)-F(\mu_\epsilon)
\le\eta\{M_2(\nu_\epsilon)-M_2(\mu_\epsilon)\}+\epsilon^2.
$$
All six errors have sum $O(\epsilon^2)=o(\epsilon)$, and
$$
\left|\frac{F(\nu_\epsilon)-F(\mu_\epsilon)}{\epsilon}
-\frac{F(\beta_\epsilon)-F(\pi_\eta)}{\epsilon}\right|
\le\frac{\epsilon}{1+\eta}\longrightarrow0.
$$
Thus the two difference quotients have identical upper limits, including extended-real upper limits. Step 5 realizes each endpoint as an ordinary finite canonical Gaussian model. Their sizes and multiplicities can vary with $\epsilon$; no derivative of one fixed finite array, interchange of atomization and differentiation, or finite-copy derivative transfer is asserted. The argument includes mixed tags at zero through the tag-preserving quantization, unbounded input means through the $L^2$ truncation, duplicated finite scores through the covariance and rank calculation, and all crossing endpoints through the same full functional. This proves all six clauses.

