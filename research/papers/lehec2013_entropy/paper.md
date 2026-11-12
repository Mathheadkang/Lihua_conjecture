> AI-generated scoped working transcription and mathematical paraphrase. The [published PDF](../../../research-local/raw_papers/lehec2013_entropy.pdf) is authoritative. Only the material needed for Theorem 2 is represented; this is not a full-paper transcription or proof verification.

<!-- source-page: 1; printed-page: 885 -->

# Representation formula for the entropy and functional inequalities

Joseph Lehec. Published 2013, volume 49(3), pp. 885–899. DOI: [10.1214/11-AIHP464](https://doi.org/10.1214/11-AIHP464).

<!-- source-page: 2; printed-page: 886 -->

## Setup for §2.2

The source works on continuous paths starting at zero, with Wiener measure, canonical process and its natural filtration. The Cameron–Martin norm is the squared integral of the drift rate. Its relative entropy notation is $H(\mu\mid\gamma)$.

<!-- source-page: 3; printed-page: 887 -->

## Theorem 2: general Föllmer drift

For a probability measure $\mu$ having a density with respect to Wiener measure $\gamma$, an adapted rate $u$ exists. With $U_t=\int_0^t u_s\,ds$, the path $U$ is Cameron–Martin almost surely under $\mu$, $x-U$ is Brownian under $\mu$, and
$$
H(\mu\mid\gamma)=\frac12\mathbb E_\mu\int_0^\infty |u_s|^2\,ds.
$$
No density derivative or Fisher-information assumption appears in this theorem.

<!-- source-page: 4; printed-page: 888 -->

## Source proof status

The paper labels the proof a sketch. It uses the density martingale, Brownian martingale representation, Girsanov and localization; this import does not certify those omitted prerequisites.

<!-- source-page: 8; printed-page: 892 -->

## Separate smooth-bridge restriction

The explicit heat-gradient drift and strong-SDE discussion in §2.5 later imposes Lipschitz regularity on $\rho$ and $\nabla\rho$, and a positive lower bound on $\rho$. Those hypotheses are not part of Theorem 2 and are not claimed for discontinuous BH terminal densities. The other pages are not transcribed here.
