# Metric Space
A metric space is a pair $(X,d)$, where $X$ is a set and $d$ is a metric on $X$ (or distance function on $X)$, that is, a function defined on $X\times X$ such that for all $x,y,z\in X$ we have:
- $d$ is real-valued, finite and non-negative.
- $d(x,y)=0$ if and only if $x=y$
- $d(x,y)=d(y,x)$: symmetric
- $d(x,y)\leq d(x,z)+d(z,y)$: Triangular inequality
$X$ is usually called the *underlying set* of $(X,d)$, and its elements are called points. All ordered $n$-tuples of real numbers like $x=(\xi_{1},\xi_{2},\dots,\xi_{n}),y=(\eta_{1},\eta_{2},\dots,\eta_{n})$ can be underlying sets of a **Euclidean space** with Euclidean metric:$$d(x,y)=\sqrt{ \left( \sum_{i=1}^{n}(\xi_{i}-\eta_{i})^{2} \right) }$$**n-dimensional unitary space** $C^n$ is the space of all ordered n-tuples of complex numbers with metric defined by$$d(x,y)=\sqrt{|\xi_1-\eta_1|^2+\cdots+|\xi_n-\eta_n|^2}$$when $n=1$, the **complex plane** $C$ is obtained. $C^n$ is sometimes called **complex Euclidean n-space.** By definition, each element of **space $B(A)$ of bounded functions** $x\in B(A)$ is defined and bounded on a set $A$, and the metric is defined by$$d(x,y)=\sup_{t\in A}|x(t)-y(t)|$$**Space** $l^p$: If $p\geq 1$ is a constant, every element in he space $l^p$ is a series $x=(\xi_{i})$ such that $|\xi_{1}|^{p}+|\xi_{2}|^p+\cdots$ converges,$$\sum_{i=1}^{\infty}|\xi_{i}|^{p}<\infty$$the metric is defined as$$d(x,y)=\left( \sum_{i=1}^\infty|\xi_{i}-\eta_{i}|^p \right)^{1/p}$$where $y=(\eta_i)$ and $\sum|\eta_{i}|^p<\infty$. While $p=2$, we get the Hilbert sequence space. let $p>1$, we define another real number $q$ such that$$\frac{1}{p}+\frac{1}{q}=1$$then $p$ and $q$ are called conjugate exponents. They satisfy:$$1=\frac{p+q}{pq},\quad pq=p+q,\quad (p-1)(q-1)=1,\quad u=t^{p-1}\iff t=u^{q-1}$$Let $\alpha$ and $\beta$ to be any  positive number, we have following inequality:$$\alpha\beta\leq \int_{0}^\alpha t^{p-1}\mathrm{d}t+\int_{0}^{\beta}u^{q-1}\mathrm{d}u=\frac{\alpha^p}{p}+\frac{\beta^q}{q}$$Let $(\eta_{i})$ and $(\xi_{i})$ satisfy$\sum|\tilde{\xi}_i|^p=1$ and $\sum|\tilde{\eta}_i|^q=1$, respectively. Setting $\alpha=|\eta_{i}|$ and $\beta=\xi_{i}$, the inequality is transferred into$$|\tilde{\xi}_{j}\tilde{\eta}_{j}|\equiv\frac{1}{p}|\tilde{\xi}_{j}|^{p}+\frac{1}{q}|\tilde{\eta}_{j}|^{q}$$Let $(\eta_{i})$ and $\xi_{i}$ to be any sequence and set$$\tilde{\xi}_{i}=\frac{\xi_{i}}{\left(\sum\lvert\xi_{k}\rvert^{p}\right)^{1/p}},\quad\tilde{\eta}_{i}=\frac{\eta_{i}}{\left(\sum\lvert\eta_{m}\rvert^{q}\right)^{1/q}}$$We got the **Holder inequality**$$\sum_{j=1}^{\infty}|\xi_{j}\eta_{j}|\leqq\left(\sum_{k=1}^{\infty}|\xi_{k}|^{p}\right)^{1/p}\left(\sum_{m=1}^{\infty}|\eta_{m}|^{q}\right)^{1/q}$$When $p=q=2$, the Cauchy-Schwarz inequality for sums:$$\sum_{j=1}^\infty|\xi_j\eta_j|\leq\sqrt{\sum_{k=1}^\infty|\xi_k|^2}\sqrt{\sum_{m=1}^\infty|\eta_m|^2}$$the space $l^2$ is the Hilbert space. The Minkowski inequality for sums:$$\left(\sum_{j=1}^{\infty}|\xi_{j}+\eta_{j}|^{p}\right)^{1/p}\leq\left(\sum_{k=1}^{\infty}|\xi_{k}|^{p}\right)^{1/p}+\left(\sum_{m=1}^{\infty}|\eta_{m}|^{p}\right)^{1/p}$$
## Open Set, Closed Set, and Neighborhood
Consider the metric space $X=(x,d)$, given $x_{0}\in X$ and positive real number $r$, we can define three subsets:$$\begin{align}
B(x_{0};r)&=\{x\in X\mid d(x,x_0)<r\}\quad(\mathrm{Open\ ball}) \\
\tilde{B}(x_0;r)&=\{x\in X\mid d(x,x_0)\leq r\}\quad\mathrm{(Closed\ ball)} \\
S(x_0;r)&=\{x\in X\mid d(x,x_0)=r\}\quad\mathrm{(Sphere)}
\end{align}$$which meet$$S(x_0;r)=\tilde{B}(x_0;r)-B(x_0;r)$$Note that those subsets don't always share the same properties with those in $\mathbb{R}^3$, for example, consider the discrete metric space with $d(x,y)=1,\ d(x,x)=0$. 
### Definition
For a subset $M$ of a metric space $X$, if for each point there is an open ball that is contained by $M$, then $M$ is said to be open. If the complement $M^C=X-M$ is open, then $M$ is closed. Open ball $B(x_{0};\varepsilon)$ is said to be a $\varepsilon$ neighborhood of $x_0$. $x_0$ is a point of each of its neighborhoods. 

