---
type: plan
title: 'Crossing subset, exact Mills integral and a certified quadratic bound'
status: succeeded
target_asset: gaussian_simes_mills_penalized_subset_reduction
inspired_by:
  - idea_4fff9841ba84
adapts: []
proof_digest: 93ea43fcfac9ff7495d44abc3e8f0ad911ca818a4ab2cbe6bfef29099a409051
statement_digest: d8696dc0ee5040d69e3a44c44fe818131df421b54610842f2b5ca99f0ec56f89
dependency_digests:
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
verified_proof_digest: 93ea43fcfac9ff7495d44abc3e8f0ad911ca818a4ab2cbe6bfef29099a409051
---

## Goal

Target: [asset](../assets/gaussian_simes_mills_penalized_subset_reduction.md)

Prove the deterministic inequality by evaluating $M_A(t)$ on one explicit subset, the $k$ crossing coordinates, and closing the estimate with an explicit quadratic inequality instead of a grid scan. All Mills-ratio facts are proved inline from the definition of $\overline\Phi$ in [Gaussian test p-values](../definitions/gaussian_test_pvalues.md); no other node is cited.

Notation: $\phi(s)=e^{-s^2/2}/\sqrt{2\pi}$, $h=\phi/\overline\Phi$, $L=\log(1/(Aq))$.

## Plan

1. [x] **Basic facts on $\overline\Phi$.** $\overline\Phi$ is $C^\infty$ with $\overline\Phi'=-\phi<0$, $\overline\Phi(s)\to1$ as $s\to-\infty$ and $\to0$ as $s\to\infty$; hence it is a strictly decreasing bijection $\mathbb R\to(0,1)$ and $\overline\Phi^{-1}:(0,1)\to\mathbb R$ is well defined. $\overline\Phi(0)=1/2$. For $t_i\in\mathbb R$, $p_i\in(0,1)$, and $p_i\le c\iff t_i\ge\overline\Phi^{-1}(c)$ for $c\in(0,1)$.

2. [x] **Derivative of $h$.** Using $\phi'(s)=-s\phi(s)$ and $\overline\Phi'=-\phi$,
   $$
   h'(s)=\frac{-s\phi\overline\Phi+\phi^2}{\overline\Phi^2}=h(s)\bigl(h(s)-s\bigr),\qquad (\log\overline\Phi)'=-h .
   $$

3. [x] **$h'>0$.** Claim $h(s)>s$ for every $s$. For $s\le0$ this holds because $h>0$. For $s>0$, $\overline\Phi(s)=\int_s^\infty\phi(x)\,dx<\int_s^\infty\frac xs\phi(x)\,dx=\frac{\phi(s)}s$ (strict because $x/s>1$ on $(s,\infty)$ and $\phi>0$), so $h(s)>s$. Hence $h'=h(h-s)>0$, $h$ is strictly increasing, and $h(s)\ge h(0)=\phi(0)/\overline\Phi(0)=\sqrt{2/\pi}$ for $s\ge0$.

4. [x] **$h'<1$ (truncated-normal variance).** Fix $s$ and let $\mu_s$ be the probability measure with density $\phi(x)\mathbf 1_{x>s}/\overline\Phi(s)$. Then $\int x\,d\mu_s=\phi(s)/\overline\Phi(s)=h(s)$ (since $\int_s^\infty x\phi=\phi(s)$), and integrating by parts, $\int_s^\infty x^2\phi(x)\,dx=s\phi(s)+\overline\Phi(s)$, so $\int x^2\,d\mu_s=1+s\,h(s)$. Therefore
   $$
   \operatorname{Var}(\mu_s)=1+s\,h(s)-h(s)^2=1-h'(s).
   $$
   The variance is strictly positive because $\mu_s$ has a density, so $(x-h(s))^2>0$ for $\mu_s$-a.e. $x$. Hence $h'(s)<1$ for every $s\in\mathbb R$. Consequence (mean value theorem): $h(s)\le h(z)+(s-z)$ for $s\ge z$.

