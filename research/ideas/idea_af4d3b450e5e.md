---
type: idea
title: >-
  Next loading checkpoint includes a safe fixed-rank Gaussian IBP with every
  baseline derivative retained
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_global_particle_potential_certificate
tags: []
---

选定radial首门的可执行细化，待新支持命题证明。固定baseline π、deterministic rank t、试探particle x=(θ,v,ell)和r-independent testweight A(X)，令K_r=S((Q_X(t)−θ−τ_s r X(v))/c_s(r v)), k_r=∂θK_r。生成核d_rK_r=τ_s X(v)k_r−τ_s²r||v||²∂θ²K_r。r<=1时c_s(rv)>=s，任意固定阶r导数由C_{s,τ}(1+|Xv|^m)控制；结合已批准conditional总权重K0，三阶一致界应使同一convex-limit pair的径向C²经evaluation闭包传递，不重新选pair。
可严格推导的Gaussian IBP只先用于明确的光滑testweight：A有界、沿Cameron–Martin方向v为C1且D_vA有界，独立extra随机量可条件化。固定rank quantile的背景导数应为 D_vQ_X(t)=τ_s∫〈w,v〉 p_Xt(θ',w,ell')dπ，绝对值<=τ_s||v||。因为∂X_v k=k_θ(τ_s||v||²−D_vQ)，Gaussian标量IBP给 E[A d_rK_r|1]=τ_s E[k D_vA−A (∂θ²K)D_vQ]。可条件在与v正交的Gaussian场，再对g=X(v)/||v||作一维分部积分；v0情形平凡。这个公式显式保留A和Q两项，不能把baseline冻结后又错误把D_vQ置零。
光滑testweight是分析测试函数，不是噪声之后选取的模型竞争者；物理v→rv始终在噪声前选。实际hybrid selector权重可能只有可测性，不保证Gaussian Sobolev/BV，故把本公式直接套到actual-rank/record权重还需要另证，并保留全部switch terms。这是随后明确技术缺口；本首门不宣称给出uniform q尺度支付或原主界。
