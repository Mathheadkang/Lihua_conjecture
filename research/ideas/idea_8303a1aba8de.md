---
type: idea
title: All-score determinant FDP cover and exact cofactor Gaussian-flow resummation
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - determinantal-cover
  - cofactor-resummation
  - signed-Gaussian-flow
  - native-plan-first-tests
---

## Provenance and purpose

The root agent proposed placing all N physical score directions, including alternatives, in the global determinant cover rather than only true-null directions. I derived the cofactor Gaussian-flow identities below. They are agent draft calculations and have not undergone native independent verification. The aim is to cancel inverse basis factors before absolute values and identify the exact physical rank kernel that remains. No main theorem, dependency or loop transition is asserted.

## All-score Parseval cover and physical label resource

Let all physical centered scores be X_i=v_i dot G with unit v_i; their means and original null labels are unchanged. Put p=||Sigma||op in [1,N] and physical c_i=1/p. Complete sum_i c_i v_i v_i^T<=I by auxiliary columns to a Parseval matrix F. These auxiliary directions never participate in BH. A basis B has probability alpha_B=det(F_B)^2. For the same actual full BH sample, define
$$
H_B=\sum_{i\in B\cap I_0}\frac{1_{\{i\in\mathcal R_q\}}}{c_i(R_q\vee1)}.
$$
The exact marginal P(i in B)=c_i gives E_B H_B=FDP sample by sample. True-to-false basis exchanges can now have nonzero payoff even if the true-null Gram is I. No physical coordinate is removed or reclassified.

For K_B=|B intersect I0| and W_B=p K_B,
$$
E W_B=m,\qquad Var(W_B)\le pm\le Nm,
$$
so
$$
E(W_B/N)^2\le(m/N)^2+m/N\le2.
$$
Also E[W_B log(W_B/m)]/N<=p/N<=1, using log x<=x-1 and the variance bound. W_B may exceed N and H_B may exceed one; that is explicitly retained. Uniform physical replication multiplies p and the inverse physical weights by the replication factor, while R also multiplies; the same folded-basis coupling gives exact replication invariance.

## Smooth frame, basis freezing flow and its signed Gaussian source

On a smooth interval of a Parseval frame path F(s), let
$$
A=F'F^{\mathsf T}=-A^{\mathsf T}.
$$
For a nonzero determinant basis write
$$
L_B=(F_B^{\mathsf T})^{-1}F_B'^{\mathsf T}.
$$
The linear ambient flow b_B(G)=-L_B G freezes its weighted basis coordinates:
$$
\frac d{ds}[F_B^{\mathsf T}G]=0
$$
when G follows this flow. Determinant weights satisfy alpha'_B/alpha_B=2 tr L_B. Therefore for the Gaussian density phi_d(G),
$$
\partial_s(\alpha_B\phi_d)+
div_G(\alpha_B\phi_d\,b_B)
=\alpha_B\phi_d\{
tr L_B+G^{\mathsf T}L_BG\}. \tag{GS}
$$
The source is signed. It must not be bounded by an inverse-basis norm before averaging.

For any test observable H_B(s,G), integrating by parts gives the exact finite generator identity
$$
\frac d{ds}E_{\!B,G}H_B
=E_{\!B,G}\left[
\partial_s H_B+b_B\cdot\nabla_G H_B+
H_B\{trL_B+G^{\mathsf T}L_BG\}
\right].
$$
For the BH observable, derivatives are finite-interface measures after positive-definite regularization. Original physical rank and nonstrict endpoint conventions remain unchanged. Changing c_i also creates explicit derivatives of 1/c_i and a weighted-coordinate versus physical-coordinate correction; neither is omitted.

The plus trace in (GS) is essential. The exact Stein identity for b_B=-L_B G is E[b_B dot grad H_B]=E[H_B{tr L_B-G^T L_B G}]. Thus adding b_B dot grad H_B to the generator requires the compensating source G^T L_B G minus tr L_B; changing determinant weights adds 2 tr L_B, producing the displayed total G^T L_B G plus tr L_B. It is not a standalone plus-sign Stein formula.

