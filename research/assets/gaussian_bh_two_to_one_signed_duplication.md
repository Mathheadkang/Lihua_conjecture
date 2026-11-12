---
type: lemma
title: Exact signed-duplication reduction from two-sided to one-sided Gaussian BH
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian_bh
  - signed_duplication
  - finite_model_reduction
---

## Statement

Let $N\geq1$, $\theta\in\mathbb R^N$, $\Sigma\in\mathcal C_N$, and $T\sim\mathcal N_N(\theta,\Sigma)$ be any admissible [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), including singular $\Sigma$. Fix any $q\in(0,1/2)$. Form the signed duplication
$$
X=(T_1,\ldots,T_N,-T_1,\ldots,-T_N),\qquad
\widetilde\theta=(\theta,-\theta),\qquad
\widetilde\Sigma=
\begin{pmatrix}\Sigma&-\Sigma\\-\Sigma&\Sigma\end{pmatrix}.
$$
Then $(2N,\widetilde\theta,\widetilde\Sigma)$ is an admissible Gaussian model, with no nonsingularity assumption. Index its coordinates as $(i,+)$ and $(i,-)$, meaning coordinate $i$ and coordinate $N+i$, respectively. The [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) for the original two-sided and duplicated one-sided models are
$$
p_i=2\overline\Phi(|T_i|),\qquad
I_0^{(2)}=\{i\in[N]:\theta_i=0\},
$$
$$
u_{i,+}=\overline\Phi(T_i),\qquad
u_{i,-}=\overline\Phi(-T_i),\qquad
\widetilde I_0^{(1)}
=\{(i,+):\theta_i\leq0\}\cup\{(i,-):\theta_i\geq0\}.
$$
Apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at the same level $q$ to $p\in[0,1]^N$ and $u\in[0,1]^{2N}$. Write their rejection sets as $\mathcal R_2$ and $\mathcal R_1$, their rejection counts as $R_2$ and $R_1$, and their false-rejection counts as
$$
V_2=|\mathcal R_2\cap I_0^{(2)}|,\qquad
V_1=|\mathcal R_1\cap\widetilde I_0^{(1)}|.
$$
Order statistics include multiplicities, every BH comparison is non-strict, the largest qualifying rank is used, and the rejection set is empty when no positive rank qualifies, exactly as in that definition.

For every realization $T=t\in\mathbb R^N$, the following exact identities and inequalities hold:
$$
\mathcal R_1
=\{(i,+):i\in\mathcal R_2,\ t_i>0\}
\cup\{(i,-):i\in\mathcal R_2,\ t_i<0\},
\qquad R_1=R_2,\qquad V_1\geq V_2.
$$
In particular, at most one signed copy of any index is rejected, and an index with $t_i=0$ has neither signed copy rejected and is itself not rejected. The identities include arbitrary ties, including ties at a BH threshold. Each original true null has both signed means zero and contributes exactly one false rejection whenever it is rejected. If $\theta_i\ne0$, exactly one signed coordinate has negative mean and is a one-sided true null; its rejection may add to $V_1$.

Consequently, using the [false discovery rate](../definitions/false_discovery_rate.md) convention $V/(R\vee1)=0$ when $R=0$,
$$
\frac{V_2}{R_2\vee1}\leq\frac{V_1}{R_1\vee1}
\quad\text{for every realization},
$$
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;N,\theta,\Sigma)
\leq
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;2N,\widetilde\theta,\widetilde\Sigma).
$$
Taking the suprema in the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) gives the standalone reduction
$$
F_2(q)\leq F_1(q),\qquad 0<q<1/2.
$$
This statement asserts no uniform finite-constant upper bound for either function.

## Proof

