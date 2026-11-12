---
type: example
title: >-
  Counterexample to gaussian_bh_entropy_coherence_trace_budget: Unbalanced
  antipodal null clones make the entropy-coherence trace ratio diverge
status: approved
source:
  kind: original
refutes: gaussian_bh_entropy_coherence_trace_budget
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_bh_fdp_mills_heat_fields
tags: []
---

## Statement

For any finite integer $N\ge2$ and $0<q\le\overline\Phi(3)$, let $d=1$, let $G$ be standard normal, and take $N$ original true nulls, all with mean zero:
$$
T_1=\cdots=T_{N-1}=G,\qquad T_N=-G.
$$
Thus $v_1=\cdots=v_{N-1}=1$ and $v_N=-1$. Define
$$
p=\frac1N,\quad U=\overline\Phi^{-1}(q),\quad H=h(U),\quad
a=\overline\Phi^{-1}(q(1-p)),\quad A=\overline\Phi^{-1}(qp),
$$
$$
c_+=\frac1{h(a)},\qquad c_-=\frac1{h(A)},\qquad d_*=c_++c_-.
$$
The finite counterfamily used below is indexed by integers $k\ge3$:
$$
q_k=\overline\Phi(k),\qquad
N_k=\left\lceil\frac{q_k}{\overline\Phi(k^4)}\right\rceil.
$$
Every $N_k$ is a finite integer. The construction is analytic and requires no computation with an array of size $N_k$.

This family is not the balanced two-test antipodal model already excluded on the board. The number of positive copies grows, the actual positive rejection rank is $N-1$, the negative rank is $1$, their tilted masses are $1-1/N$ and $1/N$, and their terminal Mills-field magnitudes are different. The all-null parallel family has only one orientation and does not cover it. The nonpositive-correlation two-null calculation has only two tests and does not cover these unequal multiplicities.

## Assumptions

### H1

For every finite $k$, $N_k$ and $d=1$ are finite positive integers and each loading has Euclidean norm one. The covariance is the Gram matrix of these loadings, so it is positive semidefinite with unit diagonal, although singular. Every original mean is zero, so the original one-sided true-null set is all $N_k$ indices. No non-Gaussian statistic, modified null label or covariance approximation is used.

### H2

We use the original ordinary BH rule, its largest qualifying rank, all multiplicities and non-strict threshold inequalities. Since $q<1/2$, on $G\ge0$ the negative statistic has p-value at least $1/2$ and cannot be selected. The $N-1$ equal positive p-values qualify at some rank if and only if they qualify at their largest possible rank $N-1$. Similarly, on $G<0$ no positive copy can be selected and the only possible rejection rank is $1$. Consequently the exact actual rejection counts are
$$
R(G)=
\begin{cases}
N-1,&G\ge a,\\
1,&G\le-A,\\
0,&-A<G<a.
\end{cases}
$$
Both endpoint equalities are included. This is an actual BH partition, not a freely chosen rank or threshold.

### H3

All hypotheses are null, so $f=\mathbf1_{\{G\ge a\}\cup\{G\le-A\}}$. Therefore
$$
F=\overline\Phi(a)+\overline\Phi(A)=q(1-p)+qp=q>0,
\qquad D=\log(1/q).
$$
The terminal tilt $Q$ is the standard normal conditioned on these two tails, and its negative-tail mass is exactly $p$. Its full path tilt is exactly the Wiener measure weighted by $f(W_1)/q$, as in the target definition.

### H4

The actual terminal field is $b(G)=c_+$ on the positive tail and $b(G)=-c_-$ on the negative tail. Write $s=\sqrt{1-t}$ and, for $t<1$, put
$$
L_+(t,z)=\overline\Phi\!\left(\frac{a-z}{s}\right),\qquad
L_-(t,z)=\overline\Phi\!\left(\frac{A+z}{s}\right),\qquad
\pi(t,z)=\frac{L_-(t,z)}{L_+(t,z)+L_-(t,z)}.
$$
Then $\pi_t=\pi(t,W_t)$ is the conditional probability of the negative terminal branch under the actual path tilt. The full heat-posterior Mills field, with the conventions in the statement, is precisely
$$
a_t=c_+-d_*\pi_t.
$$
No component or interface has been dropped.

