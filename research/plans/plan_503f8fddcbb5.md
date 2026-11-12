---
type: plan
title: >-
  Universal one-sided order through global-shift records and entrant Stein
  allocation
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_98e66d75379d
  - idea_8038676052a3
  - idea_12ea1e9582c2
tags: []
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement: there exist finite universal C_1>0 and q_{0,1} in (0,1) such that F_1(q)<=C_1 q sqrt(log(1/q)) for every 0<q<=q_{0,1}, for all finite N, all means, all unit-diagonal PSD covariances including singular matrices, and all sufficiently small q, with finite universal constants. Ordinary BH uses its largest qualifying rank and non-strict inequalities. The original true-null labels I0={j:theta_j<=0} remain fixed. Every parameter may vary with q; no rank, entropy, dimension, or smallest-eigenvalue factor is permitted.

The new trial shifts ALL statistics by the same amount, rather than only original true nulls. Its fixed ordering gives a translation-invariant record partition. A concrete allocation to weak true entrants then gives Gaussian Stein bulk and face coefficients involving the actual PSD distances 1-Sigma_jk. This is a trial, not a proved global budget. The two source ideas are draft proposals; reprove every partial lemma inline. Planning-time library searches for Gaussian rank summation by parts and Gaussian Stein record ranks returned no applicable result. No extra theorem is used as a black box. This native conversion restores the verbatim candidate archived in idea_98e66d75379d (original payload SHA256 3fd8be536acea4b306e7d711ebac70dd0e29b0dece65d43d2383e33c714974ce); the archive itself is preserved.

## Plan

1. [ ] **Fixed-label endpoint and nested record path.** Write S=barPhi, U=S^{-1}(q)>=1, u_r=S^{-1}(qr/N), Z=T(0), and T(t)=Z-t*1_N for 0<=t<=1. Count only I0 throughout, even if some original alternatives acquire negative shifted means. Reprove the Mills/marginal bound in idea_12ea1e9582c2: any fixed counted subset with marginal means <=-1 contributes at most c_- q, c_-=3 exp(-3/2), regardless of all other means. Thus FDR_I0(1)<=c_-q. The same bound later controls flow allocated to entrants with original theta_j<=-1. Do not infer mean monotonicity.

   For positive-definite Sigma, sort Z_{pi(1)}>...>Z_{pi(N)} and set a_r=Z_{pi(r)}-u_r. Prove R(t)=max({0} union {r:a_r>=t}). An actual backward entry at r occurs exactly when a_r>max_{k>r}a_k; its predecessor is s=max({0} union {k:a_k>a_r}). At such an entry s<r and the entering cohort is exactly pi(s+1),...,pi(r). Include the initial rank zero. Ties and simultaneous a_r contacts have probability zero in this positive-definite stage. Over the FULL translation path each coordinate enters exactly once; the interval [0,1] uses a subset of these cohorts.

2. [ ] **Exact positive flow, including false triggers and cascades.** Put V_r=sum_{k<=r}1{pi(k) in I0}, W_r=sum_{k<=r}1{-1<theta_{pi(k)}<=0}, and D_r=V_r/r for r>0, D_0=0. For a record jump s->r put m=V_r-V_s and A=D_r-D_s. Prove A=m/r-V_s(r-s)/(rs) when s>0, and A=m/r when s=0. If m=0, A_+=0. Otherwise give each newly entering original true null the share alpha=A_+/m<=1/r. Its weak part is

   $$
   c^w_{rs}=(W_r-W_s)\alpha
   =\frac{W_r-W_s}{r}\left[1-\frac{V_s(r-s)}{s(V_r-V_s)}\right]_+
   $$

   for s,m>0, and (W_r-W_s)/r for s=0. Retain this full bracket. The trigger pi(r) may be an alternative or a strongly negative true null. Establish the exact face/coarea identity or the equivalent pathwise finite-record identity, then integrate: FDR_I0(0)<=FDR_I0(1)+B_strong+B_weak. For a counted entrant j, self-consistency gives alpha<=q/[N S(Z_j)]1{S(Z_j)<=q}; hence B_strong<=c_-q. The remaining B_weak is the finite record sum of c^w_{rs}1{0<a_r<1}. No inactive grid levels are inserted.

3. [ ] **Translation-invariant cells and an explicit entrant potential.** Partition, up to boundaries, by the permutation pi and the strict ordering of all a_r. Each resulting polyhedral cell C is invariant under Z->Z+c*1_N. For each record in C retain its trigger i=pi(r), predecessor s, weak entrant set J_C, and constant alpha_C=A_+/m (zero when m=0). A cell can have several records: a summation over C below means one term for each of its records. At each term and weak entrant j put delta_ji=Z_j-Z_i>=0 and define

   $$
   b_{rj}(d)=\int_{u_r+d}^{u_r+d+1}\phi(y-\theta_j)\,dy,
   \qquad
   H_{rj}(x,d)=\frac{\displaystyle\int_{-\infty}^{x}
   \bigl(1_{[u_r+d,u_r+d+1]}(y)-b_{rj}(d)\bigr)
   \phi(y-\theta_j)\,dy}{\phi(x-\theta_j)}.
   $$

   Check the bounded Stein solution, limits, and piecewise derivatives explicitly. At fixed d,

   $$
   \partial_xH_{rj}-(x-\theta_j)H_{rj}
   =1_{[u_r+d,u_r+d+1]}(x)-b_{rj}(d).
   $$

   At (x,d)=(Z_j,delta_ji), this indicator is exactly 1{u_r<=Z_i<=u_r+1}. This allocates to a weak TRUE entrant, so no bound on the false trigger's mean is needed. Prove by direct Gaussian integration by parts, first with a cutoff and then with controlled limits,

   $$
   \mathbb E[1_C1_{\{u_r\le Z_i\le u_r+1\}}]
   =\mathbb E[1_C b_{rj}(\delta_{ji})]
   -(1-\Sigma_{ji})\mathbb E[1_C\partial_dH_{rj}(Z_j,\delta_{ji})]
   +\sum_k(1-\Sigma_{jk})\mathbb E[H_{rj}(Z_j,\delta_{ji})\partial_k1_C].
   \tag{ES}
   $$

   Here the boundary derivative is distributional. The sign follows from Sigma_jj=1 and sum_k partial_k1_C=0. Establish these facts rather than treating a moving band as fixed. Multiply (ES) by alpha_C and sum over records and j in J_C. The baseline B0 is at most q: b_{rj}(delta)<=S(u_r)=qr/N, alpha_C<=1/r, and for each Z every weak j belongs to exactly one full-path entry cohort. Consequently B_weak=B0+R with B0<=q. No conditional inverse variance appears.

