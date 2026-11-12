---
id: plan_large_u_exq_extended_quarter_transport_20261106_native
title: >-
  Reprove large-U EX-Q by extended quarter distance and two-sign carrier
  transport
type: plan
status: succeeded
target_asset: gaussian_bh_two_sign_curve_exclusion_large_u_exq
inspired_by:
  - idea_41e71c79a5f9
  - idea_e1601340f964
adapts:
  - gaussian_bh_two_sign_curve_exclusion_exq
proof_digest: b93eb01327bbafad7d93d287c30458da166d9566e2657429353537216fd6a92b
statement_digest: 422a8915f80d37bc2594b42629202589fe6eb5d11efe2e43269d21df06b3e719
dependency_digests:
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
verified_proof_digest: b93eb01327bbafad7d93d287c30458da166d9566e2657429353537216fd6a92b
---

## Goal

Target: [Large-U two-sign deficit-curve exclusion EX-Q](../assets/gaussian_bh_two_sign_curve_exclusion_large_u_exq.md).

Prove both conclusions (a) and (b) of the exact current Statement, including the stronger later-point assertion in (a) requiring only tilt. Retain all positive integers N, all q,r in (0,1) satisfying U>=1, L<=U, and r²<U; arbitrary finite nondecreasing integer rank curves D*, arbitrary finite mate families (including empty), arbitrary real means and fixed noises, and every loading in [-1,1]. Assume only the explicitly stated nonempty qualifying set defining R at every real z. Do not impose D*(1)<=0, bounded increments, finite quarter distance, flatness, independence, a block model, a dimension bound, or a probability good event.

The target's Proof is empty and this plan is not a verdict on either the old exact-source claim or an unrestricted main target. Starting file SHA256 values: target `78faefcfde0c077c50dd4c968d280803414fdec5646de92101e5ac054c56d575`; adaptation candidate `e402183f8be769af9689de20d41ee00fcd25c007202f81b3366446b67be73d8d`. Re-read the current target before execution and use its full Statement; do not restore a preparation snapshot.

## Plan

1. [x] **Definitions, signs, ties, and measurability.** Reconstruct the Setting of `gaussian_bh_two_sign_curve_exclusion_exq`, replacing its overloaded notation everywhere by the distinct rank curve D*(k) and level curve D*lev(w). Show u_k strictly decreases, u_N=U>0, k(u_k)=k, and D*lev is nonincreasing on [U,infinity), including its constant extension beyond u_1. Check K>=0, J>=1, L-K=sqrt(U), ell=(1-r)U+K>=0, and 1-r²/U>0; hence B is a nonnegative extended real. For each finite j,k, the set |Y_j(z)|>=u_k is Borel with finitely many boundary points unless constant, in which case it is empty or all of R. Thus M, the everywhere-defined finite-valued R, v, and the carrier counts are Borel, and S_+ and S_- are measurable; retain all isolated threshold-equality points. This argument must include a_j=0 and |a_j|=1, arbitrary fixed noises, N=1, and empty mates without dividing by a zero loading. In particular, at U=1, K=0 and [L,U]={1}, so tracked sets have zero measure and no strictly later point exists.

2. [x] **Tilt support and infinite case.** As in the source Claim (b), derive directly from tilt and v>=U that S_sigma is contained in [b,U], b=max{L,rU-K}. Since L<=U, this interval is nonempty and has length U-b<=ell. If the tracked union is empty, both claims hold immediately, including the empty supremum convention. Otherwise split B=infinity (equivalently Lambda-tilde=infinity, since the first term of B is finite) from B<infinity before any use of Q. For B=infinity, (a), including its tilt-only version, is vacuous by the specified interval convention; the support gives |S_+|+|S_-|<=2ell=ell+min{B,ell}. Do not infer finite Q from eventual constancy of D*lev or assume D*(1)<=0.

3. [x] **Strict maximality and extended quarter drop.** Reprove source E0: for every k>R(z), maximality gives M_z(k)<D*(k), hence M_z(k)<=D*(k)-1 by integrality. Reprove source E1 in its correct conditional form: if d=D*lev(v)>=J and Q(v)<infinity, then for every h>Q(v), the set defining the infimum contains an h'<h; monotonicity gives D*lev(v+h)<=d/4. Do not claim attainment at h=Q(v). In the finite-B branch, for any t_1 in S_+ or S_- with v_1=v(sigma t_1), establish U<=v_1<=(U+K)/r, d=D*(R(sigma t_1))=D*lev(v_1)>=J, and rv_1>=t_1-K>=sqrt(U). Thus v_1 Q(v_1)<=Lambda-tilde<infinity and Q(v_1)<infinity. This is the only finiteness inference needed.

