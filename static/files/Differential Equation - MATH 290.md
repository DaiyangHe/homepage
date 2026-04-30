**Author**: Dylan He
# Introduction to D.E.
## Classification of Differential Equation
* Classification by types
	* Ordinary Differential Equation (ODE)
	* Partial Differential Equation (PDE)
* Classification by orders
General form:
$$
\varphi(x,y,y')=0
$$
Normal form:
$$
y'=f(x, y)
$$
* Classification by linearity
For nonlinear ODE, there are several typical nonlinear term:  $e^y$ ,  $\sin{y}$ ,  $y^2$ , and  $yy'$ .
**Features of Linear Equation**:
* All the  $y$  and every order derivatives of  $y$  must be first-order.
* All coefficients of  they  $y$  and every order derivatives of  $y$  must contain $x$ and constants only.
* No function of  $y$  and every order derivatives of  $y$  is allowed.
# Solving the first-order D.E.
## Separable Equation
D.E.s with shape like:
$$
\frac{\mathrm{d}y}{\mathrm{d}x}=f(x)g(y)
$$
are called Separable Equation.
## Normalizing Method
- Example:
Using the air resistance in falling mass problem as an example.
$$
\frac{\mathrm{d}v}{\mathrm{d}t}=g-\frac{k}{m}v^2,\quad\text{with}\ v(0)=0
$$
If we apply some scaling variables to sub some original variables, in order to get rid of the complex coefficients in the equation, we simplify this equation.
$$
v=\alpha \omega,\quad t=\beta s
$$
We can transfer the equation in to the D.E. with respect to  $\omega$  and  $s$ .
$$
\frac{\mathrm{d}\omega}{\mathrm{d}s}=\frac{\beta}{\alpha}g-\frac{\alpha \beta k}{m}\omega^2
$$
If we intentionally let:
$$
\beta=\sqrt{ \frac{m}{kg} },\quad\alpha=\sqrt{ \frac{mg}{k} }
$$
we will find those coefficients become one.
$$
\frac{\mathrm{d}\omega}{\mathrm{d}s}=1-\omega^2
$$
## Homogeneous Equation
There are two types of linear equations: homogeneous equation and inhomogeneous equation. Consider the normal form of the first order inhomogeneous linear equation.
$$
y'=p(x)y+q(x)
$$
When  $q(x)=0$ , the equation become homogeneous. we can easily solve the homogeneous equation by separate variables.
$$
y=Ae^{\int p(x)\mathrm{d}x}
$$
## Inhomogeneous Equation
There are two methods to solve inhomogeneous equations based on the general solution  $y_{h}$  to the associated homogeneous equation, which are **Integration Factor Method** and **Variation of Parameters**.
### Integration Factor Method
For the D.E. like 
$$
y'=p(x)y+q(x)
$$
we can multiply **Integration Factor** on both sides.
$$
u(x)=e^{-\int p(x)\mathrm{d}x}
$$
For integration factor, its derivative equals to $u'(x)=-p(x)u(x)$ . Then the equation can be transferred into:
$$
u(x)y'(x)+u'(x)y(x)=u(x)q(x)
$$
Then we can solve the equation:
$$
y(x)=\frac{\int u(x)q(x)\mathrm{d}x}{u(x)}
$$
### Variation of Parameters
We all know that solution to homogeneous linear equations can be written as:
$$
y=Ae^{\int p(x)\mathrm{d}x}
$$
For inhomogeneous equations, we can just change the constant $A$ to function $v$ . Then we assume the particular solution to the associated homogeneous equation is  $y_h=e^{\int p(x)\mathrm{d}x}$ , Then the final solution can be written as $y=vy_{h}$ . Substitute it into original equation, we have that 
$$
v'y_{h}+vy_{h}'=vp(x)y_{h}+q(x)=vy_{h}'+q(x)
$$
Therefore, $v$ is given by:
$$
v'=\frac{q(x)}{y_{h}}
$$
### Bernoulli Differential Equation
Bernoulli differential differential equation is given by:
$$
\frac{\mathrm{d}y}{\mathrm{d}x}=p(x)y+q(x)y^{\alpha}
$$
where $\alpha>1$ .
To solve these equations, we can let $u=y^{1-\alpha}$ such that $\frac{\mathrm{d }u}{\mathrm{d}x}=(1-\alpha)y^{-\alpha}\frac{\mathrm{d}y}{\mathrm{d}x}$ .
$$
\frac{\mathrm{d }u}{\mathrm{d}x}=(1-\alpha)p(x)u+(1-\alpha)q(x)
$$
which is a homogeneous equation. We can solve it by the variation of parameters and the integration factors.
## Exact Equation
We can rewrite a first-order equation $\frac{\mathrm{d}y}{\mathrm{d}x}=f(x,y)$ into differential forms.
$$
f(x,y)\mathrm{d}x-\mathrm{d}y=0
$$
or symmetrically, 
$$
M(x,y)\mathrm{d}x+N(x,y)\mathrm{d}y=0
$$
Assume $M(x,y)$ and $N(x,y)$ to be differentiable. If the left side is a total difference of a function $y$ , then the equation
$$
M(x,y)\mathrm{d}x+N(x,y)\mathrm{d}y=\frac{\partial u}{\partial x}\mathrm{d}x+\frac{\partial u}{\partial y}\mathrm{d}y=0
$$
is called **exact equation**. The sufficient and necessary condition for an equation $M(x,y)\mathrm{d}x+N(x,y)\mathrm{d}y=0$ to be exact equation is
$$
\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}
$$
Solving this equation, we can find that the general solution to it is:
$$
u(x,y)=C
$$
which is also called **integral curves**. What's more, an exact equation gives rise to a conservation vector field, and the implicit solution of the equation is the potential field such that:
$$
\nabla u=M(x,y)\hat{i}+N(x,y)\hat{j}
$$
To solve the equation, we integral on the both sides:
$$
\int M(x,y)\mathrm{d}x+\varphi(y)=u(x,y)
$$
Remark that $x$ and $y$ is symmetrical. Then we take derivatives on both sides, 
$$
\frac{ \partial u}{ \partial y}=\frac{ \partial }{ \partial y}\left(\int M(x,y)\mathrm{d}x+\varphi(y)\right)=\int \frac{ \partial M}{ \partial y}\mathrm{d}x+\varphi'(y)=N(x,y)
$$
Then we can solve the $\varphi(y)$ .
$$
\varphi(y)=\int\left[ N(x,y)- \frac{ \partial}{ \partial y}\int M(x,y) \mathrm{d}x \right]\mathrm{d}y
$$
So the final solution is 
$$
u(x,y)=\int M(x,y)\mathrm{d}x+\int\left[ N(x,y)- \frac{ \partial}{ \partial y}\int M(x,y) \mathrm{d}x \right]\mathrm{d}y
$$