4. [ ] **Finite prefix summation by parts and the first uniform gate.** Output the actual coefficients before estimating them. Set d_jk=1-Sigma_jk=||v_j-v_k||^2/2 using a unit-vector Gram representation of the ORIGINAL Sigma. On a geometric cell C sum its record terms to define the bulk coefficient

   $$
   K_C(z)=-\sum_{\text{records }(i,r,s)\text{ in }C}
   \sum_{j\in J_C}\alpha_C d_{ji}\partial_dH_{rj}(z_j,z_j-z_i).
   $$

   Also define G_Cj(z) as the sum of alpha_C H_{rj}(z_j,z_j-z_i) over the records of C for which j is a weak entrant, with zero contribution otherwise. For every shared facet F between cells C,D choose unit normal n from C to D. Pair BOTH sides and output

   $$
   L_F(z)=\sum_{j:\,-1<\theta_j\le0}\sum_k d_{jk}n_k
   [G_{Dj}(z)-G_{Cj}(z)],
   \quad
   R=\sum_C\int_C K_C p_\Sigma
   +\sum_F\int_F L_F p_\Sigma\,d\mathcal H^{N-1}.
   \tag{CF}
   $$

   Prove (CF), retaining all cutoff, mean and finite-facet terms; do not drop shared facets or replace d_jk by an arbitrary Gram maximization. Pair facets in two explicit classes: adjacent permutation swaps z_a=z_b, and adjacent record-order swaps a_h=a_k. For a conditional line X_j=x with its Gaussian residual vector fixed, all comparisons z_k-z_j=theta_k-theta_j+W_k-d_jk*x are nonincreasing. Thus the global rank of j is nonincreasing. Enumerate its finite cell intervals and apply Abel summation with the full G_Cj. For cumulative constants B_l use the exact finite formula sum_l a_l(B_l-B_{l-1})=a_L B_L-a_1 B_0-sum_{l<L}(a_{l+1}-a_l)B_l. Identify each coefficient difference with the paired facet in (CF), keeping changes of alpha and H, and the smooth partial_dH term. In the rank part also retain the exact increments D_k-D_{k-1}=1{pi(k) in I0}/k-V_{k-1}/[k(k-1)] for k>=2, and D_1-D_0=1{pi(1) in I0}. This specifies a finite coefficient calculation, rather than an unnamed flow estimate.

   The certificate to TRY after these pairings is the signed integrated inequality

   $$
   \sum_C\int_C K_Cp_\Sigma+
   \sum_F\int_F L_Fp_\Sigma\,d\mathcal H^{N-1}
   \le {Aq\over N}\sum_{j:\,-1<\theta_j\le0}
   \mathbb E[1+U+|X_j|],
   \tag{RC}
   $$

   for one universal finite A and all positive-definite models. The right side is an explicit summable marginal budget, at most A q(1+U+sqrt(2/pi)). Attempt to allocate the COMBINED K/L coefficients to it using the two facet pairings, the Abel coefficients, and the actual metric d. Do not bound each unsigned facet separately, assert a pointwise derivative bound, or discard cascade compensation. The proposed potential is H and the allocation is alpha above; (RC) is not a known consequence of either. The first failure condition is inability to establish (RC) with a universal A after the explicit coefficient calculation. Save the first uncontrolled combined coefficient or integrated estimate and any legal auxiliary counterexample, then stop. A polynomial or log N bound does not pass. Mere derivation of (ES)/(CF) does not pass and is not completion of the target.

5. [ ] **Only after the uniform gate: constants and singular limit.** From the preceding steps obtain FDR_I0(0)<=2c_-q+q+Aq(1+U+sqrt(2/pi)). Check a universal conversion to C_1 q sqrt(log(1/q)) on a universal interval. Extend to each fixed singular model by Sigma_epsilon=(1-epsilon)Sigma+epsilon I, preserving original means, fixed labels, all constants, and non-strict BH thresholds. Prove finite-model FDR convergence: every individual Gaussian score has continuous unit-variance marginal, so no grid threshold is hit with positive probability even in singular models. Do not take a limit in (CF) without a uniform bound; only the already bounded original FDR needs continuity. The supremum over all models is taken after this finite-model conclusion.

## Verification

All partial identities and bounds must be written out and independently verified during execution. If Step 4 succeeds, Steps 1,2,3,5 prove precisely the target with universal constants and all original quantifiers. If it fails, retain the explicit entrant Stein decomposition and finite paired coefficients as partial work in this plan; do not write a proof into the target, change its statement, or imply that failure refutes it. Record checkpoints promptly, re-reading the exact target region before every write, with each patch at most 6000 tokens.

## Assumed definitions

Only the target's existing approved definitions of the Gaussian model, p-values, ordinary BH, FDR, and worst-case envelope are assumed. The two inspired-by ideas supply obligations, not black boxes. Gaussian Stein integration by parts, Mills' bound, the record identities, polyhedral differentiation, and the PSD limit are all to be derived inline. No draft theorem is assumed.

## Difference from failed plans

