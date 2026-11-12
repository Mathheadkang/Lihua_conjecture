---
type: lemma
title: Large-U two-sign deficit-curve exclusion EX-Q
status: approved
source:
  kind: original
  location: >-
    Proposed repair of gaussian_bh_two_sign_curve_exclusion_exq;
    plan_two_sided_averaged_flatness_exclusion_20261105, Fixed notation, Plan
    step 7, Progress / Step 7 (EX-Q), and Failure / What was established item 1
depends_on: []
uses_definitions:
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - gaussian_multifactor_representation
tags:
  - gaussian_bh
  - two_sided
  - deficit_curve
  - reflected_sign_exclusion
  - proposed_repair
  - unproved
---

## Statement

### Scope and scalar thresholds

For every positive integer $N$, $q\in(0,1)$, and $r\in(0,1)$, put
$$
p(u)=2\overline\Phi(u)\quad(u\ge0),\qquad U=p^{-1}(q),\qquad
 t_k=\frac{qk}{N},\quad u_k=p^{-1}(t_k)\quad(k\in[N]),
$$
where $\overline\Phi$ is the standard normal survival function and $[N]=\{1,\ldots,N\}$. Thus $u_k$ is strictly decreasing and $u_N=U$. Set
$$
J=\lceil\sqrt U\rceil,\qquad K=8\log U,\qquad L=K+\sqrt U.
$$
Assume explicitly $U\ge1$, as well as the original conditions $L\le U$ and $r^2<U$. All logarithms are natural.

### Arbitrary finite curve and fixed mates

Let $D^*:[N]\to\mathbb Z$ be any nondecreasing integer curve. No condition $D^*(1)\le0$ or restriction on its increments is imposed. Let $\mathcal M$ be any finite set (possibly empty), with arbitrary real $\theta_j$, loadings $a_j\in[-1,1]$, and arbitrary fixed real noises $\varepsilon_j$. For every real $z$, define
$$
Y_j(z)=\theta_j+a_jz+\sqrt{1-a_j^2}\,\varepsilon_j,\qquad
M_z(k)=\#\{j\in\mathcal M:|Y_j(z)|\ge u_k\}.
$$
Assume the set defining the following maximum is nonempty for every $z\in\mathbb R$, and put
$$
R(z)=\max\{k\in[N]:M_z(k)\ge D^*(k)\},\qquad v(z)=u_{R(z)}.
$$
The same fixed noises are used at all $z$. Threshold ties are included as displayed. The loading endpoints $a_j=0$ and $|a_j|=1$ are allowed. This is a deterministic finite-family statement, without a block-model assumption, a dimension restriction, or a probabilistic good event.

### Level extension and extended quarter distance

For $w\ge U$, define
$$
k(w)=\begin{cases}
\min\{k\in[N]:u_k\le w\},& U\le w\le u_1,\\
1,&w>u_1,
\end{cases}
\qquad D^*_{\mathrm{lev}}(w):=D^*(k(w)).
$$
For each $v\ge U$ with $D^*_{\mathrm{lev}}(v)\ge J$, put
$$
Q(v)=\inf\{h\ge0:D^*_{\mathrm{lev}}(v+h)\le D^*_{\mathrm{lev}}(v)/4\},\qquad\inf\varnothing=+\infty,
$$
$$
\widetilde\Lambda(D^*;r)=
\sup\{vQ(v):U\le v\le(U+K)/r,\ D^*_{\mathrm{lev}}(v)\ge J\},
\qquad\sup\varnothing=0.
$$
These are nonnegative extended real quantities; $v(+\infty)=+\infty$ since $v\ge U>0$. No finiteness or flatness assumption is imposed.

### Tracked sets and conclusions

Call a mate large if $|a_j|\ge r/U$. For $\sigma\in\{+1,-1\}$ let $S_\sigma$ consist of all $t\in[L,U]$ such that
$$
|t-rv(\sigma t)|\le K,\qquad D^*(R(\sigma t))\ge J,
$$
$$
\#\{j\in\mathcal M:|a_j|\ge r/U,\ |Y_j(\sigma t)|\ge v(\sigma t)\}
\ge\frac12D^*(R(\sigma t)).
$$
Set
$$
\ell=(1-r)U+K,\qquad
B=\max\left\{\frac{2K+2r^2}{1-r^2/U},\sqrt U\,\widetilde\Lambda(D^*;r)\right\}.
$$
Use $t+(+\infty)=+\infty$, $(+\infty,U]=\varnothing$, and $\min\{+\infty,\ell\}=\ell$. Measures below are Lebesgue measures.