We call $x_0$ an interior point of a set $M\subset X$ if $M$ is a neighborhood of $x_0. The interior of $M$ is the set of all interior points of $M$ and may be denoted by $M^{0}$ or $\mathrm{Int}(M)$, but there is no generally accepted notation. Int$(M)$ is open and is the largest open set contained in $M.$

For two metric spaces $X=(X,d)$ and $Y=(Y,\tilde{d})$, a mapping $T:X\rightarrow Y$ is said to be continuous at a point $x_{0}$ if $$\tilde{d}(Tx,Tx_0)<\varepsilon\quad\text{for all }x\text{ satisfying }\quad d(x,x_0)<\delta.$$$T$ is continuous if $T$ is continuous for all $x_{0}\in X$
![[Pasted image 20250123211722.png|250]]
**Theorem:** A mapping T of a metric space X into a metric space Y is continuous if and only if the inverse image of any open subset of Y is an open subset of X.
![[Pasted image 20250123211931.png|300]]
Let $M$ be a subset of a metric space $X.$ Then a point $x_0$ of $X$ (which may or may not be a point of $M$) is called an accumulation point of $M$ (or limit point of $M$) if every neighborhood of $x_0$ contains at least one point $y\in M$ distinct from $x_0.$ The set consisting of the points of $M$ and the accumulation points of $M$ is called the closure of $M$ and is denoted by $\bar{M}.$ It is the smallest closed set containing $M.$

A **dense set** in a topological space is a set whose closure equals the entire space. $X=\bar{M}$. Intuitively, it means that every point in the space is either in the dense set or can be arbitrarily closely approximated by points from the dense set. A **separable space** is a topological space that has a countable dense subset.