- `plan_one_sided_order_actual_mean_global_flux_20261106`: use actual global-shift RECORD cohorts and exact pro-rata positive FDP, not separate coordinate rank-drop curves or an inactive marginal-crossing envelope. The entrant Stein baseline is explicitly <=q.
- `plan_one_sided_order_gaussian_interpolation_sdp_20261106`: no covariance interpolation or unproved diagonal SDP completion. The proposed finite allocation and its Stein potential are displayed; only the original distances d_jk occur.
- `plan_one_sided_order_three_face_noise_packing_20261106`: no independent Gram maximization, auxiliary noise parameter, or invocation of a deterministic-level replica lemma at random ranks. The actual Sigma is retained in (ES)/(CF).
- `plan_one_sided_order_negative_contact_transport_20261106`: global shifting fixes ALL score ordering and makes every record cell translation invariant. Allocation to weak entrants supplies a calibrated <=q baseline even for alternative triggers. The new Stein equation displays a smooth distance term and paired face coefficients without inverse residual noise. Uniform control of their signed sum remains the explicit gate to try, not a claim that the old unproved transport budget follows.

- `plan_ee2f7b97740a`: replace actual-covariance interpolation packets and a restricted Hall-cut maximum by a common translation record partition and the explicit entrant Stein potential H. The previous non-potential cut circulation and inverse-noise logarithmic loss are not assumed resolved. Here the calibrated baseline and the actual-distance bulk/facet expression are derived directly, with all background interfaces paired in (CF); the new first gate is (RC), not an unsupported claim that all legal cuts telescope.

## Progress

### Steps 1 and 2: endpoint, complete record chain, and positive allocation

Execution uses only the frozen full-scope statement and this plan. The target's initial SHA256 is `7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305`. The working directory is not a Git repository, so no HEAD is available. Restrict provisionally to positive-definite Sigma and 0<q<=S(1), where S=barPhi, U=S^{-1}(q)>=1, and u_r=S^{-1}(qr/N). All original null labels remain fixed throughout the auxiliary path Z-t*1, including when an original alternative's shifted mean becomes negative.

Here is the marginal calibration needed twice below. Integration by parts gives S(y)=phi(y)/y-integral_y^infinity phi(t)/t^2 dt for y>0, hence S(y)>=phi(y)y/(1+y^2). If Y has unit variance and mean -b with b>=1, then
$$
\begin{aligned}
\mathbb E\frac{1_{\{Y\ge U\}}}{S(Y)}
&=\int_U^\infty\frac{\phi(y)}{S(y)}e^{-by-b^2/2}\,dy\\
&\le e^{-1/2}\int_U^\infty(y+1)e^{-y}\,dy
=e^{-1/2}(U+2)e^{-U}
\le3e^{-3/2}=:c_-.
\end{aligned}
$$
The last function decreases for U>=1. Whenever a counted coordinate is rejected, BH self-consistency gives 1/(R vee 1)<=q/[N S(Y)] and Y>=U. Summing this inequality over any fixed subset with means <=-1 proves its expected FDP contribution <=c_-q times its size/N, without assumptions on the other means or any monotonicity in means. Applied to Y_j=Z_j-1 and the original I0, this proves FDR_I0(1)<=c_-q.

For a fixed score vector outside finitely many tie hyperplanes, let pi sort the scores strictly decreasingly and a_r=Z_pi(r)-u_r. The ordered p-value inequality at t is equivalent to a_r>=t, so
$$
R(t)=\max(\{0\}\cup\{r:a_r\ge t\}).
$$
This is also the rejection-set size: if more than r scores passed the selected threshold, the next rank would qualify. As t decreases from +infinity to -infinity, a rank r becomes selected exactly when a_r exceeds every a_k with k>r. Immediately before crossing that contact, the largest qualifying rank is s=max({0} union {k:a_k>a_r}); this s is <r. Immediately after, it is r. The entering cohort is exactly pi(s+1),...,pi(r). Thus the full path is a finite nested chain from rank zero to rank N; its cohorts partition all coordinates. The interval [0,1] retains precisely the contacts 0<a_r<1. All score ties and all distinct-rank contact ties are affine hyperplanes of zero probability for positive-definite Sigma. Individual contacts at 0 or 1 likewise have probability zero.

Put V_r=sum_{k<=r}1{pi(k) in I0}, W_r=sum_{k<=r}1{-1<theta_pi(k)<=0}, D_0=0 and D_r=V_r/r. For a record s->r with m=V_r-V_s,
$$
A:=D_r-D_s=
\begin{cases}
m/r-V_s(r-s)/(rs),&s>0,\\
m/r,&s=0.
\end{cases}
$$
If m=0 then A_+=0. If m>0, set alpha=A_+/m; then 0<=alpha<=1/r and
$$
\alpha=\frac1r\left[1-\frac{V_s(r-s)}{s m}\right]_+
\quad(s>0),\qquad \alpha=1/r\quad(s=0).
$$
Each newly entering original true null receives this same share. In particular the complete weak allocation is (W_r-W_s)alpha with the full dilution bracket above, even when the trigger pi(r) is an alternative or a strong true null. The exact pathwise telescoping identity is
$$
D_{R(0)}-D_{R(1)}
=\sum_{\text{full-path records }s\to r}A\,1_{\{0<a_r<1\}}.
$$
Only after this identity take A<=A_+ and split the allocated entrants into strong (theta_j<=-1) and weak (-1<theta_j<=0). For an active contact, Z_pi(r)>u_r and every entrant has Z_j>=Z_pi(r), whence S(Z_j)<=qr/N<=q and
$$
\alpha\,1_{\{0<a_r<1\}}
\le\frac{q}{N S(Z_j)}1_{\{Z_j\ge U\}}.
$$
Each j belongs to just one full-path cohort. The preceding marginal calibration therefore gives B_strong<=c_-q, while
$$
B_{\rm weak}
=\mathbb E\sum_{\text{records }s\to r}
(W_r-W_s)\alpha\,1_{\{0<a_r<1\}},
\qquad
\operatorname{FDR}_{I0}(0)\le2c_-q+B_{\rm weak}.
$$
No inactive grid levels have been added. This establishes checklist Steps 1 and 2; Steps 3--5 remain open at this checkpoint.

### Step 3: bounded entrant potential, exact Stein formula, and baseline

Fix a strict permutation pi and a strict ordering of its N affine contacts a_r. Their simultaneous inequalities define an open polyhedral cell C. Every defining normal has coordinate sum zero, so C is invariant under common translation and sum_k partial_k 1_C=0 distributionally. There are finitely many such cells; their complement has probability zero. Its record list, cohort labels, and alpha are constant. Each weak j occurs in exactly one cohort per cell. A record's trigger i=pi(r) has delta=z_j-z_i>=0 for every entrant j.

