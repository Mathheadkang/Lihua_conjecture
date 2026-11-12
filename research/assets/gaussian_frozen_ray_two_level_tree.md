---
title: Sharp frozen-ray truncated moment and maximal tail for two-level Gaussian trees
type: theorem
status: draft
source:
  kind: original
  note: Researcher-authorized intermediate target of 10 November 2026; an unproved two-level-tree restriction of the frozen-ray conjecture.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
tags:
  - cross-discipline-brainstorm-20261110
  - frozen-ray
  - two-level-gaussian-tree
---

# Sharp frozen-ray truncated moment and maximal tail for two-level Gaussian trees

## Statement

Let $b_1,b_2$ be arbitrary positive integers and let $a\in[0,1]$ be arbitrary. Let all random variables
$$
G_i\quad(1\leq i\leq b_1),\qquad
G_{ij}\quad(1\leq i\leq b_1,\ 1\leq j\leq b_2)
$$
be mutually independent standard normal random variables, and set
$$
Z_{ij}=\sqrt a\,G_i+\sqrt{1-a}\,G_{ij}.
$$
The vector $(Z_{ij})$ is a centered unit-variance [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). For every real $w\geq0$ define
$$
L_w(Z)=\frac1{b_1b_2}\sum_{i=1}^{b_1}\sum_{j=1}^{b_2}
\exp\!\left(wZ_{ij}-\frac{w^2}{2}\right),\qquad
\Lambda(Z)=\sup_{w\geq0}L_w(Z).
$$
The same realization of all $G_i,G_{ij}$ is used for every $w$ in this supremum. All probabilities and expectations are under their stated joint Gaussian law; logarithms are natural.

There exist finite constants $C_{\mathrm{sh}}>0$ and $C_{\mathrm{tail}}>0$ such that, simultaneously for every $b_1,b_2\geq1$, $a\in[0,1]$, real $c\geq2$, and real $\alpha\geq2$,
$$
\mathbb E\min\{c,\Lambda(Z)\}
\leq\sqrt{\frac{\log c}{\pi}}+C_{\mathrm{sh}},
$$
$$
\mathbb P\{\Lambda(Z)\geq\alpha\}
\leq\frac{C_{\mathrm{tail}}}{\alpha\sqrt{\log\alpha}}.
$$
Both constants are independent of $b_1,b_2,a,c,\alpha$. The cases $a=0$, $a=1$, $b_1=1$, and $b_2=1$ are included, including the singular covariance at $a=1$ when $b_2>1$. No size limit, separation of transitions, or restriction on the relative growth of the parameters is imposed. Both displayed assertions with their exact coefficient and maximal-tail scale are required; the weaker order bound alone does not establish this target.

## Motivation

This restriction of the [frozen-ray maximal likelihood-ratio idea](../ideas/idea_9f8ffb204424.md) retains a nontrivial hierarchy while including independent and fully collapsed endpoints. The [planted-SNR program](../ideas/idea_dc6cf14ab94d.md), [Gibbs variational form](../ideas/idea_c36aadbe5f06.md), and [tail calibration](../ideas/idea_76d8bdfb8584.md) remain unverified candidate tools. The [stress-test program](../ideas/idea_57338934f2f7.md) records possible secondary-transition diagnostics; finite-grid excess and Monte Carlo behavior do not establish a counterexample or a proof.

The [structured-class program](../ideas/idea_7727ae2d6679.md) is related motivation only. No general Gaussian BH reduction or implication to that program is asserted. This asset has no proof; native counterexample search must precede its proof plan.