Let $(X, d)$ be a metric space, where $d$ is the distance function. A sequence $\{x_n\}$ in $X$ is called a **Cauchy sequence** if for every $\varepsilon > 0$, there exists a positive integer $N$ such that:$$d(x_n, x_m) < \varepsilon \quad \text{for all } n, m \geq N$$The space $X$ is said to be **complete** if every Cauchy sequence in $X$ converges (that is, has a limit which is an element of $X$).
# Normed Space and Banach Space
## Definition
A normed space (normed linear space) is a vector space with introduction of norms of vectors. Banach space is complete normed space. A norm on a (real or complex) vector space $X$ is a real-valued function on $X$ whose value at an $x\in X$ is denoted by $||x||$ and possesses the following properties:$$\begin{gathered}\|x\|\geqq0\\\|x\|=0\quad\Longleftrightarrow\quad x=0\\||\alpha x||=||\alpha|\ ||x||\\\|x+y\|\leqq\|x\|+\|y\|\end{gathered}$$Some examples of Banach spaces: Euclidean space $R^n$ and unitary space $C^n$ (with norm $||x||=\|x\|=\left(\sum_{j=1}^n|\xi_j|^2\right)^{1/2}$). Also $l^{p}$ space is also a Banach space with norm $\|x\|=\left(\sum_{j=1}^\infty|\xi_i|^p\right)^{1/p}$
## linear functional
A functional is an operator whose range lies on the real line $R$ or in the complex plane $C$. A linear functional is an operator on a vector space and outputs a scalar. Specifically, if $X$ is a vector space over a field $\mathbb{F}$ (where $\mathbb{F}$ is typically $\mathbb{R}$ or $\mathbb{C}$ ), a linear functional is a mapping $f:X\to\mathbb{F}$ that satisfies the following two properties for all $x,y\in X$ and $\alpha\in\mathbb{F}:$
- **Additivity**: $f(x+y)=f(x)+f(y)$
- **Homogeneity**: $f(\alpha x)=\alpha f(x)$
- **Domain and Codomain**: The domain is the vector space $X$, and the codomain is the field $\mathbb{F}$. For example, if $X$ is a space of functions, $f$ maps these functions to a scalar.
The norm of $f$ is defined as $$\|f\|=\sup_{\underset{x\neq0}{x\in\mathcal{D}(f)}}\frac{|f(x)|}{||x||}\quad \text{or}\quad \|f\|=\sup_{\underset{\|x\|=1}{x\in\mathcal{D}(f)}}|f(x)|.$$If $\mathcal{D}(f)$ is a normed space, then $f$ is continuous if and only if $f$ is bounded. Here are some examples of linear functional.
### Dot Product
The familiar dot product with one factor kept fixed defines a functional $f$:$$f(x)=x\cdot a$$let $x=a$, we know$$\|f\|\geq\frac{|f(a)|}{\|a\|}=\frac{\|a\|^2}{\|a\|}=\|a\|$$Hence $\|f\|=\|a\|$
### Definite Integral
The definite integral is a number if we consider it for a single function, as we do in calculus most of the time. However, the situation changes completely if We consider that integral for all functions in a certain function space. Then the integral becomes a functional on that space.$$f(x)=\int_{a}^bx(t)\mathrm{d}t$$Because $$\left|f(x)\right|=\left|\int_a^bx(t)dt\right|\leqq(b-a)\max_{t\in J}\left|x(t)\right|=(b-a)\left\|x\right\|$$where $J=[a,b]$, therefore$$\|f\|\geqq\frac{|f(x_0)|}{\|x_0\|}=|f(x_0)|=\int_a^bdt=b-a.$$
### Space $l^2$
We can obtain a linear functional f on the Hilbert space $l^2$. For a fixed $\alpha=(\alpha_{j}\in l^2)$, then$$f(x)=\sum_{j=1}^\infty\xi_j\alpha_j$$where $x=(\xi_{j})\in l^{2}$According to the Cauchy-Schwarz inequality$$\left|f(x)\right|=\left|\sum\xi_j\alpha_j\right|\leqq\sum|\xi_j\alpha_j|\leqq\sqrt{\sum|\xi_j|^2}\sqrt{\sum|\alpha_j|^2}=\|x\|\|a\|$$which means the the series $f(x)$ is absolutely convergent, and $f$ is bounded. 
### Dual Space
The set of all linear functionals defined on a vector space $X$ can itself be made into a vector space. This space is denoted by $X^*$ and is called the **algebraic dual space** of $X$.

the **normed space of operators** $B(X,Y)$ is the collection of all bounded linear operators between two normed spaces $X, Y$. The dual space $X'$ of a normed space $X$ is a Banach space (whether or not $X$ is).
**Example**: The Dual Space of $\mathbb{R}^n$
For the space $\mathbb{R}^n$ (with the usual Euclidean norm), the dual space $(\mathbb{R}^n)^*$ consists of all linear functionals $f:\mathbb{R}^n\to\mathbb{R}$. Each functional can be represented as a row vector $(a_1,a_2,\ldots,a_n)$ ,and the action of $f$ on a vector $x=(x_1,x_2,\ldots,x_n)$ is given by the dot product:$$f(x)=a_1x_1+a_2x_2+\cdots+a_nx_n.$$In this case, the dual norm is simply the Euclidean norm of the vector of coefficients:$$\|f\|_{X^*}=\|(a_1,a_2,\ldots,a_n)\|=\sqrt{a_1^2+a_2^2+\cdots+a_n^2}.$$
# Inner Product Space and Hilbert Space
## Definition
An **inner product space** is a vector space $X$ over a field $\mathbb{F}$ (typically $\mathbb{R}$ or $\mathbb{C}$) that is equipped with an inner product. The norm is defined by $\|x\|=\sqrt{\langle x,x\rangle}$. $l^p$ space is not the inner product space (also not the Hilbert space) when $p\neq 2$.

A **Hilbert space** is a **complete inner product space**. This means that it is an inner product space that also satisfies the condition of completeness 
## Riesz Representation
In a Hilbert space, every continuous linear functional $f$ can be represented uniquely as an inner product with some vector $y \in X$, i.e., there exists $y \in X$ such that:$$f(x)=\langle x,y\rangle\quad\text{for all }x\in X$$Kernel of an operator is the null space of it.

