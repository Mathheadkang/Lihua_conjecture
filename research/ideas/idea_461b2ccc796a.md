---
type: idea
title: 从两个原始主界倒推的缺口审查：完整净跳跃尚无统一定量控制
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
  - gaussian_bh_finite_signed_p_path_identity
  - gaussian_bh_whole_payoff_cameron_martin_balance
  - gaussian_bh_ou_integrated_signed_budget_bridge
tags:
  - goal-gap-review
  - quantitative-stop
  - '20261109'
  - preserve-history
---

这是研究者授权的完成条件修订与缺口审查，不是新数学结果、证明计划或辅助完成目标。工程说明 research-local/engineering_audit_20261109/next_run_brief.md 只用于调度建议；本记录的数学范围来自原生 show 回读的现有节点陈述与已记录失败，不把工程快照当证明。本次不重新审计已批准证明，也不改变其原陈述、依赖或审批。

## 有效主目标与验收条件

仅单侧、双侧两个原始 universal-order upper bounds 是本阶段完成根，单侧优先。仍要求存在有限普适 C_s 与正普适 q_0,s，对每个 0<q<=q_0,s，在每个有限 N、任意均值、任意单位对角 PSD 协方差（含奇异）上 F_s(q)<=C_s q sqrt(log(1/q))。模型及复杂度可随 q 变化；一侧真零为 theta_i<=0，二侧为 theta_i=0；必须使用最大非严格普通 BH 排名和完整 FDP。独立核验及实际使用的定义/依赖要求保持。

## 已有成果实际提供什么

1. 已批准有限 signed conditional p-path 恒等式：原模型（包括奇异协方差和负真零均值）下，F/q 精确等于原标签加权基线与净跳跃之和；基线在 [0,pi_0] 内。并列事件已合并，孤立可去点不计净跳跃。它给出精确对象，没有给出维数一致的跳跃预算。
2. 已批准 marked-array 完备化、有限模型值恢复、实际排名 signed 变分和匹配全局势证书可在各自范围内使用；它们不自动给出随 q 与正则化参数一致的主界。
3. 已批准完整收益 Cameron-Martin 平衡给出联合排名/真零质量夹逼、全活动最小点响应及标量高斯线 IBP。其常数
$$
C_{a,\sigma,\tau}=\frac{2\tau}{\sigma\sqrt{2\pi}}\left(2/a+\|\chi_a'\|_\infty\right)
$$
在固定参数时独立于维数、方向数、模型与 q，但不能据此宣称在 a,sigma 趋零时仍有可用一致界，或把任意匹配双势对等同于实际加载响应。
4. 已批准 signed-duplication 归约保持奇异模型、并列和实际排名，给出 F_2(q)<=F_1(q)（q<1/2）。因此二侧可在一侧成立后复用该归约写独立主证明并核验；当前一侧前提尚未成立，二侧不能先算完成。
5. OU 主来源的通用梯度结果提供解析控制的依据，不证明 BH-specific bridge。

## 精确的核心定量缺口

沿有限恒等式的记号，定义完整 NET 量（不取绝对值或逐项正部）
$$
\mathcal S(q;N,\theta,\Sigma)=\frac1N\sum_{i\in I_0}
\mathbb E_{\xi^{\,i}}\sum_{t\in J_i}
g_i(t)\{A_i(t^-)-A_i(t^+)\},
$$
以及
$$
\mathcal B(q)=\frac1N\sum_{i\in I_0}\mathbb E_{\xi^{\,i}}
\left[g_i(q)-\int_{(0,q)}A_i\,dg_i\right].
$$
已批准恒等式给出 $F/q=\mathcal B+\mathcal S$ 且 $0\le\mathcal B\le\pi_0\le1$。当前缺少如下模型一致估计：存在有限普适 $K$ 与普适 $0<q_*<1/2$，使对全部原始有限模型及 $0<q\le q_*$，
$$
\mathcal S(q;N,\theta,\Sigma)\le K\{1+\sqrt{\log(1/q)}\}.
$$
这只是主界的精确缺口表述，不是声称已证明的新引理。由于基线有界，该 NET 上界与一侧目标在普适常数意义下等价：它给出 $F/q\le1+K(1+\sqrt{\log(1/q)})$；反向由 $\mathcal S=F/q-\mathcal B\le F/q$。可再限制 $q\le e^{-1}$ 吸收常数项。第一项尚未证明的关键步骤就是对这个保留全部负项、原标签、最大排名的完整平均 NET 量提供上述一致上界。

## 路线与已知障碍对照

- 正部/无符号面成本：已独立核验的 tangent-reserve 族在固定 q=S(1) 使平均正部预算至少 c sqrt(N)，而负跳跃补偿。只否定该辅助预算的原区间，不反驳主界，也不自动否定每个不同小水平量词版本。旧 mixed trace 失败计划同样显示，拆开正面成本会丢失跨实际秩面的抵消。没有新构造的可测跨面配对，不能把“证明 signed 上界”本身写成可执行方案。
- OU 路线：充分门槛仍是 (F-q pi_0)_+ <= A(q/F) J(f)，A 必须模型一致。通用 J 上界不是该不等式；null-maximum 的 Lipschitz 协方差 witness 在真零方向增长时系数可趋零。五轮未找到反例不等于证明。目前没有把完整 BH 超额与 signed OU 响应联结的新机制。
- 全局势/CM/对数平均 cutoff：完整收益 IBP 补上固定参数的正则性工具，却未给 contact height kappa 的一致上界。已回读全局证书采用 m=S/phi，故 beta=1-m(U)/U>0（U>=1）；试粒子比较 P(x)<=kappa 是高度下界，不能反向作上界。teaching 的对数平均 cutoff 可吸收一项边界附费，但没有供给高度上界；coercive q_min 与最终 cutoff 带宽的非循环选参仍需核对。不能用新的正则化恒等式代替定量论证。
- 全真零 Simes/有限方向或固定维模型：仅各自受限结论或未证候选，不是全模型主界的替代。若将来实际证明使用，才通过原生流程声明真实依赖。

## 本次选择与停止条件

当前没有已形成的、可执行且区别于既有失败路线的新单侧定量证明计划；也没有新的满足全部原模型条件并带可核验发散比值的主界反例族。二侧已有可复用的条件归约，但一侧尚未解决，不构成现在重启搜索的理由。因此只完成完成条件修订、保存本审查并保持暂停：不增加辅助目标，不增加预算，不启动搜索或证明，不新写 pending 计划。未来新路线必须先交付具体的定量新机制、与已记录障碍的差别及第一个可检验未证步骤。

## 软件问题另记

历史/新生成项目包的 token 预算超额、任务视图和锁/事务问题属于工程问题。本次没有修改生产上下文编译器、生成驱动、状态文件或审批文件；不宣称这些软件问题已修复。仅由原生命令记录目标、调整 focus、批准项目修订和暂停。软件观察与实际改动另存 research-local/engineering_audit_20261109/，不作为数学证据。
