---
type: lemma
title: Exact two-sign deficit-curve exclusion EX-Q
status: draft
source:
  kind: original
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
  - extracted_unverified
---

## Source

Extracted verbatim from [the averaged flatness-exclusion plan](../plans/plan_two_sided_averaged_flatness_exclusion_20261105.md), Fixed notation, Plan step 7 (tracked-set definitions), Progress / Step 7 (EX-Q) (lines 167–190), and Failure / What was established, item 1 (the exact quantified statement). The source plan failed at a later step; this extracted lemma has not been independently verified.

## Local notation

- $p(u)=2\overline\Phi(u)$, $\phi$ the standard normal density, $U=p^{-1}(q)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ ($u_k$ strictly decreasing in $k$, $u_N=U$), $J=\lceil\sqrt U\rceil$, $K=8\log U$, $L=K+\sqrt U$ (Lei's constants (204)).
- **Level form of a curve.** For real $w$: $k(w)=\min\{k\in[N]:u_k\le w\}=\lceil Np(w)/q\rceil$ for $U\le w\le u_1$, $k(w)=1$ for $w>u_1$; $D^*(w):=D^*(k(w))$, nonincreasing in $w$, with $D^*(u_{k})=D^*(k)$.
- **Quarter distance and flatness.** For $v\ge U$ with $D^*(v)\ge J$: $Q(v)=\inf\{h\ge0:D^*(v+h)\le D^*(v)/4\}$ (finite, since $D^*(w)=D^*(1)\le0$ for $w>u_1$). For $r\in(0,1)$:
$$
\widetilde\Lambda(D^*;r)=\sup\{v\,Q(v):\ U\le v\le (U+K)/r,\ D^*(v)\ge J\}\qquad(\sup\varnothing=0).
$$

**Setting (self-contained).** $N\ge1$, $q\in(0,1)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ strictly decreasing, $u_N=U$. A curve $D^*:[N]\to\mathbb Z$ is nondecreasing (only this and integrality are used; $D^*(1)\le0$ and increments in $\{0,1\}$ are not needed). Mates $j\in\mathcal M$ (finite), $Y_j(z)=\theta_j+a_jz+\sqrt{1-a_j^2}\,\varepsilon_j$ with the $\varepsilon_j$ fixed; $M_z(k)=\#\{j\in\mathcal M:|Y_j(z)|\ge u_k\}$ (equivalently $p(|Y_j(z)|)\le t_k$, since $p$ is strictly decreasing; ties are thus included exactly). $R(z)=\max\{k\in[N]:M_z(k)\ge D^*(k)\}$, assumed to exist (true in $\mathcal D_N$ since $D^*(1)\le0$); $v(z)=u_{R(z)}$. Level form: $k(w)=\min\{k:u_k\le w\}$ for $w\le u_1$, $k(w)=1$ for $w>u_1$, $D^*(w):=D^*(k(w))$; then $k(u_k)=k$ and $w\mapsto D^*(w)$ is nonincreasing. $Q(v)$, $\widetilde\Lambda$, $J$, $K$, $L=K+\sqrt U$ as in Fixed notation.

Call a mate *large* if $|a_j|\ge r/U$. For $\sigma\in\{\pm\}$ let $S_\sigma$ be the set of $t\in[L,U]$ such that $z=\sigma t$ satisfies $|t-rv(z)|\le K$, $D^*(R(z))\ge J$, and the large mates with $|Y_j(z)|\ge v(z)$ number at least $D^*(R(z))/2$ ("large-carried tracked"). Put $B=\max\{(2K+2r^2)/(1-r^2/U),\ \sqrt U\,\widetilde\Lambda(D^*;r)\}$.

## Statement

for every $N$, $q$ with $L\le U$, every $r\in(0,1)$ with $r^2<U$, every integer nondecreasing curve $D^*$ on $[N]$ for which $R(z)=\max\{k:M_z(k)\ge D^*(k)\}$ exists, every finite mates family $(\theta_j,a_j)$ and every realisation of the mates' noises, the large-carried tracked sets satisfy (a) if $t_1\in S_\pm$ then not both $S_+\cap(t_1+B,U]$ and $S_-\cap(t_1+B,U]$ are nonempty (only the tilt condition is needed at the later points), and (b) $|S_+|+|S_-|\le\ell+\min\{B,\ell\}$, where $\ell=(1-r)U+K$ and $B=\max\{(2K+2r^2)/(1-r^2/U),\sqrt U\,\widetilde\Lambda(D^*;r)\}$. This is deterministic and needs no good event.

## Proof

gap: The stated range $L\le U$ also admits $U=r=1/4$. With $N=1$, $D^*(1)=0$ and no mates, both tracked sets are empty but the asserted length bound is negative. This auxiliary-lemma candidate was independently checked in idea_7d412076fc5f; the original statement remains unchanged and is not reported as a main-target refutation.

gap: the source fixed notation asserts that $Q(v)$ is finite using $D^*(1)\le0$, while the exact final statement and the Progress setting explicitly allow integer nondecreasing curves without $D^*(1)\le0$. No convention for an empty infimum or for $B=+\infty$ is stated. The broader source statement is preserved here without repairing that boundary.

**Setting (self-contained).** $N\ge1$, $q\in(0,1)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ strictly decreasing, $u_N=U$. A curve $D^*:[N]\to\mathbb Z$ is nondecreasing (only this and integrality are used; $D^*(1)\le0$ and increments in $\{0,1\}$ are not needed). Mates $j\in\mathcal M$ (finite), $Y_j(z)=\theta_j+a_jz+\sqrt{1-a_j^2}\,\varepsilon_j$ with the $\varepsilon_j$ fixed; $M_z(k)=\#\{j\in\mathcal M:|Y_j(z)|\ge u_k\}$ (equivalently $p(|Y_j(z)|)\le t_k$, since $p$ is strictly decreasing; ties are thus included exactly). $R(z)=\max\{k\in[N]:M_z(k)\ge D^*(k)\}$, assumed to exist (true in $\mathcal D_N$ since $D^*(1)\le0$); $v(z)=u_{R(z)}$. Level form: $k(w)=\min\{k:u_k\le w\}$ for $w\le u_1$, $k(w)=1$ for $w>u_1$, $D^*(w):=D^*(k(w))$; then $k(u_k)=k$ and $w\mapsto D^*(w)$ is nonincreasing. $Q(v)$, $\widetilde\Lambda$, $J$, $K$, $L=K+\sqrt U$ as in Fixed notation.

**(E0) Maximality.** For every $z$ and every $k>R(z)$: $M_z(k)\le D^*(k)-1$ (integers, definition of the maximum).

**(E1) Quarter-drop beyond $Q$.** If $D^*(v)\ge1$ and $h>Q(v)$ then $D^*(v+h)\le D^*(v)/4$. *Proof.* By the definition of the infimum there is $h'\in[Q(v),h)$ with $D^*(v+h')\le D^*(v)/4$, and $D^*$ is nonincreasing in the level. $\square$ (Strict $h>Q$ avoids any attainment question; $Q(v)<\infty$ because $D^*(w)=D^*(1)$ for $w>u_1$; this is the only place finiteness is used and only if $D^*(1)\le D^*(v)/4$, true in $\mathcal D_N$.)