(a) If $t_1\in S_+\cup S_-$, not both $S_+\cap(t_1+B,U]$ and $S_-\cap(t_1+B,U]$ are nonempty. As in the source claim, only the tilt conditions are required at the later points: there cannot exist $t_2,t_3\in(t_1+B,U]$ satisfying simultaneously
$$
|t_2-rv(t_2)|\le K,\qquad |t_3-rv(-t_3)|\le K.
$$

(b) The large-carried tracked sets satisfy
$$
|S_+|+|S_-|\le\ell+\min\{B,\ell\}.
$$

## Proof

Fix arbitrary parameters, rank curve, and finite mates satisfying the Statement. All arguments below are deterministic and use the same fixed noises at every value of the real parameter.

### Step 1 — definitions and measurability

Since the normal density is positive, $p$ is continuous and strictly decreasing from $1$ to $0$ on $[0,\infty)$. Each $t_k=qk/N$ belongs to $(0,1)$, so its inverse $u_k$ is finite; strict increase of $t_k$ gives strict decrease of $u_k$ and $u_N=U$. The minimum defining $k(w)$ exists for $w\ge U$ in the regular range because $u_N=U$. At a threshold $k(u_k)=k$; as $w$ increases the eligible set enlarges and its minimum cannot increase. Consequently $D^*_{\mathrm{lev}}$ is nonincreasing, including the extension by $D^*(1)$ beyond $u_1$. From $U\ge1$ we have $K\ge0$, $J\ge1$, $L-K=\sqrt U$, and $\ell=(1-r)U+K\ge0$. The assumption $r^2<U$ gives $1-r^2/U>0$; thus the first term of $B$ is finite and nonnegative, and the second is a nonnegative extended real.

For every fixed $j,k$, $Y_j$ is a continuous affine function, so $E_{jk}=\{z:|Y_j(z)|\ge u_k\}$ is closed. If $a_j=0$ this is all of $\mathbb R$ or empty; otherwise it has at most two boundary points. Finite sums of their indicators give Borel $M_z(k)$. With $F_k=\{z:M_z(k)\ge D^*(k)\}$, the assumed global existence gives
$$
\{z:R(z)=k\}=F_k\cap\bigcap_{l=k+1}^{N}F_l^c.
$$
Hence $R$ and $v$ are Borel. On each Borel set $\{R=k\}$ the large-carrier count is a finite sum of indicators of the sets $E_{jk}$ over the fixed eligible loadings. The defining inequalities for $S_\sigma$ therefore make it Borel. Equality points are retained throughout. This uses no division by a loading and covers $a_j=0$, $|a_j|=1$ (zero residual coefficient), empty mates, and $N=1$. If $U=1$, then $K=0$ and $L=1$, so each tracked set is a subset of $\{1\}$, of measure zero, and there is no later point in the prescribed interval.


### Step 2 — support and infinite quarter-distance case

For any $t\in S_\sigma$, tilt and $v(\sigma t)\ge U$ give $t\ge rv(\sigma t)-K\ge rU-K$. Thus
$$
S_\sigma\subset[b,U],\qquad b=\max\{L,rU-K\},\qquad U-b\le U-(rU-K)=\ell.
$$
Here $b\le U$: both $L\le U$ and $rU-K\le U$ hold, using $r<1$ and $K\ge0$. The support bound yields $|S_+|+|S_-|\le2\ell$. If the tracked union is empty, (a) has no initial point and (b) has left side zero and nonnegative right side. There is no need to infer that the set defining the supremum is empty; whenever that set is empty its stipulated value zero makes $B$ well-defined.

The first term in $B$ is finite, so $B=+\infty$ exactly when $\widetilde\Lambda(D^*;r)=+\infty$. In that case $(t_1+B,U]=\varnothing$, proving even the tilt-only version of (a); and the support bound gives $|S_+|+|S_-|\le2\ell=\ell+\min\{B,\ell\}$. This resolves the infinite branch without a finiteness assertion about any $Q(v)$. The remaining argument concerns finite $B$ only.