- Example: Solve $\frac{\mathrm{d}y}{\mathrm{d}x}=xy^2-\cos x$ 

### Integration Method
When a equation is not exact, it's essential to transfer it into exact forms with assistance of integration factor. In general cases, the necessary and sufficient condition for the function $u(x,y)$ to be the integration factor is that:
$$
\frac{ \partial (uM)}{ \partial y}=\frac{ \partial (uN)}{ \partial x}
$$
After a series of induction (see 王高雄《常微分方程》p.37), we have the integration factor:
$$
u(x,y)=e^{\int\psi(x)\mathrm{d}x}
$$
$$\psi(x)=\frac{\frac{ \partial M}{ \partial y}-\frac{ \partial N}{ \partial x}}{N}$$
#### Integration Factors Method for Separable Equations
For equation
$$
\frac{\mathrm{d}y}{\mathrm{d}x} =\frac{p(x)}{q(y)}
$$
We can rewrite it in such form:
$$
\frac{p(x)}{q(x)}\mathrm{d}x+\mathrm{d}y=0
$$
So an integration factor is just $u(x,y)=q(y)$ . 
#### Integration Method for Linear equation
The integration factor for linear equation like
$$
y'=p(x)+q(x)
$$
is given by:
$$
u(x)=e^{ -\int p(x)\mathrm{d}x }
$$
It's easy to prove that equation:
$$
e^{ -\int p(x)\mathrm{d}x }(p(x)y+q(x))\mathrm{d}x-e^{ -\int p(x)\mathrm{d}x }\mathrm{d}y=0
$$
is exact.
### Autonomous Equation
In a differential equation, if its independent variables are not explicitly included in the equation, the equation is said to be autonomous.$$\frac{\mathrm{d}y}{\mathrm{d}t} =f(y)$$
Autonomous equations have equilibrium points where $\frac{\mathrm{d }y}{\mathrm{d}t}=f(y_{0})=0$ . Obviously, the line $y=y_0$ is a solution.
## Uniqueness and Existence of Solution
### Picard-Lindelöf Theorem
The **Picard-Lindelöf Theorem** (or Existence and Uniqueness Theorem) states:
**Theorem**: Given the first-order differential equation:
$$\frac{\mathrm{d}y}{\mathrm{d}x}=f(x,y),\quad y(x_0)=y_0$$
If $f(x,y)$ and $\frac{\partial f}{\partial y}$ are continuous in a neighborhood of $(x_0, y_0)$ , then:
1. There exists a **unique solution** $y(x)$ passing through $(x_0, y_0)$ 
2. The solution is valid at least on some interval around $x_0$ 
Key Insights here are continuity of $f$ ensures the existence of a solution, and the Lipschitz condition (or continuity of $\frac{\partial f}{\partial y}$ ​) ensures uniqueness.
### Lipschitz Condition
The **Lipschitz condition** ensures the uniqueness of solutions. A function $f(x, y)$ satisfies the Lipschitz condition in $y$ on a domain $D$ if there exists a constant $L > 0$ such that:
$$
|f(x,y_1)-f(x,y_2)|\leq L|y_1-y_2|,\quad\forall(x,y_1),(x,y_2)\in D$$
The Lipschitz constant $L$ measures the rate at which $f$ changes with respect to $y$ . If $f(x, y)$ satisfies the Lipschitz condition, the Picard-Lindelöf Theorem guarantees the existence and uniqueness of solutions for the IVP. 

