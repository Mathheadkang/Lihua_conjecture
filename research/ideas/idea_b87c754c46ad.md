---
type: idea
title: 独立替代环境可使所选单真零能量的熵发散，而条件FDR贡献保持常数
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_finite_signed_p_path_identity
tags:
  - first-principles-screen
  - conditional-calibration
  - entropy-obstruction
  - draft-only
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 4
    slot: 2
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_b87c754c46ad for what was found)
---

本轮探索性解析校准，未独立核验、未批准，非主猜想反例。只检验一种新增捷径：用某个真零被FDP权重选择后的高斯能量熵，直接约束FDR膨胀。该量会被与真零完全独立的替代环境中的排名随机性放大，不能不加补偿地解释成有害适应性。

## 完全指定的原始有限高斯模型

记 $S=\overline\Phi$、$\phi$ 为标准正态密度，固定 $0<q\le S(2)$、整数 $K\ge3$。取整数 $M\ge K^5$，置
$$
N=M^K,\qquad \ell_0=1,\qquad \ell_k=M^k\quad(1\le k\le K).
$$
令 $X,U$ 为独立标准正态。唯一真零统计量为 $T_0=X$。其余统计量分成 $K$ 个替代块，第 $k$ 块的大小是 $\ell_k-\ell_{k-1}$，统计量均为 $\mu_k+U$。这是总数恰为 $N$ 的二维潜在高斯模型，所有统计量方差一，Gram协方差PSD（包括块内完全复制），原标签不变。

令 $a_0=\Phi(-1)$、$d_0=\Phi(1)-\Phi(-1)$，确定常数 $b_k$ 满足
$$
\Phi(b_k)=a_0+\frac{k}{K+1}d_0,
$$
并定义
$$
c_k=S^{-1}(q\ell_k/N),\qquad
\mu_k=c_k-b_k\quad(1\le k\le K).
$$
因为 $-1<b_k<1$ 且 $c_k\ge S^{-1}(q)\ge2$，每个替代均值严格大于1，合法。$c_k$ 递减而 $b_k$ 递增，所以 $\mu_k$ 严格递减，替代块的完整分数顺序固定。均值、块和协方差均在高斯创新前确定。

## 完整最大排名与FDR

仅为确定性BH恒等式，把真零的p值强制为0，记所得实际最大排名为
$$
L(U)=\max\bigl(\{1\}\cup\{\ell_k:U\ge b_k,\ 1\le k\le K\}\bigr).
$$
理由：在块末端排名 $\ell_k$，最弱分数是 $\mu_k+U$，故资格恰为 $U\ge b_k$；若该块末端不合格，块内较早排名的阈值更严，不可能合格。所有较大块同理，故保留了最大排名，而非自由指定一个局部根。端点使用非严格比较，概率零的等号不影响下列积分。强制p值只用于计算，不是修改原模型或提议新的检验程序。

在原模型中，标准确定性force-zero论证给出：真零被拒绝当且仅当
$$
S(X)\le qL(U)/N,
$$
且在该事件上原始完整最大排名恰等于 $L(U)$。直接证明为：从p值0增大回原值只能减小可行排名；若原值不超过 $qL/N$，排名 $L$ 仍合格，所有大于 $L$ 的排名在p值0时已经不合格，故仍不合格；反向由被拒时排名不超过 $L$ 得到。

于是对每个固定 $U$，
$$
\mathbb E_X\!\left[\frac{\mathbf1\{0\text{被拒}\}}{R\vee1}\,\middle|\,U\right]
=\frac1{L(U)}\,\frac{qL(U)}N=\frac qN.
$$
该合法族的完整FDR为 $q/N$，没有膨胀。归一化条件贡献 $(N/q)\mathbb E_X[\mathbf1\{0\text{被拒}\}/(R\vee1)\mid U]$ 恒为1。

## 选择后能量的条件混合

用唯一真零的完整FDP贡献定义概率测度
$$
\frac{dQ}{dP}=\frac{\mathbf1\{0\text{被拒}\}}{(R\vee1)(q/N)}.
$$
上式条件期望为1，故 $Q_U=P_U$：选择权重没有倾斜替代环境。给定 $U$，$X$ 的 $Q$ 分布是标准正态截断到 $X\ge c_{L}$，这里
$$
c_{L}=S^{-1}(qL(U)/N).
$$
置 $Y=X^2/2$，并令
$$
y_k=\tfrac12[S^{-1}(q\ell_k/N)]^2\quad(0\le k\le K).
$$
给定 $L=\ell_k$，$Y=y_k+W_k$。若 $c=\sqrt{2y_k}\ge2$，$W_k$ 的密度精确为
$$
p_c(w)=
\frac{\phi(c)}{cS(c)}e^{-w}\frac{c}{\sqrt{c^2+2w}}\mathbf1_{\{w\ge0\}}.
$$
Mills上下界给
$$
0\le p_c(w)\le\frac54e^{-w},\qquad
\mathbb P(W_k\ge t)\le\frac54e^{-t}.
$$
因此条件微分熵有统一界：$h(W_k)\ge-\log(5/4)$，而 $\mathbb E W_k\le5/4$ 及与指数密度的KL非负性给 $h(W_k)\le1+\log(5/4)$。每个固定模型中的所有熵均有限。

不同中心远离。将 $y(p)=[S^{-1}(p)]^2/2$ 对 $\log p$ 求导得到
$$
\left|\frac{dy}{d\log p}\right|
=\frac{cS(c)}{\phi(c)}\ge\frac45\quad(c\ge2),
$$
从而 $y_{k-1}-y_k\ge(4/5)\log M\ge4\log K$。

用区间 $[y_k,y_{k-1})$（最高区间为 $[y_0,\infty)$）从 $Y$ 识别 $L$，错误概率至多
$$
e_K=\frac54K^{-4}.
$$
而中间 $K-1$ 个排名的各自概率为 $d_0/(K+1)$，所以
$$
H_Q(L)\ge\frac{d_0(K-1)}{K+1}\log\frac{K+1}{d_0}\longrightarrow\infty.
$$
引入分类错误指示并条件化它，得到
$$
H_Q(L\mid Y)\le h_2(e_K)+e_K\log K,
$$
其中 $h_2$ 是二元离散熵。有限混合的熵链公式于是给
$$
h_Q(Y)\ge-\log(5/4)+H_Q(L)-h_2(e_K)-e_K\log K
\longrightarrow\infty.
$$

## 对新机制的结论和限制

在固定 $q$、二维潜在高斯、零均值唯一真零、严格正均值替代项这一非常规则的合法族内，未经环境补偿的所选能量熵可以任意大，而完整FDR始终为 $q/N$。因此每个真零的简单熵上界 $h_Q(Y)\le C+\log S^{-1}(q)$ 不可能成立；相同捷径不能以普通独立情形为支持直接推荐。

这不否定包含指标相对熵或环境信息减项的不同候选，更不否定主界。真正需要控制的应是完整条件FDR贡献或某种已经消掉外部环境随机性的量。这里上述归一化贡献恰为1，能区分无害多尺度排名和真实膨胀。本记录保留为draft首检，不新增辅助完成目标，也不作为已批准依赖。

## Tried

- Search round 4 for gaussian_bh_one_sided_universal_order_upper (slot 2): no candidate written (show idea_b87c754c46ad for what was found)
