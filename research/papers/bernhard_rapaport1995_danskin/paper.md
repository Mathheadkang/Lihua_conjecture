> PARTIAL AI-generated mathematical working extraction. The linked published PDF is authoritative. This is a paraphrase of one result, not a complete transcription. No local raw PDF was obtained: shell retrieval was blocked. No formula-image inspection was completed.

# On a theorem of Danskin with an application to a theorem of Von Neumann-Sion

Pierre Bernhard and Alain Rapaport, Nonlinear Analysis: Theory, Methods & Applications 24(8), 1163–1181 (1995). [DOI](https://doi.org/10.1016/0362-546X(94)00186-L); [author-hosted published PDF](https://www-sop.inria.fr/members/Pierre.Bernhard/publications/berrap95.pdf).

<!-- source-page: 1; printed-page: 1163 -->

## Theorem 1 (Danskin): sufficient compact smooth form

The introductory theorem is attributed to Danskin. For a nonempty compact topological space $V$, take $J:\mathbb R^n\times V\to\mathbb R$, continuously differentiable in its first variable. For this extraction, explicitly require joint continuity of both $J$ and $\nabla_uJ$. This is a sufficient smooth specialization, avoiding an interpretation based only on separate continuity.

Define
$$
\overline J(u)=\max_{v\in V}J(u,v),\qquad
V(u)=\{v\in V:J(u,v)=\overline J(u)\}.
$$
For $u,h\in\mathbb R^n$, the right directional derivative satisfies
$$
\lim_{t\downarrow0}\frac{\overline J(u+th)-\overline J(u)}{t}
=\max_{v\in V(u)}\langle\nabla_uJ(u,v),h\rangle.
$$

The whole active set enters the maximum. The source gives this introductory statement without a proof there; this extraction does not import the later generalizations or their proofs.

<!-- omitted: remainder of printed p.1163 and all printed pp.1164–1181 -->

## Project applicability and limits

Use only after establishing the compact parameter set and joint smoothness for the particular objective. Applying it to a negative objective yields an active-minimum formula, but that corollary is not separately extracted. Actual BH rank escape, integration and uniform integrability, Gaussian averaging, posterior tightness, and global particle-potential separation remain separate project obligations. No BH bound follows from this source alone.
