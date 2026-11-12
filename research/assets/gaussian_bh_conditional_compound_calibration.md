---
type: lemma
title: Finite-level conditional compound-p calibration for the actual BH rank
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - conditional_pvalue_distributions
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags: []
---

## Statement

Fix an integer $N\ge1$, a fixed true-null set $I_0\subseteq\{1,\ldots,N\}$, and $q\in(0,1)$. Let $P_1,\ldots,P_N\in[0,1]$ have mutually independent regular conditional coordinate distributions given a real random variable $Z$, as in [conditional p-value distributions and independence](../definitions/conditional_pvalue_distributions.md); degenerate coordinates are permitted and no individual conditional superuniformity is assumed. For almost every $z$, let $F_{i,z}$ be conditional CDFs and put
$$
M_q(z)=\sup_{0<t\le q}\frac{\sum_{i\in I_0}F_{i,z}(t)}{Nt},
\qquad K_q(z)=\max\{1,M_q(z)\}.
$$
The supremum may be taken over $t=q$ and rational $t\in(0,q)$, giving a measurable extended-real variable. Run [ordinary BH](../definitions/benjamini_hochberg_step_up.md) on the original p-values at level $q$ with the largest qualifying rank, non-strict comparisons and ties. Using the original null labels and the actual rejection count $R$, let [FDP and FDR](../definitions/false_discovery_rate.md) use $V/(R\vee1)$. Then almost surely
$$
\mathbb E[\operatorname{FDP}_{\mathrm{BH},q}\mid Z]
 \le \min\{1,2qK_q(Z)\},
$$
and hence
$$
\operatorname{FDR}_{\mathrm{BH},q}
 \le \mathbb E\big[\min\{1,2qK_q(Z)\}\big].
$$
The constant $2$ is finite and universal, independent of all dimensions, null fractions and conditional laws. Interpret the right-hand conditional bound as $1$ when $K_q=\infty$. This lemma places the level supremum outside the summed null CDF. It does not assert a Gaussian order estimate for that envelope, remove a noise floor, or prove either unrestricted main theorem.


## Proof

We prove the independent compound-p inequality first. All null labels are kept fixed. Write $\mathbb P_*$ and $\mathbb E_*$ for the law and expectation after fixing the entire nonnull vector; independence leaves the original product law of the null coordinates under this conditioning. Every argument below holds for each fixed nonnull vector, including vectors with ties and degenerate coordinates.

**The actual BH rank.** Suppose independent $X_1,\ldots,X_N\in[0,1]$ satisfy
$$
\sum_{j\in I_0}\mathbb P(X_j\le u)\le Nu\quad(0\le u\le1),
$$
and run BH at level $\alpha\in(0,1)$. Put $m=|I_0|$. If $m=0$ then FDP is identically zero, so suppose $m\ge1$. In particular the compound condition at zero implies that every null coordinate has zero probability of being zero. We work on that probability-one event. Put
$$
 A(k)=\#\{j\notin I_0:X_j\le\alpha k/N\},\qquad
 C(u)=\#\{j\in I_0:X_j\le u\},
$$
$$
 k_i=\max\{k\in\{0,\ldots,N\}:i+A(k)\ge k\},\quad
 u_i=\alpha k_i/N\quad(0\le i\le m).
$$
The set defining $k_i$ contains $k=i$, so $k_i\ge i$; it expands as $i$ increases, so $k_i$ is nondecreasing. Set
$$
 I=\max\bigl(\{0\}\cup\{i\in\{1,\ldots,m\}:C(u_i)\ge i\}\bigr).
$$
Let $R,V$ denote the actual original BH rejection and false-rejection counts for $X$. First, $R$ equals the largest qualifying rank $r$. If $r>0$, the rejection set has at least $r$ members; if it had $s>r$ members, then $X_{(s)}\le\alpha r/N\le\alpha s/N$, contradicting maximality of $r$. If $r=0$, the definition gives $R=0$. Thus for $R>0$,
$$
V=C(\alpha R/N),\qquad R=V+A(R).
$$
These identities also hold for $R=0$: $C(0)=0$, and a nonnull zero would make rank 1 qualify, so $A(0)=0$ in that case. Hence $R$ is feasible in the definition of $k_V$. If $k_V>R$, monotonicity gives $C(u_V)\ge V$, whence $C(u_V)+A(k_V)\ge k_V$ and $k_V$ would be a larger qualifying BH rank. Therefore $R=k_V$.

