---
type: theorem
title: Compact smooth Danskin formula retaining every active maximizer
status: approved
depends_on: []
uses_definitions:
  - lib_bernhard_rapaport1995_compact_smooth_envelope
source:
  kind: paper
  paper_id: bernhard_rapaport1995_danskin
  location: >-
    Theorem 1 (Danskin) and preceding hypotheses, printed p. 1163 (PDF page 1);
    sufficient joint-gradient-continuous specialization
tags:
  - danskin
  - compactness
  - directional_derivative
  - envelope
---

# Compact smooth Danskin formula retaining every active maximizer

## Statement

For a [compact smooth envelope family](../definitions/lib_bernhard_rapaport1995_compact_smooth_envelope.md), with its notation, the right directional derivative exists for every $u,h\in\mathbb R^n$ and obeys
$$
D\overline J(u;h)
=\max_{v\in V(u)}\langle\nabla_uJ(u,v),h\rangle.
$$
The maximum is taken over the entire active set $V(u)$, without selecting a unique optimizer. This is a normalized sufficient smooth form of the introductory source theorem, which Bernhard and Rapaport attribute to Danskin.

## Source scope

The definition imposes explicit joint continuity of the first gradient; the result is not being asserted under separate continuity alone. The source statement on p. 1163 supplies no proof there, and no later D1/D2 variant is imported. Source text was checked online; local PDF preservation and visual formula checking remain incomplete as recorded in the import metadata. This node remains draft pending native independent source checking.

The formula is a deterministic compact envelope analogue. It supplies no rank-survival estimate, derivative-integral interchange, uniform integrability, Gaussian averaging, global particle-potential separation, tag-price certificate, or Gaussian BH FDR bound. Those obligations require their own arguments.