If $\frac{ \partial f}{ \partial y}$ is continuous in a domain, then the Lipschitz condition is satisfied automatically.
### Extension of Solution
The **extension of solution** refers to the continuation of a solution beyond its initial interval of existence. The solution y(x)y(x)y(x) can often be extended as long as:
- $f(x, y)$ remains continuous, and
- $y(x)$ does not encounter singularities 
A solution that cannot be extended further is called a **maximal solution**. This happens when the solution either diverges or the equation restricts the domain.
### Envelope and Singular Solution
The envelope of a family of solutions refers to a curve that is tangential to all solution curves in the family. Mathematically, the envelope can be found by treating the parameter (denoted by $c$ ) of the solution family as a variable and eliminating it using partial derivatives. The curves gained are called C-test curves. 
A singular solution is a solution that cannot be derived from the general solution by simply substituting a constant parameter. Singular solutions often correspond to the envelope of the general solution family, but in some cases, they exist independently.
# Second-Order Differential Equations

A **second-order differential equation** is a differential equation that involves the second derivative of a function. It has the general form:
$$\frac{\mathrm{d}^2y}{\mathrm{d}x^2} + p(x)\frac{\mathrm{d}y}{\mathrm{d}x} + q(x)y = g(x)$$
## Types of Second-Order Differential Equations

1. **Homogeneous Equation**:
   When $g(x) = 0$ , the equation is called a **homogeneous second-order differential equation**:
 $$
   \frac{\mathrm{d}^2y}{\mathrm{d}x^2} + p(x)\frac{\mathrm{d}y}{\mathrm{d}x} + q(x)y = 0
 $$
2. **Non-Homogeneous Equation**:
   When $g(x) \neq 0$ , the equation is **non-homogeneous**:
 $$
   \frac{\mathrm{d}^2y}{\mathrm{d}x^2} + p(x)\frac{\mathrm{d}y}{\mathrm{d}x} + q(x)y = g(x)
 $$