For every $i\ge1$ with $C(u_i)\ge i$, the rank $k_i\ge i>0$ qualifies because $C(u_i)+A(k_i)\ge k_i$. Consequently $R\ge k_i$ and $V=C(\alpha R/N)\ge C(u_i)\ge i$. Conversely, if $V\ge1$, then $C(u_V)=V$, so $V$ is feasible in the definition of $I$. If $V=0$ the first implication says no positive $i$ is feasible. We have proved
$$
 I=V,\qquad R=k_I.
$$
The largest rank and every tied member of its rejection set are included in these identities; no alternative selector has been introduced.

**Reverse hazards from product association.** For bounded increasing functions $f,g$ of a single real random coordinate $Y$, an independent copy $Y'$ gives
$$
 \operatorname{Cov}(f(Y),g(Y))=
 \tfrac12\mathbb E[(f(Y)-f(Y'))(g(Y)-g(Y'))]\ge0.
$$
For independent coordinates, condition on the last coordinate. Induction shows the conditional covariance in the remaining coordinates is nonnegative, while their conditional means are increasing functions of the last coordinate and have nonnegative covariance by the displayed identity. The covariance decomposition proves association for any finite product law. Replacing an increasing function by the negative of a decreasing function proves nonpositive covariance for opposite monotonicities. This proof allows atoms and constant coordinates.

Define $E_i=\{C(u_i)\ge i\}$ and
$$
 a_i=\begin{cases}\mathbb P_*(I=i)/\mathbb P_*(I\le i),&\mathbb P_*(I\le i)>0,\\0,&\mathbb P_*(I\le i)=0.\end{cases}
$$
As null p-values increase coordinatewise, $I$ cannot increase; thus $\{I\le i\}$ is increasing, whereas $E_i$ is decreasing. Their intersection is exactly $\{I=i\}$. Association yields $0\le a_i\le\mathbb P_*(E_i)$ (the zero-denominator case is immediate). Writing $D_i=\mathbb P_*(I\le i)$, we have $D_m=1$ and $D_{i-1}=(1-a_i)D_i$, also when $D_i=0$. Descending induction therefore gives
$$
 D_i=\prod_{j=i+1}^m(1-a_j),\qquad
 \mathbb P_*(I=i)=a_i\prod_{j=i+1}^m(1-a_j).
$$
This does not divide by a vanishing cumulative probability. For $i\ge1$ put $t_i=\alpha k_i>0$. Under $\mathbb P_*$, $C(u_i)$ is a sum of independent Bernoulli variables and its mean is at most $Nu_i=t_i$.

**The required stop-loss comparison.** A convex function $\phi$ on the nonnegative integers has nondecreasing successive differences; summing them gives
$$
 \phi(k)\ge\phi(0)+k[\phi(1)-\phi(0)]\quad(k\ge0).
$$
For $B\sim\operatorname{Bernoulli}(p)$ and $Y\sim\operatorname{Poisson}(p)$, taking expectations in this inequality shows $\mathbb E\phi(Y)\ge(1-p)\phi(0)+p\phi(1)=\mathbb E\phi(B)$ whenever the expectations exist. For the applications below they are finite. Conditioning on an independent added summand preserves the inequality, since a translate of a convex function is convex. Replace the Bernoulli summands one at a time by independent Poisson variables of the same means. For independent Poisson variables of parameters $a,b\ge0$, direct convolution gives
$$
 \mathbb P(Y_a+Y_b=k)=e^{-(a+b)}\sum_{h=0}^k\frac{a^h b^{k-h}}{h!(k-h)!}
 =e^{-(a+b)}\frac{(a+b)^k}{k!}.
$$
Thus the replacement sum is Poisson with parameter its mean $\lambda$. If $\lambda\le t$, adding an independent Poisson$(t-\lambda)$ variable increases the expectation of every increasing function. Apply these facts only to the increasing convex function $\phi_i(x)=(x-i+1)_+$, where $x_+=\max\{x,0\}$. Since $\mathbf1_{\{x\ge i\}}\le\phi_i(x)$ for integer $x\ge0$, we obtain
$$
 a_i\le\mathbb P_*(C(u_i)\ge i)\le\beta_i(t_i),\qquad
 \beta_i(t)=\mathbb E[(Y_t-i+1)_+],\quad Y_t\sim\operatorname{Poisson}(t).
