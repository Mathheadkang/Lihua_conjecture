---
type: idea
title: OU 桥的高斯空球协方差首检：所有 rank≤2 原始模型均有统一候选界
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_ou_integrated_signed_budget_bridge
  - cx_gaussian_bh_positive_p_path_jump_budget_r4_s3_tangent_reserve_reset
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - ou-bridge
  - rank-boundary
  - signed-cancellation
---

执行窗口的直接解析首检，待原生独立核验，暂不当批准依赖。它解释为何已确认的rank2正跳预算反例并不自动破坏OU桥，并给后续反例搜索一个更强的受限族约束。

记a=u(q)>=1，完整实际FDP=f(G)，0<=f<=1。对任一原始真null theta_i<=0、unit loading v_i，||x||<a时T_i=theta_i+<v_i,x><a；而任何BH统计阈值u(qR/N)>=a。因此f=0在Gaussian latent ball ||x||<a上，不依赖false means、N或标签比例。取psi_a(x)=(a−||x||)_+，它bounded且1-Lipschitz，f psi_a=0。OU自伴/Dirichlet公式（须在正式证明中用平滑逼近并核对t=0,∞及积分）给Cov_gamma(f,psi_a)=∫_0^∞E<∇T_t f,∇psi_a>dt。故 J(f)>=F E[(a−||G||)_+]。这不要求每个rank selector正则，也没有逐面取绝对值。

若latent rank<=2，可加独立unused Gaussian坐标嵌入R2；F不变，Mehler semigroup的unused梯度为0，J也不变。R=||G_2||为Rayleigh，F<=P(R>=a)=e^(−a²/2)，k_2(a):=E(a−R)+=∫_0^a(1−e^(−r²/2))dr。k_2(a)/a随a非减，a>=1时k_2(a)>=a k_2(1)>=17a/120（用1−e^(−r²/2)>=r²/2−r⁴/8在[0,1]积分）。Mills下界S(a)>=a phi(a)/(a²+1)给e^(−a²/2)/S(a)<=sqrt(2pi)(a+1/a)<=2sqrt(2pi)a。因此F>0时
F(F−qpi0)+/(qJ(f)) <= F/[q k_2(a)] <=240sqrt(2pi)/17<40。

所以候选A=40覆盖全部rank<=2原始模型，包括任意N、负null means、singular covariance、mean groups任意多及随q变化。F=0时bridge平凡。这里所有中间公式仍需正式重建/独立验证，不能作为主证明已证；一般rank d的k_d(a)会有维度损失，不能把这个受限结论外推为原始统一主界。

调度意义：新正跳反例是rank2，故若这条解析首检成立，它可以有无界正variation而OU桥比值仍有统一界。以后检验OU桥必须优先真正增长latent rank或突破rank>=3情形，不能仅增加rank2模型中的均值组数就宣称OU比值发散。该思路可作为generic OU部分的测试与已确认反例压力校准，不要求现在额外添加固定rank主目标或重复已知restricted FDR定理。
