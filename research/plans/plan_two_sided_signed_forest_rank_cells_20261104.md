---
title: Finite signed Gaussian clusters and reciprocal-rank charging for two-sided BH
type: plan
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_8ccb5a5a1c27
  - idea_f8434ba89f54
  - idea_31a7cd7cb5ad
  - idea_7d718e40cb44
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged unrestricted statement through a finite connected-cluster expansion of the **actual** Gaussian BH rank cells. The new candidate tool is a signed Gaussian forest identity, closed by finite rectangle cumulants rather than an infinite diagram series, together with the beta-integral representation of the reciprocal of the largest BH rank. The intended cancellation occurs among explicit rank-cell coefficients before a positive majorant is taken. No covariance is optimized independently of the law generating those cells. This is a proposed tool to construct, not an established estimate.

The mandatory first gate is finite closure with positive integrable majorants for arbitrary PSD endpoints. If it cannot be constructed, this plan fails at that gate; exact leaf identities may still be retained. In particular, neither null-sign conjugation nor an odd number of derivatives at a null makes a term vanish under a coupled Gaussian law. No Ising positivity, infinite cycle resummation, dimension-free cumulant norm, all-null estimate, or sharp charging inequality is assumed.

The context pack has no Library analogues section. Native library searches for `Gaussian BH two-sided`, `Gaussian Brascamp Lieb entropy radial conditional sign`, `Gaussian entropy log Sobolev heat martingale convex`, and `Gaussian forest interpolation rank bin Hermite` returned no matches. No library statement is cited and no proof is adapted. A native read of [Check the exact signed-doubling transfer from two-sided BH to one-sided BH](../ideas/idea_e78c63b4cd6d.md), requested to check a possible structural shortcut absent from the pack, did not provide a proof tool: signed doubling preserves the level q and supplies no additional factor one half. No draft one-sided theorem is used.

## Plan

