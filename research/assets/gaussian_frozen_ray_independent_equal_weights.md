---
title: >-
  Sharp frozen-ray truncated moment and maximal tail for independent
  equal-weight directions
type: theorem
status: approved
source:
  kind: original
  note: >-
    Researcher-authorized intermediate target of 10 November 2026; an unproved
    special case of the frozen-ray conjecture.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
tags:
  - cross-discipline-brainstorm-20261110
  - frozen-ray
  - independent-equal-weights
---

# Sharp frozen-ray truncated moment and maximal tail for independent equal-weight directions

## Statement

For every positive integer $K$, let $Z_1,\ldots,Z_K$ be independent standard normal random variables. This is the centered [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with correlation matrix $I_K$, the $K\times K$ identity matrix. For real $w\geq0$ define
$$
L_w(Z)=\frac1K\sum_{i=1}^K\exp\!\left(wZ_i-\frac{w^2}{2}\right),\qquad
\Lambda(Z)=\sup_{w\geq0}L_w(Z).
$$
The same realization of the entire vector $Z$ is used for every $w$ in the supremum. Expectations and probabilities below are under its stated Gaussian law, and logarithms are natural.

There exist finite constants $C_{\mathrm{sh}}>0$ and $C_{\mathrm{tail}}>0$ such that, simultaneously for every positive integer $K$, every real $c\geq2$, and every real $\alpha\geq2$,
$$
\mathbb E\min\{c,\Lambda(Z)\}
\leq\sqrt{\frac{\log c}{\pi}}+C_{\mathrm{sh}},
$$
$$
\mathbb P\{\Lambda(Z)\geq\alpha\}
\leq\frac{C_{\mathrm{tail}}}{\alpha\sqrt{\log\alpha}}.
$$
Both constants are independent of $K,c,\alpha$. The supremum is over the full interval $[0,\infty)$, with no truncation of $w$ or asymptotic relation between the parameters. Both assertions, including the coefficient $1/\sqrt\pi$ in the truncated moment, are part of this target.

## Motivation

This is the independent equal-weight restriction of the [frozen-ray maximal likelihood-ratio idea](../ideas/idea_9f8ffb204424.md). The [planted-SNR proof program](../ideas/idea_dc6cf14ab94d.md), [Gibbs variational form](../ideas/idea_c36aadbe5f06.md), and [tail calibration](../ideas/idea_76d8bdfb8584.md) supply candidate mechanisms and diagnostics; their unverified identities and inequality (K) remain separate proof obligations. The [stress-test program](../ideas/idea_57338934f2f7.md) supplies numerical search families, not a proof or refutation.

This statement is an intermediate goal only. It contains no proof and asserts no reduction of a finite Gaussian BH problem to this likelihood-ratio field. The [structured-class program](../ideas/idea_7727ae2d6679.md) is a separate proposed route. Native counterexample search must precede a proof plan for this asset.

## Proof

We prove both bounds with $C_{\mathrm{sh}}=9$ and $C_{\mathrm{tail}}=150$. Only the independent standard normal specialization stated above is used.

### Gaussian preliminaries, measurability, and the scalar case

Write $\phi(x)=(2\pi)^{-1/2}e^{-x^2/2}$ and $\overline\Phi(x)=\int_x^\infty\phi(t)\,dt$. Since $\phi'(t)=-t\phi(t)$, for $x>0$,
$$
\overline\Phi(x)\le\frac1x\int_x^\infty t\phi(t)\,dt=\frac{\phi(x)}x.
$$
For each finite real vector $z$, every summand of $L_w(z)$ is continuous in $w$ and tends to zero as $w\to\infty$, by completing the square in its exponent. Thus $L_w(z)$ is continuous, tends to zero, and, because $L_0(z)=1$, attains a finite maximum on $[0,\infty)$. Continuity implies that its supremum equals the supremum over nonnegative rational $w$. The latter is a countable supremum of measurable functions of $z$, proving measurability of $\Lambda$ without selecting a maximizer measurably.

For $K=1$, maximizing $wZ-w^2/2$ over $w\ge0$ gives $\Lambda=e^{(Z^+)^2/2}$, where $Z^+=\max(Z,0)$. For $c\ge2$ put $v_c=\sqrt{2\log c}>1$. Splitting the Gaussian integral into $(-\infty,0]$, $(0,v_c)$, and $[v_c,\infty)$ gives
$$
\mathbb E\min(c,\Lambda)=\frac12+\int_0^{v_c}e^{z^2/2}\phi(z)\,dz+c\overline\Phi(v_c)
=\frac12+\sqrt{\frac{\log c}{\pi}}+c\overline\Phi(v_c).
$$
Mills' bound yields $c\overline\Phi(v_c)\le1/(\sqrt{2\pi}v_c)<1$, so the required moment bound holds with the chosen constant. For every $\alpha\ge2$ the exact scalar tail and its bound are
$$
\mathbb P(\Lambda\ge\alpha)=\overline\Phi(\sqrt{2\log\alpha})
\le\frac{1}{2\sqrt\pi\,\alpha\sqrt{\log\alpha}}
\le\frac{150}{\alpha\sqrt{\log\alpha}}.
$$
The equalities at the splitting points cause no extra term because the Gaussian law has no atoms. Here and below $\log2>1/2$, for example from $\log2=\int_1^2t^{-1}\,dt>1/2$.

### Critical truncation and all-scale envelopes

Assume henceforth $K\ge2$, and put $u=\sqrt{2\log K}>1$, so $K=e^{u^2/2}$. For $i\in\{1,\ldots,K\}$ define
$$
f_i(w)=\frac1K e^{wZ_i-w^2/2}\mathbf1_{\{Z_i\le u\}},\quad
B(w)=\sum_{i=1}^K f_i(w),\quad F=\sup_{w\ge0}B(w),
$$
$$
X_i=\frac1K e^{Z_i^2/2}\mathbf1_{\{Z_i>u\}},\qquad R=\sum_{i=1}^K X_i.
$$
For a real $z$, $\sup_{w\ge0}e^{wz-w^2/2}=e^{(z^+)^2/2}$. Consequently $0\le f_i(w)\le K^{-1}e^{u^2/2}=1$. For $z>u>0$, the same scalar maximization bounds the discarded summand by $K^{-1}e^{z^2/2}$. It follows pointwise that
$$
L_w\le B(w)+R,\qquad \Lambda\le F+R,\qquad F\le K,\qquad B(0)\le1.
$$
The functions $B$ and $\sum_{j\ne i}f_j$ are continuously differentiable and vanish at infinity for every finite sample. When a sum has no retained coordinates it is identically zero; otherwise it is positive at zero and its maximum is attained, by the compact-interval argument used for $L_w$. Their suprema equal their rational suprema and hence are measurable. These statements concern the entire half-line $[0,\infty)$.

### Uniform mean of the collective envelope

For a scalar standard normal $Z$ and a fixed finite $w\ge0$, set
$$
Q_w=(Z-w)e^{wZ-w^2/2}\mathbf1_{\{Z\le u\}}.
$$
Differentiating the finite sample sum gives $B'(w)=K^{-1}\sum_{i=1}^K Q_w(Z_i)$. Each $Q_w$ is square integrable: dropping the indicator and using $e^{2wz-w^2}\phi(z)=e^{w^2}\phi(z-2w)$ gives
$$
\mathbb E Q_w^2\le e^{w^2}\int_{\mathbb R}(z-w)^2\phi(z-2w)\,dz
=(1+w^2)e^{w^2}<\infty.
$$
In particular its first moment exists. The other tilting identity, $e^{wz-w^2/2}\phi(z)=\phi(z-w)$, yields directly
$$
\mathbb E Q_w=\int_{-\infty}^{u}(z-w)\phi(z-w)\,dz=-\phi(u-w)\le0.
$$
If an integrable real variable $Y$ has mean $\mu\le0$, then $Y_+\le|Y-\mu|$, where $Y_+=\max(Y,0)$. Cauchy--Schwarz and independence of the coordinates therefore give, for every such $w$,
$$
\mathbb E(B'(w))_+\le\sqrt{\operatorname{Var}(B'(w))}
=\sqrt{\frac{\operatorname{Var}(Q_w)}K}
\le\sqrt{\frac{\mathbb E Q_w^2}K}.
$$
We now integrate this estimate over all $w$. On $0\le w\le u/2$, $\sqrt{1+w^2}\le1+w$ and $w^2/2-u^2/4\le-u^2/8$, whence
$$
\int_0^{u/2}\sqrt{\frac{\mathbb E Q_w^2}K}\,dw
\le\int_0^{u/2}(1+w)e^{w^2/2-u^2/4}\,dw
\le\left(\frac u2+\frac{u^2}{8}\right)e^{-u^2/8}\le2.
$$
For the last inequality set $x=u^2/8$. The expression is $(\sqrt{2x}+x)e^{-x}$; elementary differentiation gives $\sup_{x\ge0}\sqrt{2x}e^{-x}=e^{-1/2}<1$ and $\sup_{x\ge0}xe^{-x}=e^{-1}<1$.