### Step 3 — maximality and the finite-distance quarter drop

If $k>R(z)$, the defining maximum precludes $M_z(k)\ge D^*(k)$. Both quantities are integers, so
$$
M_z(k)\le D^*(k)-1. \tag{1}
$$
This requires neither positivity nor an increment bound for the rank curve. For any level $v$ with $d=D^*_{\mathrm{lev}}(v)\ge J$, let $H_v=\{h\ge0:D^*_{\mathrm{lev}}(v+h)\le d/4\}$. If $Q(v)<\infty$, $H_v$ is nonempty. For any $h>Q(v)=\inf H_v$, some $h'\in H_v$ satisfies $h'<h$ (otherwise $h$ would be a lower bound larger than the infimum). Monotonicity in the level then gives
$$
D^*_{\mathrm{lev}}(v+h)\le D^*_{\mathrm{lev}}(v+h')\le d/4. \tag{2}
$$
No value at $h=Q(v)$ is asserted.

Now assume $B<\infty$ and $t_1\in S_\sigma$. Put $v_1=v(\sigma t_1)$ and $d=D^*(R(\sigma t_1))$. The threshold identity and tracking give $D^*_{\mathrm{lev}}(v_1)=d\ge J$. Tilt and $L\le t_1\le U$ yield
$$
U\le v_1\le (U+K)/r,\qquad rv_1\ge t_1-K\ge L-K=\sqrt U.
$$
Thus $v_1$ is one of the levels in the supremum, and
$$
v_1Q(v_1)\le\widetilde\Lambda(D^*;r)<\infty. \tag{3}
$$
Since $v_1\ge U>0$, this proves $Q(v_1)<\infty$. Finiteness follows solely from the finite-$B$ branch and membership in the supremum, without any assumption about $D^*(1)$.


### Step 4 — strict separated levels and the reflected cost

Still in the finite-$B$ branch, take $t_1\in S_+$ and suppose the two later tilt points in (a) exist. Write $v_1=v(t_1)$, $v_2=v(t_2)$, $v_3=v(-t_3)$ and $\Delta_i=t_i-t_1>B$ for $i=2,3$. Tilt gives $rv_i\ge t_i-K$ and $rv_1\le t_1+K$, hence
$$
v_i-v_1\ge(\Delta_i-2K)/r. \tag{4}
$$
Let $d_2=r\Delta_2/U$ and $d_3=r(t_1+t_3)/U$. Since
$$
\Delta_i(1-r^2/U)>2K+2r^2,
$$
we have
$$
\frac{\Delta_2-2K}{r}-\frac{r\Delta_2}{U}
=\frac{\Delta_2(1-r^2/U)-2K}{r}>0,
$$
and, using $t_1\le U$,
$$
\frac{\Delta_3-2K}{r}-d_3
=\frac{\Delta_3(1-r^2/U)-2K-2r^2t_1/U}{r}>0.
$$
The extra reflected displacement is $2rt_1/U\le2r$, whose cost after multiplication by $r$ is at most $2r^2$. Together with (4), this proves
$$
v_1+d_2<v_2,\qquad v_1+d_3<v_3. \tag{5}
$$
Let $\Lambda=\widetilde\Lambda(D^*;r)$ solely as a local abbreviation. The second term in $B$ and (3) give
$$
d_2=\frac rU\Delta_2>\frac r{\sqrt U}\Lambda
\ge\frac{rv_1}{\sqrt U}Q(v_1)\ge Q(v_1), \tag{6}
$$
where the last inequality uses $rv_1\ge\sqrt U$ and $Q(v_1)\ge0$. Also $t_1\ge L>0$, so $d_3\ge r\Delta_3/U$, and the same strict chain with $\Delta_3$ proves $d_3>Q(v_1)$. All strict inequalities remain valid if $Q(v_1)=0$ or $\Lambda=0$. No condition at the later points beyond tilt and their displayed locations was used.


### Step 5 — both carrier classes and the integer contradiction

Let $d=D^*(R(t_1))$ as in step 3, and let
$$
\mathcal C=\{j\in\mathcal M:|a_j|\ge r/U,\ |Y_j(t_1)|\ge v_1\}.
$$
Tracking gives $|\mathcal C|\ge d/2$. Every member has $a_j\ne0$ and $Y_j(t_1)\ne0$, since $r/U>0$ and $v_1\ge U>0$. Hence $A_+=\{j\in\mathcal C:a_jY_j(t_1)>0\}$ and $A_-=\{j\in\mathcal C:a_jY_j(t_1)<0\}$ form a disjoint partition. Because the noises are fixed, the affine identities are exact. For $j\in A_+$ the two terms in $Y_j(t_2)=Y_j(t_1)+a_j\Delta_2$ have the same sign, so
$$
|Y_j(t_2)|=|Y_j(t_1)|+|a_j|\Delta_2\ge v_1+d_2.
$$
For $j\in A_-$ the terms in $Y_j(-t_3)=Y_j(t_1)-a_j(t_1+t_3)$ have the same sign because $t_1+t_3>0$, so
$$
|Y_j(-t_3)|=|Y_j(t_1)|+|a_j|(t_1+t_3)\ge v_1+d_3.
$$
Set $z_2=t_2$, $z_3=-t_3$, $w_i=v_1+d_i$, and $k_i=k(w_i)$. By (5), $U\le w_i<v_i=u_{R(z_i)}\le u_1$, so $k_i$ is in the regular range and $u_{k_i}\le w_i<u_{R(z_i)}$. Strict decrease of the thresholds forces $k_i>R(z_i)$. Both transport inequalities include threshold ties and show
$$
|A_+|\le M_{z_2}(k_2)\le D^*(k_2)-1,\qquad
|A_-|\le M_{z_3}(k_3)\le D^*(k_3)-1,
$$
where (1) supplies the integer gaps. By (6), its counterpart for $d_3$, and (2),
$$
D^*(k_i)=D^*_{\mathrm{lev}}(w_i)\le d/4\qquad(i=2,3).
$$
Consequently
$$
\frac d2\le|\mathcal C|=|A_+|+|A_-|\le\frac d2-2,
$$
a contradiction. The argument even accommodates an empty carrier class: its nonnegative count is subject to the same maximality bound, with no assumption that either class is nonempty. This proves the asserted later-point exclusion when the initial point is in $S_+$.


### Step 6 — reflection for a negative initial point

Suppose now $t_1\in S_-$. Define a new family with $a'_j=-a_j$, $\theta'_j=\theta_j$, and $\varepsilon'_j=\varepsilon_j$. These are admissible loadings and fixed noises, with $\sqrt{1-(a'_j)^2}=\sqrt{1-a_j^2}$ and $|a'_j|=|a_j|$. Thus $Y'_j(z)=Y_j(-z)$, $M'_z(k)=M_{-z}(k)$, and the qualifying rank set is nonempty for every $z$. Its maximum is $R'(z)=R(-z)$, so $v'(z)=v(-z)$, $S'_+=S_-$, and $S'_-=S_+$. The unchanged curve and thresholds imply identical $Q$, $\widetilde\Lambda$, and $B$.