5. [x] **The crossing subset.** Fix $k$ with $p_{(k)}\le qk/N$, and put $\kappa=k/N$, $c=q\kappa$. Since $A\ge2$ and $Aq\le e^{-1}$, $c\in(0,1)$; put $u=\overline\Phi^{-1}(c)$. The indices realizing $p_{(1)},\ldots,p_{(k)}$ (counted with multiplicity, ties broken arbitrarily) form a set $K$ with $|K|=k$ and $p_i\le p_{(k)}\le c$ for $i\in K$; by step 1, $t_i\ge u$ for $i\in K$, so $X_K(t)\ge u$. For this $K$, $\kappa_K=\kappa$, $z:=z_K=\overline\Phi^{-1}(\kappa/A)\ge0$ (as $\kappa/A\le1/2=\overline\Phi(0)$), and $\tau:=\tau_A(K)=h(z)>0$.

6. [x] **Exact Mills integral.** $\overline\Phi(u)=q\kappa<\kappa/A=\overline\Phi(z)$ because $Aq\le e^{-1}<1$, so $d:=u-z>0$. By step 2,
   $$
   \int_z^u h(s)\,ds=\log\frac{\overline\Phi(z)}{\overline\Phi(u)}=\log\frac{\kappa/A}{q\kappa}=L\ge1,
   $$
   the last inequality because $Aq\le e^{-1}$. This holds for every $N$, $k$, $t$.

7. [x] **Lower bound for the $K$ term.** Since $\tau>0$ and $X_K\ge u$,
   $$
   M_A(t)\ge\tau(X_K-\tau)\ge\tau(u-\tau)=\tau d-\tau(\tau-z)=\tau d-h'(z)>\tau d-1,
   $$
   using step 2 for $\tau(\tau-z)=h(z)(h(z)-z)=h'(z)$ and step 4 for $h'(z)<1$.

8. [x] **Upper bound for $L$.** Integrating the consequence of step 4 over $[z,u]$:
   $$
   L=\int_z^{z+d}h\le\tau d+\frac{d^2}2 .
   $$
   With $a:=\tau d>0$ and $\tau^2\ge2/\pi$ (step 3, $z\ge0$), $d^2/2=a^2/(2\tau^2)\le\frac\pi4a^2$, so
   $$
   \frac\pi4a^2+a-L\ge0 .
   $$

9. [x] **Certified worst case: $a\ge\frac12\sqrt L$ for every $L\ge1$.** The quadratic $g(a)=\frac\pi4a^2+a-L$ is strictly increasing on $[0,\infty)$. At $a_0=\frac12\sqrt L$,
   $$
   g(a_0)=\frac{\pi}{16}L+\frac12\sqrt L-L=\sqrt L\Bigl(\tfrac12-\bigl(1-\tfrac\pi{16}\bigr)\sqrt L\Bigr)\le\sqrt L\Bigl(\tfrac12-\bigl(1-\tfrac\pi{16}\bigr)\Bigr)=\sqrt L\Bigl(\tfrac\pi{16}-\tfrac12\Bigr)<0,
   $$
   using $\sqrt L\ge1$ and $\pi<8$. Since $g(a)\ge0>g(a_0)$ and $g$ is increasing on $[0,\infty)$, $a>a_0$. (Only $\pi<8$ is used; no numerical value of $\pi$ is needed beyond that.)

10. [x] **Conclusion.** Combining steps 7 and 9, $M_A(t)>\tau d-1=a-1>\frac12\sqrt L-1$, which gives the stated inequality (even strictly).

## Verification

