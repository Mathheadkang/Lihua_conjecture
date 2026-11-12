> AI-generated scoped, normalized working transcription. The author PDF dated 8 May 2024 is authoritative for the locations below. Only definitions needed by Theorem 8(I), that part of the theorem, and its mixture extension in Remark 10 are imported. Other statements and proofs are not transcribed.
> [Author PDF](https://sas.uwaterloo.ca/~wang/papers/2024Chi-Ramdas-Wang-BJ.pdf); [untouched local PDF](../../../research-local/raw_papers/chi2024_negative_dependence.pdf). Printed pp. 5, 7, 10 and 11 visually checked on 8 November 2026. This is not independent extraction verification or researcher approval.

# Multiple testing under negative dependence

Ziyu Chi, Aaditya Ramdas and Ruodu Wang. Author manuscript dated 8 May 2024. Published as Bernoulli 31(2) (2025), 1230-1255, DOI [10.3150/24-BEJ1768](https://doi.org/10.3150/24-BEJ1768). Numbering and pages below refer specifically to the author manuscript, not an assumed mapping to journal pages.

<!-- source-page: 5 -->

## Section 2: Gaussian dependence

A random vector $X=(X_1,\ldots,X_K)$ is Gaussian dependent when $X_k=f_k(Y_k)$ for a jointly Gaussian vector $Y$ and coordinate functions $f_k$ that are all increasing or all decreasing. Monotonicity here is non-strict. A Gaussian correlation of $X$ is the correlation matrix of this latent $Y$. In particular, standard Gaussian statistics give one-sided p-values $P_k=\Phi(-Y_k)$ in this class, where $\Phi$ is the standard normal distribution function.

<!-- source-page: 7 -->

## Section 3.1: Simes function and uniform marginals

For a positive integer $K$, the manuscript writes $\mathcal U$ for standard uniform random variables and works with global-null vectors $P=(P_1,\ldots,P_K)\in\mathcal U^K$, without assuming their independence. For $p\in[0,1]^K$ with ascending order statistics $p_{(k)}$, define
$$
S_K(p)=\min_{1\le k\le K}\frac{K}{k}p_{(k)}.
$$
The Simes test rejects at level $\alpha\in(0,1)$ on $S_K(P)\le\alpha$. The Simes inequality is $\mathbb P(S_K(P)\le\alpha)\le\alpha$.

<!-- source-page: 10 -->

## Section 3.3: Gaussian correlation class

For a $K\times K$ correlation matrix $\Sigma$, $\mathcal G_\Sigma$ is the class of Gaussian-dependent vectors with latent Gaussian correlation $\Sigma$. No invertibility condition is imposed. Standard uniform marginals give the Gaussian-copula case.

<!-- source-page: 11 -->

## Theorem 8(I)

For $P\in\mathcal G_\Sigma\cap\mathcal U^K$, if every off-diagonal entry of $\Sigma$ is nonnegative, then
$$
\mathbb P\bigl(S_K(P)\le\alpha\bigr)\le\alpha
\qquad\text{for all }\alpha\in(0,1).
$$
The manuscript attributes this known statement to Benjamini and Yekutieli and derives it from positive regression dependence. This import records the theorem as sourced; that proof and the regression-dependence machinery are not imported.

## Remark 10: mixture extension of part (I)

The same inequality applies to distributional mixtures of positively Gaussian-dependent p-value vectors. This remark concerns mixtures of vector laws, not treating a non-Gaussian outer mixture as a single Gaussian distribution.

## Scope of this import

Only part (I) and its explicitly stated mixture extension are kept. The unrestricted correlation-matrix hypothesis includes positive semidefinite singular matrices with unit diagonal: joint Gaussian degeneracy is permitted, while the marginal uniforms remain continuous. The paper does not explicitly use the word “singular” in this statement or require a joint density.

The next paragraph of this 2024 manuscript describes general mixed-sign finite-level bounds as open; that historical statement is not a new literature-completeness claim. Remark 11 explicitly separates two-sided Gaussian p-values from the Gaussian-dependent class used here. Neither a general mixed-sign Simes bound nor a two-sided bound is imported.