If original later points $t_2,t_3$ violate the tilt-only exclusion, take the new positive magnitude $t'_2=t_3$ and new negative magnitude $t'_3=t_2$. They both exceed $t_1+B$ and do not exceed $U$, while $v'(t'_2)=v(-t_3)$ and $v'(-t'_3)=v(t_2)$ give the required tilt conditions. Apply the already proved positive-initial-point argument to this reflected family at $t_1\in S'_+$. It yields the same contradiction with the same fixed noises. Thus the stronger tilt-only exclusion holds for every initial point in the union; two later tracked points would in particular satisfy tilt and are excluded. This completes (a), including the infinite case already settled.


### Step 7 — the full measure bound

Continue with finite $B$, since step 2 resolves infinite $B$. Empty tracked union is already settled. Otherwise put $a=\inf(S_+\cup S_-)$ and $I=[a,U]$. The support bound gives $b\le a\le U$ and $|I|=U-a\le\ell$, and both tracked sets are subsets of $I$. This does not require the infimum to belong to either set. If $B\ge\ell$, the direct support bound gives $|S_+|+|S_-|\le2\ell=\ell+\min\{B,\ell\}$, so that case is also immediate.

For completeness the following argument covers every finite $B$, and in particular $B<\ell$. Given $\epsilon>0$, the definition of the infimum supplies $t_1\in S_+\cup S_-$ with $a\le t_1<a+\epsilon$. Let $c=\min\{t_1+B,U\}$; then $a\le c\le U$. By (a), if $c<U$ one sign $\sigma$ has $S_\sigma\cap(c,U]=\varnothing$. If $c=U$, the same statement holds for either sign. That tracked set is contained in $[a,c]$; the other is contained in $[a,U]$. Therefore
$$
|S_+|+|S_-|\le(U-a)+(c-a)
\le\ell+\min\{B+\epsilon,\ell\},
$$
since $c-a\le U-a\le\ell$ and $c-a\le t_1-a+B<B+\epsilon$. Send $\epsilon\downarrow0$; the function $x\mapsto\min\{x,\ell\}$ is continuous at finite $B$. This proves (b). All sets were established measurable in step 1. Endpoints and any isolated threshold ties have zero Lebesgue measure, so the argument includes $a=U$, singleton tracked sets, and all displayed closed endpoints without a positive-length assumption.

