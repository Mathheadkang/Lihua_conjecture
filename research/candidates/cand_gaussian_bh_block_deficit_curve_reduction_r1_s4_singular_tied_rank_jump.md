---
type: candidate
title: Singular two-block threshold ties and a downward raw-deficit jump
status: failed
target_asset: gaussian_bh_block_deficit_curve_reduction
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 4
direction: known_counterexamples
statement_digest: f1dda2f50a23bcb44d5591faa42a4ed7c15018980386fbefca5819ed441dbef8
performed_by: unknown
created_at: '2026-11-06T21:22:09.796Z'
extension_version: 0.0.4
---

## Object

Test the BH pathology in which perfect within-block dependence creates a simultaneous count jump, including an exact threshold tie. Let $N=4$, $q=p(4)$, $B_1=\{1,2\}$, $B_2=\{3,4\}$, and $i=1$. With independent standard normal $Z,W$ and independent unused residual normals, set

$$
(T_1,T_2,T_3,T_4)=(Z,-Z,W,W),\qquad \theta=0.
$$

Use the particular realization $Z=4$, $W=p^{-1}(3q/4)$. Thus $(P_1,P_2,P_3,P_4)=(q,q,3q/4,3q/4)$. The displayed realization has probability zero, but the statement explicitly retains threshold ties and does not discard such realizations. This is one pointwise tie test, not a claim of a positive-probability violation.

## Checks

### H1

Pass: independent one-factor blocks with loadings $(1,-1,1,1)$ give the stipulated representation. The covariance has diagonal entries one and two diagonal blocks $\left(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\right)$ and $\left(\begin{smallmatrix}1&1\\1&1\end{smallmatrix}\right)$, each positive semidefinite. Singular covariance is allowed.

### H2

Pass: $i=1$ belongs to $B_1$ and $\theta_1=0$.

### H3

Pass: $P_j=p(|T_j|)$ and $(t_1,t_2,t_3,t_4)=(q/4,q/2,3q/4,q)$ are strictly increasing. All threshold comparisons below are closed, and the largest qualifying rank is used.

### H4

Pass: the background count is $\beta(k)=2\mathbf1\{p(|W|)\le t_k\}$, independent of $(Z,\varepsilon_1,\varepsilon_2)$. It is integer, nondecreasing, and between zero and $N-|B_1|=2$. At the displayed realization,

$$
\beta=(0,0,2,2).
$$

### H5

Pass: the mate count is $M_z(k)=\mathbf1\{p(|z|)\le t_k\}$, integer and nondecreasing. At $z=4$,

$$
M=(0,0,0,1).
$$

### H6

Pass: defining the deficits exactly as stipulated gives

$$
D=(0,1,0,1),\qquad D^*=(0,0,0,1).
$$

The raw deficit has a downward jump, which is the possible obstruction tested by this object.

### NOT

Fail: the downward jump disappears under the suffix minimum. The direct qualifying counts are $1+\beta+M=(1,1,3,4)$, so their largest qualifying rank is $4$. Direct comparison with $D$ also gives largest qualifying rank $4$. After suppressing the mate count, $1+\beta=(1,1,3,3)$ has largest qualifying rank $3$, agreeing with $\max\{k:D(k)\le0\}=3$.

For the suffix curve, its increments are $(0,0,1)$, $D^*\le D\le(k-1)_{k=1}^4$, and $D^*\le0$ exactly at ranks $1,2,3$. Comparing $M$ with $D^*$ gives largest qualifying rank $4$ again. Thus the tested tie does not violate either rank identity or any curve property. Independence is preserved because this curve is a function of $W$ alone. This failed pointwise attempt establishes no universal claim about other models.

## Failure

NOT fails: simultaneous background ties produce a downward raw-deficit jump, but the suffix envelope retains the same largest qualifying ranks and satisfies the claimed unit-increment conditions.