Steps 1 to 4 are self-contained calculus facts about $\overline\Phi$ and $h$, proved from the definition of $\overline\Phi$ alone. Step 5 uses only the crossing hypothesis and the definition of order statistics with multiplicities, so ties and all ranks $k\in\{1,\ldots,N\}$ are covered. Step 6 uses $Aq\le e^{-1}$ (giving $u>z$ and $L\ge1$) and $A\ge2$ (giving $z\ge0$, needed for $\tau\ge\sqrt{2/\pi}$ in step 8). Steps 7 to 9 are exact inequalities; step 9 replaces the earlier grid scan by the explicit sign computation $g(\frac12\sqrt L)\le\sqrt L(\pi/16-1/2)<0$ for $L\ge1$. The maximum in $M_A$ is over finitely many nonempty subsets, so $M_A(t)\ge$ the $K$ term is immediate. The conclusion is exactly $M_A(t)\ge\frac12\sqrt{\log(1/(Aq))}-1$ for every $N$, $t$, $A\ge2$, $0<q\le e^{-1}/A$.

## Assumed definitions

- [Gaussian test p-values](../definitions/gaussian_test_pvalues.md) (approved): only the definition of $\overline\Phi$ is used. No draft definitions and no unproved dependencies.

## Outcome

Succeeded. The complete proof is under `## Proof` in [the target asset](../assets/gaussian_simes_mills_penalized_subset_reduction.md), following steps 1 to 10 as planned with no changes of route. Nothing is assumed beyond the approved definition of $\overline\Phi$ in [Gaussian test p-values](../definitions/gaussian_test_pvalues.md); all Mills-ratio facts ($h'=h(h-s)$, $0<h'<1$, $h\ge\sqrt{2/\pi}$ on $[0,\infty)$) are proved inline, and the final quadratic comparison uses only $\pi<8$. The conclusion holds strictly.

## Verdict

confirmed

Checked step by step against the statement ($A\ge2$, $0<q\le e^{-1}/A$, a crossing $p_{(k)}\le qk/N$ at one rank). Step 1: $\overline\Phi$ is a strictly decreasing bijection onto $(0,1)$, so $p_i\le c\iff t_i\ge\overline\Phi^{-1}(c)$. Step 2: $h'=h(h-s)$ is correct. Step 3: $\overline\Phi(s)<\phi(s)/s$ for $s>0$ gives $h>s$, so $h'>0$ and $h(z)\ge h(0)=\sqrt{2/\pi}$ for $z\ge0$. Step 4: the integration by parts $\int_s^\infty x^2\phi=s\phi(s)+\overline\Phi(s)$ is correct, so the truncated-normal variance equals $1+sh-h^2=1-h'$, which is strictly positive; the mean value bound $h(s)\le h(z)+(s-z)$ follows.
Step 5: $q\le1/(2e)<1$, so $c=qk/N\in(0,1)$. The $k$ smallest p-values, with ties broken arbitrarily, give a $K$ with $|K|=k$ and every $t_i\ge u$. Since $A\ge2$, $\kappa/A\le1/2$ and $z\ge0$; this covers $k=N$ ($\kappa=1$).
Step 6: $\int_z^u h=\log\overline\Phi(z)-\log\overline\Phi(u)=\log(1/(Aq))$ exactly, and $d>0$ because $Aq<1$.
Step 7: $\tau(u-\tau)=\tau d-h'(z)>\tau d-1$ uses $\tau>0$ and Step 4.
Steps 8 and 9: $L\le\tau d+d^2/2\le a+\frac\pi4a^2$ uses $\tau^2\ge2/\pi$. Also $g(\tfrac12\sqrt L)=\sqrt L\bigl(\tfrac12-(1-\tfrac\pi{16})\sqrt L\bigr)<0$ follows from $\sqrt L\ge1$ and $\pi<8$, and $g$ is increasing on $[0,\infty)$ with $a>0$, so $a>\frac12\sqrt L$.
Edge cases: at the largest allowed $q$, $L=1$ and every step still holds. Ties and $k=N$ are handled as above, and no division by a vanishing quantity occurs.
A numerical spot check found $h'\in(0,1)$ on $[-5,30]$ and positive slack in the final bound for several values of $A$, $Aq$ and $k/N$. No gaps found.
