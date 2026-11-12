---
type: lemma
title: Fractional-frame Gaussian surface kernel with arbitrary exposure
status: approved
source:
  kind: original
depends_on: []
uses_definitions: []
tags: []
---

## Statement

Let d,n be positive integers, let G be a standard Gaussian vector in R^d, and let v_1,...,v_n,w be unit vectors in R^d. Let c_i>=0 satisfy sum_i c_i v_i v_i^T <= I_d in the positive-semidefinite order, and put beta=sum_i c_i. Define phi(x)=(2*pi)^(-1/2)exp(-x^2/2), S(x)=integral_x^infinity phi(z)dz, and h(x)=phi(x)/S(x). For every u>=1 and all deterministic a_i>=u, the canonical Gaussian conditional law G | (w.G=y) satisfies, for every real y,
$$
\phi(y)\,\mathbb P\{v_i\cdot G\ge a_i\text{ for all }1\le i\le n\mid w\cdot G=y\}
\le \sqrt e\,h(u)\,S(u)^\beta.
$$
The canonical conditional law is the law of y*w+(I_d-w*w^T)G_0 with G_0 standard Gaussian. The constant sqrt(e) is universal and independent of d,n,the vectors, weights and thresholds; degenerate joint covariance and zero weights are allowed. The thresholds may be a_i=u-theta_i with arbitrary theta_i<=0, preserving negative one-sided null means. This is a surface-kernel result and does not itself assert any BH FDR bound.

## Proof

Write \(\phi_r(z)=(2\pi)^{-r/2}\exp(-\lVert z\rVert^2/2)\) for the standard Gaussian density on an \(r\)-dimensional Euclidean space. On the zero-dimensional space \(\{0\}\), Lebesgue measure means unit point mass and \(\phi_0(0)=1\). All products below have finitely many factors.

**Reduction and completion of the frame.** Since \(u\ge1\),
$$
uS(u)\le\int_u^\infty s\phi(s)\,ds=\phi(u),
\qquad h(u)\ge u\ge1.
$$
Replace every threshold by \(u\), and remove constraints whose original weights are zero. Both changes enlarge the event under every canonical conditional law; neither changes \(\beta\). If all original weights are zero, the desired left side is at most \(\phi(0)<1\le\sqrt e\,h(u)\), and \(S(u)^\beta=1\). Hence assume that some positive original weight remains, and let \(\mathcal O\) be the set of retained original indices. Set
$$
A=\{x:v_i\cdot x\ge u\text{ for every }i\in\mathcal O\}.
$$
Diagonalize the positive-semidefinite matrix
\(I_d-\sum_{i\in\mathcal O}c_iv_iv_i^T\). Append one unit eigenvector for each positive eigenvalue, with that eigenvalue as its weight. Let \(\mathcal I\) be the completed index set, retaining the notation \(v_i,c_i\) for all its entries. Every retained or added weight is positive, and
$$
\sum_{i\in\mathcal I}c_iv_iv_i^T=I_d,
\qquad \sum_{i\in\mathcal I}c_i=d,
\qquad \sum_{i\in\mathcal I}c_i(v_i\cdot w)^2=1.
$$
The last two identities follow by taking the trace and the quadratic form at \(w\), respectively. For original and added indices define, respectively,
$$
f_i(s)=\frac{\phi(s)\mathbf1_{[u,\infty)}(s)}{S(u)}
\quad(i\in\mathcal O),
\qquad f_i(s)=\phi(s)\quad(i\in\mathcal I\setminus\mathcal O).
$$
Each \(f_i\) is a probability density. Its supremum \(M_i\) equals \(h(u)\) for an original index, since \(u\ge1\), and equals \(\phi(0)\le h(u)\) for an added index. The completed frame identity gives, for every \(x\in\mathbb R^d\),
$$
F(x):=\prod_{i\in\mathcal I}f_i(v_i\cdot x)^{c_i}
=S(u)^{-\beta}\phi_d(x)\mathbf1_A(x).
\tag{1}
$$
Indeed, the Gaussian exponents sum to \(\lVert x\rVert^2\), their normalizing powers sum to \(d\), and the original normalizing powers sum to \(\beta\). Since all retained weights are positive, the product of the indicator powers is exactly \(\mathbf1_A\). This identity includes all threshold equalities.

