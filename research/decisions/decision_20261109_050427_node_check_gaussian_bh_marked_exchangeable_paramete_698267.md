---
type: decision
title: 'Independent check: gaussian_bh_marked_exchangeable_parameter_array'
kind: node_check
target: gaussian_bh_marked_exchangeable_parameter_array
reason: rejected
digest: a9a90b2450c0623f3ed7709c06b11e0e5c4db0e581fd1395827d27700e7bc384
performed_by: unknown
created_at: '2026-11-09T05:04:27.883Z'
extension_version: 0.0.4
---

参数数组定义的独立性对象写错：条件观测的均值和协方差依赖参数，不能同时要求观测与参数独立。应改为参数及竞争构造预先选择，并与用于生成条件 Gaussian 观测的创新噪声独立；此问题不构成主猜想的反例。
