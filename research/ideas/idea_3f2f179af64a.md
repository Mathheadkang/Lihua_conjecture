---
type: idea
title: Gaussian Hölder谱计数路线首检：可得固定阈值集中，但真零上确界仍至少损失整对数
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - source-screen
  - gaussian-holder
  - spectral-count
  - joint-selector
  - draft-calibration
---

## 来源及核验范围
Chen, Wei-Kuo; Dafnis, Nikos; Paouris, Grigoris, Improved Hölder and reverse Hölder inequalities for correlated Gaussian random vectors, arXiv:1306.2410v2。
官方记录 https://arxiv.org/abs/1306.2410v2 （记录最后修订2013-10-07）；原始PDF https://arxiv.org/pdf/1306.2410 ，Theorem 1(i), equation (1.4), 印刷pp.1–2。本轮实际读了定理协方差条件T≤P及结论。PDF封面生成日期2018-10-30与arXiv元数据年份不同，明确保存此差异，不把它冒称为某个已比对的期刊版本。作者网站列有同一作者组Advances in Mathematics 280 (2015), 643–689版本，但这里适配只依据上述已读PDF。未导入已批准引用/库节点，未改BibTeX，未做全库/撤稿审计；普通web检索与原始arXiv核验，不声称Scholar覆盖。

## 可计算的第一步：固定阈值计数（本记录的draft适配）
设m≥1个实际真零的标准化高斯噪声协方差为Γ，令p=||Γ||op∈[1,m]。令V(t)为这些实际真零p值不大于t的总数；任意负真零均值保留，双侧用原来的零均值标签。由超均匀性，Pr(p_i≤t)≤t。将Theorem 1(i)用于 f_i(Z_i)=exp(s 1{p_i≤t})，其协方差条件为Γ≤pI，对所有s≥0有
$$
E e^{sV(t)}
\le\prod_{i=1}^m [1+\Pr(p_i\le t)(e^{ps}-1)]^{1/p}
\le\exp\{(mt/p)(e^{ps}-1)\}.
$$
阈值均值通过各自固定函数f_i吸收，不把条件随机均值当真零；函数有界，不需要额外可积性。奇异Γ亦满足矩阵条件。优化s得，当v≥mt时，
$$
\Pr\{V(t)\ge v\}
\le\exp\{-[v\log(v/(mt))-v+mt]/p\}
\le(e mt/v)^{v/p}.
$$
这给实际可用的固定阈值尾界，而非BH主界。谱大特征值分离可以是工具，但不能只用trace约束就把p替成普适常数。

## 关键首检：只保留真零计数上确界仍不够
对任意实际BH模型，拒绝数R>0时t=qR/N，故
$$
\operatorname{FDP}\le
W_q:=\min\{1,\;q\sup_{0<t\le q}V(t)/(Nt)\}.
$$
若把真实最大排名条件与联合高斯替代计数都丢掉，仅估计E W_q，即便Γ=I也无法得到目标量级。取所有N个检验独立标准高斯、均值零，则p_i独立Uniform(0,1)，Y=N min_i p_i的密度在0<y<N为(1-y/N)^{N-1}。固定0<q<1/2并取有限N≥max(2,1/q)。对q≤y≤1有min p_i=y/N≤q且 W_q≥q/y，密度至少(1−1/N)^{N−1}≥e^{−1}，所以
$$
E W_q\ge e^{-1}q\int_q^1dy/y
=e^{-1}q\log(1/q).
$$
而独立全真零实际BH FDR=q。这给定量的主要量障碍，不是主界反例，也不只是因为逐指标上界超过1。

## 与旧历史及去向
旧 idea_e6e1f4c16f22 已指出未经细化的Su linking在独立真零处损失整对数；这里不是声称首次发现此一般现象。新内容为Gaussian Hölder的明确谱mgf适配，以及另一个截断真零上确界主要量的最小p值下界。不能将固定阈值集中或低谱余项直接改名为统一主界计划。

值得继续的版本必须同时保留联合高斯替代计数与实际最大排名资格，并明确控制谱分解后的随机条件均值和低排名稀疏区；仍未供给这一转移步骤。该首检为agent draft，未经过原生独立核验；不新增辅助完成目标或预算，不改变两个主界或既有成果。
