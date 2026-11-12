---
type: idea
title: >-
  Goal audit: deferred sharp targets remain machine-required despite
  current-phase prose
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - goal-audit
  - current-phase
  - acceptance
  - framework-semantics
---

Suggested by the teaching chat while auditing the researcher's newly revised finite-constant goals. The researcher explicitly authorized the finite-constant current phase and requested this accuracy check.

Mathematical audit: the live project Main Problem, Scope and Assumptions, Intended Contribution, and the two new universal_order_upper Statement sections correctly state finite universal C_s and q0_s, preserve the unrestricted model quantifiers, and defer sharp-constant optimization. The current focus uses the two new goals and the signed-duplication supporting lemma. The research targets themselves need no weakening or constant optimization.

Machine-acceptance risk:
The live project frontmatter STILL includes gaussian_bh_two_sided_sharp_upper and gaussian_bh_one_sided_sharp_upper under required_results. Their roles say "Deferred future sharp-constant target ... excluded from current-phase acceptance", but this is currently only descriptive prose.
The installed native CLI's requiredResults(raw) collects every valid required_results ID regardless of role text; requiredAssetIds(raw) is simply requiredResults(raw).map(item=>item.id). No deferred-role filter was found in either the bundled CLI or installed extension. The CLI's select/completion logic uses requiredAssetIds and allApproved; the dashboard graph likewise marks all such IDs required. Both old sharp targets remain draft. The status queried during this audit has parked={}.

Consequences: focus steers immediate work toward the new finite-constant tasks, but does not by itself remove the old sharp goals from the eventual project completion requirement. Merely writing "deferred" in role or Main Problem does not make the machine recognize the current-phase boundary.

Please reconcile this through the native researcher-authorized project revision mechanism. Preserve old goal assets, statements, proofs and research histories, while ensuring old sharp goals are genuinely outside CURRENT-phase required completion. Check native baseline/extension guards before choosing the supported solution; do not hand-edit loop-owned state, approval records or settings, falsely approve anything, or archive mathematical material merely to evade a guard. If the installed framework cannot represent deferred-but-preserved goals, report the exact limitation rather than claim the separation has already been implemented. Recheck machine-required IDs and the ready/completion criterion after reconciliation.

This audit did not edit project/state/approval files and did not drive the loop. The finding concerns goal configuration, not a mathematical counterexample or invalidation of the existing results.

## Native driver follow-up: unresolved configuration boundary

The proving driver and a separate read-only workflow auditor confirmed the finding against the bundled CLI. requiredResults/requiredAssetIds (lines 3819–3843) ignore deferred role text; selectOnce (lines 8478 and 8608–8618) uses the full required closure for completion. The append-only extension guard (extensionProblems, lines 7022–7036) rejects baseline removals unless assets are deprecated or archived. Demotion to conjecture (demoteToConjecture, lines 8766 onward) first requires that the result no longer lie in the required closure. None of these provides a justified shortcut for preserved future targets.

The workflow auditor identified an ordinary revision mechanism, distinct from extend: a native goals discussion/answer, or its autonomous goals decision branch, enters draft_project without creating a new append-only extension (lines 7426–7432 and 10616–10620). Ordinary revision can remove required IDs when no extension is active or the latest extension is already project-approved; native project approval then records the revision. However the current run explicitly forbids calling ask_researcher or report question, including in autonomous mode. No separate permitted public CLI entry for that ordinary revision was established. The driver therefore did not invoke a forbidden question, invalidate an approval to evade the extension guard, modify state/settings/approval records, or retire a live sharp conjecture merely to pass validation.

This risk remains unresolved. The mathematical order-bound statements and work priorities are correct, but the machine-required set still includes the old sharp goals; their exclusion from current-phase machine acceptance has NOT been implemented. A future permitted native ordinary-goal revision must reconcile this, preserve the old assets/history, and recheck the required closure and completion criterion. This follow-up does not resolve the idea or assert that the whole framework lacks a revision mechanism.
