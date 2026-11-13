---
type: plan
title: >-
  Dense Simes crossings via the log-convex exponential-tilt mixture and Lehec's
  dimension-free tail bound
status: succeeded
target_asset: gaussian_simes_dense_crossing_tilt_bound
origin: agent
inspired_by:
  - idea_d3f052e917d7
proof_digest: bc3c9fef8bd705dfa2ecbe9ded2042c6274971bec38d80970623efead42e3326
statement_digest: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
dependency_digests:
  lehec2015_semilogconvex_density_tail: 75d99f0cd8e61299d987531806dad47de08d99b343dea4927e16d205626a08c2
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
verified_proof_digest: bc3c9fef8bd705dfa2ecbe9ded2042c6274971bec38d80970623efead42e3326
---

## Goal

Target: [asset](../assets/gaussian_simes_dense_crossing_tilt_bound.md)

Prove $\mathbb P_{N,0,\Sigma}(D_{q,\delta})\le C_D q$ for all $\delta\in(0,1]$, $q\in(0,q_D]$, with $q_D=\overline\Phi(3)$ and $C_D=8\sqrt{2\pi}\,e^{1/2}C_L$, where $C_L$ is the universal constant of [Lehec's tail bound](../assets/lehec2015_semilogconvex_density_tail.md).

Idea. Represent $T=Ag$ with unit rows $a_i$ and consider the averaged exponential tilt
$$
f(x)=\frac1N\sum_{i=1}^N\exp\bigl(u_q\,a_i\cdot x-u_q^2/2\bigr).
$$
It is smooth, positive, has $\int f\,d\gamma_n=1$ and is log-convex ($\beta=0$). On $D_{q,\delta}$ every crossing threshold lies in $[u_q,u_q+1]$, which forces $f(g)\ge r_q\asymp 1/(q u_q)$. Markov's inequality would give only $\mathbb P(D)\lesssim q u_q$ (the same loss as the Hommel weighting of [idea_d3f052e917d7](../ideas/idea_d3f052e917d7.md)); Lehec's extra factor $1/\sqrt{\log r_q}\asymp 1/u_q$ removes exactly the factor $u_q$.

## Plan

1. [x] **Gaussian representation.** Since $\Sigma\in\mathcal C_N$ is positive semidefinite, write $\Sigma=AA^{\mathsf T}$ with $A=\Sigma^{1/2}\in\mathbb R^{N\times N}$ (so $n=N$). Row $a_i$ of $A$ satisfies $|a_i|^2=\Sigma_{ii}=1$. If $g\sim\gamma_n$, then $Ag\sim\mathcal N_N(0,\Sigma)$, so $\mathbb P_{N,0,\Sigma}(D_{q,\delta})=\gamma_n(\widetilde D)$, where $\widetilde D$ is the same event with $T_i$ replaced by $a_i\cdot g$. Singular $\Sigma$ needs no special treatment. $\widetilde D$ is a finite union of finite intersections of half-spaces, so it is Borel.

2. [x] **Thresholds.** Fix $q\in(0,q_D]$, so $u_q\ge3$. For $k\in[N]$, $qk/N\in(0,1)$; put $t_k=\overline\Phi^{-1}(qk/N)$. Since $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$, $p_i\le qk/N\iff T_i\ge t_k$. Since $qk/N\le q$, we get $t_k\ge u_q$. If moreover $qk/N\ge\overline\Phi(u_q+\delta)$, then $t_k\le u_q+\delta\le u_q+1\le 2u_q$.

3. [x] **The tilt is an admissible Lehec density.** With $\lambda=u_q>0$ define $f(x)=N^{-1}\sum_i\exp(\lambda a_i\cdot x-\lambda^2/2)$ on $\mathbb R^n$. Then:
   - $f$ is smooth and positive;
   - $\int f\,d\gamma_n=N^{-1}\sum_i e^{\lambda^2|a_i|^2/2-\lambda^2/2}=1$ (Gaussian moment generating function, $|a_i|=1$);
   - with the softmax weights $\pi_i(x)=e^{\lambda a_i\cdot x}/\sum_j e^{\lambda a_j\cdot x}$, one has $\nabla^2\log f(x)=\lambda^2\bigl(\sum_i\pi_i a_ia_i^{\mathsf T}-(\sum_i\pi_ia_i)(\sum_i\pi_ia_i)^{\mathsf T}\bigr)\succeq0$, which is a covariance matrix.
   
   So the hypotheses of the [Lehec definition](../definitions/lehec2015_semilogconvex_density.md) hold with $\beta=0$ and $\max(\beta,1)=1$.

4. [x] **Mills bounds (prove inline).** For $t>0$:
   - (a) $\overline\Phi(t)\le\varphi(t)/t$, because $\int_t^\infty\varphi\le\int_t^\infty(u/t)\varphi(u)\,du$;
   - (b) $\overline\Phi(t)\ge t\varphi(t)/(1+t^2)$, because $h(t)=\overline\Phi(t)-t\varphi(t)/(1+t^2)$ has $h'(t)=-2\varphi(t)/(1+t^2)^2<0$ and $h(t)\to0$ as $t\to\infty$.
   
   Also $t/(1+t^2)\ge 1/(2t)$ for $t\ge1$.

5. [x] **Lower bound for $f$ on the event.** On $\widetilde D$ choose a witness $k$. At least $k$ indices satisfy $a_i\cdot g\ge t_k$, and every term of $f$ is positive, so
   $$
   f(g)\ge\frac kN e^{\lambda t_k-\lambda^2/2}=\frac{\overline\Phi(t_k)}{q}e^{u_qt_k-u_q^2/2}.
   $$
   By 4(b), $\overline\Phi(t_k)e^{u_qt_k-u_q^2/2}\ge\frac{t_k}{1+t_k^2}(2\pi)^{-1/2}e^{-(t_k-u_q)^2/2}$. Since $0\le t_k-u_q\le1$ and $1\le t_k\le 2u_q$ (step 2), this is at least $\frac{1}{4u_q}(2\pi)^{-1/2}e^{-1/2}$. Hence $\widetilde D\subset\{f\ge r_q\}$ with $r_q=c_0/(qu_q)$ and $c_0=e^{-1/2}/(4\sqrt{2\pi})$.

6. [x] **Size of $r_q$.** By 4(a), $qu_q\le\varphi(u_q)$, so $r_q\ge c_0\sqrt{2\pi}\,e^{u_q^2/2}=\tfrac14e^{-1/2}e^{u_q^2/2}$. Therefore $\log r_q\ge u_q^2/2-1/2-\log4\ge u_q^2/4$, because $u_q^2/4\ge 9/4>1/2+\log 4$. In particular $r_q>1$ and $\sqrt{\log r_q}\ge u_q/2$.

7. [x] **Apply Lehec.** For $1<r<r_q$, $\{f\ge r_q\}\subset\{f>r\}$, so $\gamma_n(f\ge r_q)\le C_L/(r\sqrt{\log r})$. Letting $r\uparrow r_q$ (the right side is continuous in $r>1$) gives
   $$
   \gamma_n(\widetilde D)\le\frac{C_L}{r_q\sqrt{\log r_q}}\le C_L\frac{qu_q}{c_0}\cdot\frac{2}{u_q}=\frac{2C_L}{c_0}\,q=8\sqrt{2\pi}\,e^{1/2}C_L\,q.
   $$

## Verification

Steps 1 and 7 give $\mathbb P_{N,0,\Sigma}(D_{q,\delta})=\gamma_n(\widetilde D)\le C_Dq$ for every $N$, every $\Sigma\in\mathcal C_N$ (any rank, any signs), every $\delta\in(0,1]$ and every $q\in(0,q_D]$, with $q_D=\overline\Phi(3)\in(0,1/4]$ and $C_D=8\sqrt{2\pi}e^{1/2}C_L$. Neither constant depends on $N$, $\Sigma$ or $\delta$, because $C_L$ is independent of $n$ and $f$. That is the exact statement. Optionally, if one wants $q_D=1/4$, enlarge $C_D$ to $\max(C_D,1/\overline\Phi(3))$ and use $\mathbb P\le1\le q/\overline\Phi(3)$ for $q\in[\overline\Phi(3),1/4]$. This step is not required, since the statement only asserts that some $q_D\in(0,1/4]$ exists. The only place $\delta\le1$ enters is the bound $t_k\le u_q+1$ in step 2.

## Assumed definitions

- [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values](../definitions/gaussian_test_pvalues.md) and the [Lehec semilogconvex density](../definitions/lehec2015_semilogconvex_density.md) are all approved.
- The only cited result is [Lehec's tail bound](../assets/lehec2015_semilogconvex_density_tail.md), which is approved and already in `depends_on`. Its source note asks for fresh source verification of the transcription. The plan uses it exactly for a single normalized, smooth, positive density with a global Hessian bound ($\beta=0$), with no supremum and no truncation, so it stays inside the stated applicability boundary.
- No unproved observation is used. The Mills bounds are proved inline in step 4.

## Outcome

Succeeded. The complete proof is under `## Proof` in [the target asset](../assets/gaussian_simes_dense_crossing_tilt_bound.md), following steps 1 to 7 without change, with $q_D=\overline\Phi(3)$ and $C_D=8\sqrt{2\pi}\,e^{1/2}C_L$. Every hypothesis of [Lehec's tail bound](../assets/lehec2015_semilogconvex_density_tail.md) was checked for the single density $f$: $f$ is $C^\infty$ with values in $(0,\infty)$, $\int f\,d\gamma_N=1$ by the Gaussian moment generating function and $|a_i|=1$, and $\nabla^2\log f$ is $\lambda^2$ times a covariance matrix, so $\beta=0$ and $\max(\beta,1)=1$. The bound is applied for $r\uparrow r_q$ in its stated form $\gamma_n(f>r)\le C\max(\beta,1)/(r\sqrt{\log r})$, $r>1$. Still assumed: only that cited theorem (approved, with its source transcription marked for fresh verification). The Mills bounds are proved inline.

## Verdict

confirmed

Checked step by step against the statement and the stated form of [Lehec's tail bound](../assets/lehec2015_semilogconvex_density_tail.md) with its [hypothesis definition](../definitions/lehec2015_semilogconvex_density.md).
- Step 1: $A=\Sigma^{1/2}$ has unit rows since $\Sigma_{ii}=1$; $Ag$ has law $\mathcal N_N(0,\Sigma)$, singular case included; the pulled-back event is a finite union of polyhedra, hence Borel.
- Step 2: $q\le\overline\Phi(3)$ gives $u_q\ge3$; $t_k\ge u_q$ from $qk/N\le q$, and $t_k\le u_q+\delta\le u_q+1\le2u_q$ on a witness $k$. The equivalence $p_i\le qk/N\iff T_i\ge t_k$ is correct.
- Step 3: every hypothesis of Lehec's theorem holds for the single function $f$: it is smooth and positive, $\int f\,d\gamma_N=1$ by the Gaussian MGF and $|a_i|=1$, and $\nabla^2\log f=\lambda^2\sum_i\pi_i(a_i-m)(a_i-m)^{\mathsf T}\succeq0$ (the covariance identity checks), so $\beta=0$ and $\max(\beta,1)=1$. No supremum or truncation is involved, so the applicability boundary in the dependency is respected.
- Step 4: both Mills bounds are proved correctly; the derivative computation gives $h'=-2\varphi/(1+t^2)^2$.
- Step 5: $k/N=\overline\Phi(t_k)/q$ and $\varphi(t)e^{ut-u^2/2}=(2\pi)^{-1/2}e^{-(t-u)^2/2}$ check; with $0\le t_k-u_q\le1$ and $1\le t_k\le2u_q$ one gets $f\ge c_0/(qu_q)$ on the event.
- Step 6: $qu_q\le\varphi(u_q)$ gives $r_q\ge\tfrac14e^{-1/2}e^{u_q^2/2}$; $u_q^2/4\ge9/4>1/2+\log4\approx1.886$, so $\log r_q\ge u_q^2/4$, $r_q>1$.
- Step 7: the limit $r\uparrow r_q$ is legitimate since $\{f\ge r_q\}\subset\{f>r\}$ for $r<r_q$ and the bound is continuous in $r$; the arithmetic $2C_L/c_0=8\sqrt{2\pi}e^{1/2}C_L$ is correct. The constants depend only on $C_L$, so they are uniform in $N,\Sigma,\delta,q$ as claimed.
No gaps found. The result is only as solid as the cited Lehec transcription, which the dependency itself marks for fresh source verification.