$$
The comparison is for stop-loss expectations, not a stochastic domination of ordinary Poisson tails. The Poisson increment coupling proves monotonicity of $\beta_i$. Directly $\beta_1(t)=t$, and splitting the expectation of $Y_t-i+1$ at $i-1$ gives, for $i\ge2$,
$$
 \beta_i(t)=t-i+1+e^{-t}\sum_{k=0}^{i-2}(i-1-k)\frac{t^k}{k!}.
$$
In particular all expectations used are finite.

**A dynamic budget with certified enclosures.** The exact rank and hazard identities give
$$
 \frac{\mathbb E_*[\operatorname{FDP}]}{\alpha}
 =H_m,\qquad
 H_i=\sum_{j=1}^i\frac{j}{t_j}a_j\prod_{h=j+1}^i(1-a_h),\quad H_0=0.
$$
Indeed $I=0$ contributes zero, and on $I=j\ge1$ the FDP divided by $\alpha$ is $j/(\alpha k_j)=j/t_j$. The prefix recursion is
$$
 H_i=(1-a_i)H_{i-1}+\frac{i}{t_i}a_i.
$$
Since $a_1\le t_1$, $H_1\le1$. If $H_{i-1}\le c$ with $c\ge1$, the facts $0\le a_i\le1$ and $a_i\le\beta_i(t_i)$ imply
$$
 H_i\le c+\Delta_i(c),\qquad
 \Delta_i(c)=\sup_{0<t<i/c}(i/t-c)\beta_i(t).
$$
When $i/t_i-c\le0$ the increment can be dropped; otherwise multiply the stop-loss bound by this positive coefficient. No monotonicity relation between different $t_i$ is needed for this budget.

Here are analytic bounds used to certify $\Delta_i(c)$. Put $Q_j(t)=\mathbb P(Y_t\ge j)$. Differentiating the finite complementary Poisson sum gives $Q_j'(t)=\mathbb P(Y_t=j-1)$. Also
$$
 \beta_i(t)=tQ_{i-1}(t)-(i-1)Q_i(t),\qquad
 \beta_i'(t)=Q_{i-1}(t),\qquad
 t\beta_i'(t)-\beta_i(t)=(i-1)Q_i(t).
$$
The middle identity follows from the first by $t\mathbb P(Y_t=i-2)=(i-1)\mathbb P(Y_t=i-1)$. For $g_i(t)=(i/t-c)\beta_i(t)$ it follows that
$$
 g_i'(t)=\frac{i(i-1)}{t^2}Q_i(t)-cQ_{i-1}(t).
$$
Since $i(i-1)\mathbf1_{\{Y_t\ge i\}}\le Y_t(Y_t-1)$ and $\mathbb E[Y_t(Y_t-1)]=t^2$ (by shifting the defining Poisson series), the first term lies in $[0,1]$. Hence $-c\le g_i'\le1$, and $|g_i'|\le c$ for $c\ge1$.

For integer $k\ge0$, $(k-i+1)_+\le\binom{k}{i}$, with the binomial coefficient taken as zero when $k<i$: when $k\ge i$, the subsets containing a fixed collection of $i-1$ elements already give $k-i+1$ subsets. The Poisson series gives $\mathbb E\binom{Y_t}{i}=t^i/i!$. Therefore $\beta_i(t)\le t^i/i!$ and $g_i(t)\to0$ as $t\downarrow0$ for $i\ge2$. Define $g_i(0)=0$; also $g_i(i/c)=0$, so taking the supremum over the closed interval is equivalent. On a rational interval $[l,h]\subseteq[0,i/c]$, a midpoint upper value for $g_i$ plus $c(h-l)/2$ bounds the whole interval. Monotonicity of $\beta_i$ and the decreasing nonnegative coefficient give a second bound $(i/l-c)_+\beta_i(h)$ when $l>0$. When $l=0$, $i h^{i-1}/i!$ is a bound by the preceding factorial estimate. The minimum of these two upper bounds remains an upper bound.

