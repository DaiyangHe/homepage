# Introduction to Partial Differential Equation
## Initial Value and Boundary Value

For ODE, it's not surprising that an n-order equation has infinite solutions, depending on $n$ arbitrary constants. However, for PDE, we can expect that an $n$-order PDE with $m$ independent variables has infinite solution depending on $m-1$ independent variables and $n$ arbitrary functions. In order to select desired solutions, we need initial value or boundary value. 

Boundary value conditions can be mainly divided into three categories:
- **Dirichlet boundary condition**: The value of the solution is given on boundary.
- **Neumann boundary condition**: Normal derivative of solution is given on boundary.
- **Mixed boundary condition**: Both kinds of boundary conditions are applied.
## Types of PDE
For second-order linear PDE, it can be divided into three types: Elliptic, Parabolic, and Hyperbolic. The general form of 2rd-order linear PDE is$$\sum_{i,j=1}^na_{ij}(x)\frac{\partial^2u}{\partial x_i\partial x_j}+(\text{lower order terms})=0$$The coefficient matrix $A(x)=[a_{ij}(x)]$ is symmetric and its eigenvalues are used as the determinant.
- All $\lambda\neq 0$ and **same sign** $\implies$ Elliptic: steady-state or equilibrium
- All $\lambda\geq 0$ and **some = 0** $\implies$ Parabolic: diffusion-like processes or evolution toward equilibrium
- Exactly one $\lambda_{i}=0$ $\implies$ Hyperbolic: wave-like or signal propagation
For 2D PDE, the simplified determinant $\Delta=B^2-AC$ can be used for$$A\frac{\partial^2u}{\partial x^2}+2B\frac{\partial^2u}{\partial x\partial y}+C\frac{\partial^2u}{\partial y^2}+\text{lower order terms}=0$$
- $\Delta<0 \implies$ Elliptic
- $\Delta=0\implies$ Parabolic
- $\Delta>0\implies$ Hyperbolic
# Linear and non-linear wave
## Stationary Wave, Travelling wave, and Transport

