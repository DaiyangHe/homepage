Author: Dylan He
# Vortex Identification
### Introduction to Vortices
Vortices are ubiquitous in nature, especially in turbulent systems where a wide range of vortices with varying sizes exist. Turbulence is a **strongly dissipative system** that requires continuous energy input (turbulence does not persist without energy input). Due to this characteristic, various vortices play a crucial role in energy dissipation within turbulence. This is because the presence of vortices indicates velocity gradients in space, where fluid viscosity transforms mechanical energy into internal energy through friction-like effects. Generally speaking, **a vortex represents fluid rotation**. However, this definition does not help us extract vortex structures effectively. Therefore, we need mathematical tools to define vortices, which leads to the concept of **vortex identification**.

### First-Generation Vortex Identification Methods
The curl of velocity, or **vorticity**, was initially used to define vortices. Given the velocity vector $\boldsymbol{v}=(u,v,w)$, vorticity is expressed as the curl of the velocity field:
$$\omega=\nabla \times \boldsymbol{v}=\left(\frac{\partial w}{\partial y}-\frac{\partial v}{\partial z}\right)\hat{\boldsymbol{i}}+\left(\frac{\partial u}{\partial z}-\frac{\partial w}{\partial x}\right)\hat{\boldsymbol{j}}+\left(\frac{\partial v}{\partial x}-\frac{\partial u}{\partial y}\right)\hat{\boldsymbol{k}}$$
Substituting into the NS equation, we obtain the vorticity dynamics equation:
$$\frac{D\omega}{Dt} =\frac{\partial\omega}{\partial t}+(\boldsymbol{v}\cdot\nabla)\boldsymbol{\omega} 
=(\boldsymbol{\omega}\cdot\nabla)\boldsymbol{v}-\boldsymbol{\omega}(\nabla\cdot\boldsymbol{v})+\frac1{\rho^2}\nabla\rho\times\nabla p+\nabla\times\left(\frac{\nabla\cdot\tau}{\rho}\right)+\nabla\times\left(\frac{\mathbf{B}}{\rho}\right)$$
The five terms on the right-hand side represent the effects of velocity gradients, fluid volume changes, non-conservative body forces, and the barotropicity and viscosity of the fluid on vorticity changes. Although intuitively vortices appear in regions with concentrated vorticity, for simple flows, vortices can be determined directly through intuition and visualization. However, for three-dimensional viscous flows, particularly complex flows like turbulence, vortex structures, their evolution, and interactions are challenging to discern. Vorticity does not necessarily equate to a vortex. A classic example is the near-wall region in low-speed planar Poiseuille flow, where vorticity is large but no visible fluid rotation is observed. This is because of the **shear** near the boundary layer, which leads to a large velocity gradient.

### Second-Generation Vortex Identification Methods
Given the clear shortcomings of using vorticity to extract vortices, new identification methods emerged, such as $Ω$, $Q$, $Δ$, and $λ_2$, which are based on the **eigenvalue** evolution of the velocity gradient tensor $\frac{∂\boldsymbol{v}}{∂x_j}$. The velocity gradient tensor is defined as:
$$\nabla \boldsymbol{v}=\begin{bmatrix}\frac{\partial u}{\partial x}&\frac{\partial u}{\partial y}&\frac{\partial u}{\partial z}\\\\\frac{\partial v}{\partial x}&\frac{\partial v}{\partial y}&\frac{\partial v}{\partial z}\\\\\frac{\partial w}{\partial x}&\frac{\partial w}{\partial y}&\frac{\partial w}{\partial z}\end{bmatrix}$$

#### Q-Criterion
The velocity gradient tensor can be decomposed into a symmetric tensor $A$ and an anti-symmetric tensor $B$, where $A$ represents fluid deformation effects and $B$ represents fluid rotation:
$$\nabla \boldsymbol{v}=A+B$$
$$A=\frac{1}{2}(\nabla \boldsymbol{v}+\nabla \boldsymbol{v}^T)=\begin{bmatrix}\frac{\partial u}{\partial x}&\frac{1}{2}\big(\frac{\partial u}{\partial y}+\frac{\partial v}{\partial x}\big)&\frac{1}{2}\big(\frac{\partial w}{\partial x}+\frac{\partial u}{\partial z}\big)\\\\\\\frac{1}{2}\big(\frac{\partial u}{\partial y}+\frac{\partial v}{\partial x}\big)&\frac{\partial v}{\partial y}&\frac{1}{2}\big(\frac{\partial v}{\partial z}+\frac{\partial w}{\partial y}\big)\\\\\frac{1}{2}\big(\frac{\partial w}{\partial x}+\frac{\partial u}{\partial z}\big)&\frac{1}{2}\big(\frac{\partial u}{\partial z}+\frac{\partial w}{\partial y}\big)&\frac{\partial w}{\partial z}\\\\\end{bmatrix}$$
$$B=\frac{1}{2}(\nabla \boldsymbol{v}-\nabla \boldsymbol{v}^T)=\begin{bmatrix}0&\frac{1}{2}(\frac{\partial u}{\partial y}-\frac{\partial v}{\partial x})&-\frac{1}{2}(\frac{\partial w}{\partial x}-\frac{\partial u}{\partial z})\\\\-\frac{1}{2}(\frac{\partial u}{\partial y}-\frac{\partial v}{\partial x})&0&\frac{1}{2}(\frac{\partial v}{\partial z}-\frac{\partial w}{\partial y})\\\\\frac{1}{2}(\frac{\partial w}{\partial x}-\frac{\partial u}{\partial z})&-\frac{1}{2}(\frac{\partial v}{\partial z}-\frac{\partial w}{\partial y})&0\\\\\end{bmatrix}$$
The Q-criterion requires that vortex structures exhibit **rotation** (antisymmetric tensor $B$), and its effect must exceed that of the symmetric tensor $A$ representing deformation:
$$Q=\frac{1}{2}(\parallel B\parallel^2-\parallel A\parallel^2)$$