Step 1. For $a,b\in\mathbb R^N$,
$$
(a,b)^{\mathsf T}(X-\widetilde\theta)=(a-b)^{\mathsf T}(T-\theta).
$$
This is centered normal with variance $(a-b)^{\mathsf T}\Sigma(a-b)=(a,b)^{\mathsf T}\widetilde\Sigma(a,b)$, including variance zero. The block matrix $\widetilde\Sigma$ is symmetric, its displayed quadratic form is nonnegative, and its $2N$ diagonal entries are the diagonal entries of $\Sigma$, hence all one. Thus $X$ has exactly the asserted admissible Gaussian law even for singular $\Sigma$.


Step 2. For a positive integer $m$, let $z\in[0,1]^m$ and let $h=\widehat k_q(z)$. If $h=0$, the prescribed rejection set is empty. If $h>0$, its cardinality $r$ satisfies $r\geq h$ because $z_{(h)}\leq qh/m$. If $r>h$, then $z_{(r)}\leq qh/m\leq qr/m$, so rank $r$ also qualifies, contradicting maximality of $h$. Thus the rejection cardinality equals $h$. This uses multiplicities and non-strict comparisons, with no assumption excluding ties.


Step 3. Fix $t\in\mathbb R^N$. Symmetry of the normal density gives $\overline\Phi(-t_i)=1-\overline\Phi(t_i)$, so the signed pair is the multiset $\{a_i,b_i\}$, where $a_i=\overline\Phi(|t_i|)=p_i/2\leq1/2$ and $b_i=1-a_i\geq1/2$. Sorting the $a_i$ in nondecreasing order, followed by the $b_i$ in nondecreasing order, gives a nondecreasing ordering of the full signed multiset; ties at $1/2$ do not change its numerical order statistics. Therefore
$$
u_{(k)}=p_{(k)}/2\quad(1\leq k\leq N),\qquad u_{(k)}\geq1/2\quad(N<k\leq2N).
$$
Every signed BH threshold $qk/(2N)$ is at most $q<1/2$, so no rank $k>N$ qualifies. For $k\leq N$, the signed qualifying inequality is precisely $p_{(k)}/2\leq qk/(2N)$, equivalent to $p_{(k)}\leq qk/N$. Both procedures therefore select the same rank $K$, including $K=0$. Step 2 gives $R_1=R_2=K$.


Step 4. If $K=0$, both rejection sets are empty. For $K>0$, the signed threshold $\tau=qK/(2N)$ is strictly below $1/2$. Thus a signed pair contributes a rejection exactly when $a_i=p_i/2\leq\tau$, or equivalently $p_i\leq qK/N$, which is precisely $i\in\mathcal R_2$. When $t_i>0$, its unique smaller member is $u_{i,+}$; when $t_i<0$, it is $u_{i,-}$. When $t_i=0$, both signed values equal $1/2$ and $p_i=1>qK/N$, so none is rejected. This proves the complete asserted rejection-set identity for every real vector, including equality at either BH threshold.


Step 5. If $\theta_i=0$, both duplicated means are zero. By step 4, each rejected original true null contributes exactly one rejected signed true null; different original indices give different signed coordinates. Hence $V_1\geq V_2$. If $\theta_i\ne0$, the two means $\theta_i$ and $-\theta_i$ have opposite strict signs, so exactly one is negative and belongs to the one-sided true-null set. Its possible rejection adds to $V_1$ and does not contribute to $V_2$. This uses fixed null labels and no monotonicity in means.


Step 6. The equality $R_1=R_2$ and inequality $V_1\geq V_2$ give the claimed FDP comparison with common denominator $R_1\vee1=R_2\vee1$. If $K=0$, both FDPs are zero. These bounded random variables can be integrated under the original Gaussian law. Step 1 identifies the law of its signed image as the duplicated admissible model, giving the finite-model FDR comparison. For fixed $q$, this duplicated model is one member of the supremum defining $F_1(q)$, so every original two-sided model has FDR at most $F_1(q)$. Taking the full two-sided supremum gives $F_2(q)\leq F_1(q)$. No attainment or limit exchange is needed, and no upper bound for either function is assumed.