**Exact finite certificate.** The following complete Python 3 checker uses only integers, rational fractions, and the standard library. It is part of this proof and needs no local evidence file. Its exponential routine encloses $e^x$ at scale $S=10^{40}$: recursively rounding each nonnegative term $Sx^k/k!$ down and up preserves lower and upper bounds, and summing them preserves outward rounding. After term 140, the first omitted term is at most `nxt/S`; every subsequent ratio is at most $x/142<1$, so the omitted tail is at most `nxt/S` times $1/(1-x/142)$. Inverting positive exponential bounds outward gives lower and upper bounds for $e^{-x}$. The stop-loss routine computes the positive polynomial in the displayed exact formula with outward-rounded terms, multiplies nonnegative enclosures and then adds the offset $x-(i-1)$ exactly as a fraction. Cancellation in this last addition loses no validity. Clamping at zero is valid because $\beta_i\ge0$. All evaluated $x$ satisfy $x\le i/c\le30<142$.

Initially the heap has one leaf covering $[0,i/c]$. Replacing any selected leaf by its two halves preserves coverage. Each leaf carries an upper bound justified above, so the maximum leaf bound encloses the full supremum at every iteration. Midpoint lower bounds serve only to decide when the upper bound is sufficiently tight. The loop stops only when the maximum leaf bound is within $1/10000$ of the largest sampled lower bound. The work-cap assertion means a capped computation is never a certificate. Finally every new prefix bound is rounded upward to a multiple of $10^{-6}$. Thus completion and the explicit assertions below certify all 29 induction steps, rather than infer a bound from samples.

```python
from fractions import Fraction as F
from math import factorial
from functools import lru_cache
import heapq

SCALE=10**40
TERMS=140
TOL=F(1,10000)
ROUND=10**6
def ceildiv(a,b): return -(-a//b)
def exp_bounds(x):
    """Scaled bounds lo/SCALE <= exp(x) <= hi/SCALE, x>=0 rational."""
    assert x>=0
    n,d=x.numerator,x.denominator
    lo=hi=SCALE
    slo=shi=SCALE
    for k in range(1,TERMS+1):
        lo=lo*n//(d*k)
        hi=ceildiv(hi*n,d*k)
        slo+=lo; shi+=hi
    nxt=ceildiv(hi*n,d*(TERMS+1))
    assert n < d*(TERMS+2)
    tail=ceildiv(nxt*d*(TERMS+2), d*(TERMS+2)-n)
    return slo,shi+tail

@lru_cache(maxsize=20000)
def beta_bounds(i,x):
    """Exact bounds on E[(Pois(x)-i+1)_+] from positive polynomial and exp bounds."""
    assert i>=2 and x>=0
    if x==0:return F(0),F(0)
    el,eu=exp_bounds(x)
    eml=SCALE*SCALE//eu
    emu=ceildiv(SCALE*SCALE,el)
    n,d=x.numerator,x.denominator
    pl=pu=(i-1)*SCALE
    tl=tu=SCALE
    for k in range(1,i-1):
        tl=tl*n//(d*k)
        tu=ceildiv(tu*n,d*k)
        pl+=(i-1-k)*tl
        pu+=(i-1-k)*tu
    common=x-(i-1)
    low=max(F(0),common+F(eml*pl,SCALE*SCALE))
    high=max(F(0),common+F(emu*pu,SCALE*SCALE))
    assert low<=high
    return low,high

def supremum_upper(i,c):
    """Lipschitz branch-and-bound on [0,i/c], with |g'|<=c proved analytically."""
    assert i>=2 and c>=1
    heap=[]; serial=0; best=F(0); evaluated=0
    def add(l,h):
        nonlocal serial,best,evaluated
        mid=(l+h)/2
        bl,bu=beta_bounds(i,mid)
        coefficient=max(F(0),F(i)/mid-c)
        lower=coefficient*bl; upper=coefficient*bu
        best=max(best,lower)
        cover_upper=upper+c*(h-l)/2
        # A second, monotone product enclosure prunes tail intervals without a global mesh.
        if l==0:
            product_upper=F(i)*h**(i-1)/factorial(i)
        else:
            _,beta_high=beta_bounds(i,h)
            product_upper=max(F(0),F(i)/l-c)*beta_high
        cover_upper=min(cover_upper,product_upper)
        serial+=1; evaluated+=1
        heapq.heappush(heap,(-cover_upper,serial,l,h))
    add(F(0),F(i)/c)
    while -heap[0][0] > best+TOL:
        neg,_,l,h=heapq.heappop(heap)
        mid=(l+h)/2
        add(l,mid); add(mid,h)
        assert evaluated<200000,"Interval budget exceeded, certificate incomplete"
    upper=-heap[0][0]
    assert upper>=best and upper<=best+TOL
    return upper,best,evaluated,len(heap)

expected = [1375455, 1561440, 1667054, 1732235, 1774796, 1803743, 1824048, 1838638, 1849328, 1857288, 1863296, 1867873, 1871411, 1874159, 1876320, 1878031, 1879395, 1880496, 1881383, 1882104, 1882707, 1883209, 1883631, 1883971, 1884241, 1884502, 1884729, 1884916, 1885070]
expected_counts = [751, 631, 489, 355, 295, 225, 191, 157, 133, 119, 97, 91, 79, 71, 57, 49, 47, 35, 33, 31, 27, 23, 21, 19, 19, 17, 13, 13, 13]
c = F(1)
for i, value, count in zip(range(2,31), expected, expected_counts):
    upper, lower, evaluations, leaves = supremum_upper(i,c)
    nxt = c + upper
    c = F(ceildiv(nxt.numerator*ROUND,nxt.denominator),ROUND)
    assert c == F(value,ROUND) and c < F(19,10)
    assert evaluations == count and leaves == (count+1)//2
    beta_bounds.cache_clear()
assert c == F(188507,100000)
_, eu = exp_bounds(F(9,19))
assert F(eu,SCALE) < F(323,200)
C, r = F(19,10), F(17,20)
total = C+C*r**31/(1-r)
assert total == F(63849773397438169274766942332299886688227,
                  32212254720000000000000000000000000000000)
assert total < 2
print('CERTIFIED', c, total)
```

