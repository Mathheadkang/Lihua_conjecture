---
type: idea
title: >-
  Phase2 candidate test of the pointwise q-flux gate: a population fold with a
  square-root onset
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags: []
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 5
    slot: 2
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_ec6e01a9d5e2 for what was found)
---

待核验的第二阶段具体检验，只针对独立路线3 idea_c23fac250465 的点态q方向正通量门槛，绝非主猜想反例。取权重true1/2、false+与false−各1/4，trueθ0、falseθ=M>0，独立标准X,Z和每个测试私有ε；T_true=σZ+sqrt(1−σ²)ε，T_false±=M±a_σ X+σZ+cε，a_σ²=1−σ²−c²，σ,c>0。因此所有有限复制模型均合法unit-diagonal PSD Gaussian。建议初检M=3,c=.01，渐近族M大、c=M^−2。
先在固定σ>0用已批准有限-人口保真，再考察人口值σ↓0（不能交换这两个极限！）。σ0人口条件尾 H_X(t)=.5S(t)+.25[S((t−M−aX)/c)+S((t−M+aX)/c)]，V_X=.5S(t)，存在宏观拒绝时FDP=.5q，无宏观拒绝时0。临界qcrit(X)=inf_t S(t)/H_X(t)。在X0，false-tail/standard-tail比有一最大点t*；如果cM<sqrt(2/pi)，hazard在t=M的导数符号提示t*<M。需严格证明全局唯一、非退化及局部稳定。此时H_XX(t*,0)<0，可能令qcrit(X)在X0严格二次局部最小q*>0，并且M大使q*任意小。由此宏观拒绝事件概率在q*右侧新增const*sqrt(h)，宏观FDR人口值非局部Lipschitz。
若路线3对所有有限模型点态a.e.正通量<=K[1+sqrt(log1/q)]，则FDR在q*附近具有统一Lipschitz界，其先N∞(σ固定正)、后σ0的逐点值极限也应保留该界，形成潜在矛盾。必须核对actual-largest-crossing、非退化最优阈值、限值保真与σ↓0稳定性。尤其σ=0有限模型true null独立，可有FDR=.5q，人口macro值不同是微观秩损失；不可误用。候选失败应记首个失败条件；通过则只否定强点态q-flux门槛，仍允许原始FDR阶界与积分/有符号改进。已交第二阶段路线3审查任务检验。

## Tried

- Search round 5 for gaussian_bh_one_sided_universal_order_upper (slot 2): no candidate written (show idea_ec6e01a9d5e2 for what was found)