For a single such term abbreviate theta=theta_j, a=u_r+d, f(x)=phi(x-theta), F(x)=Phi(x-theta), Q(x)=1-F(x), and B=F(a+1)-F(a). The potential specified in the plan has the explicit continuous form
$$
H(x,d)=\begin{cases}
-B F(x)/f(x),&x<a,\\
[(1-B)F(x)-F(a)]/f(x),&a\le x\le a+1,\\
B Q(x)/f(x),&x>a+1.
\end{cases}
$$
Indeed these are the three evaluations of its defining integral; the formulas agree at both endpoints. The numerator is Cov(1{Y<=x},1{a<=Y<=a+1}), whose absolute value is at most F(x)Q(x). For x<=theta,
$$
F(x)/f(x)=\int_0^\infty e^{(x-\theta)t-t^2/2}\,dt\le\sqrt{\pi/2};
$$
the analogous integral bounds Q(x)/f(x) for x>=theta. Thus |H|<=sqrt(pi/2) for all x,d. For each fixed d, H tends to zero at both infinities by the Mills ratio (or the displayed integral and dominated convergence). Differentiating in x away from a,a+1 gives H_x-(x-theta)H=1{a<=x<=a+1}-B. The endpoint conventions do not affect any Gaussian integral.

Because a>=u_r>=1 and theta<=0, B'=f(a+1)-f(a)<0. The full d derivative is
$$
H_d(x,d)=\begin{cases}
-B' F(x)/f(x)>0,&x<a,\\
-[f(a)Q(x)+f(a+1)F(x)]/f(x)<0,&a<x<a+1,\\
B'Q(x)/f(x)<0,&x>a+1.
\end{cases}
$$
These formulas are important: the bulk has a favorable sign below the band and the opposite sign inside and above it. A crude bound |H_d|<=2 suffices solely for dominated convergence in this fixed finite model. Below the band, if x>=theta, f(a)/f(x)<=1; if x<=theta use the preceding F/f bound and f(a)<=1/sqrt(2pi). Inside the band, Q(x)/f(x)<=1/(x-theta)<=1 by the Mills upper bound S(v)<=phi(v)/v, and f(a+1)/f(x)<=1. Above the band use Q(x)/f(x)<=1 and |B'|<=f(a)<=1/sqrt(2pi). These give the stated bound. No bound obtained this way is being asserted to prove the uniform remainder estimate.

For a fixed positive-definite Gaussian density p, direct differentiation gives (z_j-theta_j)p=-sum_k Sigma_jk partial_k p. Multiply by a smooth compact cutoff chi_M and the potential h(z)=H(z_j,z_j-z_i), integrate over C, and integrate derivatives by parts. The chain rule is
$$
\sum_k\Sigma_{jk}\partial_k h=H_x+(1-\Sigma_{ji})H_d.
$$
The locally Lipschitz h has no delta contribution at its band endpoints since H is continuous there. With the above Stein equation, integration by parts therefore yields, before removing the cutoff,
$$
\begin{aligned}
\int_C\chi_M(1_{\{u_r\le z_i\le u_r+1\}}-b_{rj}(z_j-z_i))p
={}&-d_{ji}\int_C\chi_M H_d p
-\sum_k\Sigma_{jk}\int H\chi_M\partial_k1_C\,p\\
&-\sum_k\Sigma_{jk}\int_C H\partial_k\chi_M\,p,
\qquad d_{jk}:=1-\Sigma_{jk}.
\end{aligned}
$$
Take chi_M=chi(z/M) with bounded derivative, equal to one on the radius-M ball and zero outside radius 2M. The last line's cutoff term tends to zero by bounded H and the O(1/M) derivative. The volume integrands are dominated by constants plus |z_j-theta_j|; all have finite Gaussian integrals. Every boundary lies in one of finitely many affine hyperplanes. Its Gaussian surface integral is finite for this fixed positive-definite model; bounded H gives dominated convergence there as well. Finally sum_k partial_k1_C=0 replaces -Sigma_jk by d_jk. This proves exactly
$$
\mathbb E[1_C1_{\{u_r\le Z_i\le u_r+1\}}]
=\mathbb E[1_Cb_{rj}(\delta_{ji})]
-d_{ji}\mathbb E[1_CH_{rj,d}(Z_j,\delta_{ji})]
+\sum_kd_{jk}\mathbb E[H_{rj}(Z_j,\delta_{ji})\partial_k1_C].
\tag{ES-exec}
$$
All means remain the original theta, and no density with a false trigger's mean is substituted for the entrant density.

Multiply by the actual alpha of this record and sum over cells, records, and weak entrants. The band indicator is precisely 1{0<a_r<1} up to null endpoints. Since theta_j<=0 and delta>=0,
$$
0\le b_{rj}(\delta)\le S(u_r+\delta-\theta_j)\le S(u_r)=qr/N,
\qquad 0\le\alpha b_{rj}(\delta)\le q/N.
$$
For each z each weak j occurs once over the full record list, even if that record is outside the active interval. Thus the baseline B0, the expectation of this finite sum, satisfies B0<=q|J|/N<=q, where J={j:-1<theta_j<=0}. Consequently B_weak=B0+R exactly, with R the summed bulk and boundary terms of (ES-exec). This completes Step 3. Steps 4 and 5 remain open.

### Step 4 coefficient calculation: paired cells and conditional Abel identity

Factor the original positive-definite Sigma as VV^T, for example by its orthonormal eigenvectors and positive eigenvalues. Its row vectors v_j have norm one. Accordingly d_jk=1-Sigma_jk=|v_j-v_k|^2/2>=0. This is the actual covariance metric, with no maximization over other Gram matrices.