**(E2) Tilt matching.** If $|t_i-rv_i|\le K$ for $i=1,2$ then $r(v_2-v_1)\ge t_2-t_1-2K$. (Triangle inequality.)

**Claim (a).** Let $t_1\in S_+$ and $t_2,t_3\in(t_1+B,U]$ with $z=t_2$ and $z=-t_3$ satisfying the tilt condition $|t_\cdot-rv(\cdot)|\le K$ (only the tilt condition is needed at $t_2,t_3$; membership in $S_\pm$ is more). Then a contradiction follows; hence not both $S_+\cap(t_1+B,U]$ and $S_-\cap(t_1+B,U]$ are nonempty. *Proof, checked line by line.* Write $v_1=v(t_1)$, $R_1=R(t_1)$, $v_2=v(t_2)$, $v_3=v(-t_3)$.
1. $v_2-v_1>d_2:=\frac rU(t_2-t_1)$: by (E2), $v_2-v_1\ge(t_2-t_1-2K)/r$, and $(t_2-t_1-2K)/r>\frac rU(t_2-t_1)\iff(t_2-t_1)(1-r^2/U)>2K$, true since $t_2-t_1>B\ge(2K+2r^2)/(1-r^2/U)$ and $1-r^2/U>0$.
2. $v_3-v_1>d_3:=\frac rU(t_1+t_3)$: by (E2) with $t=t_3$ (the tilt condition at $z=-t_3$ is $|t_3-rv_3|\le K$), $v_3-v_1\ge(t_3-t_1-2K)/r$; and $d_3=\frac rU(t_3-t_1)+\frac{2rt_1}U\le\frac rU(t_3-t_1)+2r$ (as $t_1\le U$); $(t_3-t_1-2K)/r>\frac rU(t_3-t_1)+2r\iff(t_3-t_1)(1-r^2/U)>2K+2r^2$, true by $t_3-t_1>B$.
3. Transport. Let $\mathcal C=\{j:|a_j|\ge r/U,\ |Y_j(t_1)|\ge v_1\}$, $|\mathcal C|\ge D^*(R_1)/2$ ($t_1\in S_+$). Every $j\in\mathcal C$ has $a_j\ne0$, $Y_j(t_1)\ne0$ ($v_1\ge U>0$). $A_+=\{j\in\mathcal C:a_jY_j(t_1)>0\}$, $A_-=\mathcal C\setminus A_+$ (so $a_jY_j(t_1)<0$). For $j\in A_+$: $Y_j(t_2)=Y_j(t_1)+a_j(t_2-t_1)$, both summands of the same sign, so $|Y_j(t_2)|\ge v_1+|a_j|(t_2-t_1)\ge v_1+d_2$. For $j\in A_-$: $Y_j(-t_3)=Y_j(t_1)-a_j(t_1+t_3)$, both summands of the sign of $Y_j(t_1)$, so $|Y_j(-t_3)|\ge v_1+|a_j|(t_1+t_3)\ge v_1+d_3$. (Same noises $\varepsilon_j$ at all three $z$.)
4. Counting. $v_1+d_2<v_2\le u_1$, so $k_2:=k(v_1+d_2)$ is in the regular range, $u_{k_2}\le v_1+d_2<u_{R(t_2)}$, hence $k_2>R(t_2)$ (strict monotonicity of $u_k$), and every $j\in A_+$ is counted in $M_{t_2}(k_2)$: by (E0), $|A_+|\le D^*(k_2)-1$. Likewise $k_3:=k(v_1+d_3)>R(-t_3)$ and $|A_-|\le D^*(k_3)-1$.
5. Quarter drop. $v_1$ lies in the range of $\widetilde\Lambda$: $v_1=u_{R_1}\ge U$; $rv_1\le t_1+K\le U+K$; $D^*(v_1)=D^*(k(u_{R_1}))=D^*(R_1)\ge J$. Hence $\widetilde\Lambda\ge v_1Q(v_1)$. Also $rv_1\ge t_1-K\ge L-K=\sqrt U$. So $d_2=\frac rU(t_2-t_1)>\frac rU\sqrt U\,\widetilde\Lambda\ge\frac{rv_1}{\sqrt U}\,Q(v_1)\ge Q(v_1)$, and $d_3\ge\frac rU(t_3-t_1)>Q(v_1)$ in the same way. By (E1) (note $D^*(v_1)\ge J\ge1$), $D^*(k_2)=D^*(v_1+d_2)\le D^*(R_1)/4$ and $D^*(k_3)\le D^*(R_1)/4$.
6. Contradiction: $D^*(R_1)/2\le|\mathcal C|=|A_+|+|A_-|\le D^*(R_1)/2-2$.
The case $t_1\in S_-$ follows by applying the above to the reflected mates family $a_j\mapsto-a_j$ (then $Y^{\rm new}_j(z)=Y_j(-z)$, $R^{\rm new}(z)=R(-z)$, the roles of $S_+$ and $S_-$ are exchanged; the curve, the large/small split and the tilt condition are invariant). $\square$

