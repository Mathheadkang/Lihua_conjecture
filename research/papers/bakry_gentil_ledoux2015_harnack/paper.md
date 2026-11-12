> AI-generated partial mathematical working extraction. The [untouched author PDF](../../../research-local/raw_papers/bakry_gentil_ledoux2015_harnack.pdf) is authoritative. Context is paraphrased; displayed mathematics is normalized from the source. Only the marked passages below are covered. No whole-paper coverage, independent correctness verdict, or researcher review is claimed.

# On Harnack inequalities and optimal transportation

Dominique Bakry, Ivan Gentil and Michel Ledoux. Published in Ann. Sc. Norm. Super. Pisa Cl. Sci. (5), XIV(3) (2015), 705-727, DOI [10.2422/2036-2145.201210_007](https://doi.org/10.2422/2036-2145.201210_007). These locations refer to the 22-page [author manuscript](https://www.math.univ-toulouse.fr/~ledoux/Harnack.pdf), rather than unverified journal numbering.

<!-- source-page: 1 -->

## Scope of the source setup

The source introduces the diffusion generator $L=\Delta-\nabla V\cdot\nabla$ on a smooth complete connected Riemannian manifold, with smooth potential $V$ and invariant symmetric measure $d\mu=e^{-V}dx$. Introductory Harnack inequalities and surrounding prose are omitted.

<!-- source-page: 2 -->

## Curvature normalization needed for the Gaussian specialization

The source's equation (3), with dimension parameter $N=\infty$, is
$$
\frac12L(|\nabla f|^2)-\nabla f\cdot\nabla Lf\geq K|\nabla f|^2.
$$
For the Ornstein-Uhlenbeck generator associated with the quadratic potential on Euclidean space, the text explicitly gives $K=1$, $N=\infty$. The equivalent weighted Riemannian condition, equation (4), is $\operatorname{Ric}+\operatorname{Hess}(V)\geq K$. Its gradient commutation equation (6) is
$$
|\nabla P_tg|\leq e^{-Kt}P_t(|\nabla g|).
$$
Other material on this page and all material on pages 3-6 are omitted.

<!-- source-page: 7 -->

## Standing framework immediately before Section 2

The source again specifies a complete connected weighted Riemannian manifold, invariant reversible measure $e^{-V}dx$ (not required to be a probability), and curvature condition $CD(K,\infty)$. Only the Gaussian Euclidean case is extracted into the Library; transport, EVI and the more general diffusion setting are omitted.

<!-- source-page: 8 -->

## Gaussian profile and Proposition 2.1

The profile is $I=\varphi\circ\Phi^{-1}$ on $(0,1)$, where $\Phi(x)=\int_{-\infty}^x(2\pi)^{-1/2}e^{-u^2/2}\,du$ and $\varphi=\Phi'$. It extends continuously to $I(0)=I(1)=0$. The source lists concavity, symmetry about $1/2$, and
$$
I(v)I''(v)=-1\quad(0<v<1),\qquad
I(v)\sim v\sqrt{2\log(1/v)}\quad(v\downarrow0).
$$
Proposition 2.1 assumes $CD(K,\infty)$, $K\in\mathbb R$. For every measurable $f:M\to[0,1]$ and $t>0$, its displayed equation (16) is
$$
[I(P_tf)]^2-[P_t(I(f))]^2\geq\sigma(t)|\nabla P_tf|^2,
\qquad
\sigma(t)=\frac{e^{2Kt}-1}{K},
$$
with $\sigma(t)=2t$ at $K=0$. The two squares are outside $I(P_tf)$ and $P_t(I(f))$, respectively. This equation is on printed/PDF page 8, not page 9.

The proof begins by taking $\varepsilon\leq f\leq1-\varepsilon$, $\varepsilon>0$.

<!-- source-page: 9 -->

## Proposition 2.1 proof and explicit gradient consequence

The source interpolates $[P_s(I(P_{t-s}f))]^2$ from $s=0$ to $s=t$. The chain rule and $II''=-1$ give
$$
-\frac{d}{ds}[P_s(I(P_{t-s}f))]^2
=2P_s(I(P_{t-s}f))P_s\left(\frac{|\nabla P_{t-s}f|^2}{I(P_{t-s}f)}\right).
$$
Kernel Cauchy-Schwarz bounds this from below by $2[P_s(|\nabla P_{t-s}f|)]^2$. Applying equation (6) yields
$$
[I(P_tf)]^2-[P_t(I(f))]^2
\geq 2\int_0^t e^{2Ks}\,ds\,|\nabla P_tf|^2.
$$
The source then states, in the explanation of Corollary 2.2, the gradient consequence
$$
|\nabla P_tf|\leq\frac{I(P_tf)}{\sqrt{\sigma(t)}}.
$$
The source statement includes arbitrary measurable $[0,1]$-valued functions; its displayed proof does not detail the limiting/smoothing argument removing the initial $\varepsilon$ restriction. This distinction is preserved for independent checking.

Corollary 2.2's Harnack conclusion, all subsequent content on pages 10-22, and external references cited by the source are not extracted. In particular, this paper is not a source for a BH-specific signed budget bridge or a universal Gaussian BH FDR bound. Time-integrated gradient bounds for the project's convention require a separate derivation using the imported analytic estimates.
