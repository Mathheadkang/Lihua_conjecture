---
type: decision
title: 'New direction: gaussian_bh_one_sided_universal_order_upper'
kind: direction
target: gaussian_bh_one_sided_universal_order_upper
reason: autonomous
failed_plans_at_direction:
  - plan_252211621cea
  - plan_503f8fddcbb5
  - plan_ee2f7b97740a
  - plan_one_sided_order_actual_mean_global_flux_20261106
  - plan_one_sided_order_common_anchor_rotation_20261107
  - plan_one_sided_order_convex_proxy_label_curvature_20261107
  - plan_one_sided_order_fdp_entropy_mills_coherence_20261107
  - plan_one_sided_order_gaussian_interpolation_sdp_20261106
  - plan_one_sided_order_negative_contact_transport_20261106
  - plan_one_sided_order_peeling_history_kernel_20261107
  - plan_one_sided_order_three_face_noise_packing_20261106
rounds: 3
performed_by: unknown
created_at: '2026-11-08T08:15:06.794Z'
extension_version: 0.0.4
---

继续原始主目标，不再证明已被反例否定的纯线性辅助预算。两类失败分别需要低相干时的熵放大项与稀有分支的平方根亏损项；已保存的组合预算在代数上仍可闭合主界。新机制是按实际BH阈值网格分成凸高斯单元，重证单元内协方差收缩及有界FDP重权的条件桥比较，精确计算混合项，再检验能否支付平方根加线性亏损。不得假设全局Poincare或把未知跨单元预算当定理；如只能还原原问题，明确失败并保留完整推导。旧反例审批留在队列，不作为主目标研究的前提。