For completeness all cutoff integrals are finite. On every time interval $[0,\tau]$, $\tau<1$, the strictly positive density martingale $(L_++L_-)/q$ gives, by the local change of measure, a Brownian innovation with drift $\partial_z\log(L_++L_-)$. The bounded conditional martingale $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$ has stochastic differential $da_t=K_t\,d\widetilde W_t$, obtained by Itô's formula for its smooth heat quotient. Localization and the bounded-martingale Itô isometry give
$$
\mathbb E_{\mathbb Q}\int_0^\tau K_t^2dt
=\mathbb E_{\mathbb Q}a_\tau^2-a_0^2\le c_+^2\le H^{-2}.
$$
Here $A\ge a\ge U$, $h$ is increasing, and hence $0<c_-\le c_+\le H^{-1}$. Monotone convergence followed by Cauchy--Schwarz yields
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le H^{-1}<\infty.
$$
Also $0\le x\le H^2c_+^2<1$, since $a>U$ for finite $N$. Thus the signed trace $M$ exists absolutely and the deficit $1-x$ is strictly positive. Entropy finiteness was already computed exactly in H3.

### H5

The parameters may vary with $q$, exactly as the target permits. The displayed $q_k$ tend to zero and lie in $(0,\overline\Phi(3)]$. For any proposed universal positive $q_0$, all sufficiently large $k$ have $q_k\le q_0$. The construction retains the original means and actual singular covariance at every finite $k$; there is no replacement of a finite model by a population limit.

## Calculation

We show that the target's normalized positive trace is unbounded. All estimates below are finite-model inequalities.

#### 1. A uniform upper bound for the coherence deficit

The exact martingale relation $\mathbb E_{\mathbb Q}\pi_t=p$ gives
$$
x=H^2\left(c_+^2-2c_+d_*p
   +d_*^2\int_0^1\mathbb E_{\mathbb Q}\pi_t^2dt\right).
$$
Moreover,
$$
Hc_+=\frac{h(U)}{h(a)}
=(1-p)\exp\!\left(\frac{a^2-U^2}{2}\right)\ge1-p.
$$
Using $Hc_+\le1$ and $Hd_*\le2$, and dropping the nonnegative last term in $x$, gives the exact upper bound
$$
0<1-x\le 1-H^2c_+^2+2H^2c_+d_*p
\le2p+4p=6p.
$$
The same identity also gives $c_+\ge(1-p)/H\ge1/(2H)$.

#### 2. The complete trace is nonnegative

Let $\beta_\pm=\partial_z\log L_\pm$ denote the two component drifts, not the full marginal drift. Conditional terminal means on the two branches are separated by at least $A+a$. Therefore, for every $t<1,z$,
$$
\beta_+(t,z)-\beta_-(t,z)
=\frac{\mathbb E[W_1\mid W_t=z,W_1\ge a]
       -\mathbb E[W_1\mid W_t=z,W_1\le-A]}{1-t}
\ge\frac{A+a}{1-t}\ge A.
$$
Differentiating the actual posterior quotient yields
$$
K_t=d_*\pi_t(1-\pi_t)(\beta_+-\beta_-)(t,W_t)\ge0.
$$
Thus $M_+=M$, and a lower bound from an initial time interval is a lower bound for the full signed trace.

#### 3. The rare branch remains posterior-uncertain over a fixed time interval

Assume the explicit finite inequalities
$$
A\ge\max\{12,6\overline\Phi^{-1}(q/2)\}.
$$
Since $a\le\overline\Phi^{-1}(q/2)$, this implies $a\le A/6$. Let $\mathbb Q_-$ denote the actual path measure conditional on $W_1\le-A$. Given its endpoint $G=W_1$, its path is the original Brownian bridge; in particular
$$
W_t=tG+\sqrt{t(1-t)}Z,
$$
with a standard normal bridge marginal $Z$ independent of the endpoint at that time.

For $0\le t\le1/8$, split off endpoints $G<-2A$. Their conditional probability is
$$
\frac{\overline\Phi(2A)}{\overline\Phi(A)}\le e^{-3A^2/2}.
$$
On $-2A\le G\le-A$, the bridge mean is at least $-A/4$ and its standard deviation is at most $1/2$. Hence
$$
\mathbb Q_-(W_t<-A/3)
\le e^{-3A^2/2}+\overline\Phi(A/6)
\le e^{-3A^2/2}+\tfrac12e^{-A^2/72}.
$$
The last two Gaussian-tail comparisons follow by integrating $h(y)\ge y$; the second starts at $\overline\Phi(0)=1/2$.