For a cell C and its full record list define
$$
\begin{aligned}
K_C(z)&=-\sum_{(s,r)\in\operatorname{Rec}(C)}
\sum_{j\in J\cap\{\pi(s+1),\ldots,\pi(r)\}}
\alpha_{sr}d_{j,\pi(r)}H_{rj,d}(z_j,z_j-z_{\pi(r)}),\\
G_{Cj}(z)&=\alpha_{sr}H_{rj}(z_j,z_j-z_{\pi(r)})
\quad\text{for the unique cohort }(s,r)\text{ containing }j\in J.
\end{aligned}
$$
The second formula is equivalently the plan's record sum; for each weak j only one summand is nonzero. In a shared facet F oriented by unit normal n from C to D, the distributional derivative of 1_C is -n times surface measure and that of 1_D is +n times surface measure. Thus both sides of (ES-exec) give the single coefficient
$$
L_F(z)=\sum_{j\in J}\sum_kd_{jk}n_k
\bigl(G_{Dj}(z)-G_{Cj}(z)\bigr),
\qquad
R=\sum_C\int_C K_Cp+\sum_F\int_F L_Fp\,d\mathcal H^{N-1}.
\tag{CF-exec}
$$
Each geometric facet is counted once; lower-dimensional intersections have zero surface measure. With the common cutoff chi_M from Step 3 the identical pairing holds before taking limits. Its derivative terms tend to zero and each individual affine-facet integral converges absolutely for this fixed finite positive-definite model. No boundary at infinity, covariance-inverse estimate, omitted mean term, or unpaired cell interface remains in (CF-exec).

There are only two types of geometric facets. First consider an adjacent score swap z_a=z_b at ranks p,p+1, away from all other hyperplanes. At equality a_p=z_a-u_p<a_{p+1}=z_b-u_{p+1}, because u_p>u_{p+1}. Therefore rank p is not a suffix record on either side near this facet. No record endpoint or predecessor can cut this two-element tied block. Its two labels enter the same cohort on both sides, so every relevant cohort's null counts, weak sets, and alpha agree. Record triggers outside the block are unchanged; a trigger at p+1 exchanges a and b but its score on the facet is the same. Hence G_Dj=G_Cj for every fixed weak label j. This includes rank zero, alpha zero, and all true/false label combinations. Pure permutation facets have L_F=0.

Next keep the permutation fixed, put i=pi(h), ell=pi(k), h<k, and consider an adjacent ordering swap a_h=a_k=t. If some other l>h has a_l>t, rank h is not a suffix record on either side and the record path is unchanged. Such facets have zero jump. Otherwise all l>h except k have a_l<t. Put s=max({0} union {l<h:a_l>t}). On C, defined by a_h>a_k, the two local entries are s->h->k; on D, defined by a_h<a_k, they are replaced by s->k. Other entries agree. Define P={pi(s+1),...,pi(h)}, Q={pi(h+1),...,pi(k)}, and define alpha_ab=[D_b-D_a]_+/(V_b-V_a), with value zero when its denominator is zero. The exact coefficient changes are
$$
\beta_j=\begin{cases}
\alpha_{sk}-\alpha_{sh},&j\in J\cap P,\\
\alpha_{sk}-\alpha_{hk},&j\in J\cap Q,\\
0,&j\notin P\cup Q.
\end{cases}
$$
On the facet u_h+z_j-z_i=u_k+z_j-z_ell, so the entire H kernel, not just its indicator, agrees between the two local records. With n=(e_ell-e_i)/sqrt(2) oriented C to D,
$$
\begin{aligned}
G_{Dj}-G_{Cj}&=\beta_j H^*_j,\qquad
H^*_j:=H_{kj}(z_j,z_j-z_\ell),\\
L_F&=\frac1{\sqrt2}\sum_{j\in J\cap(P\cup Q)}
(\Sigma_{ji}-\Sigma_{j\ell})\beta_j H^*_j.
\tag{RF-exec}
\end{aligned}
$$
This is the full record-face remainder, including zero-mass cohorts and cascades. The projection Sigma_ji-Sigma_jell is not asserted nonnegative. No negative FDP increment was removed in calculating alpha: if eta_k=1{pi(k) in I0}, then
$$
\Delta D_1=\eta_1,\qquad
\Delta D_k=\frac{\eta_k}{k}-\frac{V_{k-1}}{k(k-1)}\ (k\ge2),
\quad
\alpha_{ab}=\frac{[\sum_{k=a+1}^b\Delta D_k]_+}{V_b-V_a}
\quad(V_b>V_a).
\tag{AI-exec}
$$
Thus (RF-exec) specifies every coefficient directly in terms of the exact prefix increments including their negative dilution terms.