4. [x] **Two separated later levels and the exact reflected cost.** First take t_1 in S_+, and suppose there are t_2,t_3 in (t_1+B,U] with only |t_2-rv(t_2)|<=K and |t_3-rv(-t_3)|<=K. Put v_2=v(t_2), v_3=v(-t_3), Delta_i=t_i-t_1, d_2=r Delta_2/U, and d_3=r(t_1+t_3)/U. Reprove source E2 to obtain r(v_i-v_1)>=Delta_i-2K. Since Delta_i>B>=(2K+2r²)/(1-r²/U), show v_2>v_1+d_2 and v_3>v_1+d_3. Explicitly check d_3=r Delta_3/U+2rt_1/U<=r Delta_3/U+2r: multiplying the last additive cost by r accounts for exactly 2r² in B. No later carrier-count or deficit lower bound is used. Establish d_2>r Lambda-tilde/sqrt(U)>=rv_1 Q(v_1)/sqrt(U)>=Q(v_1), and d_3>=r Delta_3/U>Q(v_1). Retain the strict inequalities even when Q(v_1)=0.

5. [x] **Transport both carrier signs and count at strictly larger ranks.** Reprove source Claim (a), steps 3--6. With C={j: |a_j|>=r/U, |Y_j(t_1)|>=v_1}, one has |C|>=d/2. On C both a_j and Y_j(t_1) are nonzero. Partition into A_+={j in C:a_j Y_j(t_1)>0} and A_-={j in C:a_j Y_j(t_1)<0}. Using the same fixed noises, prove |Y_j(t_2)|>=v_1+d_2 for j in A_+, and |Y_j(-t_3)|>=v_1+d_3 for j in A_-. For i=2,3, the level w_i=v_1+d_i satisfies U<=w_i<v_i<=u_1, so k_i=k(w_i) obeys u_{k_i}<=w_i<u_{R(z_i)} and therefore k_i>R(z_i), with z_2=t_2 and z_3=-t_3. Apply strict maximality and quarter drop to obtain |A_+|<=D*(k_2)-1<=d/4-1 and |A_-|<=D*(k_3)-1<=d/4-1. Inclusive threshold ties are harmless because only the level-to-rank separation is strict. Sum to the explicit contradiction d/2<=|C|<=d/2-2. All rank evaluations are D*(k_i); all quarter-drop evaluations are D*lev(w_i), with their equality justified by definition.

6. [x] **Reflected start and the full assertion (a).** Reprove the source reflection rather than asserting symmetry: replace each a_j by -a_j while retaining theta_j and epsilon_j; the square-root noise coefficient and |a_j| do not change, Y'_j(z)=Y_j(-z), R'(z)=R(-z), and S'_+=S_-, S'_-=S_+. The global existence of R, the same D*, Q, Lambda-tilde, and B are preserved. For t_1 in S_-, assign the reflected later positive point to the original -t_3 and the reflected later negative point to original t_2. Steps 3--5 then give the same contradiction. Conclude the stronger tilt-only assertion for either initial sign, hence the stated prohibition on two later tracked sets.

7. [x] **Infimum/epsilon measure argument including endpoints.** In finite B, finish the source Claim (b) with every boundary stated. If the union is nonempty, let a=inf(S_+ union S_-); then a>=b, both sets are contained in I=[a,U], and |I|=U-a<=ell even if the infimum is unattained. For every epsilon>0 choose t_1 in the union with a<=t_1<a+epsilon and let c=min{t_1+B,U}. Assertion (a) implies some S_sigma misses (c,U]; when c=U choose either sign. Thus that sign has measure at most c-a<=min{B+epsilon,U-a}, while the other has measure at most U-a. Consequently the sum is <=ell+min{B+epsilon,ell}; send epsilon down to zero using continuity of this scalar minimum. Singleton endpoints have zero measure; no open/closed endpoint replacement alters the bound. Record explicitly that finite B>=ell is also covered by the direct support bound 2ell, while finite B<ell is covered by this epsilon argument. Together with step 2 this proves (b) for all extended B.

## Verification

Check each displayed inequality against the exact target, with no claim that search absence is proof. Steps 1--2 settle definedness, measurable sets, nonnegative lengths, and infinite B. Steps 3--6 prove the finite-B tilt-only exclusion at arbitrary admissible initial points; the carrier-count hypothesis is needed only at t_1. Step 7 supplies the full Lebesgue measure bound. Audit U=1, N=1, empty mates, singular and zero loadings, arbitrary signed rank deficits, unattained quarter-distance infima, u_1 and U ties, unattained tracked-set infima, and B>=ell explicitly. No argument establishes a result outside this auxiliary repair's stated scope.

**First failure stop:** stop immediately at the first unsupported inequality, undefined boundary, or admissible counterexample. Mark this plan failed through the native execution workflow and record the exact failed obligation and assumptions against this new target. Never change the target's Statement to rescue a step or transfer the failure/success to the preserved original claim or either main target. A completed candidate proof still requires fresh independent native verification.

## Assumed definitions

The target's approved definitions `gaussian_test_pvalues`, `benjamini_hochberg_step_up`, and `gaussian_multifactor_representation` (and their stated approved model definition) provide only the displayed notation and conventions. There are no draft definitions or unproved dependencies assumed as black boxes. The arbitrary fixed-mate deterministic setting is used exactly as stated; no Gaussian distribution or conditional independence is invoked in the proof.

