---
type: idea
title: >-
  Test finite one-factor extremality against three centered nulls with a
  negative correlation triangle
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - unproved_probe
  - finite_extremality
  - negative_cycle
---

Optional falsification gate for a proposed finite-N one-common-factor extremality reduction, not a counterexample or an established comparison. Take N=3 and all hypotheses truly null, with centered means. Coordinatewise lowering of these all-null means lowers the event R>0, so their FDR maximum over nonpositive means occurs at zero without invoking the false mixed-null/alternative monotonicity claim. A general 3x3 correlation matrix may have all three off-diagonal correlations negative (equicorrelation rho in [-1/2,0)), while a one-common-factor matrix has correlations a_i a_j and product (a1 a2 a3)^2>=0. Compare the complete Gaussian BH/Simes rejection probability of a negative triangle with the GLOBAL one-factor maximum over a_i in [-1,1], including degenerate/tied boundaries and q-dependent near-boundary regimes. The mere covariance sign difference does not prove objective superiority. A numerical grid maximum or one candidate's FDR above q is insufficient; a valid obstruction needs a certified uniform upper bound on the whole one-factor class. If finite exact extremality fails only in an O(q) or smaller remainder, that does not refute the original q sqrt(log(1/q)) asymptotic conjecture or an approximate extremality reduction with a proved lower-order slack. The old negative-equicorrelation search-board family was not a target counterexample, so its q-scale behavior could still be informative for this stronger finite extremality gate.
