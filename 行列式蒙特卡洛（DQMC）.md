## Hubbard Model
$$
\hat{H}=-t\sum_{\langle i,j\rangle,\sigma}(c_{i\sigma}^\dagger c_{j\sigma}+\text{h.c.})+U\sum_in_{i\uparrow}n_{i\downarrow}
$$
配分函数
$$
Z=Tr(e^{-\beta H})
$$
可观测量
$$
\mathcal{O}=\frac{1}{Z}tr(\mathcal{O}e^{-\beta H})
$$
## Trotter-Suzuki时间离散化
将逆温$\beta$划分为$L_\tau$个时间片，Trotter分解
$$
e^{-\Delta\tau(\hat{H}_K+\hat{H}_U)}\approx e^{-\Delta\tau\hat{H}_K}e^{-\Delta\tau\hat{H}_U}+\mathcal{O}(\Delta\tau^2)
$$
整体的演化算符近似为时间序列的乘积
$$
e^{-\beta\hat{H}}\approx \prod_{i=1}^{L_\tau}(e^{-\Delta\tau\hat{H}_K}e^{-\Delta\tau\hat{H}_U})
$$
## Hubbard-Stratonovich变换把四费米项线性化
$$
n_{i\uparrow}n_{i\downarrow}=(n_{i\uparrow}-\frac{1}{2})(n_{i\downarrow}-\frac{1}{2})+\frac{1}{4}(n_{i\uparrow}+n_{i\downarrow})
$$
Hirsch变换（在每个$i,\tau$引入离散场$s_{i\tau}=\pm 1$）
$$
e^{-\Delta\tau U(n_{i\uparrow}-\frac{1}{2})(n_{i\downarrow}-\frac{1}{2})}=\frac{1}{2}e^{-\Delta\tau U/4}\sum_{s=\pm1}e^{\lambda s(n_{i\uparrow}-n_{i\downarrow})}
$$
其中
$$
\cosh(\lambda)=e^{\Delta\tau U/2}
$$
HS变换把二体项写成了一个关于自旋不对称的外场耦合
$Z$可以写成HS格场求和
$$
Z=\sum_{\{s\}}W(\{s\})
$$
## 对费米子部分积分——行列式形式
对两个自旋分别的二次费米子积分可以得到
$$
W({s})= \prod_{\sigma=\uparrow,\downarrow}\det(I+B^\sigma_{L_\tau}B^\sigma_{L_\tau-1}\cdots B_1^\sigma)
$$
每个时间片点单粒子传递子（单自旋）为
$$
B_\mathcal{l}^\sigma=e^{-\Delta K}e^{V_\mathcal{l}^\sigma}
$$
前者为动能项（非对角，需要对角化），后者为对角矩阵，表示局域位移
$$
(e^{V_\mathcal{l}^\sigma})=e^{\sigma\lambda s i\mathcal{l}}
$$
总的权重为两个自旋行列式的乘积
$$
W(\{s\})=\det(I+\mathcal{B}\uparrow(\{s\}))\det(I+\mathcal{B}\downarrow(\{s\}))
,\quad \mathcal{B}\sigma=\prod\mathcal{l}=L_\tau^1B_\mathcal{l}^\sigma
$$
## Monte Carlo抽样HS字段
$$
\langle\mathcal{O}\rangle=\frac{\sum_{\{s\}}\mathcal{O}(\{s\})W(\{s\})}{\sum_{\{s\}}W(\{s\})}
$$
Metropolis抽样
## 格林函数的表达和测量公式
$$
G_{ij}=\langle c_{i\sigma}c_{j\sigma}\rangle_{\{s\}}=(I+\mathcal{B}\sigma)^{-1}_{ij}
$$
**局域电子密度**
$$
\langle n_{i\sigma}\rangle=1-G_{ii}^\sigma
$$
**双占据**
$$
\langle n_{i\uparrow}n_{i\downarrow}\rangle=\langle n_{i\uparrow}\rangle\langle n_{i\downarrow}\rangle-\langle c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger c_{i\uparrow}c_{i\downarrow}\rangle\approx(1-G_{ii}^\uparrow)(1-G_{ii}^{\downarrow})
$$
**动能**
$$
E_{kin}=\sum_{i,j,\sigma}K_{ij}\langle c_{j\sigma}^\dagger c_{i\sigma}\rangle\approx Tr(KG^\uparrow)+Tr(KG^\downarrow)
$$
**相互作用能（局域）**
$$
E_U=U\sum_i\langle n_{i\uparrow}n_{i\downarrow}\rangle
$$
