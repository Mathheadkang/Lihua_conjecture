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
  - plan_one_sided_order_mixed_trace_replica_cells_20261108
  - plan_one_sided_order_negative_contact_transport_20261106
  - plan_one_sided_order_peeling_history_kernel_20261107
  - plan_one_sided_order_three_face_noise_packing_20261106
rounds: 2
performed_by: unknown
created_at: '2026-11-08T09:10:38.762Z'
extension_version: 0.0.4
---

混合迹执行已证明逐面正成本不能由整体亏损支付；新原文核对及实际断开纤维又排除未经加权检验的Hardy捷径，顺序匹配本身仍只重写未证余项。转向已保存 idea_5d513ff67111 的不同路线：先对实际FDR做带log均值惩罚和logdet协方差屏障的联合极值化，利用Price参数微分、原真假标签的边界处理、均值一二阶驻点及协方差KKT得到真实附加约束，再检验最坏模型的水平包络不等式或危险FDR区间。所有工具需重证，不能假设全局优化器存在、所有零均值最不利、Q全局协方差受控，或自动得到最终包络界。旧计划、反例与原目标量词全部保留，不增加辅助必达根。
