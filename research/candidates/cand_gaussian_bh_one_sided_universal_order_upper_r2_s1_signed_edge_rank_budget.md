---
type: candidate
title: Growing-rank signed-edge rare alternatives below one null-block rank budget
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:05:08.223Z'
extension_version: 0.0.4
---

## Object

For each integer j>=2, put q_j=exp(-j^2), d_j=ceil(exp(j^2)), L_j=ceil(exp(3j^2)), M_j=d_j(d_j-1)/2, and N_j=d_j L_j+M_j. Let U_j=S^{-1}(q_j), where S is the standard normal survival function, and let G_1,...,G_d_j be independent standard normals. For every a in {1,...,d_j}, include L_j exactly identical true-null statistics T_a,l=G_a, with means zero. For every unordered pair {a,b}, include one alternative
$$
T_{a,b}^{\mathrm{alt}}=U_j-\frac{G_a+G_b}{\sqrt2}.
$$
Run ordinary one-sided BH on all N_j statistics at q_j, retaining every multiplicity and the original largest qualifying rank.

The null span has dimension d_j tending to infinity. Alternative directions are the signed edge directions -(e_a+e_b)/sqrt(2), and their rejection counts adapt to pairwise Gaussian sums. This is neither the scalar common-factor conditional-independence profile family nor the null-span-two family. The total alternative fraction is asymptotic to (1/2)exp(-2j^2). The decisive restriction is stronger: M_j<L_j, so all alternatives together have fewer coordinates than one exact null block.

## Checks

### H1

q_j lies in (0,1/16] and tends to zero. A counterexample sequence must make FDR_j/[q_j sqrt(log(1/q_j))] unbounded.

### H2

d_j,L_j,M_j,N_j are finite positive integers. Since d_j<=2exp(j^2), one has M_j<2exp(2j^2)<exp(3j^2)<=L_j for j>=2.

### H3

All d_j L_j null means are zero. All M_j alternative means equal U_j>0, and are finite. Therefore the original true-null set consists exactly of the cloned coordinate statistics.

### H4

All coordinates are linear functions of the independent Gaussian vector G with the displayed deterministic means. The loading vectors e_a and -(e_a+e_b)/sqrt(2) are unit vectors. Consequently the covariance is a positive-semidefinite, unit-diagonal Gram matrix of rank d_j, including the permitted singularity from cloning. Null-alternative correlations are negative on incident edges, while nonincident coordinates need not share a scalar conditioning variable.

### H5

The p-values are exactly S(T). The BH rank is the largest k satisfying p_(k)<=q_j k/N_j, with ties and all multiplicities. All bounds below use its actual rejection count R and actual number V of false rejections.

### NOT

Fail. Let K be the number of rejected null blocks. Exact null ties imply V=K L_j. If K=k>=1, then every rejected null block has its common p-value at most q_j R/N_j, and
$$
R\le kL_j+M_j<(k+1)L_j,\qquad
\frac{q_jR}{N_j}\le\frac{q_j(k+1)}{d_j}.
$$
The d_j block p-values P_a=S(G_a) are independent uniforms. Hence the event K=k implies P_(k)<=q_j(k+1)/d_j. By a union bound over k and then over k-subsets of the d_j independent uniforms,
$$
\operatorname{FDR}_j\le\Pr(V>0)
\le\sum_{k=1}^{d_j}\Pr\left\{P_{(k)}\le\frac{q_j(k+1)}{d_j}\right\}
\le\sum_{k=1}^{d_j}\frac{(k+1)^k}{k!}q_j^k.
$$
Writing a_k=(k+1)^k/k!, one has a_1=2 and
$$
\frac{a_{k+1}}{a_k}=\left(1+\frac1{k+1}\right)^{k+1}<e.
$$
Therefore, for q_j<=1/16,
$$
\operatorname{FDR}_j\le\frac{2q_j}{1-eq_j}\le3q_j,
\qquad
\frac{\operatorname{FDR}_j}{q_j\sqrt{\log(1/q_j)}}\le\frac3j.
$$
This bound neither substitutes a smaller BH crossing nor conditions away any signed covariance. It allows arbitrary alternative statistics and means provided their total number remains below L_j, but relies on independent, equally sized exact null blocks. Small alternative proportion alone does not imply this block-budget hypothesis, and the argument does not apply to arbitrary null geometry or nonuniform null weights.

## Failure

NOT fails: all signed-edge alternatives together fit below one independent null block, forcing a shifted independent-uniform rank event and FDR_j<=3q_j.