$\ell^2$ Space: The space of sequences $\ell^2=\{(x_n):\sum_{n=1}^\infty|x_n|^2<\infty\}$ is a Hilbert space with the inner product:$$\langle(x_n),(y_n)\rangle=\sum_{n=1}^\infty x_n\overline{y_n}.$$$L^2$ Space: The space of square-integrable functions $L^2(\mathbb{R})=\{f:\int_{\mathbb{R}}|f(x)|^2dx<\infty\}$ is a Hilbert space with the inner product:$$\langle f,g\rangle=\int_\mathbb{R}f(x)\overline{g(x)}dx.$$
## Hilbert-Adjoint Operator
Let $T: H_{1} \to H_{2}$ be a bounded linear operator, where $H_{1}$ and $H_{2}$ are Hilbert spaces. Then the Hilbert-adjoint operator $T^*$ of $T$ is the operator $T^*: H_{2}\to H_{1}$ such that$$\langle Tx,y\rangle=\langle x,T^*y\rangle$$and:
- $\|T^*\|=\|T\|$. 
- $\langle T^{*}y,x\rangle=\langle y,Tx\rangle$
- For an operator $S:H_{1}\to H_{2}$, $(S+T)^*=S^*+T^*$
- $(T^*)^*=T$
- $\|T^*T\|=\|T\|^2$
- $(ST)^*=T^*S^*$ if $H_{1}=H_{2}$
## Self-Adjoint, Unitary and Normal Operators
### Self-Adjoint Operator
An operator $T$ is called **self-adjoint** if it is equal to its adjoint$$T^*=T$$
- They are always **symmetric** (in the case of real Hilbert spaces).
- If $T$ is self-adjoint, its spectrum lies on the real axis.
- In quantum mechanics, self-adjoint operators represent **observables** since they have real eigenvalues.
### Unitary Operator

An operator $U$ on a Hilbert space $\mathcal{H}$ is unitary if it satisfies:$$U^*U=UU^*=I,$$where $I$ is the identity operator. This means that $U$ preserves the inner product, i.e., for all $x,y\in\mathcal{H}{:}$$$\langle Ux,Uy\rangle=\langle x,y\rangle.$$Properties of unitary operators:
- They are bijective and have an inverse, which is also unitary 
- Unitary operators preserve lengths and angles, making them analogous to rotations or reflections in finite-dimensional spaces.
- In quantum mechanics, unitary operators are used to represent time evolution and state transformations, as they preserve probability.
### Normal Operators
An operator $T$ is called normal if it commutes with its adjoint:$$TT^*=T^*T.$$In other words, a normal operator is one for which the adjoint and the operator itself "can be
simultaneously diagonalized" (in finite-dimensional spaces)

Properties of normal operators:
- Every normal operator has a complete set of eigenvectors and can be diagonalized by a unitary operator, i.e., there exists a unitary operator $U$ such that $UTU^*$ is diagonal.
- Self-adjoint and unitary operators are examples of normal operators.In fact, all self-adjoint and unitary operators are normal, but not all normal operators are self-adjoint or unitary.
- The spectral theorem is a key result for normal operators, stating that they can be diagonalized by a unitary matrix in a Hilbert space.

For a linear operator $T:C^n\to C^n$,
- If $T$ is self-adjoint, then the associated matrix is a **Hermitian matrix**
- If $T$ is unitary, then the associated matrix is an **unitary matrix**
- If $T$ is normal, then the associated matrix is a **normal matrix**
Similarly, for a linear operator $T:R^n\to R^n$.
- If $T$ is self-adjoint, then the associated matrix is a **real symmetric matrix**
- If $T$ is unitary, then the associated matrix is an **orthogonal matrix**
# Basic Theorem of Banach Space
## Hahn-Banach Theorem
### Definition
Let $X$ be a real or complex vector space, and $p:X\to\mathbb{R}$ be a sublinear function (i.e., a
function that satisfies the following properties for all $x,y\in X$ and scalar $\alpha\in\mathbb{R}$ or $\mathbb{C}):$$$p(\alpha x)=\alpha p(x)\quad\mathrm{for}\quad\alpha\geq0\qquad\mathrm{and}\qquad p(x+y)\leq p(x)+p(y)$$Let $Y$ be a **subspace** of $X$, and let $f: Y \to \mathbb{R}$ (or $\mathbb{C}$) be a **linear functional** on $Y$ such that:$$f(y)\leq p(y)\quad\mathrm{for~all}\quad y\in Y$$then the **Hahn-Banach theorem** asserts that there exists an extension of $f$ to a linear functional $\tilde{f}: X \to \mathbb{R}$ (or $\mathbb{C}$) such that:
- $\tilde{f}(y)=f(y)\quad\mathrm{for~all}\quad y\in Y$
- $\tilde{f}(x)\leq p(x)\quad\mathrm{for~all}\quad x\in X$
- $\|\tilde{f}\|=\|f\|$
In other words, the Hahn-Banach theorem ensures that we can extend the linear functional from a subspace $Y$ to the whole space $X$ without increasing the bound determined by the sublinear function $p$. 
## Banach Fixed Point
Let map $T: X\to X$, if exists a $x$ such that$$Tx=x$$the $x$ is a fixed point of $T$. 