1. [x] **Construct and test the exact finite algebra before seeking an upper bound.** For fixed N, q, the null set J, and positive-definite Sigma, write H for the actual FDR and E_C for expectation under N(theta,C), set t_k = inverse-normal-survival(q k/(2N)), U=t_N, and let b_i be the smallest k with p_i <= q k/N, or N+1. Bin k<=N is ((k-1)q/N,kq/N], and bin N+1 is (q,1]; the probability-zero value p_i=0 may be assigned to bin 1. For each bin vector b define

   $$
   r(b)=\max\bigl(\{0\}\cup\{k:\#\{i:b_i\leq k\}\geq k\}\bigr),\qquad
   v(b)=\#\{i\in J:b_i\leq r(b)\},
   $$

   $$
   P_J(z)=\sum_b\frac{v(b)}{r(b)\vee1}\prod_i z_{i,b_i},\qquad
   Q_J(x,z)=\sum_{b:r(b)>0}v(b)x^{r(b)-1}\prod_i z_{i,b_i}.
   \tag{C1}
   $$

   Prove P_J(z)=integral from 0 to 1 of Q_J(x,z) dx. These are finite multilinear polynomials with rational rank coefficients, not unknown FDR functions. Derive the recursion that evaluates r(b) from all count constraints, including every hole above a qualifying rank. At independent coordinates, verify P_J(a)=q|J|/N, where a_{i,b} is the marginal bin probability. For derivative coefficients record the explicit one-dimensional arrays

   $$
   a_{i,b}^{(n)}=\int_{\{x:\,2\overline\Phi(|\theta_i+x|)\text{ is in bin }b\}}
       H_n(x)\varphi(x)\,dx.
   \tag{C2}
   $$

   Here phi is the standard normal density and H_n=(-1)^n phi^{(n)}/phi is the probabilists' Hermite polynomial. For n>=1 obtain these arrays from differences of H_{n-1} phi at the finitely many endpoints. For a centered null, a_{i,b}^{(n)}=0 when n is odd; use this fact only for an independent Gaussian integral. Check (C1) exactly on every bin vector and null labeling for N<=4. A short local deterministic check is allowed; no large local experiment is part of this plan.

2. [x] **Mandatory gate: a finite, singular-stable signed-cluster closure.** Smooth the finite-cell FDP by an even centered convolution f_delta and work first with Sigma_eta=(1-eta)Sigma+eta I. Reprove by repeated finite fundamental-theorem-of-calculus identities, rather than citing an unlisted theorem, the Gaussian forest formula

   $$
   E_{\Sigma_\eta}f_\delta
   =E_I f_\delta+
   \sum_{F\ne\varnothing}\Bigl(\prod_{ij\in F}(\Sigma_\eta)_{ij}\Bigr)
   \int_{[0,1]^F}E_{\Sigma_\eta\circ T^F(t)}
       \Bigl[\prod_{ij\in F}\partial_i\partial_j f_\delta\Bigr]dt.
   \tag{C3}
   $$

   Here F ranges over finite forests, T^F has diagonal 1, entry zero between components, and the minimum edge parameter along the unique path within a component. Prove its PSD property from its integral-of-partition-matrices representation, and justify every differentiation on the resulting compact positive-definite covariance set. A smooth extension used to derive the forest identity must agree with the Gaussian expectation on that set; an expectation at an indefinite matrix is forbidden.

   For a null vertex i of odd derivative degree in D_F, prove the **remainder identity**, not a vanishing claim. If C is the covariance at a forest point and C_s scales exactly its i-to-rest block by s, with diagonal fixed, then

   $$
   E_C D_F f_\delta
    =\int_0^1\sum_{k\ne i}C_{ik}
       E_{C_s}[\partial_i\partial_k D_F f_\delta]\,ds.
   \tag{C4}
   $$

   Indeed C_s=D_s C D_s+(1-s^2)e_i e_i^T is PSD and the expectation at s=0 vanishes by an independent centered odd coordinate. Both the original covariance prefactor and the new factor C_{ik} remain. A new edge may move an odd-degree defect to another vertex, so recursive application is not claimed to terminate.

   The explicit finite closure candidate is rectangle cumulants. With p_B(b_B) the Gaussian probability of the specified bins in B, define

   $$
   \kappa_B(b_B)=\sum_{\pi\in\mathcal P(B)}
       (-1)^{|\pi|-1}(|\pi|-1)!\prod_{A\in\pi}p_A(b_A).
   \tag{C5}
   $$

   Prove the finite inverse relation p_B=sum over partitions pi of B of product over A in pi of kappa_A. Group (C3)-(C4) into these finite objects; an unevaluated infinite walk expansion is not a closure. The allowed elementary positive majorant is

   $$
   |\kappa_B(b_B)|\leq
   \sum_{\pi\in\mathcal P(B)}(|\pi|-1)!\prod_{A\in\pi}p_A(b_A).
   \tag{C6}
   $$

   It is integrable and survives a singular Gaussian endpoint because it contains actual probability measures. Its combinatorial size is **not** a dimension-uniform budget. Produce the full finite coefficient table: the coefficient of an atom obtained by expanding the cumulants indexed by a partition pi and subpartitions pi_B is

   $$
   c_{b,\pi,(\pi_B)}=
       \frac{v(b)}{r(b)\vee1}
       \prod_{B\in\pi}(-1)^{|\pi_B|-1}(|\pi_B|-1)!.
   \tag{C7}
   $$

   Prove the same table directly from (C1) and (C5), and reconcile it with the forest remainders before using it for estimates. Do not replace this table by its total variation. Retain signed triangular Gram products; null parity does not force individual correlations to occur only to even powers.

   Required minimal tests are N=1; N=2 all-null; N=2 with one nonzero mean; N=3 with correlations (rho_12,rho_23,rho_13)=(1/3,1/3,-1/3); independence; identical and antipodal singular coordinates; and the simplex and common-gate families already in the pack. In the two-null case independently reconstruct

   $$
   H(\rho)=q+C_\rho(q,q)-2C_\rho(q/2,q),\qquad
   H(\rho)=q+\frac{\rho^2}{2}I_2(q)[I_2(q)-2I_2(q/2)]+O(\rho^4),
   \tag{C8}
   $$

   where C_rho(s,t) is the joint two-sided null p-value CDF and I_2(s)=2a_s phi(a_s), with a_s=inverse-normal-survival(s/2). Its generally nonzero quadratic term must remain. A bounded preliminary numerical evaluation gives the quadratic coefficient -0.00698898018381191 at q=.05; this is only a diagnostic, not a proof. Stop this plan if (C3)-(C7) cannot be reconciled finitely with (C8), or if a proposed majorant needs an indefinite Gaussian law, positive cycle signs, or a dimension-dependent smoothing limit.

3. [ ] **Construct a rank-coefficient charging table, using the beta integral before bounding clusters.** Starting from the explicit signed atoms (C7), integrate Q_J in (C1), and cancel all contributions containing no connection to a null. Verify this cancellation against the exact forced-zero BH identity; do not infer it from diagram parity. The output must be a finite table of signed sums of rectangle atoms, with their null anchor i, largest-rank interval, and covariance blocks recorded. The table is required to give an exact representation

   $$
   H-q|J|/N=\frac qN\sum_{i\in J}
       \left\{\int_0^U K_i(y)\,dy+E_i\right\}.
   \tag{C9}
   $$

   Each K_i and E_i must be written explicitly from (C2), (C5), (C7), the beta integral, and Gaussian rectangle probabilities. They may be signed. No K_i may be defined as the unknown FDR increment, a completion support function, or the missing negative-part term in an earlier plan. A Schur-complement pivot may introduce a standardized Gaussian variable y; its residual variables retain their actual joint Gaussian law. Solve the affine bin inequalities at that pivot to obtain their exact interval endpoints. This step must exhibit the charge allocation and prove (C9), rather than assuming such a representation exists.

4. [ ] **Prove separate coefficient packing and exterior bounds for that table.** For U sufficiently large, the specific charging certificate to seek is

   $$
   K_i(y)\leq\frac1{2\sqrt{2\pi}}\quad(0<y<U),
   \qquad E_i\leq C(1+\log U),
   \tag{C10}
   $$

   with one numerical C independent of N, means, covariance, the anchor, and all regularizations. These inequalities concern the explicit coefficient table produced in step 3; they are not premises. Prove the first by a stated finite rank-bin coefficient cancellation/charging rule, including its one-half allocation between the two signs, and a Gaussian integration of the remaining rectangle atoms. Prove the second from explicitly identified beta-integral endpoints and outer Gaussian strips. Write the resulting coefficient inequalities before summing them; a proof that merely bounds their aggregate by the desired scalar FDR bound does not establish this certificate.

   The residual Gaussian average is taken **before** any sharp packing assertion. No uniform claim for arbitrary fixed perpendicular slices is allowed, in view of the risk recorded in idea_31a7cd7cb5ad. The proof must include all-null tables and mixed tables, not reduce the former to an unproved Simes assertion. Test (C10) first in the minimal models from step 2. If it fails, freeze the finite table, parameter values and failed coefficient inequality as a method obstruction, and end this attempt. Do not move failed charges into an undefined error term. In particular, the crude positive bound (C6) is not a substitute for this signed packing argument.

5. [ ] **Combine only proved steps and remove regularizations with uniform control.** From (C9)-(C10) obtain

   $$
   H\leq q\frac{|J|}{N}
       \left[1+\frac{U}{2\sqrt{2\pi}}+C(1+\log U)\right].
   \tag{C11}
   $$

   Show that the bounds used to derive (C11) are independent of delta and eta before taking limits. For a singular endpoint each statistic still has a continuous unit-variance marginal, so the finite set of BH threshold hyperplanes has zero probability; justify convergence of the actual largest-rank FDP using its bin formulation, including ties. Handle J empty and N=1 directly. Since U is inverse-normal-survival(q/2), prove U/sqrt(log(1/q)) tends to sqrt(2) and (1+log U)/sqrt(log(1/q)) tends to zero. This yields the exact proposed constant 1/(2 sqrt(pi)) uniformly before taking the supremum in the target.

## Verification

Success requires a reproducible finite coefficient table, the signed forest/cumulant reconciliation, proved coefficient-level inequalities (C10), and uniform regularization removal. The mandatory gate is a new finite-array tool; the sharp step is its explicit reciprocal-rank charging, not a renamed trace or negative-part budget. A verified identity alone is insufficient. A finite witness against a gate or (C10) refutes only this method certificate unless its **actual** BH FDR also violates the original asymptotic quantifiers with a rigorous sequence and error bound.

Local work is restricted to short deterministic algebra and bounded quadrature. Any substantial enumeration, optimization or Monte Carlo must run on UC Davis and independently validate ordinary largest-rank BH, singular covariance, ties and R=0. Numerical agreement is never used as the proof of a uniform packing inequality. No population critical-root approximation or finite-z tangency transfer is needed by the proposed exact finite-array construction.

## Assumed definitions

Only the approved definitions listed in the target are used: Gaussian multiple-testing model, Gaussian test p-values, ordinary Benjamini-Hochberg step-up procedure, false discovery rate, and uniform worst-case Gaussian BH FDR. There are no assumed draft definitions or unproved theorem dependencies. The motivating draft ideas and earlier auxiliary calculations are rederived where used. Hermite endpoint identities, forest interpolation, rectangle cumulant inversion, positive majorants, rank charging, and every uniform bound above are proof obligations of this plan, not additional assumptions or black-box library results.

## Difference from failed plans

- `plan_two_sided_signed_face_budget_20261104`: replaces a direct signed-face sum and the failed opposite-face ordering by finite connected Gaussian clusters and the exact beta-integral rank polynomial. The first test retains the nonzero two-null quadratic contribution. Success still requires an explicit coefficient cancellation; merely naming its sum a lemma is excluded.
- `plan_two_sided_null_noise_folded_completion_20261104`: makes no diagonal SDP majorant and no optimization over an arbitrary correlation matrix. Every rectangle probability and every forest edge uses its actual generating covariance; the common-gate family is a mandatory test rather than a witness assumed to have disappeared. The finite cumulant table retains loop signs instead of taking an absolute matrix norm.
- `plan_two_sided_fixed_label_blocks_20261104`: abandons the whitened nuclear support function and the unresolved cross-score negative-part/all-null/sharp-trace chain. The new proposed tool is finite forest remainder closure plus coefficient charging directly for largest-rank cells. It does not try another Gaussian path to prove Pr28, and it uses no empirical or population tangency transfer. Its own finite closure and sharp packing gates remain unproved and must fail explicitly if obstructed.

## Progress

Earlier partial execution, 2026-11-04. Steps 1 and 2 are established below for every finite dimension. Step 3 has only the explicitly stated singleton-anchor cancellation below; its interval charging construction is unfinished. Steps 3--5 remain unchecked. The continuation recorded under Failure proves that the uniform certificate (C9)--(C10) is impossible, so the plan is now failed. The target asset is untouched. There is no proved uniform upper bound and no counterexample to the target.

The positive majorant established here applies to complete rectangle-cumulant blocks after all connected-tree terms belonging to a block have been summed. It does **not** separately dominate the absolute integral of a tree or of a term introduced by (C4). Its constants are uniform in the two regularization parameters for fixed dimension, but depend on dimension. No inference about the sharp, dimension-uniform certificate (C10) is made.

### Step 1: rank cells, beta coefficients, and independent nulls

Put $t_0=+\infty$. Apart from endpoints of probability zero, the observed-coordinate set for bin $b\leq N$ is
$$
S_b=(-t_{b-1},-t_b]\cup[t_b,t_{b-1}),
\qquad S_{N+1}=(-U,U).
$$
Endpoint conventions can be chosen to partition the line; none of the Gaussian integrals below depends on those choices. Let $n_k=\#\{i:b_i=k\}$, $c_0=0$, $c_k=c_{k-1}+n_k$, and $r_0=0$. The complete recursion is
$$
r_k=\begin{cases}k,&c_k\geq k,\\r_{k-1},&c_k<k,\end{cases}
\qquad k=1,\ldots,N.
$$
Then $r(b)=r_N$. In particular a failed constraint does not terminate the recursion: a larger rank may qualify after a hole. If $r>0$, then $c_r=r$: otherwise, for $r<N$, $c_{r+1}\geq c_r\geq r+1$ contradicts maximality, and $c_N\leq N$ handles $r=N$. Thus the rejection count is exactly $r$, including ties. The finite-cell FDP is
$$
f(T)=\sum_b w(b)\prod_j\mathbf1_{S_{b_j}}(T_j),
\qquad w(b)=\frac{v(b)}{r(b)\vee1}.
\tag{Pr1}
$$
For $r>0$, $\int_0^1v x^{r-1}\,dx=v/r$, and for $r=0$ both coefficients are zero. This proves (C1) coefficient by coefficient, for arbitrary arrays $z$, rather than only after averaging them.

Here is the forced-zero identity used in the independent calculation. Fix all p-values except $p_i$ and let $R_i$ be the largest BH rank after setting $p_i=0$. Then $R_i\geq1$, and
$$
\frac{\mathbf1_{\{i\in\mathcal R_q\}}}{R_q\vee1}
=\frac{\mathbf1_{\{p_i\leq qR_i/N\}}}{R_i}.
\tag{Pr2}
$$
Indeed, if $p_i\leq qR_i/N$, the counts of the original and forced-zero arrays agree at every rank $k\geq R_i$, so the original largest rank is $R_i$. Conversely, if $i$ is rejected at rank $R$, zeroing it cannot lower the largest rank. If the new rank were strictly greater than $R$, the original $p_i\leq qR/N$ would already be below that larger threshold, so that rank would also qualify originally, a contradiction. This proves (Pr2) for arbitrary deterministic p-values with ties. If $i$ is uniform and independent of all remaining p-values, conditioning on them makes the expectation of the right side $q/N$. Summing over $i\in J$ gives $P_J(a)=q|J|/N$ at independent coordinates. The same argument permits arbitrary dependence among the remaining coordinates when only one null anchor is being considered.

For (C2), decompose $S_b-\theta_i$ into its at most two intervals $(\ell,u)$. The identity
$$
\frac{d}{dx}\{H_{n-1}(x)\varphi(x)\}=-H_n(x)\varphi(x)
$$
gives, for $n\geq1$,
$$
a_{i,b}^{(n)}=\sum_{(\ell,u)\subset S_b-\theta_i}
\{H_{n-1}(\ell)\varphi(\ell)-H_{n-1}(u)\varphi(u)\}.
\tag{Pr3}
$$
Terms at infinite endpoints are zero. For $n=0$ use $\sum\{\Phi(u)-\Phi(\ell)\}$. For a centered null, $S_b$ is even and $H_n\varphi$ is odd when $n$ is odd, proving the asserted parity only in this one-dimensional independent integral. Gaussian integration by parts also shows that (Pr3) is the limiting independent expectation of the $n$th derivative of a smoothed bin indicator.

### Step 2a: a finite FTC proof of the forest identity on PSD paths

Use a product Gaussian mollifier: $g_{b,\delta}=\mathbf1_{S_b}*\varphi_\delta$, with independent centered variance-$\delta^2$ noise in each coordinate, and replace each indicator in (Pr1) by $g_{b,\delta}$. This gives a bounded, smooth $f_\delta$, even in each observed coordinate. All its derivatives are bounded for fixed $\delta>0$. For $C=\Sigma_\eta$, every covariance used below is at least $\eta I$.

Here is a finite FTC construction that avoids extending a Gaussian law to an indefinite matrix. Let $F$ be an already selected forest whose edge parameters satisfy $t_1\geq\cdots\geq t_k$, and let $0\leq s\leq t_k$ (use upper parameter one for $F=\varnothing$). Keep the within-component entries equal to the minimum along the forest path, and set every between-component entry to $s$. Denote this matrix by $X_F(s)$, with diagonal one. If $P_{F,u}$ is the matrix of the partition into connected components of the edges of $F$ with parameter at least $u$, then
$$
X_F(s)=s\mathbf1\mathbf1^{\mathsf T}+\int_s^1P_{F,u}\,du.
\tag{Pr4}
$$
Every partition matrix is PSD, because its quadratic form is the sum of the squared sums within its blocks. Formula (Pr4) therefore proves the required PSD property, including $T^F=X_F(0)$. The Schur product with $C$ is PSD: for PSD Gram matrices this follows by taking tensor products of their Gram vectors. More precisely,
$$
C\circ X_F(s)=\eta I+(1-\eta)(\Sigma\circ X_F(s))\succeq\eta I.
\tag{Pr5}
$$
All these paths lie in a compact set of positive-definite matrices, so Gaussian expectations have smooth extensions to a neighborhood of that set inside the positive-definite cone. Gaussian density differentiation followed by two integrations by parts gives
$$
\partial_{x_{ij}}\mathbb E_{C\circ x}h
=C_{ij}\mathbb E_{C\circ x}\partial_i\partial_j h,
\qquad i<j.
\tag{Pr6}
$$
Here $x_{ij}$ changes both symmetric off-diagonal entries. The usual factor $1/2$ in covariance differentiation cancels their multiplicity. Smooth bounded derivatives of $h$ and the uniform positive lower eigenvalue justify these operations on the compact set.

Start with $F=\varnothing$, for which $X_F(1)=\mathbf1\mathbf1^{\mathsf T}$ and $X_F(0)=I$. FTC along $s\mapsto X_F(s)$ differentiates precisely the edges joining distinct current components. Each derivative selects one such edge $e$ at its integration parameter $s$; append $e$ with parameter $t_{k+1}=s$. At that value the interpolation matrices for $F$ and $F\cup\{e\}$ agree: above $u=s$ the new edge is absent from $P_{F,u}$, and the initial term in (Pr4) already sets all remaining cross entries to $s$. Apply FTC again, now to the remaining cross-component entries. Each new edge reduces the number of components by one, so this process ends after at most $N-1$ derivatives. The zero endpoints give the evaluations at $T^F$.

This yields a sum over ordered forests with ordered parameters $1\geq t_1\geq\cdots\geq t_k\geq0$. For a fixed unordered forest, the order simplices partition its parameter cube up to the measure-zero equality faces; the evaluation is the same minimum-along-path matrix in every ordering. Combining these simplices and using (Pr6) proves (C3) exactly. Every expectation in this construction has a positive-definite covariance. The identity uses only finitely many FTC steps, not an infinite Taylor or walk expansion.

### Step 2b: odd-null remainders do not vanish

Let $D_F=\prod_{ij\in F}\partial_i\partial_j$ and choose a null vertex $i$ of odd forest degree. The function $D_Ff_\delta$ is odd in coordinate $i$. With $D_s$ diagonal, equal to $s$ at $i$ and one elsewhere, put
$$
C_s=D_sCD_s+(1-s^2)e_ie_i^{\mathsf T}.
$$
It retains the diagonal and all entries except $C_{ik}$, which become $sC_{ik}$. It is PSD; if $C\succeq\eta I$, then $C_s\succeq\eta I$ for $0<\eta\leq1$. At $s=0$, the centered null is independent of the rest, so its odd integral is zero. Applying covariance differentiation and FTC gives exactly (C4). The factor $C_{ik}$ multiplies, rather than replaces, the original forest prefactor. At a forest evaluation covariance it vanishes for $k$ outside the forest component of $i$.

For the finite closure below one may apply (C4) once to a selected odd-null vertex in each relevant forest term and retain the resulting finite sum. No recursive termination assertion is used. Since this replacement is an equality and never joins distinct components, it is compatible with component grouping below, even when it creates a repeated edge or a cycle inside a component. An expectation under the coupled law at $s>0$ is never discarded by parity.

### Step 2c: connected-tree sums are exactly finite rectangle cumulants

Fix a bin vector and write
$$
p_{B,\delta}(b_B)=\mathbb E_{C_B}\prod_{j\in B}g_{b_j,\delta}(T_j).
$$
Apply the forest identity to this product. At a forest evaluation, different components are independent; both the derivative product and the parameter cube factor over those components. Define $L_{\{i\},\delta}=p_{\{i\},\delta}$ and, for $|B|\geq2$, define the complete connected sum
$$
L_{B,\delta}=\sum_{\tau\text{ spanning tree on }B}
\left(\prod_{ij\in\tau}C_{ij}\right)
\int_{[0,1]^\tau}\mathbb E_{C_B\circ T^\tau(t)}
\prod_{j\in B}g_{b_j,\delta}^{(\deg_\tau j)}(T_j)\,dt.
\tag{Pr7}
$$
Then factorization of the finite forest sum gives
$$
p_{B,\delta}=\sum_{\pi\in\mathcal P(B)}\prod_{A\in\pi}L_{A,\delta}.
\tag{Pr8}
$$
This identity determines $L_B$ recursively from proper subsets, with coefficient one on $L_B$.

For completeness, the finite inverse can be derived in the commutative algebra with variables $z_i$ satisfying $z_i^2=0$. Set $M(z)=1+\sum_{\varnothing\ne B}p_{B,\delta}\prod_{i\in B}z_i$. Its logarithm is a finite polynomial. The coefficient of $z_B$ in $\log M$ is
$$
\sum_{\pi\in\mathcal P(B)}(-1)^{|\pi|-1}(|\pi|-1)!
\prod_{A\in\pi}p_{A,\delta},
$$
because the term of logarithmic degree $k$ lists every $k$-block partition in $k!$ orders and has coefficient $(-1)^{k-1}/k$. Exponentiating the finite polynomial gives the inverse partition relation: the $k!$ block orders cancel the $1/k!$. Its uniqueness in (Pr8) proves
$$
L_{B,\delta}=\kappa_{B,\delta}.
\tag{Pr9}
$$
Thus the connected-tree expressions, including any once-substituted (C4) remainders, are closed by (C5), with no remaining unevaluated infinite expansion.

The complete coefficient table is as follows. Index each row by a bin vector $b$, an outer partition $\pi$, and a subpartition $\pi_B$ of each $B\in\pi$. Its probability atom and scalar coefficient are
$$
A_{b,\pi,(\pi_B)}=\prod_{B\in\pi}\prod_{A\in\pi_B}p_A(b_A),
\qquad
c_{b,\pi,(\pi_B)}=w(b)\prod_{B\in\pi}(-1)^{|\pi_B|-1}(|\pi_B|-1)!.
\tag{Pr10}
$$
The sum of $cA$ is $H$. This follows directly by inserting (C5) into the inverse partition relation and then into (Pr1); it also follows from (Pr7)--(Pr9), which reconciles the forest and rectangle tables. To retain the beta integral before summing, replace $w(b)$ by $v(b)x^{r(b)-1}$ for $r(b)>0$, zero otherwise, and integrate $x$ on $[0,1]$. These are explicit coefficients for every finite $N$, not an unnamed FDR kernel. No total variation is substituted for the signed table in an estimate of $H$.

### Step 2d: positive probability majorants and their precise limit scope

Taking the absolute value only after (Pr9) gives (C6). The mollified $p_{B,\delta}$ are actual bin probabilities for $T_B+\delta E_B$, with covariance $C_B+\delta^2I$ and independent standard Gaussian $E_B$. For each partition, the product of its block probabilities is a probability measure on the bin product space, so
$$
\sum_{b_B}\sum_{\pi\in\mathcal P(B)}(|\pi|-1)!\prod_{A\in\pi}p_{A,\delta}(b_A)
=M_{|B|},\qquad
M_m=\sum_{\pi\in\mathcal P([m])}(|\pi|-1)!<\infty.
\tag{Pr11}
$$
For products of cumulants use the products of these finite majorants. Each row atom in (Pr10) is likewise a probability measure in $b$, since its final blocks are disjoint. This supplies finite positive measure domination on the closed table, uniformly in $\eta,\delta$ for each fixed $N$. The constants $M_m$ grow with $m$; they are not a dimension-uniform cumulant estimate and give no coefficient in (C10).

For a singular endpoint use the coupling
$$
T_{\eta,\delta}=\theta+\sqrt{1-\eta}\,G+\sqrt\eta\,E+\delta E',
\qquad G\sim N(0,\Sigma),
$$
with independent standard Gaussian $E,E'$. For every fixed bin boundary, each endpoint coordinate has a continuous unit-variance marginal. The finite union of boundary events therefore has probability zero, irrespective of coincident or antipodal coordinates. Hence bin indicators converge almost surely as $\eta,\delta\to0$, and bounded convergence gives every $p_{B,\delta}\to p_B$. All finite cumulant atoms, majorants and table sums converge as well. In particular (Pr11) remains a finite bin-space measure bound at the singular endpoint.

This argument removes regularization **after component regrouping**. It neither asserts convergence of individual tree absolute integrals nor constructs a majorant for the absolute value of a (C4) integrand before regrouping. It also does not exchange a regularization limit with a supremum over dimensions. Such a supremum requires the additional uniform estimates in steps 4 and 5.

### Step 2e: required minimal models and preservation of genuine correlation terms

These tests concern the exact finite identities, not (C10).

- For $N=1$ the forest sum is empty, $\kappa_1=p_1$, and a centered null has $H=q$; if $J$ is empty then $H=0$. At independent coordinates all nonsingleton cumulants vanish: $M(z)=\prod_i(1+p_i z_i)$ has no mixed coefficient in $\log M$. This recovers the step 1 baseline.
- For $N=2$ all-null, put $A_s=\{p_1\leq s\}$ and $B_s=\{p_2\leq s\}$. The rejection event is $A_{q/2}\cup B_{q/2}\cup(A_q\cap B_q)$. Inclusion-exclusion cancels $\mathbb P(A_{q/2}\cap B_{q/2})$ and gives exactly
  $$
  H(\rho)=q+C_\rho(q,q)-2C_\rho(q/2,q).
  \tag{Pr12}
  $$
  Differentiating the bivariate normal density twice at $\rho=0$ gives $H_2(x)H_2(y)\varphi(x)\varphi(y)$. Its first derivative integrates to zero on the even tail sets. The CDF is even in $\rho$, and four density derivatives are dominated by an integrable Gaussian times a polynomial on every compact $|\rho|<1$. Finite Taylor expansion therefore gives
  $$
  C_\rho(s,t)=st+\frac{\rho^2}{2}I_2(s)I_2(t)+O(\rho^4),
  \quad I_2(s)=2a_s\varphi(a_s),
  $$
  proving (C8) with its generally nonzero quadratic term. Directly in (C3), the only nonempty forest contributes
  $$
  \rho\int_0^1\mathbb E_{\rho t}\partial_{12}f_\delta\,dt
  =\rho^2\int_0^1t\int_0^1\mathbb E_{\rho ts}\partial_{1122}f_\delta\,ds\,dt.
  \tag{Pr13}
  $$
  Thus (C4) retains the factor $\rho^2/2$ at independence; it does not set the forest term to zero. The limit as $\delta\downarrow0$ of the independent fourth derivative is the bin-table sum of $w(b)a_{1,b_1}^{(2)}a_{2,b_2}^{(2)}$, equal by (Pr12) to $I_2(q)[I_2(q)-2I_2(q/2)]$; convergence follows from independent Gaussian integration by parts and dominated convergence of the bounded mollified bin functions against $H_2(x)H_2(y)\varphi(x)\varphi(y)$.
- For $N=2$, $\theta=(0,\mu)$, $\mu\ne0$, and $G_q=\mathbb P(B_q)$, the deterministic FDP identity is
  $$
  f=\mathbf1_{A_{q/2}\cap B_q^c}+\tfrac12\mathbf1_{A_q\cap B_q}.
  $$
  Consequently $H=q/2-D(q/2,q)+D(q,q)/2$, where $D(s,t)=\mathbb P(A_s\cap B_t)$. At independence this is $q/2-(q/2)G_q+(q/2)G_q=q/2$. In the two-variable cumulant table the correction is exactly $-\kappa(A_{q/2},B_q)+\kappa(A_q,B_q)/2$. This uses the actual alternative law and applies at every allowed correlation, including the endpoint limits.
- For $N=3$, $(\rho_{12},\rho_{23},\rho_{13})=(1/3,1/3,-1/3)$ has eigenvalues $1/3,4/3,4/3$, so it is positive definite. For every bin vector the table specializes to
  $$
  \kappa_{123}=p_{123}-p_{12}p_3-p_{13}p_2-p_{23}p_1+2p_1p_2p_3,
  $$
  whose inverse is $p_{123}=\kappa_{123}+\kappa_{12}p_3+\kappa_{13}p_2+\kappa_{23}p_1+p_1p_2p_3$. No sign restriction is introduced. More explicitly, the coefficient of $\rho_{12}\rho_{23}\rho_{13}$ in a centered rectangular tail probability at independence is $\prod_i a_{i,b_i}^{(2)}$. Each of the three trees contributes one third: for the tree $12,23$, the missing correlation is $\rho_{13}\min(t_{12},t_{23})$ and $\int_{[0,1]^2}\min(s,t)\,ds\,dt=1/3$. Thus the product $-1/27$ at the stated matrix is retained with its sign; individual correlations do not occur only to even powers.
- For identical and antipodal singular coordinates take $T_i=\theta_i+\epsilon_i Z$, $\epsilon_i\in\{-1,1\}$. Every $p_B$ is the one-dimensional Gaussian measure of the finite intersection $\bigcap_{i\in B}\{z:\theta_i+\epsilon_i z\in S_{b_i}\}$. This is an exact, finite interval formula for every table atom. In the centered all-null case all p-values coincide: $p_B(b_B)$ equals the common marginal bin probability when all $b_i$ in $B$ agree and is zero otherwise. The actual largest rank is $N$ for common $p\leq q$ and zero otherwise, so the table reconstructs $H=q$. This verifies the singular/tie case without a derivative limit at a singular density.
- The centered regularized simplex is $\Sigma=(1+\alpha/(N-1))I-\alpha\mathbf1\mathbf1^{\mathsf T}/(N-1)$ for $N\geq2$ and $0\leq\alpha\leq1$. Its eigenvalues are $1-\alpha$ and $1+\alpha/(N-1)$, the latter with multiplicity $N-1$. Hence all forest paths above are admissible for $\alpha<1$, and the probability-table limit proves the exact identities at $\alpha=1$. This is an identity check for the entire family, with no claimed simplex FDR estimate.
- In the common-gate family, $T_i=\theta_i+\sqrt\rho W+\sqrt{1-\rho}Z_i$ with independent standard normals and $0\leq\rho<1$, the exact atom formula is
  $$
  p_B(b_B)=\int_{\mathbb R}\varphi(w)\prod_{i\in B}
  \mathbb P\{\theta_i+\sqrt\rho w+\sqrt{1-\rho}Z_i\in S_{b_i}\}\,dw.
  \tag{Pr14}
  $$
  Each inner factor is a finite sum of Gaussian CDF differences at the bin endpoints, so this directly specifies the signed finite table. It includes the recorded $N=2n$ weak common gate with $n$ centered nulls, $n$ means $\alpha/z_N$, $\cosh\alpha=2/q-1$, $z_N=\sqrt{0.02\log N}$, and $\rho=\lambda/z_N^2$ whenever $\rho<1$. No population-root limit, sensitivity bound, or covariance optimization is used. This verifies applicability of the identities to the family, rather than establishing a uniform budget for it.

The short local deterministic diagnostics used only Python's standard library. For each $1\leq N\leq4$ they enumerated every $b\in\{1,\ldots,N+1\}^N$ and $J\subseteq[N]$, totaling 10,552 bin/label cases, and checked the rank recursion, $c_r=r$, (Pr2), and the rational beta coefficient in (C1). They also evaluated 30 independent-product polynomials exactly with rational arithmetic: $q=1/20$, null bin masses $q/N,\ldots,q/N,1-q$, and alternative bin masses proportional to $(i+1)(k+2)+1$ for zero-based coordinate $i$ and bin $k$. Each equaled $q|J|/N$. A separate finite partition enumeration verified the coefficients of cumulant inversion for $N\leq4$. These are supplemental diagnostics; the general proofs above do not rely on enumeration. Finally, direct evaluation with the standard normal quantile and density gave $I_2(.05)=0.22910046378359775$, $I_2(.025)=0.14505641275406686$, and the coefficient in (C8) $-0.00698898018381191$. No large local experiment was performed.

An independent read-only cold check of the FTC/component-factorization/majorant chain found no mathematical defect and confirmed the exact limitation of (Pr11): complete connected sums only, fixed dimension, no domination of individual derivative terms. The minimal-model checks and coefficient table are written above rather than delegated to that verdict.

### Established fragment of step 3: exact null-anchor cancellation

There is a useful additional finite cancellation before any interval charging. Define
$$
w_i(b)=\frac{\mathbf1_{\{b_i\leq r(b)\}}}{r(b)\vee1},\qquad i\in J.
$$
For a fixed $i$, sum in the cumulant table only over outer partitions having $\{i\}$ as a singleton. The inverse relation on $[N]\setminus\{i\}$ reduces that sum to the expectation of the $i$th FDP contribution under $p_i(b_i)p_{-i}(b_{-i})$. This is the actual marginal law of all remaining coordinates made independent of the uniform null $i$. Formula (Pr2) makes the sum exactly $q/N$, with no independence assumption among those remaining coordinates. Subtracting these singleton sums gives the explicit identity
$$
H-q|J|/N=
\sum_{i\in J}\sum_b w_i(b)
\sum_{\substack{\pi\in\mathcal P([N])\\|B_\pi(i)|\geq2}}
\prod_{B\in\pi}\kappa_B(b_B),
\tag{Pr15}
$$
where $B_\pi(i)$ is the block containing $i$. Expanding each cumulant in (Pr15) gives (Pr10) with $w$ replaced by $w_i$ and only these outer partitions retained. The beta-integrand coefficient is $\mathbf1_{\{b_i\leq r(b)\}}x^{r(b)-1}$ for $r(b)>0$. Thus every retained row has an explicit null anchor and a nonsingleton connected block containing that anchor. Cancellation uses forced-zero BH, not diagram parity.

At this earlier stopping point no standardized pivot/interval allocation from (Pr15) to the functions $K_i(y)$ and $E_i$ in (C9), half-sign packing, or exterior estimate in (C10) had been constructed. Formula (Pr11) could not replace those obligations. The continuation below now rules out their simultaneous dimension-uniform form, while retaining all the finite identities above.

## Failure

Continuation, 2026-11-04. Step 4 cannot be completed: the joint requirements (C9)--(C10), and hence their explicitly stated consequence (C11), impose a false bound proportional to the null fraction $|J|/N$. The following exact finite Gaussian family proves the obstruction. It does not refute the target, which has no null-fraction factor. No change to the target statement or its research status is made.

### Frozen family and finite signed table

Write $Q=\overline\Phi$. For each real $U\geq1$, set
$$
q=2Q(U),\qquad N=\left\lceil\frac{q}{Q(2U)}\right\rceil,
\qquad t_j=Q^{-1}\left(\frac{qj}{2N}\right),\quad 1\leq j\leq N.
\tag{F1}
$$
Thus $t_N=U$, $N\geq2$, and $2NQ(2U)/q\geq2$. Let $Z$ be standard normal and choose the admissible rank-one model
$$
T_1=Z,\qquad T_{j+1}=Z-2t_j\quad(1\leq j\leq N-1),
\qquad \Sigma=\mathbf1\mathbf1^{\mathsf T}.
\tag{F2}
$$
Its true-null set is exactly $J=\{1\}$, since every $t_j>0$. This freezes all means and the actual covariance for each $U$; no covariance is varied independently of its generating law.

The finite anchored table being tested is exactly (Pr15), with anchor $1$. In particular, for every nonempty coordinate set $A$ and bin vector $b_A$ its rectangle atom is explicitly
$$
p_A(b_A)=\int_{\mathbb R}\varphi(z)
 \prod_{\ell\in A}\mathbf1_{S_{b_\ell}}(z+\theta_\ell)\,dz,
\qquad
\theta_1=0,\quad\theta_{j+1}=-2t_j.
\tag{F3}
$$
Each integral is over a finite intersection of the already specified affine bin intervals. For every outer partition $\pi$ with $|B_\pi(1)|\geq2$ and subpartitions $\pi_B$, retain the row atom and coefficient
$$
\prod_{B\in\pi}\prod_{A\in\pi_B}p_A(b_A),
\qquad
w_1(b)\prod_{B\in\pi}(-1)^{|\pi_B|-1}(|\pi_B|-1)!.
\tag{F4}
$$
Equations (F1)--(F4) specify the full finite coefficient table for every member of the family, with ordinary largest-rank BH, including $R=0$ and ties. All its remaining signed coefficients and covariance blocks are the same as in (Pr10) and (Pr15). No absolute-value majorant or unlisted error term is introduced.

For clarity, collecting this table by its final probability partition leaves precisely
$$
\sum_{\substack{\pi\in\mathcal P([N])\\|B_\pi(1)|\geq2}}
 \prod_{B\in\pi}\kappa_B(b_B)
=p_{[N]}(b)-p_{\{1\}}(b_1)p_{[N]\setminus\{1\}}(b_{-1}).
\tag{F5}
$$
Indeed the complete outer-partition sum is $p_{[N]}$ by the finite inverse relation; the sum whose anchor block is a singleton is $p_{\{1\}}p_{[N]\setminus\{1\}}$ by the same relation on the other coordinates. Thus the exact forest/cumulant cancellation supplies a difference of these two actual laws; it supplies no additional positivity that could alter the value of (F4).

### Exact largest-rank calculation on a positive Gaussian strip

Fix $Z=s\in[U,2U]$ and put
$$
a=a(s)=\frac{2NQ(s)}q\in[2,N].
$$
For real $x\in(0,N]$ define $t(x)=Q^{-1}(qx/(2N))$ and
$$
A_s(x)=\frac{2N}q Q\left(\frac{s+t(x)}2\right).
\tag{F6}
$$
In particular $t(a)=s$ and $A_s(a)=a$.

For every alternative $j+1$, $s-2t_j\leq0$ throughout this strip, whereas every BH statistic threshold $t_k$ is at least $U>0$. Therefore its positive tail cannot reenter a two-sided rejection set here, and its exact rejection condition at candidate rank $k$ is
$$
|s-2t_j|\geq t_k
\quad\Longleftrightarrow\quad
t_j\geq\frac{s+t_k}2
\quad\Longleftrightarrow\quad
j\leq A_s(k).
$$
The null passes that threshold precisely when $s\geq t_k$, equivalently $k\geq a$. Consequently the exact count at rank $k$ is
$$
n_k(s)=\min\{N-1,\lfloor A_s(k)\rfloor\}
       +\mathbf1_{\{k\geq a\}}.
\tag{F7}
$$
The non-strict inequalities in the BH definition give the same formula at equality endpoints.

Differentiation of the normal quantile, on $x\geq a$, gives
$$
A_s'(x)=
\frac{\varphi((s+t(x))/2)}{2\varphi(t(x))}
\leq\frac12.
\tag{F8}
$$
Here $s\geq t(x)\geq U>0$, so $(s+t(x))/2\geq t(x)$ and the normal density is decreasing on these arguments. The function $A_s$ is increasing on its whole domain. Let $k_0=\lceil a\rceil\leq N$. Then $A_s(k_0)\geq a$ implies $\lfloor A_s(k_0)\rfloor\geq k_0-1$; truncation at $N-1$ preserves that inequality. The null passes at $k_0$, so (F7) gives $n_{k_0}(s)\geq k_0$: this rank actually qualifies.

For any qualifying rank $k\geq a$, integrating (F8) from $a$ to $k$ gives
$$
k\leq n_k(s)\leq1+A_s(k)
\leq1+a+\frac{k-a}{2},
\qquad\text{hence } k\leq a+2.
$$
A qualifying rank below $a$ also satisfies that upper bound. Taking the largest qualifying rank, rather than stopping at a first crossing, proves
$$
\lceil a(s)\rceil\leq R(s)\leq a(s)+2.
\tag{F9}
$$
Moreover $R(s)\geq a(s)$ means the null is actually rejected. Thus there is no substitution of a forced-zero rank or of a population root in this calculation.

### The coefficient budget is too small by an order in $U$

There is only one null. Nonnegativity of its FDP outside the strip and (F9) give
$$
\begin{aligned}
H
&\geq\int_U^{2U}\frac{\varphi(s)}{a(s)+2}\,ds\\
&\geq\frac{q}{4N}\int_U^{2U}\frac{\varphi(s)}{Q(s)}\,ds\\
&=\frac{q}{4N}\log\frac{Q(U)}{Q(2U)}.
\end{aligned}
\tag{F10}
$$
The second line uses $a(s)\geq2$, which was enforced by the finite choice of $N$. No asymptotic approximation or numerical experiment is used. The elementary identity $\varphi(v+U)=e^{-Uv-U^2/2}\varphi(v)$ yields
$$
Q(2U)=\int_U^\infty\varphi(v+U)\,dv
\leq e^{-3U^2/2}Q(U).
$$
Hence
$$
\frac Nq H\geq\frac{3U^2}{8},
\qquad
\frac Nq\sum_b w_1(b)
 \sum_{\substack{\pi\in\mathcal P([N])\\|B_\pi(1)|\geq2}}
 \prod_{B\in\pi}\kappa_B(b_B)
=\frac Nq H-1\geq\frac{3U^2}{8}-1.
\tag{F11}
$$
This is a lower bound on the specific signed table (F4), after the exactly proved singleton subtraction, not on its total variation.

For the same $J=\{1\}$, any table satisfying (C9) together with both inequalities of (C10) would instead imply
$$
\frac Nq H-1=\int_0^U K_1(y)\,dy+E_1
\leq\frac{U}{2\sqrt{2\pi}}+C(1+\log U).
\tag{F12}
$$
The right side is $O(U+\log U)$ for every fixed numerical $C$, whereas the lower bound in (F11) is quadratic in $U$. For any proposed $C$ and any universal lower cutoff $U_0$, take integer $U\geq U_0$ sufficiently large in (F1), so $q\downarrow0$: (F11) and (F12) contradict one another. A cutoff depending on $N$ or the model would not give the uniform quantifiers required by this plan. This rules out the requested joint coefficient certificate for **every** possible exact allocation in (C9), even before an interval allocation is chosen. Moving charges between $K_1$ and $E_1$ cannot repair it while keeping both bounds of (C10). The necessary failure is already present in (C11)'s null-fraction strengthening; it is not a failure of the finite closure gate in step 2.

The obstruction also survives positive-definite approximation. For each fixed $U$ and its finite $N$, replace $\Sigma$ by $(1-\eta)\mathbf1\mathbf1^{\mathsf T}+\eta I$. The coupling and zero-probability bin-boundary argument in step 2d imply convergence of the actual BH FDP expectation as $\eta\downarrow0$. Once $U$ makes the gap between (F11) and (F12) strictly positive for a proposed $C$, a sufficiently small positive $\eta$ preserves the violation. Thus no estimate uniform in the covariance regularization can rescue (C10).

An independent read-only check verified (F7)--(F12), including the floor/ceiling endpoints, the largest-rank upper bound, actual null rejection, the constant $3/8$, and the precise implication from (C9)--(C10) to (F12). It also checked the order of the positive-definite approximation: first fix $U$ giving a strict gap, then its finite $N$, and only then let $\eta\downarrow0$. All calculations here are finite and analytic; no substantial local computation was run.

### Scope and what would be needed

This family does not refute the target. With a single uniform null, a false rejection requires $p_1\leq qR/N\leq q$, so $H\leq q$. In particular this family's ratio $H/[q\sqrt{\log(1/q)}]$ tends to zero. What fails is the stronger assertion that the FDR bound can always be multiplied by $|J|/N$ with only an $O(U)$ normalized cost per null.

The completed finite rank, forest and cumulant identities above remain valid. A subsequent plan would need a different global allocation whose total budget is not forced to scale linearly as $|J|/N$, and would still need to prove the unrestricted upper bound with its proposed constant. Neither such an allocation nor that upper bound is proved here. The current plan is failed, the target asset is unchanged, and no falsification or approval of that asset is recorded.
