---
type: candidate
title: >-
  Zero-radius identical null clumps against a near-critical fog of weak
  alternatives
status: survived
target_asset: gaussian_bh_subexponential_rare_clump_bracket_cap
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: pass
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: d66c527595f7967458383519a22868df0977fdbc6933b1f63f69cb380debf465
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:53:04.402Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

# Zero-radius identical null clumps against a near-critical fog of weak alternatives

## Object

Degenerate case of the clump hypotheses: every clump has radius $0$ (identical directions, so all ties $D_i=k$). Fix any $\kappa\in(0,1]$ and any $q\le\overline\Phi(e)$, $u=\overline\Phi^{-1}(q)$. Parameters:

- an integer $X$ with $2\le X\le 1/(4q)$ (below: $X=\lfloor 1/(4q)\rfloor$);
- clump size $k=10^4X^3$, target rank $M=kX$;
- a number $L$ of clumps, $m=4kL$ (so $\rho:=Lk/m=1/4$), with $L$ so large that $4L\ge e^{u}$, $L\ge X$, and
$$
y_M:=\overline\Phi^{-1}(qM/m)\quad\text{satisfies}\quad y_M^2\ge 8X\log X\,\log(2/q).
$$
- coordinates: $L$ clumps $K_1,\dots,K_L$ of $k$ coordinates each, with $\theta_i=0$ and $w_i=e_l$ for $i\in K_l$ (identical directions); $n=3m/4$ alternatives $a$, each with its own basis direction $e_a$ (orthogonal to everything else) and the common mean $\theta_a=\vartheta>0$ fixed by
$$
n\,\overline\Phi(y_M-\vartheta)=M-k/2 .
$$
($d=L+n$.) Take $S=\bigcup_lK_l$, centers $c_l$ any element of $K_l$.

So the clump statistics $s_l=\overline\Phi(Z_l)$ are iid uniform, independent of the alternatives' p-values $p_a=\overline\Phi(\vartheta+Z_a)$, which are iid. The alternatives form a "fog": weak signals whose p-value intensity in the deep tail $t\approx qM/m\ll q$ is boosted by $\overline\Phi(y-\vartheta)/\overline\Phi(y)\approx 4/(3q)$, i.e. it sits at relative distance $1/(2X)$ below the BH line $mt/q$, uniformly over the multiplicative window $t\in[qk/m,qM/m]$.

## Checks

### H1
Unit vectors $w_i$, $m,d$ positive integers, $0<q\le\overline\Phi(e)<1/2$, so $u\ge e>1$; $\tau_q=e^{-u}$, $a_q=2\log u/u\le 2/e$. Pass.

### H2
$S\subseteq\{i:-a_q<\theta_i\le0\}$ since $\theta_i=0$ on $S$; alternatives have $\vartheta>0$ (it exists and is unique: $t\mapsto n\overline\Phi(y_M-t)$ increases continuously from $n qM/m=3qM/4<M-k/2$ to $n>M$). Pass.

### H3
$K_1,\dots,K_L$ are nonempty and partition $S$; $c_l\in K_l$. Pass.

### H4
Clump radius: $\|w_i-w_{c_l}\|=0\le\kappa/u$. Pass.

### H5
For $j\in K_l$, every $i\in S\setminus K_l$ has $\|w_i-w_j\|=\sqrt2>\kappa/u$ (as $\kappa\le1<\sqrt2e$). So the neighbourhood count is $k$, and $k=m/(4L)\le e^{-u}m=\tau_qm$ because $4L\ge e^u$. Pass.

### NOT

**Exact per-clump formula.** For $i\in K_l$ all clump p-values equal $s_l$, so $D_i=k$. $R_{i,0}$ (clump $l$ replaced by one $0$ and $k-1$ ones) and $R_{i,*}$ (clump $l$ replaced by $k$ zeros) are functions of the other coordinates only; write them $R_0^l,R_*^l$. BH is coordinatewise monotone, so $R_0^l\le R_*^l$, and $R_*^l\ge k$ ($p_{(k)}=0$). With $B=\max(R_0^l,k)\le R_*^l$ and $s_l\sim U(0,1)$ independent of the rest,
$$
\mathbb E\Bigl[\sum_{i\in K_l}\Psi_i\,\Big|\,\text{others}\Bigr]
=\int_0^{qR_*^l/m}\frac{k\,ds}{\max(B,ms/q)}
=\frac{qk}{m}\Bigl(1+\log\frac{R_*^l}{\max(R_0^l,k)}\Bigr).
$$
Summing, $\mathbb E\sum_{S}\Psi_i=\rho q\,(1+\mathbb E\log(R_*^1/\max(R_0^1,k)))$ with $\rho=1/4$, by symmetry.