Running this checker completes all stages and prints

```text
CERTIFIED 188507/100000 63849773397438169274766942332299886688227/32212254720000000000000000000000000000000
```

The list `expected`, indexed by $i=2,\ldots,30$, records the resulting prefix constants in units of $10^{-6}$, starting at $1375455/10^6$ and ending at $1885070/10^6=188507/100000$. The assertions separately recompute every bound and compare all prefixes and leaf counts. Consequently $H_i\le c_i<19/10$ for $1\le i\le30$ (with $c_1=1$).

**The infinite tail.** The Poisson series gives $\mathbb E e^{sY_t}=\exp(t(e^s-1))$. For $k>t>0$, Markov's inequality at $s=\log(k/t)>0$ yields
$$
 Q_k(t)\le h_k(t):=e^{-t}(et/k)^k.
$$
The elementary inequality $\log(1+x)=\int_0^x(1+v)^{-1}\,dv\ge x/(1+x)$ for $x\ge0$ implies $(1+1/k)^{k+1}\ge e$. Therefore
$$
 \frac{h_{k+1}(t)}{h_k(t)}
 =\frac{t}{k}\,e\left(\frac{k}{k+1}\right)^{k+1}\le\frac{t}{k}.
$$
By summing the integer-valued nonnegative stop-loss variable (or its nonnegative defining series), $\beta_i(t)=\sum_{k=i}^{\infty}Q_k(t)$. For $0<t<i$, the preceding ratio bound gives
$$
 \beta_i(t)\le\frac{h_i(t)}{1-t/i}.
$$
Reset the prefix upper bound at stage 30 to $C=19/10$. For any later budget value $c\ge C$ and $0<t<i/c$, positivity and $c\ge1$ yield
$$
 (i/t-c)\beta_i(t)
 \le\frac{i/t-c}{1-t/i}h_i(t)
 \le(i/t)h_i(t).
$$
For $i\ge31$, $i/C\le i-1$, and $t^{i-1}e^{-t}$ is increasing on $0<t\le i/C$ because its derivative has the sign of $i-1-t$. It follows that
$$
 \Delta_i(c)\le\frac{i}{i/C}h_i(i/C)
 =C\left(\frac{e^{1-1/C}}{C}\right)^i.