For $z\ge-A/3$, $L_-$ decreases and $L_+$ increases with $z$, so
$$
\pi(t,z)\le\frac{L_-(t,z)}{L_+(t,z)}
\le\frac{\overline\Phi(2A/(3s))}{\overline\Phi(A/(2s))}
\le e^{-7A^2/(72s^2)}\le e^{-7A^2/72}.
$$
Here $a\le A/6$ was used in the denominator, and again the tail ratio follows by integrating $h(y)\ge y$. Combining the two regions gives, uniformly on $0\le t\le1/8$,
$$
\mathbb E_{\mathbb Q_-}\pi_t
\le e^{-3A^2/2}+\tfrac12e^{-A^2/72}+e^{-7A^2/72}<\tfrac12.
$$
The strict last inequality already holds at $A=12$, and each term decreases thereafter. Finally the posterior identity
$$
\mathbb E_{\mathbb Q}\pi_t^2
=\mathbb E_{\mathbb Q}[\mathbf1_{\{W_1\le-A\}}\pi_t]
=p\mathbb E_{\mathbb Q_-}\pi_t
$$
implies
$$
\mathbb E_{\mathbb Q}[\pi_t(1-\pi_t)]\ge p/2
\qquad(0\le t\le1/8).
$$

#### 4. The finite trace-to-deficit ratio diverges

Using the full nonnegative trace, the preceding finite bounds give
$$
M=q\mathbb E_{\mathbb Q}\int_0^1 K_tdt
\ge qd_*A\int_0^{1/8}\mathbb E_{\mathbb Q}[\pi_t(1-\pi_t)]dt
\ge\frac{qpA}{32H}.
$$
Consequently
$$
\frac{M_+}{q\sqrt{1+D}(1-x)}
\ge\frac{A}{192H\sqrt{1+\log(1/q)}}.
$$
At any fixed allowed $q$, the right side diverges as $N\to\infty$ while every individual model remains finite. To invalidate any proposed universal small-level interval explicitly, use the family in Object. Then $U=k$ and $A\ge k^4$. Integrating $h(y)\ge y$ gives
$$
\overline\Phi^{-1}(q_k/2)\le k+\frac{\log2}{k},
$$
so $A\ge\max\{12,6\overline\Phi^{-1}(q_k/2)\}$ for all $k\ge3$. Elementary Mills bounds give
$$
H\le k+1/k,\qquad
D=\log(1/q_k)\le\frac{k^2}{2}+
\log\!\left(\sqrt{2\pi}(k+1/k)\right)\le k^2
\quad(k\ge3).
$$
For the last inequality the difference is positive at $k=3$ and increasing. Thus $H\sqrt{1+D}\le2k^2$, and
$$
\frac{M_+}{q_k\sqrt{1+D}(1-x)}\ge\frac{k^2}{384}\longrightarrow\infty.
$$
For any proposed finite $C$ and any $q_0>0$, choose a sufficiently large finite $k$ so that $q_k\le q_0$ and $k^2/384>C$. This finite original Gaussian model satisfies every hypothesis and violates the claimed trace budget.

Promoted from search candidate cand_gaussian_bh_entropy_coherence_trace_budget_r3_s1_unbalanced_antipodal_clones.

## Verdict

confirmed

An independent reconstruction confirms a counterexample to the auxiliary trace budget, including its universal-constant and small-level quantifiers. The pre-verdict example had SHA256 `2d556665e6f802478f968ee53a0c0d1603996df19d181f0d9db7f1227753bc17`. No statement, calculation, target asset or approval record was changed in this verification.

### Original model and actual BH rule

For every finite member, the loadings are scalars of absolute value one, the covariance is their Gram matrix, and all means are zero. Thus the singular covariance and the original all-true null set satisfy the target hypotheses. The diagonal construction has $N_k\ge2$, since $\overline\Phi(k^4)<\overline\Phi(k)$ for $k\ge3$.

For $G\ge0$ the negative loading has p-value at least $1/2>q$, so rank $N$ cannot qualify. The tied positive p-values qualify at some rank precisely when rank $N-1$ qualifies. For $G<0$, only the negative loading can qualify, and only at rank $1$. Therefore the displayed two-tail partition is the ordinary largest-rank BH rule with its original multiplicities and non-strict endpoint inequalities. It follows directly that $f$ is the indicator of the two tails, $F=q$, $D=\log(1/q)$, and the negative branch has $\mathbb Q$-probability $p=1/N$.

### Full heat field and endpoint integrability

On the positive branch, summing the $N-1$ selected loadings and dividing by the actual rejection count gives $b=c_+$. On the negative branch, $b=-c_-$. Gaussian conditioning consequently gives exactly $a_t=c_+-d_*\pi_t$. The identity $\mathbb E_{\mathbb Q}\pi_t=p$ is the tower property for the actual terminal branch indicator, not a separate mixture approximation.