For $N=1$, any tracked point has $D^*(1)\ge J>0$ and the level curve is constant, so its quarter-drop set is empty; that level is in the supremum and $B=\infty$, already handled. If mates are empty, tracking would require zero to be at least $d/2$ with $d\ge J>0$, so the tracked union is empty. For general $N$, arbitrary rank-curve values and increments and every admissible real loading, including singular endpoints, have been retained. No probability event or flatness bound has entered any step.

## Proposal provenance and boundary

Proposed new ID: `gaussian_bh_two_sign_curve_exclusion_large_u_exq`. This is a NEW unproved repair proposal, not a proof verdict for the exact original asset. The original draft, quantifiers, candidate proof, failed-plan history, and both unrestricted main targets remain untouched. The only scope restriction proposed here is the explicit auxiliary condition $U\ge1$; the other changes define the extended-real boundary cases and place all notation inside Statement. The explicit real loading range makes the source square root well-defined.

Source asset SHA256 at preparation: `e5345494eda8fa5b6d0be3fa71ed4302c0da33cea38f8ceb8ea8caabacbbf777`. Exact-source provenance is the failed plan `plan_two_sided_averaged_flatness_exclusion_20261105`, Fixed notation, tracked-set definitions in Plan step 7, Progress / Step 7 (EX-Q), and Failure / What was established item 1. The source proof is available under the old asset's Proof heading, solely as an adaptation candidate. Cold records: `idea_1d4f7586a563` and the independent candidate-only small-U check `idea_7d412076fc5f`.

## Proposed reproof checklist and first failure condition

1. Check every quantity above without $D^*(1)\le0$: level extension on $[U,\infty)$, existence of $R$, finite-family measurability (including isolated tie points), $K\ge0$, $\ell\ge0$, and a positive denominator in $B$.
2. Split $\widetilde\Lambda=+\infty$ from the finite case before using quarter drop. In the infinite case, verify (a) is vacuous under the interval convention and derive (b) directly from tilt and the nonnegative interval-length bound. Do not infer a finite $Q$ there.
3. In the finite case, prove integral maximality $M_z(k)\le D^*(k)-1$ for $k>R(z)$ and quarter drop for strictly $h>Q(v)$. At a tracked point verify its membership in the supremum range and then the needed finiteness of $Q(v)$.
4. Reconstruct tilt separation, both transported carrier classes, and the reflected $a_j\mapsto-a_j$ case with the same noises. Check the $2r^2$ reflected-shift cost, strict rank separation despite inclusive ties, both quarter-drop counts, and the exact integer contradiction. No missing flatness bound may be assumed.
5. Reconstruct the infimum/epsilon argument for the measure bound, including empty tracked sets, endpoint singletons, $B\ge\ell$, and finite $B<\ell$.

Stop at the first unsupported inequality, undefined boundary, or admissible counterexample. Record that failure against this NEW proposal; do not repair its statement during execution or infer anything about the original/main target. Native planning, execution, and fresh verification are all still required; this file supplies no proof or independent review.