## Solution to Second-Order Differential Equations
### Structure, Existence, and Uniqueness Theorem
#### Theorem 1: Principle of Superposition for Homogeneous Equations
For a linear homogeneous differential equation, if $y_1$ and $y_2$ are solutions, then so is $c_{1}y_{1}+c_{2}y_{2}$ .
For n-order linear differential equation, the structure of solutions is:$$y=y_{p}+\sum_{i=1}^{n}C_{i}y_{hi}$$
#### Theorem 2: Existence and Uniqueness Theorem for Linear 2nd Order Equations
Let $p(t)$ , $q(t)$ , and $g(t)$ be continuous on $[a,b]$ , then the differential equation:
$$y''+p(t)y'+q(t)y=g(t),\quad y(t_0)=y_0,\quad y'(t_0)=y_0'$$
has a unique solution defined for all $t$ in $[a,b]$ .
#### Wronskian
The **Wronskian** is a determinant used to determine whether a set of solutions of a differential equation is linearly independent. For a system of solutions $y_1(x),y_2(x),\ldots,y_n(x)$ of an $n$ -th order differential equation, the Wronskian is defined as:
$$W(y_1,y_2,\ldots,y_n)(x)=\begin{vmatrix}y_1(x)&y_2(x)&\cdots&y_n(x)\\y_1^{\prime}(x)&y_2^{\prime}(x)&\cdots&y_n^{\prime}(x)\\\vdots&\vdots&\ddots&\vdots\\y_1^{(n-1)}(x)&y_2^{(n-1)}(x)&\cdots&y_n^{(n-1)}(x)\end{vmatrix}$$
- If $W(y_1, y_2, \dots, y_n)(x) \neq 0$ for some $x$ , the functions $y_1, y_2, \dots, y_n$ ​ are linearly independent.
- If $W(y_1, y_2, \dots, y_n)(x) = 0$ everywhere, the solutions may be linearly dependent.
If the solutions $y_1, y_2, \dots, y_n$ ​ are linearly independent, the they are called a **fundamental set of solutions**.

### Homogeneous Case
For a homogeneous equation:
$$
\frac{\mathrm{d}^2y}{\mathrm{d}x^2} + p(x)\frac{\mathrm{d}y}{\mathrm{d}x} + q(x)y = 0
$$
- The solution involves finding the roots of the **characteristic equation** if  $p(x)$  and  $q(x)$  are constants.
#### Characteristic Equation
$$
r^2 + pr + q = 0
$$
- **Distinct Real Roots** $(r_1, r_2 )$ : Solution is$$
  y(x) = C_1e^{r_1x} + C_2e^{r_2x}
$$
-  **Repeated Roots** $( r_1 = r_2 = r )$ : Solution is
$$
  y(x) = (C_1 + C_2x)e^{rx}
$$
- **Complex Roots** $(r = \alpha \pm \beta i)$ : Solution is$$
  y(x) = e^{\alpha x}(C_1\cos(\beta x) + C_2\sin(\beta x))
$$
### Non-Homogeneous Case
For a non-homogeneous equation:
$$
\frac{\mathrm{d}^2y}{\mathrm{d}x^2} + p(x)\frac{\mathrm{d}y}{\mathrm{d}x} + q(x)y = g(x)
$$
- The **general solution** is:
$$
  y(x) = y_h(x) + y_p(x)
$$
  where:
  - $y_h(x)$ : Solution to the corresponding homogeneous equation. ( $C_{1}y_{1}+C_{2}y_{2}$ )
  - $y_p(x)$ : Particular solution to the non-homogeneous equation.
#### Methods for Finding $y_p(x)$ :