Let $X = (X, d)$ be a metric space. A mapping $T: X \to X$ is called a **contraction** on $X$ if there is a positive real number $\alpha < 1$ such that for all $x, y \in X$:$$d(Tx,Ty)\leq d(x,y)$$Geometrically this means that any points $x$ and $y$ have images that are closer together than those points $x$ and $y$; more precisely, the ratio $\frac{d(Tx, Ty)}{d(x, y)}$ does not exceed a constant a which is strictly less than $1$.
### Definition
Let $(X,d)$ be a complete metric space, and let $T:X\to X$ be a contraction mapping, then $T$ has a unique fixed point. 
### Iteration
For any initial point $x_0 \in X$, the sequence $\{x_n\}$ defined by the recurrence relation $x_{n+1} = T(x_n)$ will converge to the unique fixed point $x^*$.$$\lim_{ n \to \infty } x_{n}=x^*$$The error bound can be estimated by the prior estimate:$$d(x_{m},x^*)\leq\frac{\alpha^{m}}{1-\alpha}d(x_{0},x_{1})$$and the posterior estimate:$$d(x_{m},x^*)\leq \frac{\alpha}{1-\alpha}d(x_{m-1},x_{m})$$
## Application
### Linear Equation System
There are various direct methods (methods that would yield the exact solution after finitely many arithmetical operations if the precision-the word length of our computer-were unlimited) to solve linear equation system, a familiar example is Gauss' elimination method. However, an iteration, or indirect method, may be more efficient if the system is special, for instance, if it is sparse. Moreover, the usual direct methods require about $\frac{1}{3}n^3$ arithmetical operations (n is the number of equations and the number of unknowns), and for large n, rounding errors may become quite large, whereas in an iteration, errors due to round off (or even blunders) may be damped out eventually. In fact, iteration methods are frequently used to improve "solutions" obtained by direct methods.

To apply Banach's theorem, we need a complete metric space and a contraction mapping on it. We take the set $X$ of all ordered n-tuples of real numbers, written$$x=(\xi_1,\cdots,\xi_n),\quad y=(\eta_1,\cdots,\eta_n),\quad z=(\zeta_1,\cdots,\zeta_n),$$On $X$ we define a metric $d$:$$d(x,z)=\max_j|\xi_j-\zeta_j|$$define $T:X\to X$ by$$y=Tx=Cx+b$$In terms of components$$\eta_j=\sum_{k=1}^nc_{jk}\xi_k+b_j$$let $\omega=Tz$, we know that$$\begin{aligned}d(y,w)=d(Tx,Tz)&=\max_{j}|\eta_{j}-\omega_{j}|\\&=\max_{j}\left|\sum_{k=1}^{n}c_{jk}(\xi_{k}-\zeta_{k})\right|\\&\leqq\max_{i}|\xi_{i}-\zeta_{i}|\max_{j}\sum_{k=1}^{n}|c_{jk}|\\&=d(x,z)\max_{j}\sum_{k=1}^{n}|c_{jk}|.\end{aligned}$$which means $d(y,\omega)\leq\alpha d(x,z)$, where$$\alpha=\max_{j}\sum_{k=1}^{n}|c_{jk}|$$Therefore, we got the theorem for linear equation system:

**Theorem (Linear equations):** If a system$$x=Cx+b$$of $n$ linear equations in $n$ unknowns $\xi_1,\cdots,\xi_n$ (the components of x) satisfies$$\sum_{k=1}^n|c_{jk}|<1\quad(j=1,\cdots,n),$$it has precisely one solution $x$. This solution can be obtained as the limit $of$ the iterative sequence $(x^{(0)},x^{(1)},x^{(2)},\cdots),where$ x$^{(0)}$ is arbitrary and$$x^{(m+1)}=Cx^{(m)}+b\quad m=0,1,\cdots.$$Error bounds are$$d(x^{(m)},x)\leq\frac\alpha{1-\alpha}d(x^{(m-1)},x^{(m)})\leq\frac{\alpha^m}{1-\alpha}d(x^{(0)},x^{(1)}).$$
### Differential Equation
Banach fixed point theorem gives the **Picard's Existence and Uniqueness Theorem**:

For the initial value problem$$x'=f(x,t),\quad x(t_{0})=x_{0}$$let $f$ is continuous on the rectangular region$$R=\{(t,x)\ \big|\ |t-t_{0}|\leq a,|x-x_{0}|\leq b\}$$which means for all $(t,x)\in R,\ |f(x,t)|\leq c$. Suppose that $f$ satisfies a Lipschitz condition on $R$ with respect to its second argument, that is, there is a constant $k$ (Lipschitz constant) such that for $(t,x),(t,v)\in R$,$$|f(t,x)-f(t,v)|\leqq k|x-v|$$then the IVP has a unique solution. This solution exists on an interval $[t_{0}-b,t_{0}+b]$, where$$b<\min\left\{a,\frac{b}{c},\frac{1}{k}\right\}$$
**Proof:** define the **Picard operator** $T$ based on the initial value problem. To do this, we rewrite the differential equation in integral form:$$x(t)=x_0+\int_{t_0}^tf(x(s),s)\mathrm{d}s$$Thus, if we denote the solution at time $t$ by $y(t)$, we can rewrite it as an **operator equation**:$$x(t)=Tx(t)$$which means$$(Tx)(t)=x_0+\int_{t_0}^tf(x(s),s)ds$$It's obvious that we need to find the fixed point of the operator $T$. Firstly, according to the Lipschitz condition,$$\begin{aligned}|Tx(t)-Tv(t)|&=\left|\int_{t_0}^t\left[f(s,x(s))-f(s,v(s))\right]ds\right|\\&\leqq|t-t_0|\max_{s\in J}k\left|x(s)-v(s)\right|\\&\leqq (kb) d(x,v).\end{aligned}$$Therefore $T$ is a contraction. The solution can be obtained by the Picard iteration$$x_{n+1}(t)=x_{0}+\int_{t_{0}}^{t}f(x_{n}(s),s)\mathrm{d}s$$
# Approximation Theory
## Approximation in Normed Space
Let $X$ be a normed space, and $Y$ be the invariant subspace. Use $y\in Y$ to approximate any $x\in X$. The distance between $x$ and $Y$ is defined by$$\delta=\delta(x,Y)=\inf_{y\in Y}\|x-y\|$$If exists a $y_{0}\in Y$ satisfies$$\|x-y_{0}\|=\delta$$then $y_{0}$ is the best approximation to $x$ out of $Y$. We know that if $Y$ is a finite dimensional subspace of the normed space $X$, then the best approximation exists for each $x\in X$. The uniqueness is guaranteed by convexity.

For a subset $M$ of a vector space, if the set$$W=\{v=\alpha y+(1-\alpha)z\mid 0\leq\alpha\leq 1\}$$where $y,z\in M$, is the subset of $M$, then $M$ is said to be a convex set. For a normed space, the best approximation set of given points in a subspace is convex set.

