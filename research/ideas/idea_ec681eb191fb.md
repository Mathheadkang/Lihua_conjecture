---
type: idea
title: Leave-two-out three-face rank reduction for a noise-scale matrix budget
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

New main-goal route candidate after the two failed plans (not an approved lemma or budget). Fix q in(0,1), N>=2, and all p-values except i,j. Let c=R(1,1), s=R(0,1)=R(1,0) by permutation symmetry of the rank, r=R(0,0). Then r>=s+1>=c+2. With t_k=qk/N, the largest BH rank is r if p_i,p_j<=t_r; it is s if p_i<=t_s,p_j>t_r or symmetrically; otherwise it is c. Candidate proof: with i forced zero, changing only p_j has the single entry threshold t_r and rank r/s by the force-zero identity; combine the two coordinate identities, then neither selected means both can be set to1. Define v_k as the true-null count among the remaining coordinates selected at t_k, with v_0=0. Fixed labels alpha_i,alpha_j give F_c=v_c/(c vee1), F_s^i=(v_s+alpha_i)/s, F_s^j=(v_s+alpha_j)/s, F_r=(v_r+alpha_i+alpha_j)/r. Then FDP equals F_c+(F_s^i-F_c)1{p_i<=t_s,p_j>t_r}+(F_s^j-F_c)1{p_j<=t_s,p_i>t_r}+(F_r-F_c)1{p_i,p_j<=t_r}. Consequently the mixed statistic derivative conditional on all other values has only THREE signed faces: (F_r-F_c)delta(u_r,u_r) -(F_s^i-F_c)delta(u_s,u_r) -(F_s^j-F_c)delta(u_r,u_s). This is a candidate exact all-N reduction, to be independently checked and reproduced in a native main proof plan. It retains the largest-rank active contacts rather than counting N^2 inactive grid pairs. The ranks r,s are random functions of the remaining data; deterministic-level scalar bounds do NOT apply by an expectation/supremum exchange. A possible first new analytic gate is the actual averaged three-face matrix bound beta(H_t)<=C q(1+U)(1+sqrt(log(1/nu_t)))/sqrt(nu_t), universal in N,means,Sigma,noise. This is UNPROVED, potentially false, and is not the main theorem. Its time integral is uniformly finite since nu_t>=1-t and integral_0^1(1+sqrt(log(1/x)))/sqrt(x) dx=2+sqrt(2*pi)<5. The logarithmic noise factor permits narrow strong-correlation rank layers; no dimension factor is allowed. Failure must preserve its precise obstruction, not weaken either main statement. Source: root's current exploratory derivation while formal scalar-helper verification runs; no native approval or main proof claimed.
