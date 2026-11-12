---
type: idea
title: >-
  Finite entropy of a BH tilt does not imply finite Fisher information or
  log-Sobolev stability
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_entropy_coherence_trace_budget
tags:
  - source-scope
  - fdp-tilt
  - fisher-information
  - entropy
---

Primary-source scope check for a possible transport resource: Ronen Eldan, Joseph Lehec and Yair Shenfeld, Stability of the logarithmic Sobolev inequality via the Follmer Process, official arXiv:1903.04522v2 (29 May 2020), https://arxiv.org/pdf/1903.04522v2. Official authors/title/version and PDF header were verified. A search-indexed NSF copy incorrectly appeared with identifier 1904.02422; official arXiv shows that identifier belongs to an unrelated CNN paper, so do not propagate it.

The paper's Section 3 assumes finite relative Fisher information for its later stated tools; Theorem 6's mixture transport bound contains a dimension factor, and Theorem 8 uses the log-Sobolev deficit rather than the BH field coherence deficit 1-x. These do not directly prove the desired trace payment. No paper, source asset or approved dependency was added.

An original legal finite calibration shows the distinction explicitly. For N=1, theta=0 and T=G, f=1{G>=U}, F=q, and Q has density 1{G>=U}/q relative to standard Gaussian. Its entropy is log(1/q), but its generalized relative Fisher information is infinite: the square-root density has a jump and is not in Gaussian H^1. Treating its almost-everywhere classical derivative as zero would incorrectly omit the distributional boundary. Meanwhile the terminal Mills field b=1/H is constant on Q, so x=1 and our coherence deficit is zero. Thus the two deficits are not interchangeable. Heat regularization could make Fisher information finite, but transferring a resulting inequality back requires a uniform BH boundary/error argument; that bridge is not supplied by the source.