$$
The checker proves $e^{9/19}<323/200$, so $e^{1-1/C}/C<17/20$. Define the later budget recursively by adding $C(17/20)^i$ at stage $i\ge31$. Each such budget is at least $C$, so the bound just proved applies inductively, and for every finite $m>30$,
$$
 H_m\le C+C\sum_{i=31}^{m}(17/20)^i
 \le C+C\frac{(17/20)^{31}}{1-17/20}
 =\frac{63849773397438169274766942332299886688227}
 {32212254720000000000000000000000000000000}<2.
$$
Together with the finite certificate this proves $H_m<2$ for all $m\ge1$. Integrating over the nonnull vector gives the independent inequality $\operatorname{FDR}_{\mathrm{BH},\alpha}\le2\alpha$; the deterministic bound FDP $\le1$ also gives $\operatorname{FDR}_{\mathrm{BH},\alpha}\le\min\{1,2\alpha\}$. For $N=1$ and one null, $k_1=1$, $t_1=\alpha$, and $H_1\le1$ directly; an empty null set was handled separately. All-null configurations and deterministic alternatives were covered by the same product-law argument without further hypotheses.

**Conditional rescaling and the finite-level envelope.** Fix a value $z$ at which the conditional joint law is the product of its coordinate kernels, and set $K=K_q(z)$. If $K=\infty$ or $qK\ge1$, the asserted conditional bound is 1 and follows from FDP $\le1$. Otherwise $1\le K<\infty$ and $\alpha=qK<1$. Under this fixed conditional law, transform every coordinate by
$$
 X_j=\begin{cases}KP_j,&P_j\le q,\\1,&P_j>q.\end{cases}
$$
These are coordinatewise Borel maps into $[0,1]$, so independence is preserved. For $0<u\le\alpha$,
$$
 \sum_{j\in I_0}\mathbb P_z(X_j\le u)
 =\sum_{j\in I_0}F_{j,z}(u/K)\le NK(u/K)=Nu.
$$
At $u=0$, the finite-envelope bound and right continuity as $t\downarrow0$ force the summed null mass at zero to vanish, giving the same inequality. For $\alpha<u<1$, the summed CDF is constant at its value at $\alpha$, bounded by $N\alpha\le Nu$; at $u=1$ it is $m\le N$. Thus the independent compound condition holds on the entire unit interval. For every $1\le k\le N$ and every coordinate,
$$
 X_j\le\alpha k/N\quad\Longleftrightarrow\quad P_j\le qk/N.
$$
Indeed the transformed value of any $P_j>q$ is $1>\alpha$, while inside $[0,q]$ the equivalence is multiplication by the positive number $K$. Hence all qualifying ranks, the largest rank, its complete rejection set, the original null labels and the FDP agree exactly. The independent bound applied at level $\alpha$ proves the required pointwise conditional bound, including $K=1$. Atoms at $q$ and at any BH threshold are included by the non-strict comparisons, and no attainment of the envelope is required.

Finally, for $0<t<q$ choose rational $r_n\in(t,q)$ decreasing to $t$. Right continuity gives
$$
 \frac{\sum_{j\in I_0}F_{j,z}(r_n)}{Nr_n}
 \longrightarrow\frac{\sum_{j\in I_0}F_{j,z}(t)}{Nt}.
$$
The supremum over all thresholds therefore equals the supremum over the rational thresholds in $(0,q)$ and the endpoint $q$. For each fixed threshold a regular conditional kernel gives a measurable CDF in $z$; a countable supremum and the maximum with 1 give the claimed measurable extended-real envelope. Choose one common full-measure set on which the coordinate kernels are distributions, their joint kernel is their product, and their CDFs have the stated versions. The BH FDP is a bounded Borel function: each rank test and each coordinate rejection test is a finite combination of Borel inequalities, and $I_0$ is fixed. Its integral under that product kernel is therefore a version of its conditional expectation. The fixed-law proof applies at every $z$ in this set, with trivial bound 1 in the exceptional infinite-envelope or cap cases, so
$$
 \mathbb E[\operatorname{FDP}_{\mathrm{BH},q}\mid Z]
 \le\min\{1,2qK_q(Z)\}\quad\text{almost surely}.
$$
Taking expectation and using the tower property proves the stated FDR inequality. Only the three attached approved definitions are assumed; every estimate used here has been proved above. The conclusion is this finite conditional calibration lemma alone. $\square$
