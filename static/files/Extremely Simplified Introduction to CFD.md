## 流体动力学基本方程：

### 连续性方程
密度的变化率=流入的密度通量

$$\frac{\partial\rho}{\partial t}=-\nabla\cdot(\rho\vec{v})$$

### 能量守恒方程
流体微团内能变化率=流入微团的净热流量+体积力和表面力对流体微团的做功的功率

$$\frac{\partial(\rho T)}{\partial t} + \nabla\cdot(\rho\vec{v}T)=\nabla\cdot\left(\frac{k}{c_p}\nabla T\right)+S_T$$

### 牛顿定律、边界层及剪切应力
粘性流体层流时，各层流动的速度不同。相邻两层之间存在着摩擦力，称为内摩擦力（或称为粘滞力）

$$F=\eta S\frac{\partial u}{\partial x}$$

该方程同样用于计算壁面剪切力。

### N-S方程：
对粘性不可压缩流体微团应用牛顿第二定律，我们有NS方程：

$$\frac{\partial\vec{v}}{\partial t}+(\vec{v}\cdot\nabla)\vec{v}=f-\frac{1}{\rho}\nabla p+\frac{\mu}{\rho}\nabla^2\vec{v}$$

N-S方程概括了粘性不可压缩流体流动的普遍规律，因而在流体力学中具有特殊意义。

对于非粘性不可压缩流体， $$\mu = 0$$, $$\nabla\cdot\vec{v}=0$$, $$\rho\frac{\partial\vec{v}}{\partial t}=\rho f-\nabla p$$，NS方程退化为欧拉方程。

## 雷诺输运方程：
设单位体积上有某一物理量 $$f(\vec x,t)$$, 此物理量的区域内积分为：

$$I(t)=\iiint_V f(\vec x,t)$$

则区域积分 $$I(t)$$ 的变化率 = 区域积分的变化 + 流入的通量：

$$\frac{DI(t)}{Dt}=\iiint_{V}\frac{\partial f(\vec{x},t)}{\partial t} \mathrm{d}V + \oint_{\partial V}f(\vec{x},t)\vec{v}\cdot\mathrm{d}\vec{s}$$

## RANS, LES及湍流模型
受计算机水平的限制，从NS方程出发对湍流进行直接数值模拟(DNS)，难以解决工程中遇到的复杂湍流问题。

### RANS 方程的基本假设：
**Reynolds平均假设**：RANS方程的核心是对流场进行Reynolds平均。这意味着流场的变量被分解为平均值和脉动分量，其中平均值是对时间进行平均。这样可以将流动场分解为平均流动和湍流脉动两个部分。

**Boussinesq假设**：RANS方程中通常采用Boussinesq假设，假设应力张量中的涡粘性项与速度梯度成正比。这通过引入湍动动能和湍流耗散率来实现，以描述湍流对平均流动的影响。

**不可压缩流体假设**：在一些情况下，RANS方程还假设流体是不可压缩的，即密度是常数。

基于以上假设，RANS方程对速度和压力场取时间平均值，能够基于相对粗糙的网格以静态方式计算，从而大大降低此类仿真对计算能力的要求，并显著缩短计算时间。

RANS对密度和压力做雷诺平均，其余做密度加权平均。RANS较原方程多一项雷诺应力。 $$k-\varepsilon, k-\omega$$ 都是基于RANS的湍流模型。

## 涡量与涡识别：
涡量是速度的旋度： $$\vec{\omega}=\nabla\times\vec{v}$$

带入NS方程即可得到涡动力学方程。
$$\frac{D \vec{\omega}}{Dt} = \frac{\partial \vec{\omega}}{\partial t} + (\vec{u} \cdot \nabla) \vec{\omega} = (\vec{\omega} \cdot \nabla) \vec{u} - \vec{\omega} (\nabla \cdot \vec{u}) + \frac{1}{\rho^2} \nabla \rho \times \nabla p + \nabla \times \left( \frac{\nabla \cdot \tau}{\rho} \right) + \nabla \times \left( \frac{\vec{B}}{\rho} \right)$$
方程中右边五项分别表示流场的速度梯度、流体体积变化、非保守体积力以及流体的正压性和粘性对涡量变化的影响。
涡量不能用于涡识别。常用的第二代涡识别判据很多，并存在不少问题。

1. 判据都是标量而涡是向量
2. 物理含义不清淅
3. 会被压缩与剪切影响
4. 截断值的选取依赖经验
### 第三代涡识别判据
liutex提出了新的涡判据： $$\vec{R}=R\vec{r}$$$$R=\vec{\omega}\cdot\vec{r}-\sqrt{(\vec{\omega}\cdot\vec{r})^2-4\lambda_{ci}^2}$$

其中， $\vec{r}$ 是 $\nabla\vec{v}$ 的特征向量，其虚部是 $\lambda_{ci}$。