The simplest example of PDE about $u(x,t)$ may be:$$\frac{ \partial u}{ \partial t}=0$$By integral we have:$$0=\int_{0}^{t}\frac{ \partial u}{ \partial s}(x,s)\mathrm{d}s=u(x,t)-u(x,0)$$Therefore we have a classic solution: $u=u(x,0)$, which represents a stationary wave. This example may be too simple because $x$ here is indeed a parameter rather than an independent variable. Consider the following example:$$\frac{ \partial u}{ \partial t}+c\frac{ \partial u}{ \partial x}=0$$where $c$ is wave speed. We call this PDE as transport equation for it simulates the transportation of matters. We can import the characteristic variable $\xi=x-ct$ and $u(x,t)=v(x-ct,t)=v(\xi,t)$. we can rewrite the equation:$$\frac{ \partial u}{ \partial t}+c\frac{ \partial u}{ \partial x}=\frac{ \partial v}{ \partial t}-c\frac{ \partial v}{ \partial \xi}+c\frac{ \partial v}{ \partial \xi}=\frac{ \partial v}{ \partial t}$$Therefore $v(x,t)$ is a solution if and only if$$\frac{ \partial v}{ \partial t}=0,$$which means $u$ must be a function of $\xi$. We can see that for this equation, signals propagate along characteristics. Consider another constant $a>0$, $$\frac{ \partial u}{ \partial t}+c\frac{ \partial u}{ \partial x}+au=0$$is called damped transport equation. Its solution is given by$$u(x,t)=u(x-ct,0)e^{ -at }$$If the wave speed is not constant, then the wave will propagate along characteristic curve on the $xt-$plane. Say solution $x(t)$ to the autonomous ODE$$\frac{\mathrm{d }x}{\mathrm{d}t} =c(x)$$is the characteristic curve $\beta(x)$ of the transport function with wave speed $c(x)$. Then the solution is:$$u(x,t)=u(\beta^{-1}(\beta(x)-t),0)$$
**Example:** Solve the following equation:$$\frac{\partial u}{\partial t}+\frac{1}{x^2+1}\frac{\partial u}{\partial x}=0$$We can solve the characteristic curve:$$\frac{\mathrm{d }x}{\mathrm{d}t} =\frac{1}{x^{2}+1}$$we can get $\beta(x):\frac{1}{3}x^3+x=t+C$. Therefore the characteristic variable is $\xi=\frac{1}{3}x^3+x-t$ and the solution is$$u=v\left( \frac{1}{3}x^3+x-t \right)$$where $v(x,0)=\frac{1}{1+(x+3)^2}$, is the initial value. 
## d'Alembert Equation
Govern equation of small vibration in one-dimensional medium:$$\rho(x)\frac{\partial^2u}{\partial t^2}=\frac{\partial}{\partial x}\left(\kappa(x)\frac{\partial u}{\partial x}\right).$$It's derived from Newton's 2nd law, and we can see the RHS is the restoring forces due to the small deformation. If the medium is uniform, we get the one-dimensional wave equation:$$\frac{\partial^2u}{\partial t^2}=c^2\frac{\partial^2u}{\partial x^2},\quad\text{where the constant}\quad c=\sqrt{\frac{\kappa}{\rho}}>0$$If $u$ satisfies $u_t+cu_x=0$, it must be a solution to original PDE. Similarly, any backward wave such that $u_t-cu_x=0$ is also a solution. Therefore, we know that this wave equation is bidirectional. 
**Theorem:** Every solution to the wave equation can be written as a superposition of right and left traveling waves:$$u(t,x)=p(\xi)+q(\eta)=p(x-ct)+q(x+ct),$$where $p(\xi)$ and $q(\eta)$ are arbitrary function of characteristic variable. For the initial value:$$u(0,x)=p(x)+q(x)=f(x),\quad\frac{\partial u}{\partial t}(0,x)=-cp^{\prime}(x)+cq^{\prime}(x)=g(x),$$We have the following solution:$$u(t,x)=\frac{f(x-ct)+f(x+ct)}{2}+\frac{1}{2c}\int_{x-ct}^{x+ct}g(z)dz.$$
The first term represents two traveling waves moving in opposite directions without change in shape, and the integral term accounts for the initial velocity.
## External Forcing and Resonance
When a homogeneous vibrating medium is subjected to external forcing term $F(x,t)$, the PDE will be $$\frac{\partial^2u}{\partial t^2}=c^2\frac{\partial^2u}{\partial x^2}+F(x,t)$$with initial conditions:$$u(x,0)=f(x),\quad\frac{\partial u}{\partial t}(x,0)=g(x)$$The solution is given by$$u(x,t)=u_h(x,t)+u_p(x,t)$$where $u_{h}$ is the homogeneous wave solution, and $u_p$ is a **particular solution** that accounts for the forcing term. According to Duhamel’s Principle ([[Nonlinear Dynamics#Forced Heat Equation and Duhamel Principle|Duhamel Principle]]), we know $$u_{p}(x,t)=\frac{1}{2c}\int_0^t\int_{x-c(t-\tau)}^{x+c(t-\tau)}F(s,\tau)dsd\tau$$
# Fourier Series
## Half-Range Fourier Series
The basic form of Fourier series is given by$$f(x)\sim\frac{a_0}{2}+\sum_{n=1}^\infty\left[a_n\cos\left(\frac{n\pi x}{L}\right)+b_n\sin\left(\frac{n\pi x}{L}\right)\right]$$where$$a_n=\frac{1}{L}\int_{-L}^Lf(x)\cos\left(\frac{n\pi x}{L}\right)dx,\quad b_n=\frac{1}{L}\int_{-L}^Lf(x)\sin\left(\frac{n\pi x}{L}\right)dx$$These coefficients **project** f(x)f(x)f(x) onto the **orthogonal basis** of sine and cosine functions.

Suppose $f(x)$ is defined on $[0,L]$. There are two ways to extend it to $[-L,L]$:
- Even extension: reflect symmetrically $\rightarrow$ leads to a cosine series (Dirichlet BCs).
- Odd extension: reflect antisymmetrically $\rightarrow$ leads to a sine series (Neumann BCs).
Thus, on $[0,L]$:$$f(x)\sim\frac{a_0}{2}+\sum_{n=1}^\infty a_n\cos\left(\frac{n\pi x}{L}\right)\sim b_n\sin\left(\frac{n\pi x}{L}\right)$$
## Fourier Transform
see [[Integral Transform#Fourier Transform|Fourier Transform]].  
# Eigen solutions of Linear Evolution Equations
## Separation of Variables and Eigenfunction Expansion
If the PDE is linear and homogeneous, (also BC is homogeneous) we assume the solution can be written as a product of temporal part and spatial part. For example, consider 1D wave equation with Dirichlet BC (fixed ends):$$\frac{\partial^2u}{\partial t^2}=c^2\frac{\partial^2u}{\partial x^2},\quad0<x<L,t>0$$and initial condition:$$u(x,0)=f(x),\quad\frac{\partial u}{\partial t}(x,0)=g(x)$$we can write the solution as:$$u(x,t)=X(x)T(t)$$Substitute into the wave equation$$X(x)T''(t) = c^2 X''(x)T(t) \quad \Rightarrow \quad \frac{T''(t)}{c^2 T(t)} = \frac{X''(x)}{X(x)} = -\lambda$$This gives two ODEs, Spatial ODE:$$X^{\prime\prime}(x)+\lambda X(x)=0,\quad X(0)=X(L)=0$$and temporal ODE:$$T^{\prime\prime}(t)+c^2\lambda T(t)=0$$For spatial ODE, we know the eigenfunctions of Laplacian on $[0,L]$ with Dirichlet BC is $\left\{ \sin\left( \frac{n\pi x}{L} \right) \right\}$, where $\lambda=\left( \frac{n\pi}{L} \right)^{2}, n=1,2,3,\dots$ For temporal ODE, we have $T_n(t)=A_n\cos\left(\frac{n\pi ct}{L}\right)+B_n\sin\left(\frac{n\pi ct}{L}\right)$. The total solution is given by$$u(x,t)=\sum_{n=1}^\infty\left[A_n\cos\left(\frac{n\pi ct}{L}\right)+B_n\sin\left(\frac{n\pi ct}{L}\right)\right]\sin\left(\frac{n\pi x}{L}\right)$$Coefficients are determined by initial conditions$$A_n=\frac{2}{L}\int_0^Lf(x)\sin\left(\frac{n\pi x}{L}\right)dx,\quad B_{n}=\frac{2}{n\pi c}\int_{0}^{L}g(x)\sin\left(\frac{n\pi x}{L}\right)dx$$
## Sturm–Liouville Theory
Sturm–Liouville theory is a cornerstone of solving PDEs by separation of variables. A regular Sturm–Liouville problem is a second-order ODE of the form: $$\frac{d}{dx}\left[p(x)\frac{dy}{dx}\right]+\left[\lambda w(x)-q(x)\right]y=0,$$on $a<x<b$ with BC:$$\alpha_1y(a)+\alpha_2y^{\prime}(a)=0,\quad\beta_1y(b)+\beta_2y^{\prime}(b)=0$$We can write the S–L equation as:$$L[y]=-\frac{d}{dx}\left[p(x)\frac{dy}{dx}\right]+q(x)y=\lambda w(x)y$$Here $L$ is a **self-adjoint differential operator** under the inner product:$$\langle f,g\rangle=\int_a^bf(x)g(x)w(x)dx$$If $p,p^{\prime},q,w$ are continuous and $p,w>0$ then the set $\{y_{n}(x)\}$ forms a complete basis in $L^{2}_{w}(a,b)$, meaning any reasonable function can be expanded as:$$f(x) = \sum_{n=1}^{\infty} c_{n}y_{n}(x),$$where$$
c_{n} = \frac{\int_{a}^{b} f(x)y_{n}(x)w(x)dx}{\int_{a}^{b} y_{n}(x)^{2}w(x)dx}.$$
# Special Functions
## Green Functions method
**Green’s function method** is one of the most powerful tools for solving linear inhomogeneous PDEs, For a linear differential operator $L$ acting on $u$:$$Lu(x) = f(x), \quad x \in \Omega,$$with given boundary conditions (BCs). The Green's function $G(x, \xi)$ is defined as the solution to:
$$
LG(x, \xi) = \delta(x - \xi), \quad \text{with the same BCs in } x,$$By analogy, here the Green function is kind of like the "inverse matrix" of $L$ ($AG=e$). So we know the solution can be expressed as$$u(x)=\int_\Omega G(x,\xi)f(\xi)d\xi.$$**Example**: 1D Poisson Equation:$$-u''(x) = f(x), \quad 0 < x < L,$$where$$u(0) = 0, \quad u(L) = 0.$$We want $G(x, \xi)$ such that:$$\begin{align}
&-\frac{\partial^2}{\partial x^2} G(x, \xi) = \delta(x - \xi), \\
&G(0, \xi) = 0, \quad G(L, \xi) = 0.
\end{align}$$For $x < \xi$:$$-G'' = 0 \quad \Rightarrow \quad G(x, \xi) = A_1 x + B_1.$$For $x > \xi$:$$
-G'' = 0 \quad \Rightarrow \quad G(x, \xi) = A_2 x + B_2.$$Apply boundary conditions
- At $x = 0$: $G(0, \xi) = 0 \Rightarrow B_1 = 0$.
- At $x = L$: $G(L, \xi) = 0 \Rightarrow A_2 L + B_2 = 0$.
Because of continuity: $$G(\xi^-,\xi)=G(\xi^+,\xi)\quad\Rightarrow\quad A_1\xi=A_2\xi+B_2.$$And consider the property of Dirac Delta function, we Integrate $-G'' = \delta$ from $\xi - \epsilon$ to $\xi + \epsilon$:
$$-[G'(\xi^+) - G'(\xi^-)] = 1 \quad \Rightarrow A_2 - A_1 = -1.$$The Green solution is$$G(x,\xi)=\begin{cases}\frac{x(L-\xi)}{L},&0\leq x\leq\xi,\\\frac{\xi(L-x)}{L},&\xi\leq x\leq L.&\end{cases}.$$
## Bessel Function
Bessel functions appear when solving PDEs in cylindrical coordinates. Bessel equation can be derived from Helmholtz equation $\nabla^2u+k^2u=0$, after separation of variables, the radial part is$$r^2R^{\prime\prime}(r)+rR^{\prime}(r)+(k^2r^2-m^2)R(r)=0$$or generalized version$$x^2y^{\prime\prime}+xy^{\prime}+(x^2-\nu^2)y=0$$where $\nu$ is the order of Bessel function. The general solution is $$y(x)=AJ_\nu(x)+BY_\nu(x)$$where $J_{\nu}$ is the Bessel function of the first kind, which is finite at $x=0$. And $Y_{\nu}$ is the Bessel function of the second kind (Neumann function), which is singular at $x=0$.

**Properties:**
- Oscillatory for large $x$:
$$J_{\nu}(x) \approx \sqrt{\frac{2}{\pi x}} \cos \left(x - \frac{\nu \pi}{2} - \frac{\pi}{4}\right)$$
- Orthogonality (Sturm–Liouville property): If $\alpha_{\nu,n}$ is the $n$-th positive zero of $J_{\nu}$,
$$
\int_{0}^{1} r J_{\nu}(\alpha_{\nu,m} r) J_{\nu}(\alpha_{\nu,n} r) \, dr = 0 \quad (m \neq n)$$
- Zeros: Important for eigenvalue problems with boundary conditions $R(a) = 0$.
## Legendre Function
Legendre functions arise when solving PDEs in spherical coordinates. For example, Laplace's equation in spherical coordinates ($r,\theta, \phi$):
$$\frac{\partial}{\partial r} \left( r^2 \frac{\partial u}{\partial r} \right) + \frac{1}{\sin \theta} \frac{\partial}{\partial \theta} \left( \sin \theta \frac{\partial u}{\partial \theta} \right) + \frac{1}{\sin^2 \theta} \frac{\partial^2 u}{\partial \phi^2} = 0$$
Separating $\theta$ and $\phi$ gives the associated Legendre equation. Legendre equation:$$(1-x^2)y^{\prime\prime}-2xy^{\prime}+\ell(\ell+1)y=0$$

**Properties**:
- Orthogonality:
$$\int_{-1}^{1} P_{\ell}(x)P_{m}(x) \, dx = \frac{2}{2\ell+1} \delta_{\ell m}$$
- Normalization: $P_{\ell}(1) = 1$
- Recurrence:$$
(\ell + 1)P_{\ell+1}(x) = (2\ell + 1)xP_{\ell}(x) - \ell P_{\ell-1}(x)$$When separation in $\phi$ gives a factor $e^{im\phi}$, the $\theta$-part satisfies:$$(1-x^2)y'' - 2xy' + \left[\ell(\ell+1) - \frac{m^2}{1-x^2}\right]y = 0,$$with $x = \cos\theta$. Solutions are associated Legendre functions:$$
P_\ell^m(x) = (-1)^m(1-x^2)^{m/2}\frac{d^m}{dx^m}P_\ell(x)$$