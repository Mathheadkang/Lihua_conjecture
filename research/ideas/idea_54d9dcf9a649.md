---
type: idea
title: 条件FDR贡献矩候选的尖峰障碍：弱公共因子与确定替代梯
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_finite_signed_p_path_identity
  - directional_entropy_one_sided_fdr_bound
tags:
  - conditional-calibration
  - moment-candidate-obstruction
  - full-rank-mask
  - draft-counterexample
  - quick-screened
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 5
    slot: 1
    statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
    outcome: no candidate written (show idea_54d9dcf9a649 for what was found)
---

对本轮新候选 idea_c9477a4733f5 的后续解析首检。下述是完整证明候选及单人Quick审查，不是已独立确认的反例，不修改原候选量词，不标记原生 falsification 或 approved。其对象是较强的条件贡献矩预算，而不是任一BH主界。没有增加辅助完成根或启动新的原生搜索轮次。

## 冻结要检验的条件矩断言

沿 idea_c9477a4733f5 的完整原模型定义，对原始真零 $i$，
$$
\mathcal C_i(\xi^{\,i})=\frac Nq
\mathbb E\left[\left.\frac{\mathbf1\{i\in\mathcal R_q\}}{R_q\vee1}
\right|\xi^{\,i}\right],
\qquad
\xi^{\,i}_j=Z_j-\Sigma_{ji}Z_i.
$$
假零上定义为0。待检验的断言是存在固定普适 $\lambda>0$、有限 $A_0,A_1$ 及 $q_*>0$，使
$$
\log\left(\frac1N\sum_i\mathbb E e^{\lambda\mathcal C_i}\right)
\le A_0+A_1 S^{-1}(q)
\quad(0<q\le q_*).
$$
这里 $S=\overline\Phi$。下面候选族对每个固定 $\lambda>0$ 都使左侧与 $1+S^{-1}(q)$ 的比值无界。所有常数及充分大的N门槛均与N无关；不要求优化这些门槛。

## 原始有限模型，全部参数显式

取充分大的偶数 $N$，置
$$
L=\log N,\quad q=L^{-2},\quad
a=L^{-1/2},\quad \sigma=\sqrt{1-a^2},\quad
m_0=m_1=N/2.
$$
令 $G,\varepsilon_1,\ldots,\varepsilon_{m_0}$ 独立标准正态。真零统计量为
$$
T_i=aG+\sigma\varepsilon_i,\qquad 1\le i\le m_0.
$$
令 $c_k=S^{-1}(qk/N)$，替代统计量为
$$
T_{m_0+j}=(1+a)c_j-G,\qquad 1\le j\le m_1.
$$
真零均值全为0；替代均值 $(1+a)c_j>0$ 严格递减。每个统计量方差一，协方差是此显式线性高斯数组的Gram矩阵，故PSD。替代项共用同一因子，产生奇异性，仍属于原模型。模型、均值和N均可随q变化，未使用错误的固定模型极限。

取任一真零 $i$，记其中心分数为 $X_i=T_i$，并置
$$
V_i=aX_i-G.
$$
它与 $X_i$ 独立，$V_i\sim N(0,\sigma^2)$。给定 $X_i=x,V_i=v$，其他统计量精确为
$$
T_j=a^2x-av+\sigma\varepsilon_j\quad(j\le m_0,\ j\ne i),
$$
$$
T_{m_0+j}=(1+a)c_j-ax+v.
$$
完整残差向量 $\xi^{\,i}$ 恰生成 $(V_i,(\varepsilon_j)_{j\ne i})$：每个替代残差等于 $V_i$，每个其他真零残差为 $-aV_i+\sigma\varepsilon_j$。这些变量互相独立，且共同独立于 $X_i$。所以以下事件的概率正是所需残差概率，不是错误地条件在另一个背景上。

## 全部排名的精确替代计数

对任意排名 $k$，阈值为 $y_k=c_k$。条件路径上的替代合格数精确等于
$$
B_k(x,v)=\min\left\{m_1,\left\lfloor
\frac Nq S\left(\frac{y_k+ax-v}{1+a}\right)
\right\rfloor\right\}.
$$
它由替代均值排序直接得到，并保留非严格比较。只要对某k有完整合格数至少k，k就合格；排除所有较大k才能确定实际最大排名。下面同时做这两件事。