Also H_B remains a function of every physical score through the actual R. Along the basis-freezing flow, an unselected column j has weighted-score residual velocity
$$
(f_j'-L_B^{\mathsf T}f_j)\cdot G.
$$
It vanishes for j in B but generally not otherwise. For the physical centered score X_j=f_j\cdot G/\sqrt{c_j}, the full residual is
$$
\frac{(f_j'-L_B^{\mathsf T}f_j)\cdot G}{\sqrt{c_j}}
-\frac{c_j'}{2c_j}X_j.
$$
These velocities move the original rank denominator even for physical tests absent from B, and are retained inside the generator's derivatives. Freezing basis coordinates is not a license to delete the other physical scores or replace their Gaussian conditional law.

## Exact cofactor first moment

Let f_i be column i of F and c_i=||f_i||^2. If dual_{B,j}=(F_B^T)^{-1}e_j, with the basis-position convention, then
$$
\sum_{B\ni i}\alpha_B\,dual_{B,i}=f_i,
$$
and for j different from i,
$$
\sum_{B\ni i,j}\alpha_B\,dual_{B,j}
=c_i f_j-\langle f_i,f_j\rangle f_i. \tag{CF}
$$
One direct derivation differentiates, with columns treated independently, the unnormalized inclusion polynomial
$$
\sum_{B\ni i}\det(F_B)^2
=\det(M)\,f_i^{\mathsf T}M^{-1}f_i,\qquad M=FF^{\mathsf T},
$$
then evaluates at M=I. No division by a possibly tiny basis determinant survives in (CF).

Put g_i=f_i'-A f_i. Summing the cofactor identities against f_j'^T gives
$$
\boxed{\quad
E_B[1_{\{i\in B\}}L_B]
=-c_i A+f_i g_i^{\mathsf T}.
\quad} \tag{LM}
$$
Indeed L_B=sum_{j in B}dual_{B,j} f_j'^T, F F'^T=-A, and sum_j <f_i,f_j> f_j'=A f_i. In particular E_B L_B=-A, so its trace and its quadratic Gaussian form vanish after the unweighted basis average. This checks the total probability source in (GS).

## Pair the source with actual selected true-null labels

For a fixed Gaussian sample set
$$
h_i(G)=1_{\{i\in I_0,\ i\in\mathcal R_q\}}/(R_q\vee1),
\qquad H_B=\sum_i 1_{\{i\in B\}}h_i/c_i.
$$
Using (LM) and the skew-symmetry of A,
$$
E_B[H_B\{tr L_B+G^{\mathsf T}L_BG\}]
$$
$$
=\sum_{i\in I_0}\frac{h_i(G)}{c_i}
\left\{
f_i\cdot g_i+(G\cdot f_i)(G\cdot g_i)
\right\}. \tag{RS}
$$
Thus inverse basis factors cancel algebraically before taking an absolute value. The remaining quantity is a sum of explicit rank-one signed score kernels with the original largest-rank indicators. This is not a uniform inverse-conditional-variance claim.

The h_i do depend on G. Replacing them by constants, or applying the unweighted source cancellation to the weighted selected-label source, would be wrong. Similarly (RS) alone does not prove a small bound; estimating its terms separately can merely recover the old unsigned Gaussian trace loss.

## Match to the existing finite mechanisms

The antisymmetric basis-exchange identity in idea_e145c41fb8f7 and (GS) are two exact ways of accounting for the cover's motion. They must not both be counted as independent positive errors. Current terms and explicit importance-weight derivatives cancel pathwise when physical scores are fixed. For genuinely moving scores, the generator still has the real BH interface terms, the source (RS), and the weighted-to-physical coordinate corrections.

The determinant-weighted tail kernels in idea_cb8b42129f28 can be applied before this cofactor averaging, or used to bound carefully matched residuals after it. Averaging everything immediately via (RS) removes the determinant gain; taking absolute values first can instead lose dimensions. Finding a signed grouping that avoids both losses is the next actual mathematical task.

The full-score cover addresses the true-only cover's constant-law limitation under independent nulls with correlated alternatives, but does not by itself establish a physical-rank scale budget. These are concrete finite identities and resources for a proof attempt, not a declaration that the missing averaged signed kernel already satisfies the main bound.

## Canonical horizontal cover with dimension-free determinant action

The root subsequently proposed the following constant-weight variant, which I checked directly. It avoids differentiating a largest eigenvalue. On the exact straight-line covariance path Gamma_s=(1-s)I+s Sigma, put c=1/(2N), L_s=Gamma_s^{1/2}, E_s=(I-c Gamma_s)^{1/2}, and
$$
F_s=[\sqrt c\,L_s,\ E_s].
$$
The first N columns are the physical score vectors with constant importance 1/c=2N; the last N are auxiliary columns only. This matrix is Parseval. Its factors commute because they are scalar functions of Sigma, and
$$
F_s'F_s^T=cL_s'L_s+E_s'E_s
=\tfrac c2(\Sigma-I)-\tfrac c2(\Sigma-I)=0.
$$
Thus the row-gauge A vanishes exactly. The skew generator Omega=F^T F'-F'^T F has zero physical-physical and extra-extra blocks, while
$$
\Omega_{\rm physical,extra}
=-\frac{\sqrt c}{2}(\Sigma-I)L_s^{-1}E_s^{-1}.
$$
All its basis-exchange currents connect a physical column to an auxiliary column. A physical alternative still has zero null label, but its geometry remains present.

The total squared frame speed is
$$
\|F_s'\|_{\rm HS}^2
=\frac c4\operatorname{tr}\frac{(\Sigma-I)^2}{\Gamma_s}
+\frac{c^2}{4}\operatorname{tr}\frac{(\Sigma-I)^2}{I-c\Gamma_s}.
$$
The scalar spectral inequality (lambda-1)^2/(1-s+s lambda)<=lambda/s+1/(1-s), trace Sigma=N, and I-c Gamma_s>=I/2 give
$$
\|F_s'\|_{\rm HS}^2
\le\frac1{8s(1-s)}+\frac18.
$$
For the second term use tr(Sigma-I)^2=tr Sigma^2-N<=N^2. Consequently integral_0^1 ||F_s'||_HS ds is bounded by a universal constant, including singular final Sigma.

For determinant amplitudes d_B=det(F_B), horizontality gives
$$
\sum_B(d_B')^2=\|F_s'\|_{\rm HS}^2.
$$
To check this at a fixed time, apply an orthogonal column change sending F to [I,0]. Horizontality then sends F' to [0,C]. The derivative of the unit exterior product has one term for each row-to-extra replacement, and their squared coefficients sum to ||C||_HS^2. Orthogonal changes preserve the exterior-product norm. Thus the determinant cover has dimension-free Hellinger action (and four times this squared speed as its a.e. Fisher action), without an inverse-basis estimate.

For this variant W_B=2N K_true, EW_B=m and Var W_B<=2Nm, so E(W_B/N)^2<=pi_0^2+2pi_0<=3. It remains a full physical FDP cover, including replication invariance for a fixed model when the duplicated physical columns are coupled at the same latent embedding.

This action bound does not imply a generic pathwise Lipschitz estimate for FDR in frame Hilbert-Schmidt speed. H_B can be much larger than one; its squared norm can grow with N on small-rank states. The root's one-pivot/large-coherent-null-block cusp shows that an unrestricted Gaussian RMS-speed payment would be false. The actual straight-line noise smoothing, original rank masks, and signed source/cofactor terms must be used. No such missing payment is inferred from the action bound alone.

## Exact mixed-label two-test source/residual check

This checks the new cofactor-flow decomposition against the actual N=2 BH formula; it is not claimed as a new two-test BH theorem. Let X be the centered null and mu+Y the alternative, with Corr(X,Y)=rho, sigma^2=1-rho^2, a=u(q/2), b=u(q), and c=b-mu. The actual null FDP is
$$
h_0(X,Y)=1_{\{X\ge a\}}+
K(X)1_{\{Y\ge c\}},\qquad
K(X)=\tfrac12 1_{\{X\ge b\}}-1_{\{X\ge a\}}.
$$
For symmetric covariance motion with rho'=1, the physical velocities are
$$
W_X=\frac{Y-\rho X}{2\sigma^2},\qquad
W_Y=\frac{X-\rho Y}{2\sigma^2}.
$$
The cofactor own-null freezing residual at the alternative face is
$$
r_Y=W_Y-\rho W_X
=\frac{(1+\rho^2)X-2\rho Y}{2\sigma^2},
$$
which is not orthogonal to Y. Its face contribution is phi(c)E[r_Y K(X)|Y=c]. The remaining Gaussian source is E[h_0 X W_X]. Integrating Y conditional on X gives exactly
$$
E[h_0 XW_X]=\tfrac12\phi(c)E[XK(X)\mid Y=c].
$$
Indeed E[(Y-rho X)1{Y>=c}|X=x]=sigma phi((c-rho x)/sigma); the other term of h_0 is independent of Y after conditioning X and contributes zero.

Only after adding this source does the position-correlated term cancel:
$$
FDR'_\rho
=\phi(c)E\left[
\frac{X-\rho c}{\sigma^2}K(X)\mid Y=c\right]
=\frac{\phi(c)}\sigma E[DK(X)\mid Y=c],
$$
where D=(X-rho Y)/sigma is standard and independent of Y. Integrating the two tail indicators recovers the direct check
$$
FDR'_\rho=\tfrac12\phi_2(b,c;\rho)-\phi_2(a,c;\rho).
$$
The centered determinant-scaled scalar estimate in idea_1ed1245e80c7 can now be applied to each tail with its own Mills center; the resulting signed Mills drift is still retained. Applying that estimate directly to r_Y before adding the source would have violated its orthogonality hypothesis.

For N>2, h_i depends on all other physical scores through the actual rank. The analogous conditional integration creates further physical-interface terms; this two-test calculation does not prove they cancel pairwise or justify deleting a background residual. An executable continuation must derive that full signed matching, with explicit coefficients, before estimating its determinant-weighted kernels.