A **strictly convex norm** is a norm such that$$\|x+y\|<2\quad \text{for all}\quad\|x\|=\|y\|=1$$For strictly convex normed spaces (space with a strictly convex norm), the best approximation is unique. We know that the Hilbert space is strictly convex.
## Uniform Approximation
The selection of norms determines the kind of approximation. The norm$$\|x\|=\max_{t\in J}|x(t)|,\quad \text{where } J=[a,b]$$is applied for **the uniform approximation** (also known as **Chebyshev approximation**). Extreme point of $x\in C[a,b]$ is the point $t_{0}\in[a,b]$ such that$$|x(t_{0})|=\|x\|$$At $t_{0}$, $|x(t)|$ has the max. A finite dimensional subspace $Y$ of the real space $C[a,b]$ is said to satisfy the **Haar condition** if every $y\in Y, ~y\neq 0$, has at most $n-1$ zeros in $[ a , b]$ , where $n= \dim Y.$ The best approximation is unique if and only if the Haar condition is satisfied.
## Approximation in Hilbert Space
For any $x$ in a Hilbert space $H$ and closed subspace $Y$, the best approximation of $x$ in $Y$ is unique. We can express $H$ by direct sum:$$H=Y+Z,\quad\text{where }Z=Y^{\perp}$$Therefore $x\in H$, $x=y+z$, also $z=x-y$ and $\langle x-y,y\rangle=0$. If $Y$ is a finite dimensional subspace, let $\dim y=n$, then we have the basis $\{y_{1},y_{2},\dots,y_{n}\}$. According to the orthogonality, we can extract a linear equation system:$$\langle y_j,x-y\rangle=\langle y_j,x-\sum\alpha_ky_k\rangle=0$$that is,$$\langle y_{j},x\rangle-\sum_{i=1}^n\alpha_{i}\langle y_{j},y_{i}\rangle=0$$The coefficient determinant is given by$$G(y_1,\cdots,y_n)=\begin{vmatrix}\langle y_1,y_1\rangle&&\langle y_1,y_2\rangle&&\cdots&&\langle y_1,y_n\rangle\\\\\langle y_2,y_1\rangle&&\langle y_2,y_2\rangle&&\cdots&&\langle y_2,y_n\rangle\\\vdots&&\vdots&&\ddots&&\vdots\\\langle y_n,y_1\rangle&&\langle y_n,y_2\rangle&&\cdots&&\langle y_n,y_n\rangle\end{vmatrix}$$There are two interesting properties of **Gram determinant**:
- A set of elements in Hilbert space is linearly independent if and only if $G(y_{1},\dots,y_{n})\neq 0$.
- The distance between $x$ and its best approximation $y$ is given by$$\|z\|^2=\|x-y\|^2= \frac{G(x,y_{1},\dots,y_{n})}{G(y_{1},\dots,y_{n})}$$
# Spectral Theory of Linear Operators
## Spectral Theory of Linear Operators in Normed Spaces
### Basic Concepts
The resolvent of an operator $T:\mathcal{D}(T)\to X$ on normed space $X$ is defined as$$R_{\lambda}=(T-\lambda I)^{-1}$$**Regular value** $\lambda$ of $T$ is complex number such that:
1. $R_{\lambda}(T)$ exists. (This means characteristic polynomial has only trivial solution)
2. $R_{\lambda}(T)$ is dense in $X$. (This means $T-\lambda I$ is surjective, range of it is the entire space)
3. $R_{\lambda}(T)$ is bounded.
All $\lambda$ is the **resolvent set** $\rho(T)$ of $T$. $\sigma(T)=\mathbb{C}-\rho(T)$ is the **spectrum** of $T$. Furthermore, the spectrum can be divided into the following three sets:
- **Point spectrum** $\sigma_{p}(T)$: It consists of all $\lambda\in\mathbb{C}$ for which $T-\lambda I$ is not injective. In other words, $R_{\lambda}$ does not exist. $\lambda\in \sigma_{p}(T)$ is the eigenvalue of $T$.
- **Continuous spectrum** $\sigma_{c}(T)$:  It consists of all $\lambda\in\mathbb{C}$ for which $T-\lambda I$ is injective, $R_{\lambda}(T)$ is dense but unbounded. (Satisfies condition 1 and 3, not 2)
- **Residual spectrum** $\sigma_{r}(T)$: It consists of all $\lambda\in\mathbb{C}$ for which $T-\lambda I$ is injective, but the range of $T - \lambda I$ is not dense and has no bounded inverse. (Satisfies condition 1, not 3)
$$\begin{array}{|c|c|c|c|c|} \hline {\text{Satisfied}} & \text{Not satisfied} & \lambda \text{ belongs to: } \\ \hline \mathbf{R}_{1},\mathbf{R}_{2},\mathbf{R}_{3} & & \rho(T)\\ \hline & \mathbf{R}_{1}\quad\quad  & \sigma_{p}(T)\\ \mathbf{R}_{1}\ \ \quad\ \mathbf{R}_{3} &\quad\mathbf{R}_{2}\quad & \sigma_{c}(T)\\ \mathbf{R}_{1}\ \ \quad\quad\ \ &\quad\quad\mathbf{R}_{3} & \sigma_{r}(T)\\ \hline \end{array}$$We first note that the four sets in the table are disjoint and their union is the whole complex plane:$$\mathrm{C}=\rho(T)\cup\sigma(T)=\rho(T)\cup\sigma_{p}(T)\cup\sigma_{c}(T)\cup\sigma_{r}(T)$$
## Bounded Linear Operators
For any Bounded Linear Operator $T\in B(X,X)$, where $X$ is the Banach space. If $\|T\|<1$, then the bounded linear operator $(I-T)^{-1}$ exists and$$(I-T)^{-1}=\sum_{j=0}^\infty T^j=I+T+T^2+\cdots$$we know that $\rho(T)$ of $T$ is open and spectrum of $T$ is closed. For each $\lambda_{0}\in \rho(T)$, we have the following representation$$R_{\lambda}=\sum_{j=0}^{\infty}(\lambda-\lambda_{0})^{j}R_{\lambda_{0}}^{j+1}$$This series is absolutely convergent for every $\lambda$ such that$$|\lambda-\lambda_{0}|<\frac{1}{\|R_{\lambda_{0}}\|}$$The spectral radius $r(T)$ of a bounded linear operator $T:X\to X$ is the largest magnitude
of all elements in the spectrum:$$r(T)=\sup\{|\lambda|:\lambda\in\sigma(T)\}.$$Let $X$ be a complex Banach space, $T\in B(X,X)$ and $\lambda,\mu\in \rho(T)$, we have:$$R_{\lambda}-R_{\mu}=(\lambda-\mu)R_{\lambda}R_{\mu}$$
**Spectral Mapping Theorem for Polynomials:** Consider the polynomial$$p(\lambda)=\alpha_n\lambda^n+\alpha_{n-1}\lambda^{n-1}+\cdots+\alpha_0$$then$$\sigma(p(T))=p(\sigma(T))$$that is, the spectrum of the operator:$$p(T)=\alpha_nT^n+\alpha_{n-1}T^{n-1}+\cdots+\alpha_0I$$consists precisely of all those values which the polynomial $p$ assumes on the spectrum of $T$.
# Spectral Theorem of Compact Operators
## Compact Linear Operators
### Definition
Let $X$ and $Y$ be normed spaces and let $B$ be a bounded subset of $X$, linear operator $T:X\to Y$ is said to be compact if $T(B)$ is precompact (closure $\overline{T(B)}$ is compact).
### Properties
1. Compact operators must be continuous.
2. For two continuous linear operators $A$ and $B$, if any of them is compact, then $AB$ is compact.
3. Finite-rank operators is compact
The linear operator sequence $T_{n}$ is said to be compact linear operator sequence if $T_{n}$ is compact for any $n$. 
## Spectral Theory
A compact linear operator $T:X\to X$ on a normed space $X$ has the following properties:
- Eigenvalues of $T$ if finite.
- Any spectral value $\lambda\neq 0$ is an eigenvalue.
- Dimension of eigenspace for any $\lambda\neq 0$ is finite.
## Operator Functions of Compact Operators
For a compact linear operator $T:X\to X$ on normed space $X$, and its adjoint operator $T^*$, the function$$(T-\lambda I)x=y$$with associated homogeneous function$$(T-\lambda I)x=0$$is operator function. Similarly, we have the operator function about the adjoint operator and associated homogeneous form. We Consider them at the same time:$$\begin{align}
Tx-\lambda x=y \quad(1)\\
Tx-\lambda x=0 \quad(2)\\
T^*f-\lambda f=g \quad(3)\\
T^*f-\lambda f=0 \quad(4)
\end{align}$$For any $\lambda\neq 0$, we have the following properties: $(1)$ is solvable if and only if for all $f$ satisfies $(4)$, $y$ satisfies $f(y)=0$. Therefore, if $(4)$ has only trivial solution $f=0$, then$(1)$ is solvable for any $y$. Similarly, $(3)$ is solvable if and only if for all solution $x$ to $(2)$, $g$ satisfies that $g(x)=0$. Therefore, if $(2)$ has only trivial solution $x=0$, then$(3)$ is solvable for any $g$.

