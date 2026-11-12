---
type: definition
title: Definition (false discovery rate)
status: approved
source:
  kind: original
depends_on: []
tags:
  - fdr
  - multiple_testing
  - error_rate
---

## Definition

For a positive integer $N$, a fixed true-null set $I_0\subseteq\{1,\ldots,N\}$, and a random rejection set $\mathcal R\subseteq\{1,\ldots,N\}$ under a specified sampling law, define the rejection count $R=|\mathcal R|$ and the false-rejection count $V=|\mathcal R\cap I_0|$. The false discovery proportion and false discovery rate are
$$
\operatorname{FDP}=\frac{V}{R\vee1},\qquad \operatorname{FDR}=\mathbb E\!\left[\frac{V}{R\vee1}\right],\qquad R\vee1=\max\{R,1\}.
$$
In particular, the false discovery proportion is zero when there are no rejections. Expectation always refers to the full sampling law of the rejection set.