On each compact time interval before $1$, Gaussian convolution is smooth and its denominator is positive. The heat quotient solves the backward equation with the Doob drift $\partial_z\log(L_++L_-)$; Itô's formula under the terminally tilted path law therefore yields $da_t=K_t\,d\widetilde W_t$. The quotient is the conditional expectation of a bounded terminal variable, so localization and Itô isometry give
$$
\mathbb E_{\mathbb Q}\int_0^\tau K_t^2dt
=\mathbb E_{\mathbb Q}a_\tau^2-a_0^2\le c_+^2.
$$
Letting $\tau\uparrow1$ and using Cauchy--Schwarz over time and probability proves absolute integrability of $K$. Since $h$ is strictly increasing and $a>U$, $|a_t|\le c_+<1/H$; hence $0\le x<1$. Thus the normalized ratio is well defined and no failure of an endpoint-existence hypothesis is being substituted for failure of the stated inequality.

### Deficit and signed-trace checks

Expanding the exact posterior field gives
$$
x=H^2\left(c_+^2-2c_+d_*p+d_*^2\int_0^1\mathbb E_{\mathbb Q}\pi_t^2dt\right).
$$
The directly verified relation $Hc_+=(1-p)\exp((a^2-U^2)/2)\ge1-p$, together with $Hc_+\le1$ and $Hd_*\le2$, gives $0<1-x\le6p$ and $d_*\ge c_+\ge1/(2H)$.

Differentiating the posterior gives $\partial_z\pi=\pi(1-\pi)(\beta_--\beta_+)$, with no missing mixture term. The component conditional terminal means lie respectively above $a$ and below $-A$, so $\beta_+-\beta_-\ge(A+a)/(1-t)\ge A$. Hence $K_t\ge0$ everywhere and $M_+=M$. The lower bound on an initial time interval therefore cannot be cancelled by an omitted negative contribution later.

### Finite posterior-overlap check

Under $\mathbb Q_-$, conditioning on the terminal value leaves the original Brownian bridge unchanged. For $t\le1/8$, endpoints in $[-2A,-A]$ give bridge mean at least $-A/4$ and standard deviation at most $1/2$. Therefore
$$
\mathbb Q_-(W_t<-A/3)
\le e^{-3A^2/2}+\tfrac12e^{-A^2/72}.
$$
Both tail estimates are valid: $h(y)\ge y$ for $y\ge0$ gives $\overline\Phi(2A)/\overline\Phi(A)\le e^{-3A^2/2}$ and $\overline\Phi(A/6)\le\tfrac12e^{-A^2/72}$. On the remaining bridge positions, $A\ge6a$ implies
$$
\pi(t,z)\le
\frac{\overline\Phi(2A/(3\sqrt{1-t}))}
{\overline\Phi(A/(2\sqrt{1-t}))}
\le e^{-7A^2/[72(1-t)]}\le e^{-7A^2/72}.
$$
At $A\ge12$ the sum of these three finite error terms is less than $1/2$. The Bayes identity $\mathbb E_{\mathbb Q}\pi_t^2=p\mathbb E_{\mathbb Q_-}\pi_t$ then gives $\mathbb E_{\mathbb Q}\pi_t(1-\pi_t)\ge p/2$ uniformly for $0\le t\le1/8$. Consequently
$$
M\ge qd_*A\frac{p}{16}\ge\frac{qpA}{32H},\qquad
\frac{M_+}{q\sqrt{1+D}(1-x)}
\ge\frac{A}{192H\sqrt{1+\log(1/q)}}.
$$

### Diagonal quantifiers and scope

For $q_k=\overline\Phi(k)$ and $N_k=\lceil q_k/\overline\Phi(k^4)\rceil$, one has $A\ge k^4$. Integrating $h(y)\ge y$ gives $\overline\Phi^{-1}(q_k/2)\le k+(\log2)/k$, so both finite posterior-overlap conditions hold for every $k\ge3$. Integration by parts gives the elementary Mills bound $h(k)\le k+1/k$, and
$$
\log(1/q_k)\le\tfrac12k^2+
\log\bigl(\sqrt{2\pi}(k+1/k)\bigr)\le k^2.
$$
The last difference is positive at $3$ and has positive derivative for $k\ge3$. Thus $H\sqrt{1+D}\le2k^2$, yielding the stated lower bound $k^2/384\to\infty$. Given any proposed finite $C$ and any positive $q_0$, a sufficiently large finite $k$ simultaneously satisfies $q_k\le q_0$ and $k^2/384>C$. All dimensions and covariances in that member remain finite and exactly Gaussian.

This confirms falsity only of $M_+\le Cq\sqrt{1+D}(1-x)$. The same models have actual FDR exactly $q$, so they do not refute either unrestricted $O(q\sqrt{\log(1/q)})$ main upper-bound target.
