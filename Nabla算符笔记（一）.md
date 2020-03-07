# Nabla算符笔记（一）
*写在前面：  
本笔记将包含四个部分，分别是：两个公式、两个势、不同坐标系的算符形式、一些运算公式  
希望能较全面地涵盖电动里的所有内容*
## 高斯公式
我们先对三维矢量场$\boldsymbol{F}:coordinate(x,y,z)\rightarrow vector(a,b,c)$定义通量
$$\Phi=\mathop{\iint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
其中$S$代表一个人为选定的空间曲面，$d\boldsymbol{a}$代表的面积微元矢量方向为法向量方向、大小为面积微元大小  
考虑一个被闭合的曲面包裹的有限体积，先计算对闭合曲面的总通量
$$\Phi=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
现在，我们将这一有限体积切成两个部分，再分别对切开的体积的闭合曲面计算通量并相加  
由于切割面上的通量被从两个方向计算了一次，相互抵消，另外原本的通量也都被计算了一次，故  
$$\mathop{\oiint}\limits_{(S_1)}\boldsymbol{F}\cdot d\boldsymbol{a}+\mathop{\oiint}\limits_{(S_2)}\boldsymbol{F}\cdot d\boldsymbol{a}=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
由此一来，我们可以无限地去切割这个有限体积，并计算各体积微元的闭合曲面通量相加，可得  
$$\lim_{N\rightarrow\infty}\sum^{N}_{i=1}\mathop{\oiint}\limits_{(S_i)}\boldsymbol{F}\cdot d\boldsymbol{a}=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
于是我们可以引入符号  
$${\rm div}\boldsymbol{F}=\frac{\mathop{\oiint}\limits_{(dS)}\boldsymbol{F}\cdot d\boldsymbol{a}}{dV}$$
根据这个定义，显然有
$$\mathop{\iiint}\limits_{(V)}{\rm div}\boldsymbol{F}dV=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
我们来继续深究符号${\rm div}F$，根据定义，我们选取一个立方体积微元，其对角坐标$(x,y,z);(x+dx,y+dy,z+dz)$，则其总通量
$$\begin{aligned}\mathop{\oiint}\limits_{(dS)}\boldsymbol{F}\cdot d\boldsymbol{a}&=-F_xdydz-F_ydzdx-F_zdxdy\\&+(F_x+\frac{\partial F_x}{\partial x}dx)dydz+(F_y+\frac{\partial F_y}{\partial y}dy)dzdx+(F_z+\frac{\partial F_z}{\partial z}dz)dxdy\\&=(\frac{\partial F_x}{\partial x}+\frac{\partial F_y}{\partial y}+\frac{\partial F_z}{\partial z})dxdydz\end{aligned}$$
故
$${\rm div}\boldsymbol{F}=\frac{\mathop{\oiint}\limits_{(dS)}\boldsymbol{F}\cdot d\boldsymbol{a}}{dV}=\frac{\partial F_x}{\partial x}+\frac{\partial F_y}{\partial y}+\frac{\partial F_z}{\partial z}$$
引入Nabla算符$\nabla=\frac{\partial}{\partial x}\hat{i}+\frac{\partial}{\partial y}\hat{j}+\frac{\partial}{\partial z}\hat{k}$，可得
$${\rm div}\boldsymbol{F}=\nabla\cdot\boldsymbol{F}$$
至此，高斯公式可写为
$$\mathop{\iiint}\limits_{(V)}\nabla\cdot\boldsymbol{F}dV=\mathop{\oiint}\limits_{(S)}\boldsymbol{F}\cdot d\boldsymbol{a}$$
## 斯托克斯公式
我们接着对三维矢量场$\boldsymbol{F}:coordinate(x,y,z)\rightarrow vector(a,b,c)$定义环流量
$$\Gamma=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
其中$C$代表一个认为选定的闭合路径，$d\boldsymbol{l}$代表路径上的线元向量方向与路径切向同向、大小和线元长度相等
考虑一个被闭合路径围成的一块有限曲面，先计算闭合路径的环流量
$$\Gamma=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
我们可以将曲面从中间切分成两半，对两块曲面边缘的闭合路径计算环流量并相加  
由于切割线上的环流量从两个方向上各计算了一次，相互抵消，且其它部分的环流量都计算了一次，故
$$\mathop{\oint}\limits_{(C_1)}\boldsymbol{F}\cdot d\boldsymbol{l}+\mathop{\oint}\limits_{(C_2)}\boldsymbol{F}\cdot d\boldsymbol{l}=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
当我们无线地去切割曲面，对每个小曲面计算环流量并相加时，就有
$$\lim_{N\rightarrow\infty}\sum^N_{i=1}\mathop{\oint}\limits_{(C_i)}\boldsymbol{F}\cdot d\boldsymbol{l}=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
定义符号
$${\rm curl}\boldsymbol{F}\cdot\hat{n}=\frac{\mathop{\oint}\limits_{(dC)}\boldsymbol{F}\cdot d\boldsymbol{l}}{da}$$
其中$da$是微小闭合路径$dC$围出的微笑面积的大小，$\hat{n}$则是面元的法向量，由闭合路径的右手定则确定其方向  
根据这一定义，我们有
$$\mathop{\iint}\limits_{(S)}{\rm curl}\boldsymbol{F}\cdot d\boldsymbol{a}=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$
我们继续研究符号${\rm curl}\boldsymbol{F}$，根据定义，我们在xy平面上选取一个正方形，对角坐标为$(x,y,z_0);(x+dx,y+dy,z_0)$，沿正方向（逆时针）计算这个正方形路径的环流量，有
$$\begin{aligned}\mathop{\oint}\limits_{(dC)}\boldsymbol{F}\cdot d\boldsymbol{l}&=F_xdx-F_ydy\\&+(F_y+\frac{\partial F_y}{\partial x}dx)dy-(F_x+\frac{\partial F_x}{\partial y}dy)dx\\&=(\frac{\partial F_y}{\partial x}-\frac{\partial F_x}{\partial y})dxdy\end{aligned}$$
故
$${\rm curl}\boldsymbol{F}\cdot\hat{n}=({\rm curl}\boldsymbol{F})_z=\frac{\mathop{\oint}\limits_{(dC)}\boldsymbol{F}\cdot d\boldsymbol{l}}{da}=\frac{\partial F_y}{\partial x}-\frac{\partial F_x}{\partial y}$$
同理对于x和y方向也可作推导，故
$${\rm curl}\boldsymbol{F}=(\frac{\partial F_z}{\partial y}-\frac{\partial F_y}{\partial z})\hat{i}+(\frac{\partial F_x}{\partial z}-\frac{\partial F_z}{\partial x})\hat{j}+(\frac{\partial F_y}{\partial x}-\frac{\partial F_x}{\partial y})\hat{k}$$
已有Nabla算符$\nabla=\frac{\partial}{\partial x}\hat{i}+\frac{\partial}{\partial y}\hat{j}+\frac{\partial}{\partial z}\hat{k}$，可得
$${\rm curl}\boldsymbol{F}=\nabla\times\boldsymbol{F}=
\left|\begin{array}{cccc}\hat{i}&\hat{j}&\hat{k}\\\frac{\partial}{\partial x}&\frac{\partial}{\partial y}&\frac{\partial}{\partial z}\\F_x&F_y&F_z\end{array}\right|$$
至此，斯托克斯公式可写为
$$\mathop{\iint}\limits_{(S)}(\nabla\times\boldsymbol{F})\cdot d\boldsymbol{a}=\mathop{\oint}\limits_{(C)}\boldsymbol{F}\cdot d\boldsymbol{l}$$