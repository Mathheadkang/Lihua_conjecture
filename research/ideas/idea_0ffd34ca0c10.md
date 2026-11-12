---
type: idea
title: 收到新增三条 teaching 提案：有限 signed 路径、对数截断与 OU 定量桥的初筛去向
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_whole_payoff_cameron_martin_balance
tags:
  - teaching-handoff
  - new-input
  - route-switch
---

本轮CM搜索第4轮期间再次扫 teaching/来源元数据，发现此前27条快照之后新增的外部agent-origin提案 idea_408804d0bbf6、idea_452ab0a935b7、idea_ef26ea5c4801（另外两条命中为执行窗口自己的审计与CM路线）。三条已通过native show全读；原卡片不改，不把外部独立brainstorm当原生验证。

1. idea_408804d0bbf6：优先级高的直接有限模型路线。首个恒等式初算：有限N时 t<q/N必有i被拒且R>=1，故A_i(0+)=0；t→q−若i仍拒则R=N，或i已不拒A=1，故A_i(q−)=1。除有限阈值交点外，R常数，A的AC导数等于1{i拒}/(q r)。对g_i dA作分部积分给所述weighted signed-charge表达。theta_i<0时g_i非减≤1，baseline g_i(q)−∫A dg_i在[0,1]。这只是执行窗口的解析初筛，尚未独立验证；须严查同步跳跃、常数路径、可测性与条件积分，再原生验证有限恒等式。positive-part budget是不同的强门，必须独立反驳/筛选，失败不损signed identity或主界。
2. idea_452ab0a935b7：对数cutoff的deterministic公式可直接初算。d/dt psi(r/e^t)=−r∂r psi，积分分部得 r bar-chi′=epsilon bar-chi+epsilon c psi_low−epsilon(1+c)psi_high，上界epsilon bar-chi+epsilon c。冻结c/整个cutoff才可做q变分；扩展max/certificate不是逐cutoff最优对的平均。其价值是消除一项明确rank边界附加费，不给kappa上界；先检验是否真阻挡quantitative proof，再决定是否建新目标，避免又搭一条无定量结尾的正则化链。已有CM目标不因此改变陈述。
3. idea_ef26ea5c4801：最高优先级的新定量桥，F(F−qpi0)+/(qJ(f))是否有统一上界直接连接目标，值得先falsify。初筛确认代数方向：若桥成立，J≤(pi/2)I(F)≤C F sqrt(log(e/F))，F>=q时得到F≤q+Cq sqrt(log(e/q))，F<q时已足。通用OU估计不蕴含BH桥；其primary source必须走原生来源核验。单null的sup梯度1/sigma发散而L1~qU的校准说明当前CM sup范数不能作为最终norm；这不反驳固定sigma的CM命题。

调度选择：先完成并保存当前CM第4轮原子阶段，然后用原生流程优先立项/首验新直接定量方向，不把未尝试提案仅标低优先而遗忘。CM草稿与已完成轮次全部保留；如暂停它的排程，须通过native park而非修改状态/删除记录。新路径先验有限signed identity，并筛OU桥/正part强化的具体合法对象，不能给main写一个包含“再证明统一预算”空洞步骤的假计划。