考虑
$$
x\in I_N=[\sqrt L/2,\sqrt L],\qquad
v\in J_N=[10/L,11/L].
$$
置 $t(x)=NS(x)/q$、固定常数 $C=e^{100}$，并令
$$
k_-(x)=\lceil2t(x)\rceil,\qquad
k_+(x)=\lceil Ct(x)\rceil.
$$
Mills界给 $t(x)$ 介于常数倍 $N^{1/2}L^{3/2}$ 与 $N^{7/8}L^{3/2}$ 之间。因此充分大的N上一致有
$$
N^{1/3}\le k_-<k_+\le N/4.
$$
相应分位数 $y_{k_-},y_{k_+}$ 均介于 $x/2$ 与x之间，且 $U:=S^{-1}(q)\ge2$、$U=o(\sqrt L)$。例如分位数性质由
$S(x/2)/S(x)\to\infty$ 一致超过固定常数 $C+1$ 得到；ceil引起的相对误差趋零。

### 一个确定合格的低端排名

标准正态hazard $h=\phi/S$ 满足 $s\le h(s)\le s+1/s$。因
$$
\log\frac{S(y_{k_-})}{S(x)}
=\int_{y_{k_-}}^x h(s)ds\le\log3
$$
及 $h(s)\ge y_{k_-}\ge x/2$，
$$
x-y_{k_-}\le2\log3/x.
$$
所以对 $v\ge10/L$，
$$
a(x-y_{k_-})-v\le (4\log3-10)/L<0.
$$
因此替代计数公式中的参数严格小于 $y_{k_-}$，floor前数量严格大于整数 $k_-$；cap $m_1$ 也大于 $k_-$。故仅替代项已经给 $B_{k_-}\ge k_-$，此排名确定合格。且 $S(x)\le qk_-/N$，所以原真零i在实际最大排名下必被拒绝。

### 排除所有大于高端的全局排名

令 $y_+=y_{k_+}$。由
$$
\log\frac{S(y_+)}{S(x)}\ge\log C,\qquad
h(s)\le x+2/x\le2x,
$$
得到
$$
x-y_+\ge\log C/(2x).
$$
函数
$$
f(y)=y\{a(x-y)-v\}
$$
在 $[U,y_+]$ 上凹。上端满足
$$
f(y_+)\ge\frac{\log C}{4\sqrt L}-\frac{11x}{2L}
\ge\frac{19.5}{\sqrt L}.
$$
下端满足 $f(U)\ge U/4$，对充分大的N成立。因此整个区间均有 $f(y)\ge1/\sqrt L$。

对任意 $k\ge k_+$，其阈值 $y_k\in[U,y_+]$，令
$$
d_k=\frac{a(x-y_k)-v}{1+a}>0.
$$
由 $h(s)\ge s$，
$$
\frac{S(y_k+d_k)}{S(y_k)}
\le e^{-y_kd_k}
\le e^{-1/(2\sqrt L)}
\le1-\frac1{4\sqrt L}.
$$
从而替代计数（floor或cap只会减小它）满足
$$
B_k(x,v)\le\left(1-\frac1{4\sqrt L}\right)k.
$$

## 其他真零的统一残差事件

对上述所有x,v，其他真零分数不超过 $1/\sqrt L+\sigma\varepsilon_j$。在 $2\le y\le\sqrt L$ 上，
$$
S\left(\frac{y-1/\sqrt L}{\sigma}\right)
\le S(y-1/\sqrt L)\le e^2 S(y).
$$
第一步用正参数和 $\sigma<1$，第二步由hazard上界在长度 $1/\sqrt L$ 的区间上积分得到。