**Claim (b).** $|S_+|+|S_-|\le\ell+\min\{B,\ell\}$, $\ell:=(1-r)U+K$ (Lebesgue measure; $S_\pm$ are finite unions of intervals since $R(\cdot)$ is piecewise constant with finitely many jumps, every $M_z(k)$ being a step function of $z$ with finitely many jumps). *Proof.* Tilt and $v\ge U$ give $t\ge rU-K$, so $S_\pm\subset I:=[a,U]$ with $a=\inf(S_+\cup S_-)\ge\max\{L,rU-K\}$, $|I|\le\ell$ (if $S_+\cup S_-=\varnothing$ there is nothing to prove). For $\epsilon>0$ pick $t_1\in S_+\cup S_-$, $t_1<a+\epsilon$, and $c=\min\{t_1+B,U\}$. By (a) one of the sets, say $S_\sigma$, misses $(c,U]$. Then $|S_+|+|S_-|\le|I|+|S_\sigma\cap[a,c]|\le\ell+\min\{B+\epsilon,\ell\}$; let $\epsilon\downarrow0$. $\square$

**Consequence used in step 9.** $\min\{B,\ell\}\le\frac{2K+2r^2}{1-r^2/U}+\min\{\sqrt U\,\widetilde\Lambda,U\}$, and $\frac{(1-r)U}{\sqrt{1-r^2}}=\gamma_rU$.

**Role of the constants (checked).** $J$ enters only through the range of $\widetilde\Lambda$ and the tracked-set definition (any threshold $\ge1$ works for (a)); $L-K=\sqrt U$ is exactly what converts $\sqrt U\,\widetilde\Lambda$ into $Q(v_1)$ (a larger lower cut $L$ would allow a smaller multiple of $\widetilde\Lambda$); the $2r^2$ in $B$ pays the reflected shift $2rt_1/U\le2r$; the upper limit $(U+K)/r$ in $\widetilde\Lambda$ is exactly $\sup rv_1$ allowed by tilt at $t_1\le U$. No good event, no probability, no property of $D^*$ beyond integrality and monotonicity.