For $w\ge u/2$, substitute $z=u-s$ in the defining second-moment integral. Keeping the factor $K^{-1}=e^{-u^2/2}$, the exponent is exactly
$$
2w(u-s)-w^2-\frac{(u-s)^2}{2}-\frac{u^2}{2}
=-(w-u)^2-(2w-u)s-\frac{s^2}{2}.
$$
Thus
$$
\frac{\mathbb E Q_w^2}K
=\frac{e^{-(w-u)^2}}{\sqrt{2\pi}}
\int_0^\infty(u-w-s)^2e^{-(2w-u)s-s^2/2}\,ds.
$$
Since $2w-u\ge0$, we may drop its nonpositive contribution to the exponent. Also $(u-w-s)^2\le2(u-w)^2+2s^2$. The standard Gaussian normalization and integration by parts give respectively
$$
\int_0^\infty e^{-s^2/2}\,ds=\sqrt{\pi/2},\qquad
\int_0^\infty s^2e^{-s^2/2}\,ds
=[-se^{-s^2/2}]_0^\infty+\int_0^\infty e^{-s^2/2}\,ds=\sqrt{\pi/2}.
$$
Consequently
$$
\frac{\mathbb E Q_w^2}K\le((w-u)^2+1)e^{-(w-u)^2},
$$
and, substituting $t=w-u$ and enlarging the domain,
$$
\int_{u/2}^\infty\sqrt{\frac{\mathbb E Q_w^2}K}\,dw
\le\int_{\mathbb R}\sqrt{t^2+1}e^{-t^2/2}\,dt
\le\int_{\mathbb R}(|t|+1)e^{-t^2/2}\,dt=2+\sqrt{2\pi}.
$$
The maps involved are jointly measurable in the sample and $w$, being finite sums of continuous exponential functions times Borel indicators. For every finite $T$, the fundamental theorem of calculus gives pointwise
$$
\sup_{0\le w\le T}B(w)\le B(0)+\int_0^T(B'(w))_+\,dw.
$$
Tonelli applies to the nonnegative integrand; the bounds just proved show that its integral of expectations over the whole half-line is finite. Taking expectations, and then increasing integer $T$ to infinity using monotone convergence for the nonnegative suprema, proves
$$
\mathbb EF\le1+2+2+\sqrt{2\pi}<8.
$$
There is no unproved interchange of differentiation and expectation in this argument: the derivative is of a finite sample sum, and both scalar moments were computed directly at each $w$.

### Sharp truncated moment

For nonnegative numbers, $\min(c,a+b)\le a+\min(c,b)$ and $\min(c,\sum_i b_i)\le\sum_i\min(c,b_i)$. The second inequality follows by splitting into the cases $\sum_i b_i\le c$ and $\sum_i b_i>c$; in the latter case either a term is at least $c$, or the sum of the truncated terms is the original sum. Therefore
$$
\min(c,\Lambda)\le F+\min(c,R)\le F+\sum_{i=1}^K\min(c,X_i).
$$
For every real $c\ge2$, put $v=\sqrt{2\log(Kc)}>u$. On $u<Z<v$, the mark $X_1$ equals $K^{-1}e^{Z^2/2}<c$, and on $Z\ge v$ it is at least $c$; it is zero on $Z\le u$. Direct integration thus gives exactly
$$
K\mathbb E\min(c,X_1)
=\int_u^v e^{z^2/2}\phi(z)\,dz+cK\overline\Phi(v)
=\frac{v-u}{\sqrt{2\pi}}+cK\overline\Phi(v).
$$
Since $Kc\phi(v)=1/\sqrt{2\pi}$ and $v>1$, Mills' bound gives $cK\overline\Phi(v)\le1/(\sqrt{2\pi}v)\le1$. For $a,b\ge0$, squaring $\sqrt{a+b}\le\sqrt a+\sqrt b$ proves $\sqrt{a+b}-\sqrt a\le\sqrt b$. Hence
$$
\mathbb E\min(c,\Lambda)
\le8+1+\frac{\sqrt{\log(Kc)}-\sqrt{\log K}}{\sqrt\pi}
\le9+\sqrt{\frac{\log c}{\pi}}.
$$

### Deletion variance, with product tensorization proved directly

Define $F_{-i}=\sup_{w\ge0}\sum_{j\ne i}f_j(w)$ and $d_i=F-F_{-i}$. These variables are measurable by the rational-supremum argument, and $F_{-i}$ depends only on $Z_{-i}=(Z_j)_{j\ne i}$. For each sample choose any common maximizer $w_*$ of $B$; in the identically zero case take $w_*=0$. No measurable choice is needed. Nonnegativity of $f_i$ gives $F_{-i}\le F$, whereas evaluation at $w_*$ gives $F_{-i}\ge F-f_i(w_*)$. Thus
$$
0\le d_i\le f_i(w_*)\le1,\qquad
\sum_{i=1}^K d_i\le\sum_{i=1}^K f_i(w_*)=F,\qquad
\sum_{i=1}^K d_i^2\le F.
$$
We give the independent-coordinate variance inequality used next. For independent coordinates $Y_1,\ldots,Y_n$ and square-integrable $H=h(Y_1,\ldots,Y_n)$, claim
$$
\operatorname{Var}(H)\le\sum_{i=1}^n\mathbb E\operatorname{Var}(H\mid Y_{-i}).
$$
For $n=1$ this is equality, with conditioning on the trivial sigma-field. To prove the induction step, write $Y'=(Y_2,\ldots,Y_n)$ and $G(Y')=\mathbb E_{Y_1}h(Y_1,Y')$, where subscripts on expectations mean integration in the named independent coordinates. The conditional variance decomposition and the induction hypothesis for $G$ give
$$
\operatorname{Var}(H)=\mathbb E\operatorname{Var}(H\mid Y')+\operatorname{Var}(G)
\le\mathbb E\operatorname{Var}(H\mid Y')
+\sum_{i=2}^n\mathbb E\operatorname{Var}(G\mid (Y_j)_{j\ne1,i}).
$$
To bound each last summand, fix the other coordinates $(Y_j)_{j\ne1,i}$ and let $Y_i^*$ be an independent copy of $Y_i$. For any square-integrable function $g(Y_i)$, expansion of the square and independence show $\operatorname{Var}_{Y_i}(g)=\tfrac12\mathbb E_{Y_i,Y_i^*}(g(Y_i)-g(Y_i^*))^2$. Applying this identity to $G$ and Jensen to its $Y_1$ integral gives
$$
\operatorname{Var}_{Y_i}(\mathbb E_{Y_1}h)
=\tfrac12\mathbb E_{Y_i,Y_i^*}
\left[\mathbb E_{Y_1}\{h(Y_1,Y_i,\ldots)-h(Y_1,Y_i^*,\ldots)\}\right]^2
\le\tfrac12\mathbb E_{Y_i,Y_i^*}\mathbb E_{Y_1}
\{h(Y_1,Y_i,\ldots)-h(Y_1,Y_i^*,\ldots)\}^2
=\mathbb E_{Y_1}\operatorname{Var}_{Y_i}(h).
$$
The omitted arguments in this display are precisely the fixed other coordinates and are identical in the two terms. Integrating in those coordinates gives the required $i$th summand of the claimed inequality. This proves the induction; all expressions are finite or bounded by an integrable square because $H$ is square integrable and conditional averaging is a contraction in squared expectation.

Now $0\le F\le K$ ensures square integrability. For any square-integrable variable $U$ and a quantity $a$ fixed under the conditioning, $\mathbb E((U-a)^2\mid\mathcal G)=\operatorname{Var}(U\mid\mathcal G)+(\mathbb E(U\mid\mathcal G)-a)^2$. Applying this with $U=F$, $\mathcal G=\sigma(Z_{-i})$, and $a=F_{-i}$, the variance inequality gives
$$
\operatorname{Var}(F)\le\sum_i\mathbb E\operatorname{Var}(F\mid Z_{-i})
\le\sum_i\mathbb E(F-F_{-i})^2\le\mathbb EF\le8.
$$
For every real $\alpha\ge32$, $\alpha/2-\mathbb EF\ge\alpha/2-8\ge\alpha/4$. Chebyshev's inequality therefore yields
$$
\mathbb P(F\ge\alpha/2)\le\frac{8}{(\alpha/4)^2}=\frac{128}{\alpha^2}.
$$

### Conditional rare marks and the binomial moments

Let $p=\overline\Phi(u)$, $M=\sum_i\mathbf1_{\{Z_i>u\}}$, and $\lambda=Kp$. The normal density is positive everywhere, so $0<p<1$. Independence makes $M$ binomial with parameters $K,p$. Since $K\phi(u)=1/\sqrt{2\pi}$ and $u>1$, Mills' bound gives
$$
\lambda\le\frac1{\sqrt{2\pi}u}\le1.
$$
For completeness, fix a subset $S\subset\{1,\ldots,K\}$ of size $m$. The event that $\{i:Z_i>u\}=S$ has probability $p^m(1-p)^{K-m}>0$. By independence, conditional on this event the coordinates with indices in $S$ are independent with the law of $Z$ given $Z>u$: this follows first for product events by factoring numerator and denominator, and then for their generated sigma-field. Therefore the marks with indices in $S$, listed in increasing index order, have the $m$-fold product law of $K^{-1}e^{Z^2/2}$ conditional on $Z>u$. This product law is the same for every $S$ of size $m$. Averaging over those sets proves that, conditional on $M=m$, the ordered positive marks have that same independent product law. Their sum is $R$, irrespective of the ordering. For $m=0$ it is the empty sum zero.

For $j\ge1$, use the falling factorial $(m)_j=m(m-1)\cdots(m-j+1)$. The product is zero for an integer $0\le m<j$. Expanding $(M)_j$ as the sum over ordered $j$-tuples of distinct indices of the products of their exceedance indicators proves
$$
\mathbb E(M)_j=(K)_j p^j\le(Kp)^j=\lambda^j.
$$
When $j>K$ the index sum is empty and both sides of the equality are zero. In particular, $M^2=(M)_2+M$ implies
$$
\frac{\mathbb EM^2}{Kp}=1+(K-1)p\le1+Kp\le2.
$$
Direct expansion of the four falling factorial polynomials gives the identity $M^4=(M)_4+6(M)_3+7(M)_2+M$. Thus
$$
\mathbb EM^4\le\lambda^4+6\lambda^3+7\lambda^2+\lambda\le15.
$$

### Rare-sum tail and all parameter ranges

Fix real $\alpha\ge32$. For an integer $1\le m\le\sqrt\alpha$ with $m\le K$, put $t=\alpha/(2m)$. Then $t\ge\sqrt\alpha/2\ge2$, and $v=\sqrt{2\log(Kt)}>u$. If the sum of the $m$ positive marks is at least $\alpha/2=mt$, at least one mark is at least $t$. Under the conditional mark law this is the event $Z\ge v$, because $Z>u>0$ and the mark function is increasing there. The conditional union bound and Mills' bound give
$$
\mathbb P(R\ge\alpha/2\mid M=m)
\le\frac{m\overline\Phi(v)}p
\le\frac{m}{p\sqrt{2\pi}Kt v}
=\frac{2m^2}{Kp\,\alpha\sqrt{2\pi}\,v}.
$$
Here $Kt=K\alpha/(2m)\ge\sqrt\alpha$, since $K\ge2$ and $m\le\sqrt\alpha$. Hence $v\ge\sqrt{\log\alpha}$, and averaging the last bound over $1\le M\le\sqrt\alpha$ gives at most
$$
\frac{2\mathbb EM^2}{Kp\,\alpha\sqrt{2\pi\log\alpha}}
\le\frac{4}{\sqrt{2\pi}\,\alpha\sqrt{\log\alpha}}
\le\frac{2}{\alpha\sqrt{\log\alpha}}.
$$
These inequalities remain valid when an individual conditional upper bound exceeds one. The event $M=0$ contributes zero; for the complementary count regime Markov's inequality and the fourth moment give
$$
\mathbb P(M>\sqrt\alpha)\le\frac{\mathbb EM^4}{\alpha^2}\le\frac{15}{\alpha^2}.
$$
Combining both count regimes proves
$$
\mathbb P(R\ge\alpha/2)\le\frac{2}{\alpha\sqrt{\log\alpha}}+\frac{15}{\alpha^2}.
$$
Since $\Lambda\le F+R$, the collective and rare-sum bounds now imply
$$
\mathbb P(\Lambda\ge\alpha)
\le\frac{2}{\alpha\sqrt{\log\alpha}}+\frac{143}{\alpha^2}
\le\frac{145}{\alpha\sqrt{\log\alpha}},\qquad \alpha\ge32.
$$
For the last inequality, $\log\alpha\le\alpha-1\le\alpha^2$ for $\alpha\ge2$, the first inequality following by integrating $1/t\le1$ from $1$ to $\alpha$. Thus $\sqrt{\log\alpha}/\alpha\le1$. On the remaining range $2\le\alpha<32$, the function $\alpha\sqrt{\log\alpha}$ is increasing (its derivative is $\sqrt{\log\alpha}+1/(2\sqrt{\log\alpha})>0$), and
$$
\alpha\sqrt{\log\alpha}\le32\sqrt{\log32}<32\sqrt5<150,
$$
using $\log2<1$ and hence $\log32=5\log2<5$. The probability bound one therefore yields $\mathbb P(\Lambda\ge\alpha)\le150/(\alpha\sqrt{\log\alpha})$ throughout this range as well.

Together with the scalar case, both assertions now hold for every positive integer $K$ and all real $c,\alpha\ge2$, with no relation between these parameters. Every supremum used above ranges over the full half-line. This completes the proof.
