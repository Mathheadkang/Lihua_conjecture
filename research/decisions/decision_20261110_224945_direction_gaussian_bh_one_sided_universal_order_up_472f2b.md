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
created_at: '2026-11-10T22:49:45.850Z'
extension_version: 0.0.4
---

独立重规划给出新的完整胞腔平移路线：先用 Cameron-Martin 变换把带原真零标签及 1/R 权重的实际 BH 贡献推到中心超平面，再以明确的 q 尺度作 Mehler 平滑；独立模型已显示 reciprocal-threshold 因子能消除多余 sqrt(log N)。这绕开先前把全量贡献拆成绝对面通量、丢失实际跨面匹配的步骤。先反驳或证明新草稿依赖的拥塞门槛，优先任意秩一混合标签和小秩二相关构型；未证明门槛前不得宣称主界完成。两项完成根和原总预算不变。
