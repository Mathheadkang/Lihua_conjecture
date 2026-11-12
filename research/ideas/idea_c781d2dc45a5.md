---
type: idea
title: Retain actual null p-value distributions in the clipped rank-jump identity
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - gaussian-bh
  - boundary-jumps
  - composite-nulls
  - weighted-identity
  - unproved-estimate
---

This corrects the composite-null relaxation exposed by idea_a47114025878. The weighted identity below is an exact deterministic/probabilistic calculation. The Gaussian estimate needed for either full sharp uniform FDR bound remains unproved. In particular, the false unweighted one-sided lemma from idea_aaa81d69e1fc is not being reused.

## Actual-null-p parameterization

Fix a true one-sided null i with theta_i<=0, q in (0,1), m>=1, a=q/m, and z_u=barPhi^{-1}(u). Parameterize by its ACTUAL p-value u=barPhi(theta_i+G_i), so G_i=z_u-theta_i. Its marginal cdf and density on (0,1) are

$$
F_i(u)=\mathbb P\{p_i\leq u\}=\bar\Phi(z_u-\theta_i),\qquad
f_i(u)=\frac{\phi(z_u-\theta_i)}{\phi(z_u)}.
$$

Because theta_i<=0, F_i(u)<=u. Gaussian regression gives G_{-i}=rho_i G_i+W_i, with W_i independent of G_i and hence of p_i, including singular covariance and singular residual covariance. Along a fixed residual realization w, every other statistic retains its actual mean:

$$
T_j(u,w)=\theta_j+\rho_{ji}(z_u-\theta_i)+w_j.
$$

Let r_i(u,w) be the ordinary BH rejection count after forcing p_i to zero and using these other actual statistics. This is an integer in {1,...,m} and has finitely many changes: an affine Gaussian coordinate crosses any fixed one-sided BH grid value at most once (at most twice for a two-sided coordinate); identically constant ties do not create infinitely many rank changes.

The deterministic BH forced-zero identity yields the exact false-discovery contribution

$$
C_i=\mathbb E_W\int_0^1
\frac{f_i(u)\mathbf1\{u\leq a r_i(u,W_i)\}}{r_i(u,W_i)}\,du.
$$

No superuniform replacement p_i>=barPhi(G_i), no change to another actual mean, and no global FDP monotonicity are used.

## Weighted clipped identity

For a fixed residual, suppress i,w and define

$$
J(u)=\frac{F_i(\min\{u,a r(u)\})}{r(u)}.
$$

On each constant-r interval,

$$
J'(u)=\frac{f_i(u)\mathbf1\{u<a r(u)\}}{r(u)}
$$

almost everywhere. Since r is bounded and has finitely many changes,

$$
J(0+)=0,\qquad
J(1-)=\frac{F_i(a r_*)}{r_*}\leq a,\qquad r_*=r(1-).
$$

The endpoint must be understood as the one-sided limit, not an arbitrarily assigned value r(1). Summing interval integrals therefore gives exactly

$$
\int_0^1\frac{f_i(u)\mathbf1\{u\leq ar(u)\}}{r(u)}\,du
=\frac{F_i(a r_*)}{r_*}
-\sum_t\left[J(t+)-J(t-)\right].
$$

Weak BH inequalities, isolated threshold equalities and tangencies do not alter this integral because the actual null marginal distribution has a continuous density. When theta_i=0, F_i(u)=u and J reduces exactly to H(u)=min{u/r(u),a}.

Define the weighted harmful-jump functional by ALL negative J jumps,

$$
D_i^{\mathrm{wt}}(r)=\sum_t\left[J(t-)-J(t+)\right]_+.
$$

The exact signed identity implies

$$
\operatorname{FDR}^{(1)}
\leq\sum_{i\in I_0}\mathbb E\frac{F_i(a r_{i,*})}{r_{i,*}}
+\sum_{i\in I_0}\mathbb E D_i^{\mathrm{wt}}
\leq\frac{m_0q}{m}+\sum_{i\in I_0}\mathbb E D_i^{\mathrm{wt}}.
$$

A uniform estimate on this weighted variation with the target leading constant would be sufficient, but no such estimate has been proved here. The signed identity could support a weaker estimate preserving cancellations instead.

For two-sided true nulls, theta_i=0, so their actual p-value is Uniform(0,1). Its independent equiprobable sign gives the two paths G_i=+/-barPhi^{-1}(u/2), and the exact contribution is the average of the unweighted clipped identities on those two paths. The corresponding Gaussian boundary estimate also remains open.

## Caution: rank decreases can now be harmful

For theta_i<0, write g_i(t)=F_i(t)/t. The density f_i(t)=exp(theta_i z_t-theta_i^2/2) is increasing in t, so its average g_i(t) is strictly increasing. This proves that for an INCREASING rank jump r^-<r^+, the positive weighted drop is bounded by the corresponding unweighted H drop on the SAME actual-p path:

$$
[J(t-)-J(t+)]_+\leq H(t-)-H(t+).
$$

It does NOT prove domination of the total weighted harmful variation. At a decreasing-rank jump beyond both cutoffs, H is constant at a while J can drop because F_i(ar)/r=a g_i(ar) increases with r.

There is an exact admissible Gaussian example: m=2, a=q/2, T_1=Z-c, T_2=Z, c>0, and audit null i=1. Its actual-p path has G_1=z_u+c. The forced-zero rank drops from 2 to 1 at

$$
u_0=\bar\Phi(z_q-c)>q=2a.
$$

At this point H has zero jump, but the harmful weighted J drop is

$$
\frac{F_1(q)}2-F_1(a)
=a\left[g_1(q)-g_1(a)\right]>0.
$$

Thus the weighted functional must count every negative J jump, including rank decreases. A blanket assertion that all harmful weighted drops are bounded by old H drops is false even in a two-coordinate perfectly positively correlated Gaussian model.

Finally, setting the audited null to a boundary parameter along the same actual-p path changes other effective means to theta_j-rho_{ji}theta_i. This shift depends on the audited coordinate i; it does not place all audited nulls simultaneously in a single common boundary-mean model. No global reduction of all negative nulls to theta_i=0 follows from the pointwise identities. Both full unrestricted upper targets remain draft and unproved.