1. **Method of Undetermined Coefficients**: Assume a form for $y_p(x)$ based on $g(x)$ and solve for coefficients.
2. **Variation of Parameters**: Use $y_h(x)$ to construct $y_p(x)$ using integrals.
3. **Complex method**: Exploits the exponential representation of complex numbers.
##### Method of Undetermined Coefficients
- If $f(t)$ is a polynomial$$ay''+by'+cy=P_n(t)=A_nt^n+A_{n-1}t^{n-1}+\ldots+A_0$$
Let $y_p=B_nt^n+B_{n-1}t^{n-1}+\ldots+B_0$ , back substitute it into original equation to determine coefficients. 
- If $f(t)$ is a exponential function$$ay''+by'+cy=Ae^{Bt}$$
We firstly calculate the fundamental set of solutions to the homogeneous equation $\{y_{1}, y_{2}\}$ . If $e^{Bt}\notin \{y_{1},y_{2}\}$ , we let $y_{p}=Me^{Bt}$ . Then solve $M$ . If $e^{Bt}\in\{y_{1},y_{2}\}$ , we just try $y_{p}=Mt^ne^{Bt}$ , from $n=1$ iteratively until M can be solved.
- If $f(t)$ is a trigonometric function$$ay''+by'+cy=P_n(t)=A_1\sin(\omega t)+A_2\cos(\omega t)$$
Just let $y_{p}=B_{1}\sin(\omega t)+B_{2}\cos(\omega t)$ .
##### Variation of parameters
Assume the particular solution $y_p(x)$ is a linear combination of the homogeneous solutions, but with variable coefficients:$$y_p(x)=v_1(x)y_1(x)+v_2(x)y_2(x)$$
We got$$
\begin{cases}v_1'y_1+v_2'y_2=0\\v_1'y_1'+v_2'y_2'=\frac{f(t)}{a}\end{cases}
$$
note that the coefficient matrix contains Wronskian. So we have
$$v_2=\frac{1}{a}\int\frac{y_1f(t)}{W(y_1,y_2)}\mathrm{d}t$$
$$v_1=-\frac{1}{a}\int\frac{y_2f(t)}{W(y_1,y_2)}\mathrm{d}t$$
Then we have the particular solution:
$$y_p=\Big(-\frac{1}{a}\int\frac{y_2f(t)}{W(y_1,y_2)}\mathrm{d}t\Big)y_1+\Big(\frac{1}{a}\int\frac{y_1f(t)}{W(y_1,y_2)}\mathrm{d}t\Big)y_2$$
##### Complex Method
This method is useful when solving linear homogeneous or non-homogeneous equations with oscillatory terms. For D.E. like:$$ay^{\prime\prime}+by^{\prime}+cy=A\sin(\omega t)$$
It's the imaginary part of$$ay^{\prime\prime}+by^{\prime}+cy=Ae^{i\omega t}$$
Just let $y_p=Me^{i\omega t}$ to solve $M=\alpha\pm\beta i$ , and according to Euler's Equation $e^{i\omega t}=\cos(\omega t)+i\sin(\omega t)$ we can know that the solution is$$(\alpha+\beta i)[\cos(\omega t)+i\sin(\omega t)]=[\alpha\cos(\omega t)-\beta\sin(\omega t)]+i[\alpha\sin(\omega t)+\beta\cos(\omega t)]$$
The imaginary part $\alpha\sin(\omega t)+\beta\cos(\omega t)$ is the solution to the original equation.
# Higher-order differential equations
## Differential Equations in n-D linear space
### Vectorized Form
Assume $n$ th order D.E.:$$\frac{\mathrm{d}^ny}{\mathrm{d}x^n}=F\left( x,y,\frac{\mathrm{d}y}{\mathrm{d}x},\dots,\frac{\mathrm{d}^{n-1}y}{\mathrm{d}x^{n-1}}\right)$$Let $y_{1}=y,y_{2}=\frac{\mathrm{d}y}{\mathrm{d}x},\dots,y_{n}=\frac{\mathrm{d}^{n-1}y}{\mathrm{d}x^{n-1}}$ , then we can write the equation into:$$\begin{cases}
\frac{\mathrm{d}y_{1}}{\mathrm{d}x}=y_{2} \\
\dots\dots\dots \\
\frac{\mathrm{d}y_{n-1}}{\mathrm{d}x}=y_{n} \\
\frac{\mathrm{d}y_{n}}{\mathrm{d}x}=F(x,y_{1},y_{2},\dots,y_{n})
\end{cases}$$In other words, if $y=\varphi(x)$ is the solution to the n-order D.E., then the system of equation inducted by it$$\begin{cases}
y_{1}=\varphi(x) \\
y_{2}=\varphi'(x) \\
\dots\dots\dots \\
y_{n}=\varphi^{n-1}(x)
\end{cases}$$must be the solution to the equation system above. Note that the number of equations equal to the number of unknown equations. Therefore, we can transform the equation system into standard form below:$$\begin{cases}
\frac{\mathrm{d}y_{1}}{\mathrm{d}x}=f_{1}(x,y_{1},y_{2},\dots,y_{n}) \\
\frac{\mathrm{d}y_{2}}{\mathrm{d}x}=f_{2}(x,y_{1},y_{2},\dots,y_{n}) \\
\dots\dots\dots\dots\dots \\
\frac{\mathrm{d}y_{n}}{\mathrm{d}x}=f_{n}(x,y_{1},y_{2},\dots,y_{n})
\end{cases}$$We can express them in terms of vectors.$$\mathbf{f}(x,\mathbf{y})=(f_{1}(x,\mathbf{y}),f_{2}(x,\mathbf{y}),\dots,f_{n}(x,\mathbf{y})),\qquad\mathbf{y}=(y_{1},y_{2},\dots,y_{n})$$then we can write the equation system into vectorized form$$\frac{\mathrm{d}\mathbf{y}}{\mathrm{d}x}=\mathbf{f}(x,\mathbf{y})$$Which means we transformed a n-order D.E. into first-order D.E. in an n-D linear space $V^n$ . 
### Normed Linear Space
In order to study the uniqueness and existence of solution, we need to introduce norms into $V^n$ . Here are three kind of norms:
- $\rvert\rvert y \rvert\rvert=\sqrt{ \sum_{i=1}^{n}y_{i}^2 }$ 
- $\lvert\rvert y \rvert\rvert=\sum_{{i=1}}^n|y_{i}|$ 
- $||y||=\max \{|y_{1}|,|y_{2}|,\dots,|y_{n}|\}$ 
After the introduction of norms, $V^n$ becomes an n-D **normed linear space**, as known as **Banach space**. In Banach space, the Lipschitz condition remains the same form. 
## Structures of linear D.E.
### Properties and Structures of solution
The same as second-order D.E. (Wronskian, Addition,...)
### Reduced-order and power-series solutions
#### Reduce Order
n-order D.E. can be generally written as$$F(x,y,y',y'',\dots,y^{(n)})$$We discuss it in three kinds of equation.
1. Do not contain  $y,y',\dots,y^{(k-1)}$  explicitly, which means$$F(x,y^{(k)},y^{(k+1)},\dots,y^{n})$$Let  $y^{(k)}=u$  ,then we can reduce the order to $y-k$ .$$F(t,u,u',\dots,u^{(n-k)})=0$$Then the solution is$$x=\underbrace{\int dx\int dx\cdots\int}_{n}udx$$
2. without $x$ . Let $u=y'$ can reduce 1 order.