## Fredholm Alternative Theorem
For any operator function, the following cases are possible and only one of them will  hold:
1. $$Ax=y,\quad A^*f=g$$for any $y,g$ has a unique solution $x,f$. Associated homogeneous functions$$Ax=0,\quad A^*y=0$$have only trivial solutions $x=0,f=0$.
2. $$Ax=0,\quad A^*y=0$$have linearly independent solutions of the same number:$$x_{1},x_{2},\dots,x_{n}\quad \text{and}\quad f_{1},f_{2},\dots,f_{n}\quad \text{where }n\geq 1.$$Associated inhomogeneous functions$$Ax=y,\quad A^*f=g$$are solvable if and only if $y,g$ satisfies that$$f_{k}(y)=0,\quad g(x_k)=0, \qquad\text{where }k=1,\dots,n$$For any $\lambda\neq 0$, $T_{\lambda}=T-\lambda I$ satisfies Fredholm alternative.
# Bounded Self-Adjoint Linear Operators
## Spectral Theorem
For self-adjoint Operators such that $T^*=T$, all eigenvalues (if exist) are real number (in fact, the whole spectrum is real), and corresponding eigenvectors are orthogonal. The spectrum of $T$ on a Hilbert space lies on the closed interval on real axis $[m,M]$ such that$$m=\inf_{\|x\|=1}\langle Tx,x\rangle,\quad M=\sup_{\|x\|=1}\langle Tx,x\rangle$$the norm of $T$ is given by$$\|T\|=\max\{|m|,|M|\}=\sup_{\|x\|=1}|\langle Tx,x\rangle|.$$Bounded self-Adjoint operator $T$ has no residual spectrum$$\sigma_{r}(T)=\emptyset.$$
## Spectral family and Representation
### Spectral Family
Consider a matrix $T$ with $n$ eigenvalues $\lambda_{j}$ corresponding to $n$ eigenvectors $x_{j}$, then $x_{j}$ is a standard orthogonal basis of the Hilbert space $H$. For any $x\in H$, we can represent it as $x=\sum_{j=1}^n\gamma_{j}x_{j}$ by projection. Therefore we know$$Tx=\sum_{j=1}^n\lambda_{j}\gamma_{j}x_{j}$$thus the projection operator can be defined by $P_{j}:H\to H,\ x\to\gamma_{j} x_{j}$. Then the representation is$$x=\sum_{j=1}^nP_{j}x,\quad \text{and}\quad I=\sum_{j=1}^nP_{j}$$For the bounded linear self-adjoint operator $T$, we consider the sum of projection operators$$E_{\lambda}=\sum_{\lambda_{j}\leq \lambda}P_{j}$$we can see that$$\begin{align}
E_{\lambda}E_{\mu}=E_{\mu}E_{\lambda}=E_{\lambda}&,\quad\text{when }\lambda<\mu \\
E_{\lambda}=0,\quad\text{when }\lambda<\lambda_{1};\qquad &E_{\lambda}=I,\quad \text{when }\lambda\geq\lambda_{n}
\end{align}$$The **spectral family** is the family of $E_{\lambda}$:$$\mathcal{E}=(E_{\lambda})_{\lambda\in R}$$For an self-adjoint operator in n-d Hilbert space $H$, the spectral representation is given by$$T=\sum_{j=1}^n\lambda_{j}\delta E_{\lambda_{j}}$$Thus the dot product $\langle Tx,y\rangle$ can be written in terms of Riemann-Stieltjes integral:$$\langle Tx,y\rangle=\int_{-\infty}^{\infty}\lambda \mathrm{d}\omega(\lambda)$$where $\omega(\lambda)=\langle E_{\lambda}x,y\rangle$.