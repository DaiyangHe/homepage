## Evolution Equation
### Fundamental Solution to 1D Heat Equation
The term evolution equation refers to a dynamical partial differential equation that involves both time t and space x = (x₁, . . . , xₙ) as independent variables and takes the form$$\frac{\partial u}{\partial t} = K[u],$$where $K$ involves only the spatial derivatives of $u$, and $t$ or $x$. An example is Heat equation, which models how temperature $u(x,t)$ evolves in space and time due to conduction:$$\frac{ \partial u}{ \partial t}=\alpha \frac{ \partial^{2} u}{ \partial x^{2}}$$Consider an infinite rod under a unit heat pulse at origin:$$u(x,0)=\delta(x)$$ use Green function method, we know the solution is a Gaussian homogeneous heat kernel$$K(x,t)=u(x,t)=\frac{1}{\sqrt{4\pi\alpha t}}\exp\left(-\frac{x^2}{4\alpha t}\right),\quad t>0.$$we can see heat diffuses as a bell curve that broadens over time, with variance grows linearly and amplitude decreases as $\frac{1}{\sqrt{ t }}$. If initial temperature is arbitrary $u(x,0)=f(x)$, solution is given by **convolution with the homogeneous heat kernel**:$$u(x,t)=\int_{-\infty}^\infty\frac{1}{\sqrt{4\pi\alpha t}}\exp\left(-\frac{(x-y)^2}{4\alpha t}\right)f(y)dy.$$It indicates that the conduction of heat can also be described as a process that initial profile $f(x)$ **blurs out under Gaussian averaging**. Therefore, the fundamental solution is also called the Gaussian filter.
### Forced Heat Equation and Duhamel Principle
Inhomogeneous heat equation describes the bar subject to external heating source $h(x,t)$. $$\frac{ \partial u}{ \partial t}-\alpha\frac{ \partial^2 u}{ \partial x^2}=h(x,t)$$Duhamel’s principle says: The solution of a forced linear evolution PDE is the superposition of homogeneous solutions driven by the forcing, viewed as "instantaneous initial data". General solution with forcing is:$$u(x,t)=\underbrace{\int_{-\infty}^\infty K(x-y,t)f(y)}_{\text{evolution of initial condition}}dy+\underbrace{\int_0^t\int_{-\infty}^\infty K(x-y,t-s)h(y,s)dy}_{\text{accumulated effect of forcing}}ds.$$
### Black–Scholes Equation and Financial Mathematics
The most important and influential partial differential equation in financial modeling and
investment is the celebrated Black- Scholes equation$$\frac{\partial u}{\partial t}+\frac{\sigma^2}{2}x^2\frac{\partial^2u}{\partial x^2}+rx\frac{\partial u}{\partial x}-ru=0,$$The dependent variable $u(t,x)$ represents the monetary value of a single financial *option*, meaning a contract to either buy or sell an asset at a specified *exercise price* $p$ at a certain future time $t_{\star }.$ The value $u(t,x)$ of the option will depend on the current time $t\leq t_\star$ and the current price $x\geq0$ of the underlying asset. As with many financial models, one assumes the absence of arbitrage, meaning that there is no way to make a riskless profit. The constant $\sigma>0$ represents the asset's *volatility*, while $r$ denotes the (assumed fixed) *interest rate for bank deposits*, where investors could place their money with a guaranteed rate of return instead of buying the option. (Investors borrowing money to buy the asset would use a negative value of $r. )$ The derivation of the Black-Scholes equation from basic financial modeling relies on the theory of stochastic differential equations.