### Series Solution Method for Second-Order Differential Equations

The series solution method is used to find an approximate solution to second-order linear differential equations, especially when the equation cannot be solved by elementary functions. This method involves assuming the solution in the form of a power series.

#### General Form of Second-Order Linear ODE

Consider the second-order linear differential equation:$$
y'' + p(x) y' + q(x) y = r(x)
$$where  $p(x), q(x), r(x)$  are continuous functions of  $x$ .
#### Assumed Form of Solution

Assume the solution $y(x)$  can be written as a power series around  $x = x_0$$$ 
y(x) = \sum_{n=0}^{\infty} a_n (x - x_0)^n
$$where  $a_n$  are the coefficients to be determined.
#### Steps for Finding the Solution
1. **Substitute the series into the ODE**:  
   Write the derivatives of $y(x)$ in terms of the power series:$$\begin{aligned}
y'(x) &= \sum_{n=1}^{\infty} n a_n (x - x_0)^{n-1}\\
   y''(x) &= \sum_{n=2}^{\infty} n(n-1) a_n (x - x_0)^{n-2}
\end{aligned}$$
2. **Substitute into the differential equation**:  
   Substitute these expressions for $y(x)$ , $y'(x)$ , and  $y''(x)$  into the differential equation.

3. **Collect like terms**:  
   Combine terms of the same powers of  $(x - x_0)$ .