**A geometric integral inequality, proved here.** Suppose \(r\ge1\), the vectors \(e_i\in\mathbb R^r\) are unit vectors, the weights \(p_i\) are positive, and
$$
\sum_i p_ie_ie_i^T=I_r.
$$
Suppose also that \(g_i\) is integrable, positive and smooth on a nonempty open interval \(J_i\), and zero outside its closure; its values at finite endpoints may be any finite nonnegative values. The intervals may be unbounded. We prove
$$
\int_{\mathbb R^r}\prod_i g_i(e_i\cdot z)^{p_i}\,dz
\le\prod_i\left(\int_{\mathbb R}g_i(s)\,ds\right)^{p_i}.
\tag{2}
$$
All applications below are positive powers of translated and scaled Gaussian densities, either untruncated or truncated to a half-line, so these hypotheses hold and every scalar integral is strictly positive and finite.

Let \(m_i=\int g_i\) and \(\rho_i=g_i/m_i\). Write \(\Phi(t)=\int_{-\infty}^t\phi(s)\,ds\). On \(J_i\), define the increasing transport
$$
T_i(s)=\Phi^{-1}\left(\int_{\inf J_i}^s\rho_i(t)\,dt\right).
$$
The argument of \(\Phi^{-1}\) lies strictly between zero and one. Thus \(T_i\) is smooth on \(J_i\), with
$$
T_i'(s)>0,\qquad \rho_i(s)=\phi(T_i(s))T_i'(s).
\tag{3}
$$
Let \(D=\{z:e_i\cdot z\in J_i\text{ for every }i\}\), an open convex set. Outside \(D\), the integrand of (2) vanishes except possibly on the finitely many hyperplanes corresponding to finite endpoints of the \(J_i\). These hyperplanes have Lebesgue measure zero because each \(e_i\) is a unit vector. This also proves that the integral is zero if \(D\) is empty, even if the closed support slabs intersect.