For completeness the precise one-dimensional summation by parts is as follows. For fixed weak j write X_j=Z_j-theta_j, X_k=Sigma_kj X_j+W_k, where W is independent of X_j and W_j=0. Independence follows since the joint Gaussian characteristic function factors when the covariance with X_j is zero. Condition on W=w. Then
$$
z_k-z_j=\theta_k-\theta_j+w_k-d_{jk}x,
\qquad x=X_j.
$$
All these differences are nonincreasing, so the rank of j is nonincreasing. All comparison hyperplanes cut this line into finitely many intervals I_l=(x_{l-1},x_l), l=1,...,L, with infinite outer endpoints. Outside a residual-null set there are no ambiguous nontransverse crossings. Let a_l=alpha of j's unique entry on I_l, r_l its endpoint, i_l its trigger, d_l=d_j,i_l, and h_l(x)=H_{r_l,j}(theta_j+x,z_j-z_i_l). The preceding facet analysis proves h_l(x_l)=h_{l+1}(x_l) for every effective crossing, including permutations. Denote this common value by h(x_l). Smoothly inside I_l,
$$
h_l'(x)=H_x+d_l H_d.
$$
The derivative of a_l h_l as a distribution therefore has smooth density a_l(H_x+d_l H_d) and point masses (a_{l+1}-a_l)h(x_l). Integrating against the centered standard normal density phi(x), with vanishing endpoint terms from bounded H, gives the exact conditional remainder
$$
R_j(w)=-\sum_{l=1}^L a_l\int_{I_l}d_l H_d\phi(x)\,dx
-\sum_{l=1}^{L-1}(a_{l+1}-a_l)h(x_l)\phi(x_l).
\tag{CL-exec}
$$
Indeed Stein integration by parts has E[x g]=E[g'] with the point masses included; the original conditional remainder is integral a_l(H_x-xH)phi. On a facet sum_k n_k=0 implies n dot Sigma_.j=-sum_k d_jk n_k. Thus the line's negative point-mass term is exactly (RF-exec) after integrating over W. This identifies both the orientation and the covariance projection, rather than replacing the surface term by an independent covariance.

Set B_0=B_L=0 and B_l=h(x_l)phi(x_l) for 1<=l<L. For these numerical constants, direct expansion and reindexing gives the finite Abel formula
$$
\sum_{l=1}^L a_l(B_l-B_{l-1})
=a_LB_L-a_1B_0-\sum_{l<L}(a_{l+1}-a_l)B_l.
$$
Accordingly (CL-exec) is also
$$
R_j(w)=\sum_{l=1}^L a_l\left[
-\int_{I_l}d_l H_d\phi(x)\,dx+B_l-B_{l-1}\right].
\tag{AB-exec}
$$
All smooth d_l H_d terms and all alpha changes (RF-exec), with (AI-exec)'s dilution increments, are retained. Although the global rank of j is monotone, neither the record endpoint r_l nor its pro-rata coefficient a_l has been shown monotone. This completes the requested finite coefficient calculation, not the uniform gate (RC).

### Signed bulk/record-face trial and the first unresolved estimate

Throughout the preceding construction set alpha=0 when m=0, including in Step 2. The following calculation keeps, rather than discards, the favorable below-band bulk. For each cell record and weak entrant put x=z_j, a=u_r+z_j-z_i, t=z_i-u_r=x-a. Write f_j(x)=phi(x-theta_j), F_j(x)=Phi(x-theta_j), Q_j(x)=1-F_j(x), B=F_j(a+1)-F_j(a), and
$$
\begin{aligned}
c_{<}(x,a)&=[f_j(a)-f_j(a+1)]F_j(x)/f_j(x),\\
c_{0}(x,a)&=[f_j(a)Q_j(x)+f_j(a+1)F_j(x)]/f_j(x),\\
c_{>}(x,a)&=[f_j(a)-f_j(a+1)]Q_j(x)/f_j(x).
\end{aligned}
$$
All three c's are nonnegative. The exact sign-separated remainder, after eliminating the identically zero permutation and ineffective record facets, is
$$
\begin{aligned}
\mathcal J:={}&
\sum_C\sum_{(s,r)\in\operatorname{Rec}(C)}\sum_{j\in J\cap\operatorname{cohort}(s,r)}
\int_C\alpha_{sr}d_{ji}
\left[-c_<1_{\{t<0\}}+c_01_{\{0<t<1\}}+c_>1_{\{t>1\}}\right]p(z)\,dz\\
&+\frac1{\sqrt2}\sum_{\substack{F:\,s\to h\to k\ \mathrm{vs.}\ s\to k}}
\int_F\sum_{j\in J\cap(P\cup Q)}
(\Sigma_{ji}-\Sigma_{j\ell})\beta_jH^*_j(z)p(z)\,d\mathcal H^{N-1}(z).
\tag{SJ-exec}
\end{aligned}
$$
Here i=pi(r) in the volume sum, i=pi(h) and ell=pi(k) in the facet sum, and beta_j is exactly (RF-exec), with all dilution terms (AI-exec). The equality is R=mathcal J, not an upper bound. On record facets the common t=a_h=a_k also determines H^*_j<0 for t<0 and H^*_j>0 for t>1. Thus a combined sign argument would have to relate the metric-weighted beta on such facets to the negative c_< bulk; d_jk>=0 alone does not give that relation.

The following finite legal sign test rules out the tempting local cancellation or rank-monotone allocation shortcut. Take N=3, Sigma=I_3, theta_1=theta_3=0, theta_2>0, and the open permutation region z_1>z_2>z_3. At a facet a_2=a_3=t with a_1>t, the side C with a_2>a_3 has record chain 0->1->2->3. Its prefix FDPs are D_1=1, D_2=1/2, D_3=2/3, so alpha_01=1, alpha_12=0, alpha_23=1/6. Side D has chain 0->1->3, with alpha_13=0. The only changed weak allocation is j=3, with beta_3=-1/6. The oriented actual-metric factor is Sigma_32-Sigma_33=-1, and hence
$$
L_F=H_{3,3}(z_3,0)/(6\sqrt2).
$$
The facet is nonempty for every t: z_3=u_3+t, z_2=u_2+t, and z_1>u_1+t suffice. In particular L_F>0 throughout its t>1 portion. In both adjacent cells all nonzero-alpha weak entries are self-triggered, so d_jj=0 and their bulk coefficients vanish identically. The remaining weak coefficient is zero. Thus this positive facet cannot be canceled pointwise by its adjacent bulk cells. Along the conditional X_3 line, the rank of coordinate 3 stays equal to three across the facet, but its allocation drops from 1/6 to zero. Rank monotonicity therefore does not imply allocation monotonicity or a favorable sign for the Abel coefficient. This is a counterexample only to those auxiliary sign shortcuts; it does not violate (RC), let alone the target. Other facets and score ranges remain in (SJ-exec).

One can bound the above-band *bulk alone* by a summable marginal term, but that does not dispose of the mixed band or the record faces. Indeed t>1 implies x>a+1>=u_r+1 and
$$
\frac{c_>(x,a)}{S(u_r)}
\le\frac{\phi(u_r)}{S(u_r)}\frac{Q_j(x)}{f_j(x)}
\le\frac{u_r+u_r^{-1}}{x-\theta_j}\le2.
$$
Here theta_j<=0, f_j(a)<=phi(u_r), and both Mills inequalities were proved above. Since alpha<=1/r=q/[NS(u_r)] and d_ji<=2, each such bulk summand is <=4q/N pointwise. Each weak j has only one record per cell, so the entire positive t>1 bulk is <=4q|J|/N. The negative t<0 bulk remains in (SJ-exec); it is not thrown away to estimate the faces. For the mixed-band term the corresponding formula is
$$
\frac{c_0(x,a)}{S(u_r)}
=\frac{f_j(a)Q_j(x)}{S(u_r)f_j(x)}
+\frac{f_j(a+1)F_j(x)}{S(u_r)f_j(x)},
\quad 0<t<1.
$$
The first term has the same <=2 bound. At this checkpoint the second term, a moving upper-endpoint term, was not bounded; the next subsection supplies a direct marginal bound, so it is no longer part of the unresolved gate. The sign test above still shows why giving every face a presumed favorable sign cannot complete the record-face estimate. Applying Abel to the full coefficients gives (AB-exec); substituting (H_x-xH)phi=(1_band-B)phi merely returns the initial exact moving-band expectation and supplies no new budget. No unconditional deterministic-level identity has been substituted at a random record rank.

### Further established estimate: all positive bulk has a universal O(q) bound

Recheck the remaining upper-endpoint mixed-band term without treating its moving contact as independent. Fix a sample, a cell, a weak entrant j, and its unique full-path record with trigger i and endpoint r. On 0<t<1 put X=z_j-theta_j, tau=t, a=z_j-tau=u_r+delta_ji, and Y=X-tau=a-theta_j. Then Y>=a>=u_r>=U>=1 because theta_j<=0. The upper-endpoint part of the positive bulk is exactly
$$
M_j=\alpha_{sr}d_{ji}
\frac{\phi(X+1-\tau)\Phi(X)}{\phi(X)}1_{\{0<\tau<1\}}.
$$
Its allocation obeys the following inequalities in the stated directions:
$$
\alpha_{sr}\le\frac1r
=\frac{q}{NS(u_r)}
\le\frac{q}{NS(z_j-\tau)}
\le\frac{q}{NS(X-\tau)}.
$$
The middle step uses z_j-tau=u_r+delta_ji>=u_r; the last uses z_j=X+theta_j<=X and the fact that S decreases. Consequently, using d_ji<=2 and Phi(X)<=1,
$$
M_j\le\frac{2q}{N}
\frac{\phi(Y+1)}{\phi(X)S(Y)}1_{\{X\ge U\}}.
$$
Mills' lower bound gives
$$
\begin{aligned}
\frac{\phi(Y+1)}{S(Y)}
&\le (Y+Y^{-1})e^{-Y-1/2}\\
&\le e^{1/2}(X+1)e^{-X},
\qquad Y=X-\tau\ge1,\quad 0\le\tau\le1.
\end{aligned}
$$
Here Y+Y^{-1}<=X+1 and exp(-Y-1/2)<=exp(1/2-X). Thus the random tau and record rank have disappeared from the deterministic pointwise upper envelope. The entire cell/record sum has at most one such term for this j at each sample, by the full-path cohort partition. Its expectation therefore uses only X_j's unconditional standard normal marginal:
$$
\begin{aligned}
\mathbb E M_j
&\le\frac{2q e^{1/2}}{N}
\int_U^\infty (x+1)e^{-x}\,dx\\
&=\frac{2q e^{1/2}}{N}(U+2)e^{-U}
\le\frac{6e^{-1/2}q}{N}<\frac{4q}{N}.
\end{aligned}
$$
The monotonicity of (U+2)e^{-U} for U>=1 was already checked in Step 1. There is no conditioning on the random rank, no independence assumption on tau, and no substitution of a random threshold into a deterministic-level lemma.

For each j, the lower-endpoint mixed-band term is <=4q/N pointwise by the earlier c_0 first-term estimate. The above-band term is also <=4q/N pointwise, and their supports 0<t<1 and t>1 are disjoint. Hence their sum is <=4q/N pointwise. Combining with the newly bounded M_j proves
$$
\mathcal P:=\sum_C\sum_{(s,r)}\sum_{j\in J\cap\operatorname{cohort}(s,r)}
\int_C\alpha_{sr}d_{ji}
\bigl[c_01_{\{0<t<1\}}+c_>1_{\{t>1\}}\bigr]p(z)\,dz
\le(4+6e^{-1/2})q|J|/N\le8q|J|/N.
\tag{PB-exec}
$$
Keep the favorable negative volume explicitly as
$$
\mathcal N:=\sum_C\sum_{(s,r)}\sum_{j\in J\cap\operatorname{cohort}(s,r)}
\int_C\alpha_{sr}d_{ji}c_<1_{\{t<0\}}p(z)\,dz\ge0,
$$
and denote by mathcal F the entire signed record-facet sum, namely the second line of (SJ-exec) with the exact (RF-exec) coefficients. The unchanged exact decomposition is now R=mathcal P-mathcal N+mathcal F. Thus every positive bulk term has been uniformly bounded; the remaining possible need for cancellation is exclusively between the complete record-facet flux and the retained negative bulk. A universal bound on mathcal F alone would suffice, but is a stronger requirement than controlling mathcal F-mathcal N.

### Further record-face trial retaining the favorable bulk

Here are two additional finite calculations of the residual; neither provides its missing uniform bound. First, if B denotes the band probability for j's selected entry, the defining covariance numerator of H satisfies |H|phi(X_j)<=B. Since B<=S(u_r) and alpha<=1/r, this gives the universal pointwise endpoint amplitude
$$
\alpha|H|\phi(X_j)\le\alpha B\le q/N.
\tag{EA-exec}
$$
At each conditional-line record crossing H and B match across the facet. Each one-sided alpha satisfies (EA-exec), so the absolute line jump obeys |(alpha_+-alpha_-)H phi(X_j)|<=2q/N. Summing this estimate alone leaves (2q/N) times the number of effective record crossings. That number is finite for fixed N but has no established universal expected bound here. This estimate is therefore not used to discard the actual metric or the signed cancellations in (RF-budget-unproved).

Second, the band start on the conditional line, call it A_j(x)=u_r+z_j-z_i for j's unique full-path entry, is continuous at every cell crossing by the explicit two-facet calculation. Inside each interval its derivative is d_ji in [0,2]. Hence A_j is a globally continuous nondecreasing piecewise affine function. This is a property of the band start, not a claim that alpha is monotone. Let the finitely many connected components of {x:z_j(x)<A_j(x)} be denoted by I=(a,b). On each such component the entrant is below its band. Put e(x)=alpha(x)H(x)phi(x), with one-sided values at cell boundaries, and let B_j(x) be the corresponding band probability. On every smooth cell subinterval of I the Stein equation gives exactly
$$
e'_{\rm smooth}(x)=
\alpha(x)d_{ji}c_<(x)\phi(x)-\alpha(x)B_j(x)\phi(x).
$$
Consequently the negative record jumps inside I and the full favorable volume there combine to
$$
\begin{aligned}
&-\sum_{x_l\in I}[e(x_l+)-e(x_l-)]
-\int_I\alpha(x)d_{ji}c_<(x)\phi(x)\,dx\\
&\hspace{1cm}=e(a+)-e(b-)-\int_I\alpha(x)B_j(x)\phi(x)\,dx.
\tag{NB-pair-exec}
\end{aligned}
$$
This is the exact finite distributional fundamental theorem on I. Infinite-endpoint values are zero by bounded H times phi. Outside a residual-null set record crossings do not coincide with the band endpoints, so their assignment to these components is unambiguous; exceptional coincidences can equally be handled by one-sided limits. All remaining conditional record jumps, those at or above the lower band endpoint, are still retained with the original sign in (CL-exec).

Thus the beneficial bulk really can be paired, rather than ignored: below-band record jumps turn into the endpoint differences and the nonpositive last integral in (NB-pair-exec). However (EA-exec) bounds each resulting endpoint only separately. There is no established dimension-free bound on their *total signed sum*, nor on the remaining above-band record jumps with their full alpha differences. The monotone A_j may cross the line z_j(x) more than once, since its slopes range from zero to two; this calculation does not provide a bound on the number of components. The legal N=3 example already shows why the needed alpha sign cannot be inferred from the rank or the band-start monotonicity. This is the exact remaining global summation issue after a genuine attempt to use the favorable negative volume. It does not assert that a universal cancellation is false.

### Scoped independent check of the positive-bulk estimate

A fresh independent reviewer, as communicated by the parent worker, checked the mixed-band marginal envelope and the all-positive-bulk estimate against the pre-EA version SHA256 `be2ea17e69272bc90a79a1f3f7c8c554a98b6b911442ce52bd8d297b46ba4bf8`. The reviewer confirmed the allocation inequality directions, unconditional marginal integration despite data-dependent tau, unique full-path cohort summation, and the positive-bulk calculation, except for a strictness defect in the final summed display when J is empty. That display is now uniformly corrected to P<=(4+6e^{-1/2})q|J|/N<=8q|J|/N; for J empty both sides are zero. The per-entrant numerical inequality 6e^{-1/2}q/N<4q/N is valid since q>0 and N>=1. This scoped check does not verify (EA-exec), (NB-pair-exec), the unresolved record-flux budget, the singular extension, or the target theorem. No approval status is implied.

### Final independent scoped checks

Fresh reviewers rechecked the final pre-note snapshot ec3e74b157f7a1a7f68edbb83ce7205dcf968df90853180298e599d898c4dda7. The Steps 1–3 block, then lines 120–232, remained byte-identical with digest be63500e9589276634dc5750fc3141e83b8a17d77192e7bcd12a694ff3ee6b93; no local defect was found in calibration, record/cohort allocation, the entrant Stein identity or its baseline. A separate fresh facet reviewer reconstructed the finite facet and conditional-line identities and confirmed the legal three-test local-sign example. It then checked the appended amplitude and negative-body pairing trial at then lines 420–446, digest a885868983bb18074421c0bb74752665ebdfe5443f1c7e5a993d4ded2a2fb8ea, and the retained Failure at then lines 451–468, digest fbd9aed67381a995527c3c112ec2dedb2e89128d8322059a298e71836ffc593a. The signed definition e=alpha H phi yields the endpoint signs in (NB-pair-exec) exactly. Another brand-new reviewer accepted the corrected positive-bulk argument, then lines 365–418, digest 44d322226ab60ce0021725150c22f79dcb98b12188fe9a065ef9377258a73608, including J empty. No selected-rank independence, omitted negative body, or singular-limit claim was accepted. These are scoped checks of the written partial derivations, not native verification or approval of the target; the uniform combined record-flux budget remains unresolved.

## Failure

The first essential unresolved gate is Step 4, specifically the following *combined signed integrated estimate*, with every coefficient fixed by (AI-exec), (RF-exec), and (SJ-exec):
$$
\mathcal J\ \le\ \frac{Aq}{N}\sum_{j\in J}\mathbb E[1+U+|X_j|]
\quad\text{for one universal finite }A,
\qquad X_j=Z_j-\theta_j\sim N(0,1).
\tag{RC-unproved}
$$
After (PB-exec), all positive bulk is bounded by 8q|J|/N. The exact remaining expression requiring a universal summable estimate is therefore
$$
\mathcal F-\mathcal N
\ \le\ \frac{A'q}{N}\sum_{j\in J}\mathbb E[1+U+|X_j|]
\tag{RF-budget-unproved}
$$
for a finite universal A'. This is a sufficient residual gate for (RC-unproved), with the favorable negative bulk retained in full; no stronger claim that the signed facet flux alone must be bounded is made. All facet coefficients remain those explicitly fixed in (RF-exec). Actual covariance projections have no automatic sign; allocation can decrease with the entrant's unchanged rank, even for Sigma=I_3. The explicit auxiliary example disproves two candidate shortcuts but is not a counterexample to either displayed unproved budget. No claim of impossibility, no uncontrolled log N replacement, and no independent Gram or smallest-eigenvalue bound is used.

Steps 1--3 and the finite coefficient portion of Step 4 are established as written; Step 4's uniform inequality and therefore Step 5 are not completed. Obtaining (RC-unproved), or a different justified universal bound on the exact combined remainder, is what would be needed to finish this plan. In particular the draft target's all-N, all-means, all-unit-diagonal-PSD statement, including singular matrices and q-dependent models, is untouched and unproved by this execution. There is no target Proof edit. The plan is marked failed as required at this first unproved gate; failure of the plan does not refute the target.