4. **Solve for the coefficients**:  
   To satisfy the equation for all $x$ , the coefficients of each power of  $(x - x_0)$  must independently equal zero. This results in a recurrence relation for the coefficients  $a_n$ .

   Typically, the recurrence relation has the form:$$
   a_n = \frac{-1}{n(n-1)} \left( \text{terms involving lower coefficients} \right)
  $$ The recurrence is determined by the specific form of $p(x)$ , $q(x)$ , and $r(x)$ .

5. **Find the general solution**:  
   Using the recurrence relation, you can compute the coefficients $a_n$ and thus the solution to the differential equation in the form of the power series.
#### Example: Solving $y'' - y = 0$ 

1. **Equation**: $$
   y'' - y = 0
  $$
2. **Assume a power series solution**:$$
   y(x) = \sum_{n=0}^{\infty} a_n x^n
  $$
3. **Find derivatives**:$$
   y'(x) = \sum_{n=1}^{\infty} n a_n x^{n-1}, \quad y''(x) = \sum_{n=2}^{\infty} n(n-1) a_n x^{n-2}
  $$
4. **Substitute into the equation**:$$
   y''(x) - y(x) = 0 \quad \Rightarrow \quad \sum_{n=2}^{\infty} n(n-1) a_n x^{n-2} - \sum_{n=0}^{\infty} a_n x^n = 0
  $$
5. **Align powers of $x$** **and solve for coefficients**:
   By setting the coefficients equal to zero for each power of  $x$ , we get the recurrence relation and can solve for  $a_n$ .
# System of Linear Differential Equation
## General Theorem
### Vectorization
Considering the standard form of n-order system differential equation:$$\frac{\mathrm{d}y_{i}}{\mathrm{d}x}=\sum_{j=1}^na_{ij}(x)y_{j}+f_{i}(x)$$or in terms of matrices$$\frac{\mathrm{d}\mathbf{y}}{\mathrm{d}x}=\mathbf{A}(x)\mathbf{y}+\mathbf{f}(x)$$where$$\mathbf{A}(x)=[a_{ij}(x)]_{n\times n},\quad \mathbf{y}=\begin{bmatrix}
y_{1} \\
y_{2} \\
\dots \\
y_{n}
\end{bmatrix},\quad \mathbf{f}(x)=\begin{bmatrix}
f_{1}(x) \\
f_{2}(x) \\
\dots \\
f_{n}(x)
\end{bmatrix}$$Any property and formula of first-order differential equation can be adapted to the system of differential equation.
### Liouville's Formula
Liouville's Formula provides a way to express the **determinant of the fundamental matrix solution** of a system of linear differential equations. In simpler terms, Liouville’s formula describes how the determinant of the matrix of solutions to a linear system evolves over time.
Consider the homogeneous linear system of differential equation:$$\frac{\mathrm{d}\mathbf{y}}{\mathrm{d}x}=\mathbf{A}(x)\mathbf{y}$$The **fundamental matrix** $\varPhi(x)$ is a matrix whose columns consist of linearly independent solutions to this system.$$\varPhi(x)=[y_{ij}(x)]_{n\times n}=\begin{bmatrix}
y_{11}&y_{12}&\dots&y_{1n} \\
y_{21}&y_{22}&\dots&y_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
y_{n1}&y_{n2}&\dots&y_{nn}
\end{bmatrix}$$The general solution of the system can be written as:$$y(x)=\varPhi(x) \mathbf{y}(0)$$where $\mathbf{y}(0)$ is the vector of initial conditions. **Liouville's formula** states that for a system of linear differential equations$$\frac{\mathrm{d }\varPhi}{\mathrm{d}x}=\mathbf{A}(x)\varPhi(x)$$The determinant of fundamental matrix is given by$$\det(\varPhi(t))=\det(\varPhi(0))\exp\left(\int_0^t\mathrm{tr}(\mathbf{A}(x))dt\right)$$
#### Interpretation and Key Points
- **Determinant of Fundamental Matrix**: $\det(\varPhi(t))$ represents the volume change of the solution space as time progresses. If $\det⁡(\varPhi(0))=1$, this quantity remains $e^{tr(A)t}$, which is determined entirely by the trace of the matrix $A$.
- **Trace of the Matrix**: The trace $tr(A)$ gives insight into the **stability** of the system. If $tr(A)>0$, the solutions to the system tend to grow exponentially. If $tr(A)<0$, the solutions tend to decay exponentially.
- **Liouville's Formula and the Volume of Solution Space**: The formula tells us how the volume (or area, in lower dimensions) of the parallelogram formed by the linearly independent solutions evolves over time. In other words, the determinant of the fundamental matrix quantifies the stretching or shrinking of the solution space. If the system has a non-zero determinant, the solutions form a non-degenerate space.
### Inhomogeneous linear system of differential equation
For inhomogeneous linear system of differential equation$$\frac{\mathrm{d}\mathbf{y}}{\mathrm{d}x}=\mathbf{A}(x)\mathbf{y}+\mathbf{f}(x)$$If $\varPhi(x)$ is a fundamental matrix of associated homogeneous system, any solution of this system can be expressed as$$\varphi(x)=\varPhi(x)\mathbf{C}+\varphi^*(x)$$where $C$ is a constant vector related to $\varphi(x)$ and $\varphi^*(x)=\varPhi(x)\mathbf{C}(x)$ (variation of parameter) is the particular solution.
## Constant Coefficient Linear System of Differential Equation
### The Fundamental Matrix
Given a square matrix $A$, the **matrix exponential** $e^{At}$ is defined as the following power series:$$e^{At}=I+At+\frac{(At)^2}{2!}+\frac{(At)^3}{3!}+\ldots=\sum_{i=0}^{\infty}\frac{(At)^i}{i!}$$If $A$ is diagonalizable, i.e., $A=PDP^{-1}$, then$$e^{At}=Pe^{Dt}P^{-1}$$The general solution to a constant coefficient linear system of differential equation is$$\mathbf{y}=e^{Ax}C+\int_{x_{0}}^xe^{A(x-s)}f(s)\ \mathrm{d}s$$
### Undetermined Exponential Method
The **undetermined exponential method** is commonly used for solving **non-homogeneous systems** of linear differential equations. Consider the non-homogeneous system$$\frac{\mathrm{d}\mathbf{y}}{\mathrm{d}x}=\mathbf{A}(x)\mathbf{y}+\mathbf{f}(x)$$guess $y_{p}=\mathbf{c}e^{Ax}$, where $\mathbf{c}$ is undetermined. If $λ_1​,λ_2​,…,λ_n​$ are distinct eigenvalues of $A$, and $v_1,v_2,…,v_n$ are their corresponding eigenvectors, the solution to the system is:$$y(t)=\sum_{i=1}^n c_{i}e^{λ_it}\mathbf{v_{1}}$$
where $c_{1}​,c_{2}​,…,cn$​ are constants determined by the initial conditions.
#### Example