Assume \(D\ne\varnothing\) and put
$$
\Theta(z)=\sum_i p_iT_i(e_i\cdot z)e_i,
\qquad D\Theta(z)=\sum_i p_iT_i'(e_i\cdot z)e_ie_i^T.
$$
For every nonzero \(h\), the quadratic form
\(\sum_i p_iT_i'(e_i\cdot z)(e_i\cdot h)^2\) is strictly positive: all derivatives are positive, and \(\sum_i p_i(e_i\cdot h)^2=\lVert h\rVert^2>0\). Thus \(D\Theta(z)\) is positive definite. Furthermore, for distinct \(z,z'\in D\), set \(h=z'-z\). Convexity puts their entire segment in \(D\), and
$$
(\Theta(z')-\Theta(z))\cdot h
=\int_0^1\sum_i p_iT_i'(e_i\cdot(z+th))(e_i\cdot h)^2\,dt>0.
$$
Consequently \(\Theta\) is injective on \(D\).

Two algebraic inequalities give the pointwise comparison needed for change of variables. First, for any real numbers \(a_i\), Cauchy--Schwarz and the frame identity show that, for every unit vector \(t\),
$$
\left|t\cdot\sum_i p_ia_ie_i\right|
\le\left(\sum_i p_ia_i^2\right)^{1/2}
\left(\sum_i p_i(e_i\cdot t)^2\right)^{1/2}
=\left(\sum_i p_ia_i^2\right)^{1/2}.
$$
Taking the supremum over \(t\) yields
$$
\left\lVert\sum_i p_ia_ie_i\right\rVert^2\le\sum_i p_ia_i^2.
\tag{4}
$$
Second, let \(V\) have columns \(\sqrt{p_i}e_i\); then \(VV^T=I_r\). For positive \(q_i\), Cauchy--Binet gives
$$
\det\left(\sum_i p_iq_ie_ie_i^T\right)
=\sum_{|J|=r}\alpha_J\prod_{i\in J}q_i,
\qquad \alpha_J=\det(V_J)^2\ge0.
$$
Evaluating at \(q_i=1\) gives \(\sum_J\alpha_J=1\). Differentiating with respect to \(q_i\) there gives
$$
\sum_{J\ni i}\alpha_J
=\operatorname{tr}(p_ie_ie_i^T)=p_i,
$$
using the derivative of the determinant at \(I_r\). Weighted arithmetic--geometric mean therefore implies
$$
\det\left(\sum_i p_iq_ie_ie_i^T\right)
\ge\prod_{|J|=r}\left(\prod_{i\in J}q_i\right)^{\alpha_J}
=\prod_iq_i^{p_i}.
\tag{5}
$$
Zero \(\alpha_J\) are simply omitted in this product. Taking traces of the frame identity gives \(\sum_i p_i=r\). Combining (3)--(5), with \(a_i=T_i(e_i\cdot z)\) and \(q_i=T_i'(e_i\cdot z)\), yields on \(D\)
$$
\begin{aligned}
\prod_i\rho_i(e_i\cdot z)^{p_i}
&=(2\pi)^{-r/2}
\exp\left(-\frac12\sum_i p_iT_i(e_i\cdot z)^2\right)
\prod_iT_i'(e_i\cdot z)^{p_i}\\
&\le\phi_r(\Theta(z))\det D\Theta(z).
\end{aligned}
$$
The inverse function theorem and injectivity show that \(\Theta:D\to\Theta(D)\) is a \(C^1\) diffeomorphism onto an open subset of \(\mathbb R^r\). Choose an increasing compact exhaustion \(K_k\) of \(D\). Change of variables on each \(K_k\), followed by monotone convergence, gives
$$
\int_D\prod_i\rho_i(e_i\cdot z)^{p_i}\,dz
\le\lim_{k\to\infty}\int_{\Theta(K_k)}\phi_r(t)\,dt
=\int_{\Theta(D)}\phi_r(t)\,dt\le1.
$$
Restoring the constants \(m_i^{p_i}\) proves (2). This argument uses no smoothness at support endpoints. In dimension zero there are no unit directions and no positive projected weights; the corresponding integral is the empty product \(1\) against unit point mass. We use that convention directly below, without transport.

**Integration on the exposed hyperplane.** Fix any real \(y\), put \(H=w^\perp\), and use its Euclidean Lebesgue measure. For \(i\in\mathcal I\), set
$$
b_i=v_i\cdot w,\qquad \ell_i=\sqrt{1-b_i^2},\qquad P_H=I_d-ww^T.
$$
When \(\ell_i>0\), define \(e_i=P_Hv_i/\ell_i\) and \(p_i=c_i\ell_i^2>0\). Restricting the completed frame to \(H\) gives
$$
\sum_{\ell_i>0}p_ie_ie_i^T=I_H.
\tag{6}
$$
Indeed, \(P_Hv_i\) has norm \(\ell_i\), and projection of \(\sum_i c_iv_iv_i^T=I_d\) on both sides gives \(I_H\) when acting on \(H\).

If any index with \(\ell_i=0\) has \(f_i(b_i y)=0\), then \(F(yw+z)=0\) for every \(z\in H\), and there is nothing to bound. Otherwise these indices contribute constant factors at most \(M_i^{c_i}\). For each index with \(\ell_i>0\), put
$$
g_i(s)=f_i(\ell_i s+b_i y)^{1/\ell_i^2}.
$$
This is a power of a Gaussian density, either on \(\mathbb R\) or on the half-line \(s\ge(u-b_i y)/\ell_i\). Its integral satisfies
$$
\begin{aligned}
\int_{\mathbb R}g_i(s)\,ds
&=\ell_i^{-1}\int_{\mathbb R}f_i(t)^{1/\ell_i^2}\,dt\\
&\le\ell_i^{-1}M_i^{1/\ell_i^2-1}\int_{\mathbb R}f_i(t)\,dt
=\ell_i^{-1}M_i^{1/\ell_i^2-1},
\end{aligned}
\tag{7}
$$
since \(0<\ell_i\le1\). Also
\(g_i(e_i\cdot z)^{p_i}=f_i(v_i\cdot(yw+z))^{c_i}\).
If \(d\ge2\), apply (2) on \(H\), using (6) and (7), to obtain
$$
\begin{aligned}
\int_HF(yw+z)\,dz
&\le\prod_{\ell_i=0}M_i^{c_i}
\prod_{\ell_i>0}\left(\ell_i^{-1}M_i^{1/\ell_i^2-1}\right)^{c_i\ell_i^2}\\
&=\left(\prod_{\ell_i>0}\ell_i^{-c_i\ell_i^2}\right)
\prod_{i\in\mathcal I}M_i^{c_ib_i^2}.
\end{aligned}
\tag{8}
$$
In particular, boundary-only intersections of projected half-lines contribute zero by the boundary argument in (2). A constraint constant on the slice was retained outside that argument, with its actual endpoint value.

If \(d=1\), every \(\ell_i=0\), \(H=\{0\}\), and the same bound (8) follows directly from
\(F(yw)\le\prod_iM_i^{c_i}\); here \(b_i^2=1\), \(\sum_i c_i=1\), and the first product in (8) is empty. This direct evaluation includes deterministic threshold equalities, where the conditional event can have probability one.

**The universal constant.** The completed quadratic-form identity implies
$$
\prod_{i\in\mathcal I}M_i^{c_ib_i^2}
\le h(u)^{\sum_i c_ib_i^2}=h(u).
\tag{9}
$$
For \(0\le t<1\), the function \(t+(1-t)\log(1-t)\) has derivative \(-\log(1-t)\ge0\) and value zero at \(t=0\). Hence
$$
-(1-t)\log(1-t)\le t\quad(0\le t\le1),
$$
where the left side at \(t=1\) is its limit zero. Taking \(t=b_i^2\) gives
$$
\log\prod_{\ell_i>0}\ell_i^{-c_i\ell_i^2}
=\frac12\sum_{b_i^2<1}c_i[-(1-b_i^2)\log(1-b_i^2)]
\le\frac12\sum_i c_ib_i^2=\frac12.
\tag{10}
$$
For \(d=1\) the sum on the left is empty, so the same bound holds. Equations (8)--(10) prove
$$
\int_HF(yw+z)\,dz\le\sqrt e\,h(u).
\tag{11}
$$

Finally, under the canonical conditional law the vector is \(yw+Z_H\), where \(Z_H=P_HG_0\) is standard Gaussian on \(H\). Orthogonality gives \(\phi_d(yw+z)=\phi(y)\phi_{d-1}(z)\), so for this particular, arbitrary \(y\),
$$
\int_H\phi_d(yw+z)\mathbf1_A(yw+z)\,dz
=\phi(y)\,\mathbb P\{yw+Z_H\in A\}.
$$
This also holds in dimension one with the specified unit point mass. Integrating the pointwise identity (1) and applying (11) therefore yields
$$
\phi(y)\,\mathbb P\{v_i\cdot G\ge u\text{ for every }i\in\mathcal O\mid w\cdot G=y\}
\le\sqrt e\,h(u)\,S(u)^\beta.
$$
The original conditional event is contained in this enlarged event for every \(y\). This proves the assertion for the original thresholds, including \(a_i=u-\theta_i\) with \(\theta_i\le0\). The argument is pointwise in \(y\), uses no inverse covariance matrix, and imposes no nonsingularity assumption on the joint constraint vector. No BH FDR statement is used or inferred. \(\square\)
