---
type: idea
title: Phase2 路线1历史对照与实际解析首测：精确Gaussian负载梯的全BH秩和harmonic边界
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - phase2
  - route1
  - analytic-test
  - signed-sections
  - historical-comparison
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 4
    slot: 3
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_d31f99b82bbb for what was found)
---

## Scope and provenance

Phase1原文idea_c41ff8195c98与总冻结idea_df1d7c436d5e不改。本轮先读native plan-pack，再逐条show批次1全部78条正文，并为核对隐式解决与批准scope额外native show相关资产的Statement（理由：旧ideas常仍写unproved但对应成果已approved）。本节点为第二阶段解析检验和历史对照，非独立proof approval、主猜想反例或新proof plan。未联网、未运行重型实验、未编辑assets/definitions/original ideas/loopstate。

## Historical overlap and reusable results

路线1的Gaussian regression section+全signed jumps与plan_252211621cea（signed half-line occupation，Failure中的SO/M）实质重叠；该旧计划已完成path/interface accounting与conditional K/Abel公式，剩余masked oriented switch sum M的uniform q(1+U)预算未证，进一步scalar IBP只重构未知FDR。plan_one_sided_order_actual_mean_global_flux_20261106和plan_one_sided_order_negative_contact_transport_20261106亦停在aggregate actual signed negative-contact/flux支付；plan_one_sided_order_peeling_history_kernel_20261107的PH-budget在P4-saturation同样成为normalized FDR本身。这些Failure由当前native pack读取，无需重读整Proof。路线1只是把这些signed预算改写为section remainder，尚未给消除旧obstruction的新机制。

本轮fresh Statement确认：gaussian_bh_correlated_clone_first_variation、gaussian_bh_rare_clone_mills_variation、gaussian_bh_private_noise_cutoff_signed_transport_variation、gaussian_bh_averaged_signed_mean_level_complementarity皆approved。前两者原模型必须固定有限PD；signed face只移动该坐标，其他统计固定在face值，不能与沿regression line全坐标共同变化的jump混淆。后两者是固定σ,s,a下completed population的actual suffix-rank全signed响应/averaged stationarity，无uniform regularizer-free trace支付。

gaussian_bh_two_to_one_signed_duplication当前approved，精确同q<1/2下F2≤F1，包含singular与ties。故当前order目标若one-sided gate成功，two-sided可直接转移；不必把路线1原文单独two-sided section预算当强制第二任务。仍保留原文7式为独立可测强候选，不改写原文。

具体已知shortcut反例：idea_d353cd54790b的free-tail envelope有iid all-null qlog1/q下界；idea_3db5febfc68b给actual FDP fibre断裂与weighted Hardy反例；idea_d9a38341c7a7证明PD face derivative不能直接套singular原模型；idea_6237edb910d2展示absolute row费用破坏signed cancellation。它们不否定本路线全signed预算本身。

## Actual analytic test: exact ladder family

取任意有限N≥2及固定0<q≤S(1)，S=barPhi，u_r=S^{-1}(qr/N)，r=1,...,N。令X~N(0,1)，

$$
T_0=X,
\qquad T_j=2u_j-X\quad(j=1,\ldots,N-1).
$$

均值θ=(0,2u_1,...,2u_{N-1})，唯一true null为0。方向v=(1,-1,...,-1)，Σ=vv^T是unit-diagonal PSD、rank1，完全合法singular jointly Gaussian；所有alternative均值严格正。设d_j=u_j-u_{j+1}>0及b_j=2u_j-u_{j+1}=u_j+d_j。由于u(t)在t<1/2严格凸，d_j递减，故b_1>...>b_{N-1}>u_N。

强制P0=0后alternative顺序固定，alternative j位于rank j+1。其资格等价

$$
2u_j-X\ge u_{j+1}\iff X\le b_j.
$$

故强制秩完整为r0(X)=max({1}∪{j+1:X≤b_j})。从实际BH最大秩也能直接重建：X<u_N时true null无法在任何rank拒绝，而所有N-1 alternatives满足rank N-1，因此R=N-1,V=0；X≥u_N时null被拒，真实R=r0(X)（由exact force-zero identity）。具体区间与非严格约定：u_N≤X≤b_{N-1}时R=N；b_r<X≤b_{r-1}时R=r（2≤r≤N-1）；X>b_1时R=1。各b_j等号归较大rank j+1。以上不是自由选rank或各block独立优化。

