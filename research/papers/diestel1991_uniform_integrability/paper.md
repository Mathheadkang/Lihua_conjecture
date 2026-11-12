> AI-generated scoped mathematical transcription, not a full-paper transcription. The [untouched publisher PDF](../../../research-local/raw_papers/diestel1991_uniform_integrability.pdf) is authoritative. Only the retained definitions, Theorems 1 and 3 and selected proof formulas are normalized here. Source proofs were visually inspected on printed pp. 41-43 and 46-50; complete proofs remain in the PDF. All other prose, examples and theorems are omitted. No OCR text is used: the PDF has no text layer and native OCR failed. New Library nodes remain draft.

# Uniform integrability: an introduction

Joe Diestel. Rendiconti dell'Istituto di Matematica dell'Universita di Trieste 23 (1991), 41-80.

<!-- source-page: 1; printed-page: 41 -->

## Probability-space definition and Theorem 1

$(\Omega,\Sigma,P)$ is an arbitrary probability space; $K\subset L_1(P)$ is scalar-valued. Uniform integrability means
$$
\lim_{c\to\infty}\sup_{f\in K}\int_{\{|f|>c\}}|f|\,dP=0.
$$
Theorem 1 equates this with
$$
\sup_{f\in K}\|f\|_1<\infty,\qquad
\forall\epsilon>0\ \exists\delta>0:\quad P(E)\le\delta\Longrightarrow\sup_{f\in K}\int_E|f|\,dP\le\epsilon.
$$

<!-- source-page: 2; printed-page: 42 -->

## Theorem 1: proof formulas

$$
\int_E|f|\,dP\le cP(E)+\int_{\{|f|>c\}}|f|\,dP,
\qquad cP(|f|>c)\le\|f\|_1.
$$

<!-- source-page: 3; printed-page: 43 -->

## Theorem 1: proof endpoint

$$
M=\sup_{f\in K}\|f\|_1<\infty\Longrightarrow P(|f|>c)\le M/c.
$$
[Omitted: examples, Theorem 2 and remaining page content.]

<!-- source-page: 4; printed-page: 44 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 5; printed-page: 45 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 6; printed-page: 46 -->

## Theorem 3 (Dunford-Pettis) and dual pairing

$$
K\subset L_1(P):\qquad K\text{ is relatively weakly compact}\quad\Longleftrightarrow\quad K\text{ is uniformly integrable}.
$$
$$
L_1(P)^*=L_\infty(P),\qquad \langle f,g\rangle=\int_\Omega fg\,dP.
$$
[Omitted: explanatory duality prose.]

<!-- source-page: 7; printed-page: 47 -->

## Theorem 3: forward proof endpoint

For a weak-star closure point $\mu$ in $L_\infty(P)^*$,
$$
|\mu(E)|\le\sup_{f\in K}\left|\int_E f\,dP\right|\le\sup_{f\in K}\int_E|f|\,dP.
$$
Uniform absolute continuity forces countable additivity and $P$-absolute continuity; Radon-Nikodym returns an $L_1(P)$ density.

## Theorem 4 used in the converse

$$
\sup_n\|f_n\|_1<\infty,\quad\forall E\in\Sigma:\ \int_E f_n\,dP\longrightarrow0
\quad\Longrightarrow\quad\{f_n:n\ge1\}\text{ is uniformly integrable}.
$$
[Omitted: full argument; inspect printed pp. 47-50 in the PDF.]

<!-- source-page: 8; printed-page: 48 -->
[Omitted: Theorem 4 gliding-hump proof; source page visually checked.]

<!-- source-page: 9; printed-page: 49 -->
[Omitted: Theorem 4 gliding-hump proof continuation; source page visually checked.]

<!-- source-page: 10; printed-page: 50 -->
[Omitted: Theorem 4 proof conclusion, completion of Theorem 3's converse, and subsequent material; source page visually checked. The converse takes a weakly convergent subsequence, subtracts its limit, and applies Theorem 4.]

<!-- source-page: 11; printed-page: 51 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 12; printed-page: 52 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 13; printed-page: 53 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 14; printed-page: 54 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 15; printed-page: 55 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 16; printed-page: 56 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 17; printed-page: 57 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 18; printed-page: 58 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 19; printed-page: 59 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 20; printed-page: 60 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 21; printed-page: 61 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 22; printed-page: 62 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 23; printed-page: 63 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 24; printed-page: 64 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 25; printed-page: 65 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 26; printed-page: 66 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 27; printed-page: 67 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 28; printed-page: 68 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 29; printed-page: 69 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 30; printed-page: 70 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 31; printed-page: 71 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 32; printed-page: 72 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 33; printed-page: 73 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 34; printed-page: 74 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 35; printed-page: 75 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 36; printed-page: 76 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 37; printed-page: 77 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 38; printed-page: 78 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 39; printed-page: 79 -->
[Omitted: page outside extraction scope.]

<!-- source-page: 40; printed-page: 80 -->
[Omitted: page outside extraction scope.]