对所有整数 $k\ge N^{1/3}$ 且 $y_k\le\sqrt L$，相应其他真零计数均值至多 $e^2qk/2$。二项Chernoff界和对至多N个排名的并合给出一个只依赖 $(\varepsilon_j)_{j\ne i}$ 的事件 $E_i$，满足
$$
\mathbb P(E_i)\longrightarrow1,
$$
并且在 $E_i$ 上，这些排名的其他真零合格数均不超过 $k/(16\sqrt L)$。具体地，失败概率可界为
$$
N\exp\{-cN^{1/3}\log L/\sqrt L\}\longrightarrow0,
$$
因为目标计数与均值之比至少为常数倍 $L^{3/2}$。该上界同时控制全部x,v，不把不可数个x逐点并合。

在 $v\in J_N$、$E_i$ 上，所有 $k\ge k_+$ 的总合格数至多
$$
\left(1-\frac1{4\sqrt L}\right)k+
\frac{k}{16\sqrt L}+1<k
$$
（N充分大）。最后的1保留了被考察真零本身。因此没有任何更大排名合格，包含原规则的并列及全局最大排名：
$$
k_-(x)\le R_i(x;\xi^{\,i})<k_+(x)
\le2Ct(x)\qquad(x\in I_N).
$$

## 条件贡献尖峰及矩发散

在上述残差事件上，i在整个 $I_N$ 被拒绝，所以完整条件积分给出
$$
\mathcal C_i\ge
\frac Nq\int_{I_N}\frac{\phi(x)}{2CNS(x)/q}\,dx
\ge\frac1{2C}\int_{\sqrt L/2}^{\sqrt L}x\,dx
=\frac{3}{16C}L.
$$
记 $c_0=3/(16C)>0$。$V_i$ 的高斯密度在 $J_N$ 一致有正下界，且 $E_i$ 与 $V_i$ 独立，因此
$$
\mathbb P_{\xi^{\,i}}(\mathcal C_i\ge c_0L)\ge c_1/L
$$
对所有真零i及充分大N成立，$c_1>0$普适。真零占一半，故任何固定 $\lambda>0$ 上，
$$
\log M_\lambda
\ge\lambda c_0L-\log L+O(1).
$$
另一方面 $q=L^{-2}$ 给 $S^{-1}(q)\le2\sqrt{\log L}$。因此 $\log M_\lambda/(1+S^{-1}(q))\to\infty$。同一候选还使每个固定 $p>1$ 的指标平均 $\mathbb E\mathcal C_i^p$ 至少为常数倍 $L^{p-1}$，不能用自然的 $(1+S^{-1}(q))^p$ 统一支付。

## 科学边界、Quick检查与后续要求

- 冻结对象是 idea_c9477a4733f5 的固定指数矩断言；全模型、全部常数与q区间量词均未偷换。不是改称一个更弱矩条件已经成立。
- 这是原始有限高斯模型族：固定确定均值、合法Gram协方差、原标签、最大非严格BH；残差独立性和全局较大排名排除都在上文展开。未运行巨大局部计算，也未使用模拟或浮点来认证。
- 该族本身落在已批准 directional_entropy_one_sided_fdr_bound 的单公共因子、单真零方向范围内。其 $\pi_0=1/2$、方向熵 $(1/2)\log2$、平均加载系数至多 $1/2$，所以已批准结果仍给 $F\le C'q(1+S^{-1}(q))$。候选矩的发散不反驳主界，反而说明条件贡献可呈窄而高的尖峰，矩控制比均值控制强得过多。
- Quick检查重点：逐一核对两种排名阈值的ceil误差、替代计数的floor与cap、全部高端排名及残差sigma-field；也检查了 $N\to\infty$ 时公共加载趋零和替代均值增长仍在模型范围。隐含“充分大N”需在独立审查中再核对一致性。
- Requested/executed audit mode: Quick；无独立子agent，无修复或审批；可报告 quick-screened，不能报告 verified/certified/confirmed refutation。若要正式否定该较强矩路线，应由新上下文独立核验这份冻结构造。当前只保存为draft候选障碍，不新增辅助目标、计划或预算。

## Tried

- Search round 5 for gaussian_bh_one_sided_universal_order_upper (slot 1): no candidate written (show idea_54d9dcf9a649 for what was found)
