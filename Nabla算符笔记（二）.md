# Nabla算符笔记（二）
## 梯度与标量势
考虑三维矢量场$\boldsymbol{F}:coordinate(x,y,z)\rightarrow vector(a,b,c)$，满足条件处处$\nabla\times\boldsymbol{F}=0$  
根据斯托克斯公式  
$$\mathop{\iint}\limits_{(S)}(\nabla\times\boldsymbol{F})\cdot d\boldsymbol{a}=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
我们对任意的闭合环路都有  
$$\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}=0$$
选取空间中的两点$P_1,P_2$，作积分
$$\mathop{\int}\limits_{(L:P_1\rightarrow P_2)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
上式中路径$L$的选取可以是任意的，所以我们取任意两条路径$L_1,L_2$来寻找关联
$$\mathop{\int}\limits_{(L_1:P_1\rightarrow P_2)}\boldsymbol{F}\cdot d\boldsymbol{l}-\mathop{\int}\limits_{(L_2:P_1\rightarrow P_2)}\boldsymbol{F}\cdot d\boldsymbol{l}=\mathop{\int}\limits_{(L_1:P_1\rightarrow P_2)}\boldsymbol{F}\cdot d\boldsymbol{l}+\mathop{\int}\limits_{(L_2:P_2\rightarrow P_1)}\boldsymbol{F}\cdot d\boldsymbol{l}\overset{Stokes}{=}0$$  
证明，任意的初始位置相同的积分都是等值的，即
$$\mathop{\int}\limits_{(L:P_1\rightarrow P_2)}\boldsymbol{F}\cdot d\boldsymbol{l}=const$$
由此可以定义标量势$\phi:coordinate(x,y,z)\rightarrow magnitude\,w$
$$\phi(P)=-\int^{P}_{P_0}\boldsymbol{F}\cdot d\boldsymbol{l}+\phi(P_0)$$
可以看出标量势的差是唯一的  
使用Nabla算符$\nabla=\frac{\partial}{\partial x}\hat{i}+\frac{\partial}{\partial y}\hat{j}+\frac{\partial}{\partial z}\hat{k}$
$$\boldsymbol{F}=-\nabla\phi=-(\frac{\partial\phi}{\partial x}\hat{i}+\frac{\partial\phi}{\partial y}\hat{j}+\frac{\partial\phi}{\partial z}\hat{k})$$
## 题外话
由上面的推导，我们可以知道$\nabla\times\boldsymbol{F}\equiv0\Rightarrow\exist\phi,\,\boldsymbol{F}=-\nabla\phi$  
另一方面，我们可以直接取任意一个梯度场$\nabla\phi$代入斯托克斯公式
$$\mathop{\iint}\limits_{(S)}(\nabla\times\nabla\phi)\cdot d\boldsymbol{a}=\mathop{\oint}\limits_{(C)}\nabla\phi\cdot d\boldsymbol{l}=\mathop{\oint}\limits_{(C)}d\phi=0$$
所以我们可以得到充要条件$\nabla\times\boldsymbol{F}\equiv0\Leftrightarrow\exist\phi,\,\boldsymbol{F}=-\nabla\phi$   
但是需要注意这个结果不是使用于一切空间的，这里只做了对于完整三维空间($\R^3$)的推导，实际上，这一结论对于所有平凡的de Rham同调群都成立
## 矢量势
考虑三维矢量场$\boldsymbol{F}:coordinate(x,y,z)\rightarrow vector(a,b,c)$，满足条件处处$\nabla\cdot\boldsymbol{F}=0$  
根据高斯公式
$$\mathop{\iiint}\limits_{(V)}\nabla\cdot\boldsymbol{F}dV=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
我们对于空间中的任意闭合曲面都有
$$\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}=0$$
我们先在该曲面上选取一个闭合环路$C$，这一环路可以在空间中限定出一个曲面$S$，可以对曲面计算通量
$$\mathop{\iint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
由固定环路限定出的空间曲面可以是任意的，我们先选取两个由同一个环限定出的曲面$S_1,S_2$，考察其通量（以环路的右手定则确定正方向）之间的关系
$$\mathop{\iint}\limits_{(S_1:C's +side\rightarrow-side)}\boldsymbol{F}\cdot d\boldsymbol{a}-\mathop{\iint}\limits_{(S_2:C's +side\rightarrow-side)}\boldsymbol{F}\cdot d\boldsymbol{a}=\mathop{\iint}\limits_{(S_1:C's +side\rightarrow-side)}\boldsymbol{F}\cdot d\boldsymbol{a}+\mathop{\iint}\limits_{(S_2:C's -side\rightarrow+side)}\boldsymbol{F}\cdot d\boldsymbol{a}\overset{Gauss}{=}0$$
证明，环路围城的曲面的选择不影响通量大小，即
$$\mathop{\iint}\limits_{(S:C_0)}\boldsymbol{F}\cdot d\boldsymbol{a}=const$$
我们可以用环流量来定义一个新的势$\boldsymbol{A}:coordinate(x,y,z)\rightarrow vector(a,b,c)$
$$\mathop{\iint}\limits_{(S:C_0)}\boldsymbol{F}\cdot d\boldsymbol{a}=\mathop{\oint}\limits_{(C_0)}\boldsymbol{A}\cdot d\boldsymbol{l}$$
进一步，根据斯托克斯公式，可得
$$\boldsymbol{F}=\nabla\times\boldsymbol{A}$$
需要注意的是，矢量势$\boldsymbol{A}$目前只定义了旋度，还不能够唯一地确定，我们还需要为其人为地补充更多的条件
## 题外话
由上面的推导，我们可以知道$\nabla\cdot\boldsymbol{F}\equiv0\Rightarrow\exist\boldsymbol{A},\,\boldsymbol{F}=\nabla\times\boldsymbol{A}$  
另一方面，我们可以直接选取任意旋度场$\nabla\times\boldsymbol{A}$直接代入高斯公式
$$\mathop{\oiint}\limits_{(S)}(\nabla\times\boldsymbol{A})\cdot d\boldsymbol{a}=\mathop{\iiint}\limits_{(V)}\nabla\cdot(\nabla\times\boldsymbol{A})dV=0$$
所以我们可以得到充要条件$\nabla\cdot\boldsymbol{F}\equiv0\Leftrightarrow\exist\boldsymbol{A},\,\boldsymbol{F}=\nabla\times\boldsymbol{A}$  
与之前相同，以上所有推导都是在完整三维空间$(\R^3)$中进行的  
在实际中，磁感应强度$\boldsymbol{B}$满足处处旋度为零，我们在定义磁矢势$\boldsymbol{A}$时，首先可以得到$\boldsymbol{B}=\nabla\times\boldsymbol{A}$  
另外我们通常为了满足洛伦兹协变性的要求为其补上特定的散度定义
$$\nabla\cdot\boldsymbol{A}+\mu\varepsilon\frac{\partial\phi}{\partial t}=0$$