**Mean profile of the fog.** Let $g(t)=n\overline\Phi(y(t)-\vartheta)$, $y(t)=\overline\Phi^{-1}(t)$, $y_r=y(qr/m)$, and $\Lambda(y)=\overline\Phi(y-\vartheta)/\overline\Phi(y)$, increasing in $y$. Then $g(qr/m)/r=(nq/m)\Lambda(y_r)$ is decreasing in $r$ and equals $1-1/(2X)$ at $r=M$.
(i) Size of $\vartheta$: $\Lambda(y)\ge e^{\vartheta y-\vartheta^2/2}$ (write $\overline\Phi(y-\vartheta)=\int_y^\infty\varphi(x)e^{\vartheta x-\vartheta^2/2}dx$), and $\Lambda(y_M)\le m/(nq)=4/(3q)$; $\vartheta<y_M$ (else $\Lambda(y_M)\ge 1/(2qM/m)>4/(3q)$), hence $\vartheta\le 2\log(2/q)/y_M$.
(ii) Flatness: with hazard $h=\varphi/\overline\Phi$, $0<h'<1$ and $h(y)>y$, for $k\le r\le M$,
$$
\log\frac{\Lambda(y_r)}{\Lambda(y_M)}=\int_{y_M}^{y_r}(h(y)-h(y-\vartheta))dy\le\vartheta(y_r-y_M)\le\frac{\vartheta\log(M/r)}{y_M}\le\frac{2\log(2/q)\log X}{y_M^2}\le\frac1{4X}.
$$
So $g(qr/m)\le r(1-\tfrac1{2X})(1+\tfrac1{3X})\le r(1-\tfrac1{6X})$ on $(k,M]$, and $g(qr/m)\le r(1-\tfrac1{2X})$ for $r\ge M$.

**Good event $G$.** Let $F_A(t)=\#\{a:p_a\le t\}$ and $N_C(t)=\#\{l'\ne1:s_{l'}\le t\}$.
- $A_1$: $F_A(qr/m)\le g(qr/m)+r/(6X)-2$ for all integers $r>k$. By Bernstein (variance $\le g\le r$, deviation $\ge r/(7X)$ since $r>k\ge84X$), each failure has probability $\le e^{-r/(103X^2)}$; summing over $r>k=10^4X^3$ gives $P(A_1^c)\le 10^5X^4e^{-97X}<10^{-30}$.
- $A_2$: $F_A(qM/m)\ge M-k$. $P(A_2^c)\le e^{-(k/2)^2/(2M)}=e^{-k/(8X)}$, negligible.
- $A_3$: $N_C(t)\le\lambda(L-1)t$ for all $t$, with $\lambda=1/(4qX\rho)=1/(qX)\ge4$. Daniels' identity for the uniform empirical process ($P(\sup_tF_n(t)/t\ge\lambda)=1/\lambda$) gives $P(A_3^c)\le 1/4$.

On $A_3$, $kN_C(qr/m)\le k\lambda Lqr/m=r/(4X)$, and $N_C(qr/m)<1$ for $r<4M$, so $N_C=0$ on $r\le M$.
On $A_1\cap A_3$: for $k<r\le M$, $1+F(qr/m)=1+F_A\le r-1<r$; for $r\ge M$, $1+F\le 1+r(1-\tfrac1{2X})+\tfrac r{6X}-2+\tfrac r{4X}<r$. The $k-1$ ones never count ($qr/m<1$). Hence $R_0^1\le k$.
On $A_2$: $k+F(qM/m)\ge k+M-k=M$, hence $R_*^1\ge M=kX$.
So on $G=A_1\cap A_2\cap A_3$ (probability $\ge 0.74$), $\log(R_*^1/\max(R_0^1,k))\ge\log X$.

**Conclusion.**
$$
\mathbb E\sum_{i\in S}\Psi_i\ge\frac q4\bigl(1+0.74\log X\bigr).
$$
With $X=\lfloor1/(4q)\rfloor$ and $\log(1/q)\ge u^2/2$ (from $\overline\Phi(u)\le e^{-u^2/2}/2$), $\log X\ge u^2/2-\log 5$, so the charge is at least $q(0.09u^2-0.05)$. Given any $A_3,q_3$, choose $q\le q_3$ with $0.09u^2-0.05>A_3(1+u)$ (e.g. $u\ge 12A_3+12$); the bound $A_3q(1+u)$ fails. Since $X$ is free, any $X=e^{\omega(u)}$ with $X\le1/(4q)$ already gives a charge of order $q\log X\gg q(1+u)$. Pass (conclusion violated).

Numerical sanity check (Poisson approximation of the fog, scratch script, not a proof): $q=0.01$, $X=20$, $k=2000$, $y_M=60$ gave mean $R_0\approx2.4\times10^3$, mean $R_*\approx7.9\times10^4$, $\mathbb E\log(R_*/\max(R_0,k))\approx3.33\ge\log20\approx3.00$.

## Mechanism

The charge $\Psi_i$ has denominator $\max(R_{i,0},D_i,mp_i/q)$ instead of the true $R_{i,*}$. A fog of $\Theta(m)$ weak alternatives with $\vartheta\approx 2\log(2/q)/y_M$ makes the count of the other coordinates subcritical by exactly $1/(2X)$ on the deep-tail window $[qk/m,qM/m]$, which has length only $\log X/y_M$ in the $y$ scale; there the log-intensity of the fog changes by $\le\vartheta\log X/y_M\to0$. One extra zero cannot start the cascade, $k$ extra zeros run it to $M=kX$, so each clump pays $\frac{qk}m\log X$. Clumps do not interfere because $\rho qX\le1/16$. No global-null or Simes structure is used: the counterexample lives entirely in the alternatives.