## Adapted from

- `gaussian_bh_two_sign_curve_exclusion_exq`, Proof Setting, E0--E2, Claim (a) steps 1--6 and reflection, and Claim (b), are an **unchecked adaptation candidate only**. The target supplies the same strictly decreasing thresholds, nondecreasing integer rank curve, finite affine mate family with fixed noises, and global existence of R; these transfer the algebraic setup. Reprove every borrowed step as listed above; no conclusion of that draft is cited as a theorem. Its proof uses no additional external result that is needed as a black box here.
- Changed hypotheses/conventions: the new explicit U>=1 gives K>=0 and ell>=0 and addresses the source's small-U length failure. The explicit real loading range includes all zero and singular endpoints. Rank D* and level D*lev remain distinct. The new extended Q and Lambda-tilde conventions replace the invalid unconditional finiteness claim: infinite B is separated first; finite Q is derived only for a tracked level in the finite-B branch. Do not import D*(1)<=0 from any older setting. Reconstruct the support length even for infinite B, both strict separated-level estimates including the 2r² cost, both transported sign counts, the reflected initial sign, and the infimum/epsilon argument with endpoints. These changes are obligations of this plan, not repairs already certified by the source.

Library searches for `two sign deficit curve quarter distance`, `maximal rank quarter drop`, and `two sign exclusion` returned no matching known result. No library statement is used as an undeclared dependency.



## Outcome

Completed all seven checklist steps, each first saved in Progress, and transferred their full arguments to the Proof of [Large-U two-sign deficit-curve exclusion EX-Q](../assets/gaussian_bh_two_sign_curve_exclusion_large_u_exq.md). The duplicate Progress section was removed after verifying the full transfer. Both (a), including its stronger later tilt-only assertion, and (b) are proved as a candidate for fresh independent native verification. The asset remains draft. No researcher approval or verdict about the preserved original claim or either unrestricted main target is implied.

Only the exact Statement assumptions and the already approved definitions are used; no draft definitions or unproved dependencies are assumed. Rank and level curves remain distinct; extended infinite cases, strict quarter-drop distances, maximal-rank integer gaps, both carrier signs, same-noise reflection, the exact reflected 2r² cost, and measurable-set infimum/epsilon boundaries are written explicitly.

Integrity check: deleting only the newly inserted Proof text recovers the starting target SHA256 `78faefcfde0c077c50dd4c968d280803414fdec5646de92101e5ac054c56d575`, so the Statement, frontmatter, and proposal provenance are byte-identical. Candidate asset SHA256: `8e7c6a00804e32873f99e440daec5760681ae2b02a99bac395e2c45fc05de2cd`. Preserved source asset SHA256 remains `e402183f8be769af9689de20d41ee00fcd25c007202f81b3366446b67be73d8d`. No proof_digest is written by this execution.

Maintenance: validation returned 0 problems. Target-specific links preview and apply returned 0 files and 0 review items. Notation audit read all three uses_definitions files, their approved model dependency, and the configured macros.tex and notations.tex (both contain only central-file comments). No undefined symbol, conflicting meaning, or missing definition relation was found. Auxiliary symbols E_jk, F_k, H_v, d, d_i, w_i, k_i, b, a, c, and the local Lambda abbreviation are defined where used; R is explicitly the local qualifying-rank maximum rather than an implicit ordinary BH rejection count. No additional notation convention was needed.


## Verdict

confirmed

Independent verification of the complete current Statement and canonical Proof, steps 1–7, against the supplied definitions; the native plan reasoning, historical candidate, and other audits were not consulted. Reviewed asset SHA256: `8e7c6a00804e32873f99e440daec5760681ae2b02a99bac395e2c45fc05de2cd`.

The proof establishes both conclusions for every stated finite N, admissible q and r, arbitrary nondecreasing integer curve with globally defined maximal rank, and arbitrary finite fixed affine mates. Monotonicity and the threshold identity for the level extension are correct. Finite B legitimately implies finite Q at each tracked initial level; the quarter drop is used only at strictly larger distances. The inequalities in (4)–(6), including the reflected cost 2r^2 and the factor sqrt(U) in B, yield strict level separation and distances exceeding Q. Each transported carrier class is counted at a rank strictly greater than the later maximal rank; inclusive threshold ties preserve the two integer gaps and the contradiction |C| <= d/2 - 2 < d/2. Reflection preserves every hypothesis and exchanges the later tilt points correctly.

The B=+infinity branch, empty supremum and tracked sets, U=1, N=1, arbitrary curve signs and increments, zero and unit-magnitude loadings, fixed noises, and empty mates cause no omitted case. Borel measurability follows from the finite affine threshold tests. The support length is at most ell; the infimum/epsilon argument proves the exact bound ell+min(B,ell) without requiring attainment of the infimum. No proof repair, statement change, additional hypothesis, or unresolved gap is needed. This verdict concerns this auxiliary lemma only.
