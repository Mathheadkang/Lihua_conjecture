---
type: definition
title: Definition (ordinary Benjamini-Hochberg step-up procedure)
status: approved
source:
  kind: original
depends_on: []
tags:
  - benjamini_hochberg
  - step_up
  - multiple_testing
---

## Definition

For a positive integer $N$, p-values $p=(p_1,\ldots,p_N)\in[0,1]^N$, and level $q\in(0,1)$, write $p_{(1)}\leq\cdots\leq p_{(N)}$ for the order statistics, including multiplicities. The ordinary Benjamini-Hochberg step-up procedure sets
$$
\widehat k_q(p)=\max\bigl(\{0\}\cup\{k\in\{1,\ldots,N\}:p_{(k)}\leq qk/N\}\bigr).
$$
Its rejection set is
$$
\mathcal R_q(p)=\begin{cases}
\{i\in\{1,\ldots,N\}:p_i\leq q\widehat k_q(p)/N\},&\widehat k_q(p)>0,\\
\varnothing,&\widehat k_q(p)=0.
\end{cases}
$$
The number of rejections is $R_q(p)=|\mathcal R_q(p)|$. This definition uses the largest qualifying rank, non-strict threshold inequalities, and no dependence correction.
