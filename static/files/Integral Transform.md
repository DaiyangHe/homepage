## Fourier Transform
### Fourier Series
#### Definition
For a periodic function $f(t)$, the Fourier series representation is given by$$f(t)=a_0+\sum_{n=1}^\infty\left(a_n\cos\left(\frac{2\pi n}{T}t\right)+b_n\sin\left(\frac{2\pi n}{T}t\right)\right),\quad\mathrm{for}-\pi\leq t\leq\pi$$where$$\begin{gathered}a_0=\frac{1}{T}\int_0^Tf(t)dt\\a_{n}=\frac{2}{T}\int_0^Tf(t)\cos\left(\frac{2\pi n}{T}t\right)dt\\b_{n}=\frac{2}{T}\int_0^Tf(t)\sin\left(\frac{2\pi n}{T}t\right)dt\end{gathered}$$The complex exponential form is given by$$f(t)=\sum_{n=-\infty}^\infty c_ne^{i\frac{2\pi n}{T}t}$$
where$$c_n=\frac{1}{T}\int_0^Tf(t)e^{-i\frac{2\pi n}{T}t}dt$$If function is defined on $[-L,L]$, then we need linear transform $y=\frac{Lx}{\pi}$ coefficients are given by$$\begin{aligned}
F(y)&=\frac{a_0}{2}+\sum_{n=1}^\infty[a_n\cos ny+b_n\sin ny]\\
a_{0}&=\frac{\int_{-\pi}^{\pi}F(y)dy}{\pi}=\frac{\int_{-L}^{L}f(x)\frac{\pi}{L}dx}{\pi}=\frac{\int_{-L}^{L}f(x)dx}{L}\\
a_{n}&=\frac{1}{\pi}\int_{-\pi}^\pi F(y)\cos(ny)dx=\frac{1}{L}\int_{-L}^Lf(x)\cos(\frac{n\pi x}{L})dx\\
b_{n}&=\frac{1}{\pi}\int_{-\pi}^\pi F(y)\sin(ny)dx=\frac{1}{L}\int_{-L}^Lf(x)\sin(\frac{n\pi x}{L})dx
\end{aligned}$$
### Fourier Transform
#### Definition
The Fourier Transform decomposes a function (usually a time-domain signal) into a sum (or integral) of sine and cosine waves of different frequencies.$$\hat{f}(\omega)=\int_{-\infty}^\infty f(t)e^{-i\omega t}dt$$The inverse Fourier Transform can recover the original signal from its frequency representation:$$f(t)=\frac{1}{2\pi}\int_{-\infty}^\infty\hat{f}(\omega)e^{i\omega t}d\omega$$
#### Properties
##### Linearity
The Fourier Transform of a linear combination of functions is the linear combination of the Fourier Transforms of those functions.$$\mathcal{F}(c_{1}f_{1}(t)+c_{2}f_{2}(t))=c_{1}\hat{f_{1}}(\omega)+c_{2}\hat{f_{2}}(\omega)$$
##### Time Shifting
Shifting a function in the time domain results in a phase shift in the frequency domain.$$\mathcal{F}(f(t-t_{0}))=e^{-i\omega t_{0}}\mathcal{F}(f(t))$$
##### Frequency Shifting
A shift in the frequency domain corresponds to a multiplication of the time-domain function by an exponential.$$\mathcal{F}^{-1}(\hat{f}(\omega-\omega_{0}))=f(t)e^{i\omega_{0}t}$$
##### Differential Property
The Fourier Transform of the derivative of an function equals to $i\omega \hat{f}(\omega)$.$$\mathcal{F}(f')=i\omega \mathcal{F}(f)$$
##### Integral Property
If we have a function such that $\int_{-\infty}^{\infty}f(t)\mathrm{d}t=0$, then$$\mathcal{F}\left(\int_{-\infty}^tf(t)dt\right)=\frac{1}{i\omega}\mathcal{F}(f)$$If $\int_{-\infty}^{\infty}f(t)\mathrm{d}t\neq0$, then$$\mathcal{F}\left(\int_{-\infty}^tf(t)dt\right)=\frac{1}{i\omega}\mathcal{F}(f)+\pi \hat{f}(0)\delta(\omega)$$
##### Convolution Theorem
The Fourier Transform of the convolution of two functions is the pointwise product of their Fourier Transforms.$$\mathcal{F}(f_{1}*f_{2})=\hat{f_{1}}\cdot\hat{f_{2}}$$
##### Parseval’s Theorem
This theorem states that the total energy of a signal (integrated over all time) is the same in both the time and frequency domains.$$\int_{-\infty}^{\infty}f(t)^2\mathrm{d}t=\frac{1}{2\pi}\int_{-\infty}^{\infty}|\hat{f}(\omega)|^2\mathrm{d\omega}$$In terms of Fourier Series, it can also be written as$$\begin{align}
\int_{-\pi}^{\pi}&\left|f\left(x\right)\right|^{2}dx=2\pi\sum_{n=-\infty}^{\infty}\left|c_{n}\right|^{2} \\
c_n&=\frac{1}{2\pi}\int_{-\pi}^{\pi}f\left(x\right)e^{-inx}dx
\end{align}$$Generally, for the Fourier Series$$f\left(x\right)=a_0+\sum_{n=1}^\infty\left(a_n\cos\frac{n\pi x}{L}+b_n\sin\frac{n\pi x}{L}\right)$$the Parseval's theorem is given by$$\frac{1}{2L}\int_{-L}^Lf^2\left(x\right)dx=a_0^2+\frac{1}{2}\sum_{n=1}^\infty\left(a_n^2+b_n^2\right)$$
## Laplace Transform
Fourier Transform requires a function satisfies the Dirichlet condition and is absolutely integrable over $(-\infty, \infty)$. However, many realistic function cannot meet the condition. For example, function with respect to time ($t>0$). For an arbitrary function $\phi(t)$, we can utilize properties of **unit step function** and **exponential decay function** to make it suitable for Fourier transform. $u(t)$ can converts the domain to $[0,\infty)$, and $e^{-\beta t}$ can make the function to be absolutely integrable. Therefore, consider the following function:$$\phi(t)u(t)e^{-\beta t},\quad \beta>0$$The Fourier transform always exists with suitable $\beta$. Do Fourier transform on it,we obtain the **Laplace Transform**.
### Definition
Laplace transform converts integral and differential equations into algebraic equations. I's defined as:$$\mathcal{L}\{f(t)\}=F(s)=\int_0^\infty f(t)e^{-st} dt$$
### Laplace Transform Table
The Laplace transform table is shown as follows:

| Function $ f(t)$                | Laplace Transform $ F(s) = \mathcal{L}\{f(t)\}$ |
| ------------------------------- | ----------------------------------------------- |
| $1$                             | $\frac{1}{s}$, $s > 0$                          |
| $\frac{t^n}{n!}$                | $\frac{1}{s^{n+1}}$, $n \geq 0$                 |
| $e^{at}$                        | $\frac{1}{s - a}$, $s > a$                      |
| $t e^{at}$                      | $\frac{1}{(s-a)^2}$, $s > a$                    |
| $t^n e^{at}$                    | $\frac{n!}{(s-a)^{n+1}}$, $s > a$               |
| $\sin(\omega t)$                | $\frac{\omega}{s^2 + \omega^2}$                 |
| $\cos(\omega t)$                | $\frac{s}{s^2 + \omega^2}$                      |
| $e^{at} \sin(\omega t)$         | $\frac{\omega}{(s-a)^2 + \omega^2}$             |
| $e^{at} \cos(\omega t)$         | $\frac{s-a}{(s-a)^2 + \omega^2}$                |
| $u(t - T)$ (Unit step function) | $\frac{e^{-sT}}{s}$                             |
| $\delta(t)$ (Impulse function)  | $1$                                             |
| $\delta(t - T)$                 | $e^{-sT}$                                       |
### The existence theorem of the Laplace transform
The Laplace transform of a function $f(t)$ exists only if
- $f(t)$ is continuous or piece-wise continuous on the given closed interval
- $f(t)$ must be of exponential order, which means when $t\geq 0$, $$|f(t)|\leq Me^{ct},\quad c\geq 0$$
Note that the condition is **sufficient** but **not necessary**. e.g. $f(t)=\frac{1}{\sqrt{ t }}$.
### Properties of Laplace Transform
#### Linearity
Suppose $f$ and $g$ are piecewise continuous functions of exponential order, and $𝛼$ and $𝛽$ are constants. Then
$$\mathcal{L}\{\alpha f(t)+\beta g(t)\}=\alpha \mathcal{L}\{f(t)\}+\beta \mathcal{L}\{g(t)\}$$
**Note**:
1. In general, $\mathcal{L}\{f(t)g(t)\}\neq\mathcal{L}\{f(t)\}\cdot\mathcal{L}\{g(t)\}$.
2. Many functions like $e^{t^2}$, $\frac{1}{t}$, and $\tan t$ do not have Laplace transforms, for they are beyond exponential order.

#### the Laplace Transform of Derivatives
Suppose $y$ is a piece-wise differential function of exponential order. Suppose also that $y’$ is of exponential order. Then for large values of $s$, $$\mathcal{L}\{y'\}(s)=e^{-st}y(t)\Big|_0^\infty+s\int_0^\infty e^{-st}y(t)\mathrm{d}t$$ (Integration by parts). Then we have:
$$\mathcal{L}\{y'\}(s)=s\mathcal{L}\{y\}(s)-y(0)=sF(s)-y(0)$$
For higher order derivatives, we also have:$$\mathcal{L}\{y''\}=s\mathcal{L}\{y'\}-y'(0)=s(sY-y(0))-y'(0)$$$$\mathcal{L}\{y''\}=s^2Y-sy(0)-y'(0)$$
#### the Integration Property
Suppose $y$ is a piece-wise differential function of exponential order. Suppose also that $y’$ is of exponential order. Then for large values of $s$, $$\mathcal{L}\left( \int_{0}^tf(t)\mathrm{d}t \right)=\frac{1}{s}F(s)$$
This property is also iterative, which means $$\mathcal{L}[\underbrace{\int_0^tdt\int_0^tdt\cdots\int_0^t}_{n}f(t)dt]=\frac{1}{s^n} F(s)$$
#### First Shifting Property
$$\mathcal{L}\{e^{ct}f(t)\}(s)=\int_{0}^{\infty}y(t)e^{-(s-c)t}\ \mathrm{d}t=F(s-c)$$
#### Second Shifting Property
Suppose $f$ is a piece-wise continuous function of exponential order and $f(t)=0$ when $t<0$. Let $F(𝑠)$ be the Laplace transform of $f$. Then
$$\mathcal{L}(f(t-\tau))=e^{-s\tau}F(s)$$
It's important to note that $f(t)=0$ when $t<0$ **must** be met to apply the second shifting property. In order to meet this condition, the Heaviside function is$$H(x)=\begin{cases}
0,\quad x\leq0 \\
1,\quad x> 0
\end{cases}$$
We know that $\mathcal{L}(H(t))=\frac{1}{s}$, and $\mathcal{L}(H(t-\tau))=\frac{1}{s}e^{-s\tau}$.
This property can also be expressed in terms of $H(x)$. If $\mathcal{L}(f(t)H(t))=F(s)$, then for any positive integer: $$\mathcal{L}(f(t-\tau)H(t-\tau))=e^{-s\tau}F(s)$$
#### the Derivatives of the Laplace Transform
Suppose $f$ is a piece-wise continuous function of exponential order. Let $F(𝑠)$ be the Laplace transform of $f$. Then$$L\{tf(t)\}(s)=-F^{\prime}(s)$$
More generally, if 𝑛 is any positive integer, then$$\mathcal{L}\{t^nf(t)\}(s)=(-1)^nF^{(n)}(s)$$
Referring to integration property, we know that $$\mathcal{L}\left( \frac{f(t)}{t} \right)=\int_{0}^{\infty}F(s)\mathrm{d}s$$
### Impulse Functions and The Dirac Delta Function
#### Impulse Functions
Consider a force function of unit impulse acting in a short time interval as$$\delta_p^\epsilon(t)=
\begin{cases}
\frac{1}{\epsilon}, & p\leq t<p+\epsilon, \\
 \\
0, & t<p\mathrm{~or~}t\geq p+\epsilon & 
\end{cases}$$It's unit impulse because $\int_{p}^{p+\epsilon}\delta_p^\epsilon(t)\ \mathrm{d}t=1$. We can translate it by the Heaviside function$$\delta_p^\epsilon(t)=\frac{1}{\epsilon}\left(H_p-H_{p+\epsilon}\right)=\frac{1}{\epsilon}\left(H(t-p)-H(t-(p+\epsilon))\right)$$If the width of the impulse is very sharp, the unit impulse turns into the **Dirac Delta Function**$$\delta_p(t)=\lim_{\epsilon\to0}\delta_p^\epsilon(t)$$Indeed, it's defined as$$\delta(t)=
\begin{cases}
\infty & t=0 \\
0 & t\neq0 & 
\end{cases}$$with $\int_{-\infty}^{\infty}\delta(t)\mathrm{d}t=1$. Suppose $p\in \mathbb{R}$ is any fixed point and let 𝑓 be any function that is continuous at $t=p$. Then$$\begin{aligned}
\int_{-\infty}^{\infty}\delta(t)f(t)\mathrm{d}t=f(0)
\end{aligned}$$or we can say:$$\int_{-\infty}^\infty\delta(t-p)f(t)\mathrm{d}t=f(p)$$Let $f(t)=e^{-st}$ ,the Laplace transform of $\delta(t-p)$ for $p\geq 0$ is given by$$\mathcal{L}\{\delta(t-p)\}=\int_0^\infty\delta(t-p)e^{-st}\ \mathrm{d}s=e^{-sp}$$Specifically, we have when $p=0$, $\mathcal{L}(\delta_{0})=1$
In linear systems theory, the **impulse response** h(t)h(t) is the output of a system when the input is δ(t)δ(t). For a system described by a differential equation, the impulse response represents the system's reaction to an impulse. The solution $y(t)$ to the second-order equation$$a\frac{\mathrm{d}y^2}{\mathrm{d}t^2}+b\frac{\mathrm{d }y}{\mathrm{d}t}+cy=\delta(t),\quad \text{with} y(0)=y'(0)=0$$is called the unit impulse response function to the system modeled by the differential equation. note that the unit impulse response equation is the reciprocal of the characteristic polynomial $as^2+bs+c$.
### Convolution
#### Definition
Recall the property of the Laplace transform:$$\mathcal{L}(f(t)g(t))\neq \mathcal{L}(f(t))\mathcal{L}(g(t))$$We need to define a new type of "product". Convolution is defined as$$(f*g)(t)=\int_0^tf(\tau)g(t-\tau)\ \mathrm{d}\tau$$
#### Properties of Convolution
- **Commutative Property**: $f∗g=g∗f$
- **Associative Property**: $f∗(g∗h)=(f∗g)∗h$
- **Distributive Property**: $f∗(g+h)=(f∗g)+(f∗h)$
- **Scaling**: $a(f∗g)=(af)∗g=f∗(ag)$
- **Time-shifting**: $(f(t−a)∗g(t))=(f∗g)(t−a)$
- **Differential**: $\frac{\mathrm{d }}{\mathrm{d}t}(f*g)(t)=\frac{\mathrm{d }f}{\mathrm{d}t}*g+f(0)g(t)=f*\frac{\mathrm{d }g}{\mathrm{d}t}+f(0)g(t)$
- **Integral**: $\int_{0}^t(f*g)\ \mathrm{d}\xi=f(t)*\int_{0}^tg(\xi)\ \mathrm{d}\xi=\int_{0}^tf(\xi)\ \mathrm{d}\xi*g(t)$
- **Norm**: $|f*g|\leq|f|*|g|$
- **Delta**: $f*\delta=f=\delta*f$
One of the most important properties is that the Laplace transform of the convolution of two functions is the product of their individual Laplace transforms:$$\mathcal{L}(f*g)=\mathcal{L}(f)\cdot\mathcal{L}(g)$$Therefore, it's quite similar to product.
#### Solve 2nd-order differential equation
The **state-free response** (sometimes called the **homogeneous response**) refers to the part of the system’s solution that depends solely on the system's **initial conditions** and not on the input signal. In other words, it's the solution to associated homogeneous equation. The **input-free response** (sometimes referred to as the **natural response**) refers to the part of the system’s solution that evolves due to the **initial conditions**, without any external forcing (input). Consider such an IVP problem$$ay''+by'+cy=f(t),\quad\text{with }y(0)=y_{0},\ y'(0)=y_{1}$$the solution can be written as $$y=y_{s}(t) \text{ (state-free solution)}+y_{i}(t)\text{ (input-free solution)}$$If $e(t)$ is the unit impulse response function for the system, then the state-free response is$$y_{s}=e*f$$and the input-free response is$$y_i=ay_0e'+(ay_1+by_0)e$$