#### $\Omega$ Method
The $\Omega$ method is an extension of the Q-criterion and can degenerate into the Q-criterion under special circumstances. A drawback of the Q-criterion is that small vortical structures may be overlooked if both $A$ and $B$ have small norms but satisfy rotation dominance. Thus, $\Omega$ is defined as:
$$\Omega=\frac{\left|\left|B\right|\right|_F^2}{\left|\left|B\right|\right|_F^2+\left|\left|A\right|\right|_F^2}$$

#### $\Delta$ Method
Matrices represent linear transformations, which can be viewed as rotations and scaling of a vector. The velocity gradient tensor represents both rotation (fluid rotation) and scaling (fluid acceleration or deceleration) at a point. A matrix with real eigenvalues implies scaling, while complex eigenvalues imply rotation. Therefore, for three-dimensional flows, the presence of two conjugate complex eigenvalues indicates streamlines bending. The characteristic equation:
$$\det(\nabla v-\lambda I)=0$$
can be written as:
$$\lambda^3+P\lambda^2+Q\lambda+R=0$$
where:
$$\begin{aligned}
&P=-\left(\lambda_1+\lambda_2+\lambda_3\right)=-\operatorname{tr}(\nabla V)\\
&Q=\lambda_1\lambda_2+\lambda_2\lambda_3+\lambda_3\lambda_1=-\frac{1}{2}\Big[\mathrm{tr}(\nabla V^2)+\mathrm{tr}(\nabla V)^2\Big]\\
&R=-\lambda_{1}\lambda_{2}\lambda_{3}=-\det(\nabla V)
\end{aligned}$$
The discriminant of this equation is:
$$\begin{aligned}
&\Delta=(Q'/3)^3+(R'/2)^2 \\
&Q^{\prime}=Q-\frac{P^{2}}{3} \\
&R'=R+\frac{2P^3}{27}-\frac{PQ}{3}
\end{aligned}$$
To have two complex roots, $Δ>0$. This method's advantage is its rigorous mathematical derivation, making it precise for distinguishing vortex and non-vortex regions. However, using $Δ$ to measure vortex strength lacks sufficient justification.

#### $\lambda_{2}$ Method
Similarly, decomposing the velocity gradient tensor into symmetric part $A$ and antisymmetric part $B$ yields:
$$A^2＋B^2＝－∇(∇p)/ρ$$
where $p$ represents pressure and $\rho$ represents density. When $A^2＋B^2$ has two negative eigenvalues, the pressure is minimal within the plane formed by the corresponding eigenvectors. If eigenvalues are arranged as $λ_1>λ_2>λ_3$, having two negative eigenvalues is equivalent to $λ_2<0$. However, this method assumes incompressibility and neglects unsteady and viscous terms, making it inaccurate for fields with strong unsteady and viscous effects. Additionally, $\lambda_{2}$ is a scalar and is polluted by stretching, compression, and shear.

### Third-Generation Vortex Identification Method—Liutex
$\vec{R}$ is defined as a vector using the real eigenvector of the velocity gradient tensor as the direction and twice the local fluid angular velocity as its magnitude. Liutex focuses on extracting the rigid rotation component from fluid motion to represent vortices, avoiding interference from stretching and shearing:
$$\begin{aligned}&\vec{R}=R\vec{r}\\&R=\vec{\omega}\cdot\vec{r}-\sqrt{(\vec{\omega}\cdot\vec{r})^{2}-4\lambda_{ci}^{2}}\end{aligned}$$
where $\vec{r}$ is the eigenvector of $\nabla \boldsymbol{v}$, and $\lambda_{ci}$ is the imaginary part of the eigenvalue.