Suppose we have the following system:$$\frac{d}{dt}\mathbf{y}(t)=
\begin{pmatrix}
1 & 0 \\
0 & 2
\end{pmatrix}\mathbf{y}(t)+
\begin{pmatrix}
0 \\
1
\end{pmatrix}$$The solution to the homogeneous system is:$$\mathbf{y}_h(t)=e^{
\begin{pmatrix}
1 & 0 \\
0 & 2
\end{pmatrix}t}\mathbf{y}(0)=
\begin{pmatrix}
e^t & 0 \\
0 & e^{2t}
\end{pmatrix}\mathbf{y}(0)$$Now, assume the particular solution has the form $\mathbf{y}_p(t)=\begin{pmatrix}a \\ b\end{pmatrix}$, where $a$ and $b$ are constants. Substitute into the equation:$$\begin{pmatrix}
1 & & 0 \\
0 & & 2
\end{pmatrix}
\begin{pmatrix}
a \\
b
\end{pmatrix}=
\begin{pmatrix}
0 \\
1
\end{pmatrix}$$so $a=0$ and $b=\frac{1}{2}​$. Thus, the particular solution is $\mathbf{y}_p(t)=\begin{pmatrix}0 \\ \frac{1}{2} \end{pmatrix}$. The general solution is $$\mathbf{y}(t)=
\begin{pmatrix}
e^t & 0 \\
0 & e^{2t}
\end{pmatrix}\mathbf{y}(0)+
\begin{pmatrix}
0 \\
\frac{1}{2}
\end{pmatrix}$$