With a change of variables, it transforms into exactly heat equation: 
- Time reversal: $\tau = T-t$ (time to maturity).
- Log transformation: $x = \ln \frac{S}{K}$.
- Scale option price: $V(S,t) = K e^{-r\tau} u(x,\tau)$.
Then we have:$$\frac{\partial u}{\partial\tau}=\frac{1}{2}\sigma^2\frac{\partial^2u}{\partial x^2}.$$The solution is a convolution of the terminal payoff with the **Gaussian heat kernel**. Explicitly, for a call option, the celebrated **Black–Scholes formula** emerges:$$C(S,t) = S\Phi(d_{1}) - Ke^{-r(T-t)}\Phi(d_{2}),$$where:$$
d_{1,2} = \frac{\ln(S/K) + (r \pm \frac{1}{2}\sigma^{2})(T-t)}{\sigma\sqrt{T-t}},$$and $\Phi(\cdot)$ = standard normal CDF.
### Nonlinear Diffusion
#### Burgers Equation
The 1D viscous Burgers equation is:$$\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}=\nu\frac{\partial^2u}{\partial x^2},$$which is a simplified version (no pressure gradient term to smoothen solution) Navier-Stokes Equation. It models the competition between **advection** (1st-order term, nonlinear self-steepening of waves) and **diffusion** (2nd-order term, smoothing and dissipation). When $\nu=0$, it becomes a nonlinear transport equation (inviscid Burgers’ equation). 
#### Cole–Hopf Transformation
The viscous Burgers equation can be transformed into the heat equation. Let $$u(x,t)=-2\nu\frac{\partial}{\partial x}\ln\phi(x,t),$$and plug in we have:$$\phi_{t}=\nu \phi_{xx}.$$Then under initial condition  $u(x, 0)=f(x)$, we have:$$\phi(x,t)=\int_{-\infty}^\infty K(x-y,t)\phi(y,0)dy$$where$$\phi(x,0)=\exp\left(-\frac{1}{2\nu}\int^xf(y)dy\right).$$
### Dispersion and Solitons
#### Linear dispersion
Generally speaking, 3rd-order term induces dispersion, which means different wave components propagate at different speeds, and the waveforms spread out but the energy remains conserved. The simplest dispersion is:$$u_{t}+u_{xxx}=0$$which models the unidirectional propagation of linear dispersive waves. Use Fourier transform, we have: $$\frac{\partial\widehat{u}}{\partial t}-\operatorname{i}k^3\widehat{u}=0,$$where parameter $k$ represents spatial frequency. With the corresponding initial condition $\widehat{u}(k, 0)=\hat{f}(k)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}f(x)e^{-\operatorname{i}kx}dx$, the solution is $$u(t,x)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}\widehat{f}(k)e^{\mathrm{i}(kx+k^3t)}dk$$Similarly, the solution to linear Schrödinger equation $$iu_{t}+u_{xx}=0$$is also Gaussian-like:$$u(x,t)=\frac{1}{\sqrt{4\pi it}}\int e^{i(x-y)^2/(4t)}f(y)dy.$$
#### Solitons and KdV Equation
A soliton is a localized wave that retains its shape while propagating. It arises due to balance between **dispersion** (which tends to spread waves) and **nonlinearity** (which tends to focus/steepen waves). KdV Equation combines both of them:$$u_t+6uu_x+u_{xxx}=0.$$Its travelling wave solution is $$u(x,t)=A\operatorname{sech}^2(\sqrt{A/2}(x-At)),$$which mean its velocity is proportional to amplitude $A$. Also nonlinear Schrödinger (NLS) equation, which models envelope of wave trains in deep water or optics, has solution:$$u(x,t)=\eta\operatorname{sech}(\eta(x-2\xi t))e^{i(\xi x-(\xi^2-\eta^2)t)},$$indicates that localized wave packet that propagates without dispersing.
## Flow on lines
### Dynamic System
A _dynamical system_ is a rule advancing states in time. For continuous time, the rule is differential equation, and for discrete-time, that is difference equation (iterative advancing). A brief introduction refers to [Mathematical Modeling Tutorial - DE](http://hdy.xozv.top/static/files/Mathematical_Modeling_Tutorial_Differential_Equation.pdf)
### Phase Line
The autonomous scalar ODEs ($\dot{x}=f(x)$), which is the simplest but surprisingly complete class: in 1D there are no periodic or chaotic orbits—only equilibria and monotone motion between them. Refers to [[Differential Equation - MATH 290#Autonomous Equation|Autonomous Equation]]. When $f(x^*)=0$, we say $x^*$ it's a fixed point (equilibrium). **
- (Lyapunov) stability: solutions starting sufficiently close stay close for all $t>0$.
- Asymptotic stability: stable and $x(t)\to x^*$.
- Instability: some nearby solutions move away.
There are linearization method to classify: let $u=x-x^*$, by Taylor series we have:$$\frac{\mathrm{d }u}{\mathrm{d}t}=f(x^*+u)=f^{\prime}(x^*)u+O(u^2).$$
- If $f'(x^{*}) < 0$: $u(t) \sim u(0) e^{f'(x^{*})t}$ decays $\Rightarrow$ asymptotically stable.
- If $f'(x^{*}) > 0$: grows $\Rightarrow$ unstable.
- If $f'(x^{*}) = 0$: nonhyperbolic: linear test is inconclusive; decide by the sign change of $f$ across $x^{*}$ (e.g. $x' = x^{2}$ has a semi-stable equilibrium at 0: attracts from the left, repels from the right).
Hyperbolic equilibria are robust to small perturbations; nonhyperbolic ones are where **bifurcations** occur when a parameter is introduced.
## Bifurcation
A bifurcation occurs when a small smooth change in a system parameter causes a qualitative (topological) change in the dynamics. Consider $\dot{x}=f(x,r)$, at certain critical $r=r_{c}$, the structure of equilibria or their stability changes.
### Saddle–Node Bifurcation (Fold)
Normal form:$$\dot{x} = r + x^2.$$
- Equilibria: $x = \pm \sqrt{-r}$ (exist only if $r < 0$).
- Stability: left branch stable, right branch unstable.
- At $r = 0$, equilibria collide and annihilate.
Geometry:
- For $r < 0$: two fixed points.
- At $r = 0$: single semi-stable fixed point.
- For $r > 0$: no fixed points.
An canonic example is logistic model with harvesting:$$\dot{x}=rx\left(1-\frac{x}{K}\right)-h.$$with critical harvest $h_{c}=\frac{rK}{4}$
### Transcritical Bifurcation
Normal form:
$$\dot{x} = rx - x^2.$$
- Equilibria: $x = 0$ and $x = r$.
- Stability:
- $x = 0$ stable if $r < 0$, unstable if $r > 0$.
- $x = r$ unstable if $r < 0$, stable if $r > 0$.
- At $r = 0$, the equilibria exchange stability.
Example: SIS disease model:$$\frac{dI}{dt}=\beta I\left(1-\frac{I}{N}\right)-\gamma I$$By linearization, we have$\frac{\mathrm{d }I}{\mathrm{d}t}\approx(\beta-\gamma)I=\gamma(R_{0}-1)I$. The above conclusion can be easily validated.
### Pitchfork Bifurcation
Occurs in symmetric systems ($x\to-x$ symmetry).
(a) Supercritical Pitchfork
$$\dot{x} = rx - x^3.$$Equilibria: $x=0$, and $x = \pm \sqrt{ r }$ (for r > 0). Stability:
- For r < 0: only x = 0 (stable).
- For r > 0: x = 0 unstable, two symmetric stable equilibria appear.
where a single branch splits into two stable branches as parameter increases.
(b) Subcritical Pitchfork$$\dot{x} = rx + x^3.$$
- $x = 0$ stable for $r < 0$, unstable for $r > 0$.
- Two unstable equilibria appear for $r < 0$.
In real systems, imperfections smooth out the ideal diagram. If exact symmetry is broken, say $\dot{x}=rx-x^{3}+\epsilon$, the pitchfork unfolds into a saddle-node pair. This is called an imperfect bifurcation. 
## Flows on the Circle
On a circle, trajectories can wrap around. This makes oscillations and periodic motion possible. Consider the dynamic system $\dot{\theta}=f(\theta)$, think $\theta$ as an angular variable. The simplest case is uniform oscillator: $\dot{\theta}=\omega$. 
#### Phase Locking and Entrainment
Consider overdamped pendulum: $\dot{\theta}=\tau-\sin\theta$. It's derived from $$mL^2\ddot{\theta}+bL^2\dot{\theta}+mgL\sin\theta=\Gamma$$where $b$ is very large. This equation links with lots of natural phenomenon. An example synchronization of fireflies. Assume that in the absence of stimuli, the firefly goes through its
cycle at a frequency $\omega$, according to $\theta=\omega.$ Now suppose there's a periodic stimulus whose phase $\Theta$ satisfies$$\dot{\Theta}=\Omega,$$where $\Theta=0$ corresponds to the flash of the stimulus. We model the firefly's response as$$\dot{\theta}=\omega+A\sin(\Theta-\theta)$$The difference between two phases $\phi=\Theta-\theta$, then we have:$$\dot{\phi}=\dot{\Theta}-\dot{\theta}=\Omega-\omega-A\sin\phi$$It can be nondimensionalized by introducing$$\tau=At,\quad \mu=\frac{\Omega-\omega}{A},$$then$$\phi'=\mu-\sin \phi$$where $\phi'=\frac{\mathrm{d }\phi}{\mathrm{d}\tau}$. Because this system has a stable fixed point if $-1<\mu<1$, the phase difference tends to be constant. Therefore the interval $\Omega-A<\omega<\Omega+A$ is the range of entrainment. 

Another example is the Superconducting Josephson Junctions. A Josephson junction consists of two closely spaced superconductors separated by a weak connection. Cooper pairs in these superconductors performs a single macro wave function. Due to the quantum tunneling, it carries supercurrent. Now suppose it's driven by a constant current $I$, when $I<I_{c}$ no voltage will be developed. Phase difference $\phi$ between two superconductors will become a constant according to the Josephson current-phase relation $I=I_{c}\sin \phi$. When $I$ exceeds $I_c$, a constant phase difference can no longer be maintained and a voltage develops across the junction. The phases on the two sides of the junction begin to slip with respect to each other, with the rate of slippage governed by the Josephson voltage-phase relation $V=\frac{\hbar}{2e}\dot{\phi}$. Then we form a parallel circuit by adding a capacitor $C$ and a resistor $R$. According to Kirchhoff’s voltage and current laws, we have$$\frac{\hbar C}{2e}\ddot{\phi}+\frac{\hbar}{2eR}\dot{\phi}+I_c\sin\phi=I,$$which is exactly the form we discussed before. Similarly, we have$$\phi^{\prime}=\frac{I}{I_{c}}-\sin\phi.$$
## Dynamic Systems in the Plane
We now study systems of the form$$\dot{x}=Ax,\quad x \in \mathbb{R}^2, A\in \mathbb{R}^{2\times 2}$$The qualitative behavior depends entirely on the eigenvalues of $A$ for its solution is $x(t)=e^{ At }x_{0}$. 
### Classification of Linear System
Case 1: Real eigenvalues
Suppose $A$ has eigenvalues $\lambda_1, \lambda_2 \in \mathbb{R}$.
- Both negative: stable node (all solutions decay to origin).
- Both positive: unstable node (all solutions diverge).
- Opposite signs: saddle point (one stable and one unstable direction).
- Repeated eigenvalue: if diagonalizable $\rightarrow$ star node; if not $\rightarrow$ degenerate node with shearing.
Case 2: Complex eigenvalues
Suppose $\lambda = \alpha \pm i\beta$.
- $\alpha < 0$: stable spiral (spiral into origin).
- $\alpha > 0$: unstable spiral.
- $\alpha = 0$: center (closed orbits, pure oscillations, linearized version of harmonic oscillator).
Note it's impossible that $A$ has mixed eigenvalues in 2D.

Each type corresponds to a distinct phase portrait:
- Nodes: straight-line approach/escape.
- Saddle: hyperbolic structure with stable/unstable manifolds.
- Spiral: rotating convergence/divergence.
- Center: periodic orbits.

Strogatz includes a famous nonlinear dynamics example: $$\begin{align}
&\dot{R}=aR+bJ\\&\dot{J}=cR+dJ
\end{align}$$where $R(t)$ = Romeo’s love, $J(t)$ = Juliet’s love. If $a^2>b^2$, the relationship always fizzles out to mutual indifference. If $a^2<b^2$, the lovers are more daring, or perhaps more sensitive to each other. Now the relationship is explosive. Depending on their feelings initially, their relationship either becomes a love fest or a war. In either case, all trajectories approach the line $R=J$, so their feelings are eventually mutual.
### Phase Plane Analysis
A phase portrait is the global picture of trajectories in the plane. Key steps:
1. Find fixed points: solve $\dot{x} = f(x,y)$, $\dot{y} = g(x,y)$.
2. Linearize: compute Jacobian
$$
J = \begin{pmatrix}
f_x & f_y \\
g_x & g_y
\end{pmatrix}.
$$
Eigenvalues classify local behavior (node, spiral, saddle, etc).
3. Sketch nullclines ($f = 0$, $g = 0$) → intersections give equilibria.
4. Determine vector field directions in each region.
5. Assemble into a global phase portrait.
**Index theory**: Defines index of a closed curve = net number of times vector field rotates.
- Around a fixed point: node/saddle/spiral → index +1 or −1.
- Index theory constrains possible configurations of equilibria.
- For example: sum of indices in a bounded region = index of vector field on boundary.
This is useful in classifying phase portraits when equilibria are not all hyperbolic.

Nonlinear system near equilibrium: $$\dot{\mathbf{x}}=A\mathbf{x}+\mathbf{h}(\mathbf{x}),\quad\mathbf{h}=O(\|\mathbf{x}\|^2).$$If equilibrium is hyperbolic, local dynamics are topologically conjugate to the linearized system. If equilibrium is non-hyperbolic, higher-order terms matter, which means bifurcations appear. If there exists $H(x,y)$ such that$$\dot{x} = \frac{\partial H}{\partial y}, \quad \dot{y} = -\frac{\partial H}{\partial x},$$then trajectories lie on level curves of $H$. In physics, these systems are Hamiltonian systems (no dissipation) --- energy is conserved. An example is Simple pendulum without damping. 
## Limit Cycles
A limit cycle is an **isolated closed orbit** in the phase plane. They are the mathematical representation of sustained oscillations. An example is Van der Pol oscillator:$$\ddot{x}-\mu(1-x^2)\dot{x}+x=0.$$ It forms a limit cycle when $\mu>0$. In contrast, Lotka–Volterra predator-prey model has periodic orbits, but not limit cycles for they form closed families, not isolated. 
### Poincaré–Bendixson Theorem
This is the central theorem of planar dynamics: If a trajectory of a smooth 2D system remains in a compact region and does not converge to an equilibrium, then its limit set is a periodic orbit (a limit cycle). This theorem explains why limit cycles dominate 2D nonlinear systems. In 3D, chaos becomes possible; in 2D, cycles are the only nontrivial attractors. 

Consider Liénard system: $$\ddot{x}+f(x)\dot{x}+g(x)=0,$$where f be an even function and g be an odd function, it's obvious that it contains Van der Pol oscillator. A Liénard system has a unique and stable limit cycle surrounding the origin if it satisfies the following additional properties:
- $g(x) > 0$ for all $x > 0$;
- $\lim_{x \to \infty} F(x) := \lim_{x \to \infty} \int_{0}^{x} f(\xi) d\xi = \infty$;
- $F(x)$ has exactly one positive root at some value $p$, where $F(x) < 0$ for $0 < x < p$ and $F(x) > 0$ and monotonic for $x > p$.
Near a Hopf bifurcation, systems often reduce to weakly nonlinear oscillators.
Amplitude equation:
$$\begin{align}
&\dot{r} = \mu r - \alpha r^3,\\
&\dot{\theta} = \omega.
\end{align}$$
- Radial dynamics → stable or unstable limit cycle depending on sign of μ.
- This reduction explains how small-amplitude cycles emerge from equilibria.
### Hopf bifurcation
Consider a 2D system near an equilibrium. Its Jacobian has complex eigenvalues:$$\lambda_{1,2}(r)=\alpha(r)\pm i\omega(r),$$where $r$ is a parameter.
- At $r = r_c$ $\alpha(r_c) = 0$.    
- As $r$ crosses $r_c$, the equilibrium changes stability. 
- A limit cycle is born or destroyed.
Near the bifurcation, we can reduce dynamics to polar coordinates: $$\dot{r}=\mu r-\beta r^3,\quad\dot{\theta}=\omega.$$
- $\mu$: bifurcation parameter ($\mu=0$ at bifurcation). 
- $\beta$: nonlinear saturation.
#### Types of Hopf Bifurcation
1. Supercritical Hopf ($\beta > 0$)
   - For $\mu < 0$: stable equilibrium.
   - For $\mu > 0$: equilibrium becomes unstable, stable limit cycle emerges.
   - Oscillations grow smoothly from zero amplitude.
   - Common in physics, biology.

2. Subcritical Hopf ($\beta < 0$)
   - For $\mu < 0$: unstable limit cycle coexists with stable equilibrium.
   - At $\mu = 0$, equilibrium loses stability, leaving only unstable cycles $\rightarrow$ large-amplitude oscillations occur abruptly.
   - Dangerous in engineering (sudden jumps).
### Global Bifurcation
Hopf is local (determined by linearization + cubic term). Global bifurcations involve the global phase portrait and are harder to analyze.
(a) Homoclinic Bifurcation
- A homoclinic orbit is a trajectory that leaves a saddle point and returns to it.
- At bifurcation: stable and unstable manifolds of a saddle connect.
- Nearby, large-period oscillations occur (period → ∞ as cycle approaches saddle).
(b) Heteroclinic Bifurcation
- A heteroclinic orbit connects two different saddles.
- Dynamics can jump between states → models "winner-take-all" switching.
(c) Saddle-Node of Limit Cycles
- Two cycles (one stable, one unstable) collide and annihilate.
- Analog of saddle-node in equilibrium theory.
- Example: oscillatory chemical reactions.
## Lorenz System
This is maybe the most famous dynamic system. Edward Lorenz (1963) derived the equations while modeling atmospheric convection$$\begin{aligned}&\dot{x}=\sigma(y-x),\\&\dot{y}=x(\rho-z)-y,\\&\dot{z}=xy-\beta z.\end{aligned}$$with parameters:
- $\sigma > 0$: Prandtl number,
- $r > 0$: Rayleigh number (driving strength),
- $b > 0$: geometric factor.
Interpretation:
- $x$: intensity of convection,
- $y$: temperature difference,
- $z$: vertical temperature profile distortion.
System is invariant under $(x,y) \mapsto (-x, -y)$, which explains the “butterfly wings” of the Lorenz attractor.
### Stability Analysis
(a) Origin
Jacobian at origin:$$J(0) = \begin{pmatrix} -\sigma & \sigma & 0 \\ r & -1 & 0 \\ 0 & 0 & -b \end{pmatrix}.$$

- For $r < 1$: all eigenvalues negative $\Rightarrow$ origin stable.
- At $r = 1$: pitchfork bifurcation $\rightarrow$ origin loses stability, two symmetric equilibria $P_{\pm}$ appear.

(b) Symmetric equilibria: $P_\pm=\left(\pm\sqrt{b(r-1)},\pm\sqrt{b(r-1)},r-1\right).$
- Stable for small $r > 1$.
- As $r$ increases, these equilibria undergo Hopf bifurcation $\rightarrow$ oscillatory instability $\rightarrow$ chaotic dynamics.
It indicates a route to chaos: when $r<1$: origin stable; $r > 1$: origin unstable, two stable equilibria $P_\pm$. At larger $r$: equilibria $P_\pm$​ destabilize via **Hopf bifurcation**. Trajectories wander between neighborhoods of equilibria → chaotic attractor.

This system also famous for the first example of strange attractor: An attractor that is fractal (non-integer dimension), invariant (trajectories stay on it), sensitive to initial conditions. 
## Other Topics
### Lyapunov Exponents
#### Definition
A Lyapunov exponent measures the exponential rate at which nearby trajectories diverge or converge. Take two nearby initial conditions separated by δx(0). Their separation evolves as:
$$\|\delta x(t)\| \approx \|\delta x(0)\|e^{\lambda t}.$$
- If λ < 0: perturbations shrink → stable (converging).
- If λ > 0: perturbations grow → sensitive dependence on initial conditions (chaos).
- If λ = 0: neutral direction (typical for flows along trajectories).
#### Formal definition
$$
\lambda = \lim_{t \to \infty} \frac{1}{t} \ln \frac{\|\delta x(t)\|}{\|\delta x(0)\|}.$$
#### Properties
- In n-dimensional systems, there are n Lyapunov exponents (one per principal direction).
- For flows, one exponent is always 0 (corresponding to motion along the trajectory itself).
- A system is chaotic if it has at least one positive exponent.
#### Examples
- Stable equilibrium: all exponents negative.
- Limit cycle: one zero exponent (along cycle), rest negative.
- Lorenz attractor: one positive, one zero, one negative → chaos.
#### Physical meaning
- Largest Lyapunov exponent sets the predictability horizon:
$$T_{\text{predict}} \sim \frac{1}{\lambda_{\max}} \ln \frac{\Delta}{\delta_0},$$
where $\delta_0$ is initial error, $\Delta$ is tolerance.
- This is why long-term weather prediction is fundamentally limited.
### Hartman-Grobman Theorem
#### Statement
Near a hyperbolic equilibrium point (all eigenvalues of Jacobian have nonzero real parts), the nonlinear system$$\dot{x} = f(x)$$is topologically conjugate to its linearization$$\dot{y} = J(x^*)y, \quad J = Df(x^*).$$In words:
- Locally, the geometry (phase portrait) of the nonlinear system looks exactly like that of the linearized system, up to a continuous deformation.
- Straight lines in linear system become curved trajectories in nonlinear system, but qualitative behavior is identical.
#### Implications
- Validates our method of classifying equilibria by eigenvalues.
- Nodes, saddles, spirals → persist in nonlinear systems.
- Non-hyperbolic equilibria (where eigenvalue = 0 or purely imaginary) are special: linearization fails → bifurcations or centers may occur.
#### Examples
- 1D: If $f'(x^*) \neq 0$, stability type of equilibrium matches linearized result.
- 2D: Saddle, spiral, node classifications all hold by Hartman-Grobman.
- Hopf bifurcation: non-hyperbolic case ($\Re\lambda = 0$) where theorem doesn't apply — nonlinear terms crucial.