因此该null的section integrand完全显式：u_N以下g=0；首次跳到1/N；在每b_j处从1/(j+1)向1/j跳。所有后续jump均正且不可相消：

$$
\operatorname{FDR}
=\frac qN+\sum_{j=1}^{N-1}\frac{S(b_j)}{j(j+1)},
\qquad
\mathcal B(q)=\sum_{j=1}^{N-1}\frac{S(b_j)}{j(j+1)}>0.
$$

这直接核对路线1原式(3)和首次anchor≤q/N（本族恰等于q/N）。它否定“所有剩余signed jumps自动消成0”的shortcut；相同正向余项不能靠文字pairing抹去。

## Rigorous first-gate conclusions in this family

上界S(b_j)≤S(u_j)=qj/N给

$$
0<\mathcal B(q)\le\frac qN(H_N-1),
\quad
\operatorname{FDR}\le\frac qN H_N\le q.
$$

所以对这整个合法N变动、rank-one mixed-label族，路线1关键命题(5)确实成立：任意L≥1取A=1、B=0即可（若原文要求B>0，任取B=1亦可）。这是族内解析支持，绝非全covariance证明。

另一方面可把原文(6)的rough harmonic说明升级为精确反例证明。逆tail导数及Mills给

$$
d_j\le\frac{q/N}{\phi(u_j)}=\frac{m(u_j)}j\le\frac1{ju_j}.
$$

u_j≥U≥1且normal hazard h(t)≤t+1/t，因此

$$
\int_{u_j}^{u_j+d_j}h(t)dt
\le d_j\{u_j+d_j+1/u_j\}
\le3/j\le3,
$$

于是S(b_j)≥e^{-3}qj/N，

$$
\frac{N\operatorname{FDR}}q
\ge1+e^{-3}(H_N-1)\longrightarrow\infty.
$$

因此不存在全N统一C使每一个null贡献≤Cq/N；这是对路线1被禁止shortcut(6)的真正解析否定。全FDR仍≤q，故辅助per-null反例不是任何主猜想反例；从N微小null比例退出不能推出跨所有null汇总预算。

## Fully specified small finite check, actually executed

用Python标准库NormalDist/erfc直接核对N=4,q=.01，无Monte Carlo、无巨大阵列。θ=(0,5.614067536687622,5.1516586070978,4.864758117168897)，Σ由上v=(1,-1,-1,-1)外积精确给定。
u=(2.807033768343811,2.575829303548900,2.432379058584449,2.326347874040841)。
b=(3.038238233138722,2.719279548513351,2.538410243128056)。
实际全BH在X=(2.2,2.4,2.6,2.8,3.1)的(R,V)分别(3,0),(4,1),(3,1),(2,1),(1,1)，与上述全部区间一致。解析积分的浮点评估anchor=.0025，B=.001604105794246697，FDR=.004104105794246696<q。这些小数为diagnostic，不是区间认证；精确界与反例依赖上文不等式，不依赖浮点。

## Selection and first substantive obstacle

路线1本轮不被关键命题(5)的此首测否定，但与旧signed occupation/flux路线高度重复。首测没有给跨null sections的任何新守恒律。B=FDR−anchor且0≤anchor≤q，uniform估计B≤AqL+B0S(L)在L≈√(2log1/q)处本就接近原目标规模；仅写该gate并不缩短证明。真正需要的是不重构未知FDR、同时保留actual largest-rank masks及mean/rank标记的Gaussian跨section估计，常数必须独立N、rank、means与任何regularizer。旧失败未被目前机制移除，因此不建议立即把原架构1原样转新plan。

可有限复用：exact force-zero身份、fixed-PD signed-face/rare Mills已批准公式与same-q two-to-one transfer；不能从已批准existence/continuity/complementarity直接支付剩余预算。备选可优先首验本批idea_18bd38404716的whole-avalanche标签配对：先在三非共线方向写trigger+旧label+新label三指标，判断是否能有成本受控的二维收缩。此为尚未执行的新首验，不宣称Grothendieck已适用。

## Tried

- Search round 4 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_d31f99b82bbb for what was found)
