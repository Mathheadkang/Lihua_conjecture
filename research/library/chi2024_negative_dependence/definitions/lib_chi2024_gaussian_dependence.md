---
type: definition
title: >-
  Definition (Gaussian dependence and latent Gaussian correlation in
  Chi-Ramdas-Wang)
status: approved
source:
  kind: paper
  paper_id: chi2024_negative_dependence
  location: >-
    Author manuscript dated 8 May 2024, Section 2 printed p. 5 and Section 3.3
    printed p. 10
depends_on: []
tags:
  - gaussian_dependence
  - correlation
  - simes
---

# Definition (Gaussian dependence and latent Gaussian correlation in Chi-Ramdas-Wang)

Let $K\ge1$ be an integer. A real random vector $X=(X_1,\ldots,X_K)$ is Gaussian dependent if there are a jointly Gaussian vector $Y=(Y_1,\ldots,Y_K)$ and measurable functions $f_1,\ldots,f_K$ that are all nondecreasing or all nonincreasing, such that $X_k=f_k(Y_k)$ for every $k$. The correlation matrix $\Sigma$ of the latent $Y$ is called a Gaussian correlation of $X$; the marginal variances used to form that correlation are positive.

For a $K\times K$ correlation matrix $\Sigma$, the source writes $\mathcal G_\Sigma$ for the class of all such Gaussian-dependent vectors with Gaussian correlation $\Sigma$. Correlation matrix means a symmetric positive-semidefinite real matrix with diagonal entries one. No inverse of $\Sigma$ or joint density is required, and the jointly Gaussian vector may be degenerate.

For example, if $Y$ has standard normal marginals, $P_k=\Phi(-Y_k)$ is a concordant decreasing transform, where $\Phi$ is the standard normal distribution function. The matrix $\Sigma$ refers to the latent Gaussian correlation, not the covariance matrix of the transformed coordinates.
