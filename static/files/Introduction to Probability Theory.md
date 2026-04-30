Probability, Random Variables, and Distributions- IE 1070
## Conditional Probability, Independence, and Law of Total Probability
Mean value:
$$
\bar{x}=\sum_{i=1}^n\frac{x_i}n=\frac{x_1+x_2+\cdots+x_n}n
$$
The Sample Variance:
$$
s^2=\sum_{i=1}^n\frac{(x_i-\bar{x})^2}{n-1}
$$
A permutation is an arrangement of all or part of a set of objects. The number of permutations of $n$ distinct objects taken $r$ at a time is
$$_nP_r=\frac{n!}{(n-r)!}$$
### Conditional Probability and Independence
When event $B$ is given, the probability of $A$ is given by
$$
P(A|B)=\frac{P(A\cap B)}{P(B)}
$$
An informal method to check the independence between two events is that if $P(A|B)=P(A)$, then they are independent. Generally, events $A_{1},A_{2},\dots,A_{n}$ such that 
- $P(A_1\cap \dots\cap A_{n})=P(A_{1})\dots P(A_{n})$
- Any non-empty subset of $\{A_{1},A_{2},\dots,A_{n}\}$ is independent
are independent. For two events, A and B is independent $\Leftrightarrow P(A\cap B)=P(A)P(B)$.
For those are dependent, we have $P(A\cup B)=P(A)+P(B)-P(A\cap B)$
### Partition and Total Probability
If a sample space is divided into some number of mutually exclusive events, and that their union makes up the whole sample space, it's called "collectively exhaustive" or a partition. A partition is countable sets $\{A_{1},A_{2},\dots,A_{i}\}$ in sample space $S$ such that
- if $i\neq j$, then $A_{i}\cap A_{j}=\varnothing$ 
- $A_{1}\cup A_{2}\cup \dots\cup A_{i}=S$
For any event $B\in S$, we have the total probability formula:
$$
P(B)=\sum_{i=1}^{n}P(B\cap A_i)=\sum_{i=1}^{n} P(B|A_{i})\cdot P(A_{i})
$$
Combination:
$$\binom nr=\frac{n!}{r!(n-r)!}$$
The number of partitions can be calculated by following theorem:
**Theorem:** The number of ways of partitioning a set of $n$ objects into $r$ parts with $n_1$, $n_2$, $...$ , $n_r$ elements is:
$${n\choose n_{1},n_{2},\dots,n_{r}}=\frac{n!}{n_{1}!n_{2}!\ \dots n_{r}!}$$
### Bayes' Theory
According to conditional probability, we can derive the equation with the assistance of $P(A\cap B)$:
$$
P(B|A)\cdot P(A)=P(A|B)\cdot P(B)
$$
Therefore, if $P(B)\neq 0$,
$$
P(A|B)=P(B|A)\cdot \frac{P(A)}{P(B)}
$$
The key point in this process is **exchangeability**: $A\cap B=B\cap A$. 
Another critical point of Bayes's theory is that altering posterior probabilities based on new evidence and prior probabilities. We can expressed it by:
$$
P(A_{i}|B)=\frac{P(B|A_{i})P(A_{i})}{P(B)}=\frac{P(B|A_{i})P(A_{i})}{\sum_{i=1}^{n}P(B|A_{i})P(A_{i})}
$$
## Discrete Random Variables
A **discrete random variable** is a real-value function defined in a discrete sample space $\Omega$ (which means $\Omega$ is finite or countable). Specifically, we assign a real number $X(\omega)$ to each element $\omega \in \Omega$. 
### Probability Mass Function (pmf) and Cumulative Distribution Function (cdf)
For discrete random variables $X$ for all possible values $x$, its probability mass function is a set of ordered pairs $(x,f(x))$ such that
- $f(x)\geq 0$ for $\forall x$
- $\sum_{x}f(x)=1$
- $P(X=x)=f(x)$
Cumulative distribution function of a discrete random variable $F(x)$ denotes the probability that $X\leq x$. The cdf can be given by pmf as 
$$
F(x)=P(X\leq x)=\sum_{t\leq x}f(t)
$$
For discrete random variables, we have $P(a<X\leq b)=F(b)-F(a)$, $P(a\leq X\leq b)=F(b)-F(a)+f(a)$. From the definition we have:
$$
f(x_{i})=F(x_{i})-F(x_{i-1})
$$
## Continuous Random Variables
Similarly, a **continuous random variable** is a  real-value function defined in a continuous sample space $\Omega$. The **Probability Density Function** is a real value function such that
- $f(x)\geq0, \mathrm{for~all~} x\in R$
- $\int_{-\infty}^{\infty}f(x) dx=1$
- $P(a<X<b)=\int_{a}^{b}f(x) dx$
For continuous random variables, the cdf is defined as:
$$F(x)=P(X\leq x)=\int_{-\infty}^{x}f(t) dt$$
From the definition we can see that:
$$
P(a<X<b)=F(b)-F(a)
$$
$$
f(x)=\frac{\mathrm{d }F(x)}{\mathrm{d}x} 
$$
## Joint Probability Distribution Function
For 2 discrete random variables$X$ and $Y$, the *pmf* is defined as a function such that:
- $f(x,y)\geq 0$
- $\sum_{x}\sum_{y}f(x,y)=1$
- $f(x,y)=P(X=x,Y=y)$
For any region $A$ in the $xy$ plane, $P((X,Y)\in A)=\sum\sum_Af(x,y)$.
The *pmf* of $X$ and $Y$ are given by summing another variables.
$$
g(x)=\sum_{y}f(x,y),\qquad h(y)=\sum_{x}f(x,y)
$$
They are called **Marginal Probability Mass Function**. 
For condition probability that $P(X=x|Y=y)$ is given by:
$$
p(x|y)=\frac{f(x,y)}{h(y)}
$$
The $p(x|y)$ is the conditional distribution of discrete random variable $X$ given $Y=y$. 
Similarly, for continuous random variables, the joint probability distribution function satisfies:
- $f(x,y)\geq 0$
- $\int_{y}\int_{x}f(x,y)\ \mathrm{d}x\mathrm{d}y=1$
- $\iint_{A}f(x,y)\ \mathrm{d}x\mathrm{d}y=P([x,y]\in A)$
The marginal density equation is given by:
$$
g(x)=\int_{-\infty}^{\infty}f(x,y)\mathrm{d}y,\qquad h(y)=\int_{\infty}^{\infty}f(x,y)\mathrm{d}x
$$
## Mathematical Expectation
### Introduction to Expectation
Expectation is weighted average of all possible values of random variable. For discontinuous random variable, the expectation is defined as:$$\mu(x)=E(x)=\sum_{x}xf(x)$$Similarly, for continuous random variable, the expectation is$$\mu(x)=E(x)=\int_{-\infty}^{\infty}xf(x)\mathrm{d}x$$Also for the function of random variable $g(x)$, we have:$$\mu(x)=E(x)=\sum_{x}g(x)f(x)$$$$\mu(g(x))=E(g(x))=\int_{-\infty}^{\infty}g(x)f(x)\ \mathrm{d}x$$
### Moment of Random Variables
When $g(x)=x^r$, the expectation of $E(x^{r})$ is r-order moment, $E((x-\mu)^r)$ is r-order center moment. $$\mu_{k}=E[(x-\mu)^r]=\frac{1}{n}\sum_{i=1}^n(x_{i}-\mu)^r$$The expectation is the first-order moment, and variance is the second-order center moment. The third-order center moment is skewness, which represents the asymmetry of the distribution. kurtosis is the forth-order center moment, which indicates the peak of the PDF at the mean value. For those two center moment, we have the following inequality$$\frac{\mu_{4}}{\sigma^4}\geq\left( \frac{\mu_{3}}{\sigma^3} \right)^2+1$$
### Properties of Expectation
If $X$ and $Y$ follows joint mass distribution $f(x,y)$, then $$E(g(x,y))=\sum_{y}\sum_{x}g(x,y)f(x,y)$$If $f(x,y)$ is a joint density distribution, we have:$$E(g(x,y))=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}g(x,y)f(x,y)\ \mathrm{d}x\mathrm{d}y$$calculation of expectation is linear, which means$$E(aX+bY)=aE(X)+bE(Y)$$
If two random variables are **independent**, then$$E(XY)=E(X)E(Y)$$
### Variance and Covariance
Let X be a random variable with probability distribution $f(x)$ and mean $\mu$. The variance of $X$ is$$\sigma^2=E[(X-\mu)^2]=\sum(x-\mu)^2f(x)$$if $X$ is discrete, and$$\sigma^2=E[(X-\mu)^2]=\int_{-\infty}^{\infty}(x-\mu)^2f(x)\ \mathrm{d}x$$if $X$ is continuous. For two discrete random variables $X$ and $Y$, the covariance is defined as$$\sigma_{XY}=\text{Cov}(X,Y)=E[(X-\mu_{X})(Y-\mu_{Y})]=\sum_x\sum_y(x-\mu_X)(y-\mu_y)f(x,y)$$if $X$ and $Y$ are continuous, we have$$\sigma_{XY}=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}(x-\mu_X)(y-\mu_y)f(x,y)dxdy$$Generally, we have$$\sigma_{XY}=E(XY)-\mu_{X}\mu_{Y}$$Covariance measures how a change in one variable affects a change in another variable, i.e., the degree of linear dependence. Therefore, we can define the correlation coefficient by standardize the covariance.$$\rho=\frac{\sigma_{XY}}{\sigma_{X}\sigma_{Y}}$$
### Properties of Variance
For any random variable, The variance can be calculated by$$\text{Var}(X)=E(X^2)-E(X)^2$$If new variable $Y=aX+b$, we have the variance$$\sigma_{Y}^2=a^2\sigma_{X}^2$$For any random variable $X=X_{1}+X_{2}+X_{3}+\dots+X_n$, we have$$\mu_{X}=\sum_{i=1}^{n}X_{i}$$If they are independent, we know that$$\sigma_{X}^2=\sum_{i=1}^{n}\sigma_{i}^2$$
## Discrete Distribution
### Bernoulli distribution
If a random variable $X$ satisfies $P(X=1)=p$ and $P(X=0)=1-p$, then $X$ follows the Bernoulli distribution with parameter $p$, $X\sim \text{Bern}(p)$. We know that $$\mu=p,\quad\sigma^2=p(1-p)$$
### Binomial Distribution
The number of successes in $n$ Bernoulli trail follows the **binomial distribution**$$P(X=x)=b(x;n,p)=\binom{n}{x}p^xq^{n-x},\quad x=0,1,2,\ldots,n$$The mean and variance of the binomial distribution $b(x;n, p)$ are$$\mu=np,\quad\sigma^2=np(1-p)$$
### Multinomial Distribution
The binomial experiment becomes a multinomial experiment if we let each trial have more than two possible outcomes. Suppose that we have $n$ trail with $k$ possible outcomes with probability $p_{1},p_{2},p_{3},\dots,p_{k}$. Then we have the joint probability distribution $$f(x_1,x_2,\ldots,x_k;p_1,p_2,\ldots,p_k,n)=\binom{n}{x_1,x_2,\ldots,x_k}\prod_{i=1}^np_{i}^{x_{i}}$$where $\sum_{i=1}^{k}x_{i}=n$. Similarly, we have corollary like binomial distribution$$\mu_{X_{i}}=np_{i},\quad\sigma_{X_{i}}^2=np_{i}(1-p_{i})$$That's because for each possible outcome, the experiment can be described as a binomial experiment. 
### Hypergeometric Distribution
Let $X$ be a random variable, the number of successes in $n$ samples selected from $N$ items. Then it follows the hypergeometric distribution. The probability distribution is given by$$h(x;N,n,k)=\frac{\binom{k}{x}\binom{N-k}{n-x}}{\binom{N}{n}},\quad\max\{0,n-(N-k)\}\leq x\leq\min\{n,k\}$$The mean value and variance is$$\mu=\frac{nk}{N},\quad\sigma^2=\frac{N-n}{N-1}\cdot n\cdot\frac{k}{N}\left(1-\frac{k}{N}\right)$$When $n$ is small compare to $N$, then the hypergeometric distribution approaches the binomial distribution.
For **Multivariate Hypergeometric Distribution**, we have $$f(x_{1},x_{2},\ldots,x_{k};a_{1},a_{2},\ldots,a_{k},N,n)=\frac{\binom{a_{1}}{x_{1}}\binom{a_{2}}{x_{2}}\cdots\binom{a_{k}}{x_{k}}}{\binom{N}{n}}$$where $\sum_{i=1}^kx_{i}=n$ and $\sum_{i=1}^ka_{i}=N$.
### Negative binomial Distribution
Let $X$ denote the number of trials that needed to get $k$ success (with probability $p$) in a negative binomial experiment. The probability distribution of the random variable X , the number of the trial on which the $k$th success occurs, is$$P(X=x)=b^*(x;k,p)=\binom{x-1}{k-1}p^kq^{x-k},\quad x\geq k$$Some ones will define the negative binomial distribution as the probability that the number $X$ of successes when $r$th failures occur. Therefore$$P(X=x)=\binom{k+r-1}{k}p^{r}q^k$$with expectation $\frac{rp}{1-p}$ and variance $\frac{rp}{(1-p)^2}$.
### Geometric Distribution
If repeated independent trials can result in a success with probability p and a failure with probability q=1−p, then the probability distribution of the random variable X, the number of the trial on which the **first** success occurs, is geometric distribution$$P(X=x)=g(x;p)=pq^{x-1},\quad x=1,2,3,\ldots.$$with expectation $\frac{1}{p}$ and variance $\frac{1-p}{p^2}$.
The cdf of geometric distribution is given by$$F(x)=\sum_{y\leq x}P(Y=y)=p\sum_{y=0}^{x-1}(1-p)^{y}=1-(1-p)^x$$
### Poisson Distribution
The Poisson distribution models the number of events occurring within a fixed interval of time or space, given that the events **happen with a constant rate** $\lambda$ and are **independent** of each other.$$P(X=k)=\frac{\lambda^ke^{-\lambda}}{k!},\quad k=0,1,2,\ldots$$The **mean** and **variance** of the Poisson distribution are **both** $\lambda$. For small values of $\lambda$, the distribution is highly skewed (leaning to the right). As $\lambda$ increases, the distribution becomes more symmetric and approaches a normal distribution.
The Poisson distribution can be derived as a limit of the **binomial distribution**. Consider a scenario where we have:
- A large number of trials (e.g., very small intervals)
- A small probability of success in each trial (i.e., the rate $\lambda$ is small)
- The number of trials $n$ is large, but $p = \frac{\lambda}{n}$​ is also small, so the expected number of successes in the interval remains constant at $\lambda$
As $n \to \infty$ and $p \to 0$, with $np = \lambda$, the binomial distribution approaches the Poisson distribution. This gives rise to the formula for the Poisson distribution$$\text{Pois}(x)=\lim_{ n \to \infty,\ np\to\lambda}\binom{n}{x}p^xq^{n-x}=\frac{\lambda^xe^{-\lambda}}{x!}$$While $\lambda \to \infty$, the Poisson distribution approaches to the normal distribution.
## Continuous Distribution
### Flat Distribution
If the random variable $X$ satisfies$$P(X=x)=\begin{cases}
\frac{1}{b-a},\quad&\text{if }a\leq x\leq b \\
0,\quad&\text{elsewhere}
\end{cases}$$follows a flat distribution. Mean and variance is respectively$$\mu=\frac{a+b}{2},\quad \sigma^2=\frac{(b-a)^2}{12}$$
### Exponential Distribution
The exponential distribution is a continuous probability distribution often used to model the time between events in a **Poisson process**. A Poisson process is a type of stochastic process in which events occur randomly and independently at a constant average rate. The PDF is given by$$f(x;\lambda)=\lambda e^{-\lambda x},\quad x\geq0$$$\lambda$ is the rate parameter, which represents the **inverse of the mean time between events**. And the CDF is given by$$F(x;\lambda)=1-e^{-\lambda x},\quad x\geq0$$Mean and variance is respectively$$\mu=\frac{1}{\lambda},\quad \sigma^2=\frac{1}{\lambda^2}$$**Note**: 
### **Normal Distribution**
If PDF of an random variable $X$ is$$f(x)=\frac{1}{\sqrt{ 2\pi\sigma^2 }}e^{ \frac{-(x-\mu)^2}{2\sigma^2} }$$then it follows a normal distribution $X\sim N(\mu,\sigma^2)$, when $\mu=0$ and $\sigma^2=1$ $N(0,1)$ is the standard normal distribution. Z-score normalization $z=\frac{x-\mu}{\sigma}$ is used to perform standardization. 
#### Normalization Constant Theorem
if there is a non-negative real function $g(x)$ such that$$c=\int_{-\infty}^{\infty}g(x)\ \mathrm{dx}$$then $f(x)=\frac{g(x)}{c}$ is a PDF.
#### Properties

1. **Symmetry**
The normal distribution is **symmetric** about the mean $\mu$. The curve is highest at $\mu$ and tapers off as moving away from the mean in either direction.
2. **Bell-Shaped Curve**
The graph of the normal distribution is a smooth, **bell-shaped curve**. It is the **Gaussian curve**, which is smooth, continuous, and unimodal (having a single peak at the mean).
3. **68-95-99.7 Rule**
One of the most important properties of the normal distribution is the **68-95-99.7 rule**, which states:
- About **68%** of the data falls within one standard deviation of the mean, i.e., between $\mu - \sigma$ and $\mu + \sigma$.
- About **95%** of the data falls within two standard deviations of the mean, i.e., between $\mu - 2\sigma$ and $\mu + 2\sigma$.
- About **99.7%** of the data falls within three standard deviations of the mean, i.e., between $\mu - 3\sigma$ and $\mu + 3\sigma$.
4. **Skewness and kurtosis**
The **skewness** of a normal distribution is $0$, meaning it is perfectly symmetric. The **kurtosis** of a normal distribution is **3** (often described as "mesokurtic"), meaning it has a moderate, bell-shaped peak.
5. **Linearity**
Any linear combination of independent normal random variables is also normally distributed. If $X_1,X_2,\ldots,X_n$ are independent normal random variables with means $\mu_1,\mu_2,\ldots,\mu_n$ and
variances $\sigma_1^2,\sigma_2^2,\ldots,\sigma_n^2$, then for any constants $a_1,a_2,\ldots,a_n$, the random variable:$$Y=a_1X_1+a_2X_2+\cdots+a_nX_n$$is normally distributed with mean and variance given by:
$$\begin{aligned}
E[Y]=a_1\mu_1+a_2\mu_2+\cdots+a_n\mu_n \\ \mathrm{Var}(Y)=a_1^2\sigma_1^2+a_2^2\sigma_2^2+\cdots+a_n^2\sigma_n^2
\end{aligned}$$
6. **Cumulative Distribution Function (CDF)**
The CDF of the standard normal distribution $N(0,1)$ is denoted by$$\Phi(x)=P(Z\leq x)=\int_{-\infty}^x\frac{1}{\sqrt{2\pi}}e^{-\frac{t^2}{2}}dt$$The error function is defined as the probability that random variable $X\sim N\left(0, \frac{1}{2} \right)$ within $0$ to $x$.$$\mathrm{erf}(x)=\frac{2}{\sqrt{\pi}}\int_0^xe^{-t^2}dt$$It also can be calculated by the standard normal distribution and series expansion:$$\Phi(x)-\Phi(-x)=\mathrm{erf}(x)=\frac{2}{\sqrt{\pi}}\sum_{n=0}^\infty\frac{(-1)^nx^{2n+1}}{n!(2n+1)}$$
#### Approximate Binomial Distribution with Normal Distribution
The **normal distribution** can be used to approximate the **binomial distribution** to simplify the calculation.
##### Conditions for Approximation
- **Large number of trials**: $n$ should be large enough. There is no strict cutoff, but a common rule of thumb is that the normal approximation works well when both $np$ and $n(1-p)$ are greater than 5:$$np\geq5\quad\mathrm{and}\quad n(1-p)\geq5$$
- **Moderate probability** $p$: The success probability $p$ should not be too close to $0$ or $1$. If $p$ is close to $0$ or $1$, the binomial distribution is highly skewed, and the normal approximation may not be accurate.
##### Approximation
For a random variable $X$ following the binomial distribution with $\mu$ and $\sigma^2$, we have approximation $X\sim N(\mu,\sigma^2)$. we can estimate the PDF and CDF by$$\begin{align}
P(X=k)=n\left(\frac{k-\mu}{\sigma}-0.5\leq z\leq\frac{k-\mu}{\sigma}+0.5;\mu,\sigma \right)\\\mathrm{P(X\leq x)=\sum_{r=0}^x b(r;n,p)=P(z\leq\frac{x+0.5-\mu}{\sigma})}
\end{align}$$where $x+0.5$ is called continuity correction.
##### Continuity Correction

Since the binomial distribution is discrete and the normal distribution is continuous, a continuity correction is often applied to improve the approximation. This correction compensates for the difference between the discrete and continuous nature of the distributions. For a binomial random variable $X\sim\text{Binomial}(n,p)$, when using the normal approximation, the probability $P(X=k)$ is approximated by the probability $P(k-0.5\leq Z\leq k+0.5)$ where $Z\sim N(np,\sqrt{np(1-p)}).$
For example, to approximate $P(X\leq k)$ for a binomial random variable,$$P(X\leq k)\approx P\left(Z\leq\frac{k+0.5-np}{\sqrt{np(1-p)}}\right)$$
### Gamma Function
When $s$ is not non-positive integer, the Gamma function is defined by the following integral:$$\Gamma(s)=\int_0^\infty t^{s-1}e^{-t}\mathrm{d}t=\int_{0}^{\infty}e^{-x}x^{s} \frac{\mathrm{d}x}{x}$$In fact, the integral converges where $s$ is non-positive integer.
#### Analytic Continuation
Take the geometric series as an example. We know$$S_{n}=\lim_{ n \to \infty } \sum_{i=1}^nr^i=\frac{1}{1-r}$$requires $|r|<1$, but the RHS $y=\frac{1}{1-r}$ is defined for all $r\neq 0$. We called the RHS is an analytic continuation of LHS, and has a pole at $r=1$. The Gamma Function can be extended by the recurrence relation$$\Gamma(s+1)=s\Gamma(s)$$which can be proved by partial integral. According to this relation, we can be inspired that$$\Gamma(n+1)=n!$$Another way to extend the Gamma Function is using the functional equation reflection formula.$$\Gamma(s)\Gamma(1-s)=\pi \csc(\pi s)=\frac{\pi}{\sin(\pi s)}$$Obviously, $\Gamma\left( \frac{1}{2} \right)=\sqrt{ \pi }$, and for other half-integers, there are specific formulas that involve $\pi$, such as:$$\Gamma\left(\frac12+n\right)=\frac{(2n)!}{4^n(n!)^2}\cdot\sqrt{\pi}$$Here are some special values:
- $\Gamma(1)=1$
- $\Gamma(2)=1!=1$
- $\Gamma\left(\frac{3}{2}\right)=\frac{\sqrt{\pi}}{2}$
- $\Gamma(3)=2!=2$
And there are also another way to study $\Gamma\left( \frac{1}{2} \right)$
#### Beta Function
The Beta function $B(x,y)$ is defined for $x>0$ and $y>0$ by the following integral$$B(x,y)=\int_0^1t^{x-1}(1-t)^{y-1}\mathrm{d}t=\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}$$From this function,  we got another distribution: **Beta Distribution**.$$f(x;\alpha,\beta)=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}x^{\alpha-1}(1-x)^{\beta-1}=\frac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha,\beta)}\quad\mathrm{for}\quad x\in[0,1]$$With mean $\mu=\frac{\alpha}{\alpha+\beta}$ and variance $\sigma^2=\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$. For $x=m$ and $y=n$ are positive integers, we have:$$B(m,n)=\frac{(m-1)!(n-1)!}{(m+n-1)!}$$The shape parameters $\alpha$ and $\beta$ determine the skewness and modality of the distribution:
- When $\alpha = \beta = 1$, the Beta distribution is uniform.
- When $\alpha > 1$ and $\beta > 1$, the distribution is unimodal and symmetric.
- When $\alpha < 1$ and $\beta < 1$, the distribution has U-shaped behavior, concentrating near $0$ and $1$.
- When $\alpha > \beta$, the distribution is skewed towards $1$
- When $\alpha < \beta$, it is skewed towards 0.
#### Gamma Distribution and Normal Distribution
The $2m$-order moment of standard normal distribution is given by$$\mu_{2m}=\frac{1}{\sqrt{ 2\pi }}\int_{\infty}^{\infty}x^{2m}e^{-x^2/2}\mathrm{d}x=\prod_{i=1}^m (2i-1)=\frac{2^m}{\sqrt{ \pi }}\Gamma\left( m+\frac{1}{2} \right)$$There is a connection between the **Gamma distribution** and the **normal distribution** in the context of large values of the shape parameter. Firstly, the PDF of Gamma Distribution is given by$$f(x;\alpha,\beta)=\frac{x^{\alpha-1}e^{-x/\beta}}{\Gamma(\alpha)\beta^\alpha},\quad x>0$$with mean $\mu=\alpha\beta$ and variance $\alpha\beta^2$. If $\alpha$ is large, the Gamma distribution can be approximated by a normal distribution$$\mathrm{Gamma}(\alpha,\beta)\sim N(\alpha\beta,\alpha\beta^2)\quad\mathrm{as}\quad\alpha\to\infty$$
#### Erlang Distribution
The Erlang distribution is a special case of the **gamma distribution**, where the shape parameter $\alpha$ is an integer. The PDF of the Erlang distribution is given by:$$f(x)=\frac{x^{n-1}e^{-x/\beta}}{\beta^n(n-1)!},\quad x>0$$It can be shown that if the times between successive events are independent, each having an exponential distribution with parameter $\beta$, then the total elapsed waiting time $X$ until all $n$ events occur has the Erlang distribution, with mean $\mu=\beta n$ and variance $\sigma^2=\beta^2n$.
#### Weibull Distribution
The PDF of the **Weibull Distribution** is given by$$f(x;k,\lambda)=\begin{cases}\frac{k}{\lambda}\left(\frac{x}{\lambda}\right)^{k-1}e^{-(x/\lambda)^k}&\mathrm{for}\quad x\geq0\\0&\mathrm{for}\quad x<0&&\end{cases}$$with mean$$\mu=\lambda\Gamma\left(1+\frac{1}{k}\right)$$and variance$$\sigma^2=\lambda^2\left[\Gamma\left(1+\frac{2}{k}\right)-\left(\Gamma\left(1+\frac{1}{k}\right)\right)^2\right]$$when $k=1$ it's **Exponential Distribution**, $k=2$ it's **Rayleigh Distribution**. The **hazard function** $h(x)$, which gives the instantaneous failure rate at time $x$, is the ratio of the PDF to the survival function (1 minus the CDF). For the Weibull distribution:$$h(x;k,\lambda)=\frac{f(x;k,\lambda)}{1-F(x;k,\lambda)}=\frac k\lambda\left(\frac x\lambda\right)^{k-1}$$The hazard function characterizes the likelihood of failure occurring at a given time. Depending on the value of $k$, the hazard function can either increase or decrease with time which reflects whether the failure rate is increasing or decreasing.
#### Cauchy Distribution
The Cauchy distribution is a continuous probability distribution that is notable for its heavy tails and lack of a well-defined mean and variance. It is often used in scenarios where data exhibit **extreme outliers** or **heavy-tailed behavior**. PDF is given by$$f(x;x_0,\gamma)=\frac{1}{\pi\gamma\left[1+\left(\frac{x-x_0}{\gamma}\right)^2\right]}$$for standard Cauchy distribution is$$f(x)=\frac{1}{\pi} \frac{1}{1+x^2}$$and CDF:$$F(x;x_0,\gamma)=\frac{1}{2}+\frac{1}{\pi}\arctan\left(\frac{x-x_0}{\gamma}\right)$$The Cauchy Distribution has no mean and variance.
### Chi-Square Distribution
The PDF is given by$$f(x;\nu)=\frac{1}{2^{\nu/2}\Gamma(\nu/2)}x^{\frac{\nu}{2}-1}e^{-x/2},\quad x>0,\nu>0$$with mean $\mu=\nu$, and variance $\sigma^2=2\nu$. Where $\nu$ is the degree of freedom, which determine the shape of the Chi-Square Distribution. 
![[Pasted image 20241216195238.png|400]]
For $k$ random variables $X_{i}$ following the standard normal distribution $X_{i}\sim N(0,1)$, then$$Z=\sum_{i=1}^kX_{i}^2$$follows the Chi-Square Distribution.
## Limit Theorem
### Inequality and Law of Large Numbers
#### Inequality
##### Markov's Inequality
Markov's inequality provides an upper bound on the probability that a non-negative random variable is greater than or equal to a certain value. It is one of the simplest and most widely used inequalities in probability theory.
**Theorem**: Let $X$ be a non-negative random variable, and $a>0.$ Then:$$P(X\geq a)\leq\frac{E[X]}a$$
##### Chebyshev's Inequality
Chebyshev's inequality gives a bound on the probability that a random variable deviates significantly from its mean. It is a generalization of the Law of Large Numbers. 
**Theorem**: Let $X$ be a random variable with expected value $\mu$ and variance $\sigma^2$. For
any $k>0$, the following inequality holds:$$P(|X-\mu|\geq k\sigma)\leq\frac1{k^2}$$
##### Boole's Inequality and Bonferroni's Inequality
Boole's inequality, also known as the **Union Bound**, gives a bound on the probability of the union of events. It is a fundamental result in probability theory.
**Theorem**: Let $A_1,A_2,\ldots,A_n$ be events in a probability space. Then:$$P\left(\bigcup_{i=1}^nA_i\right)\leq\sum_{i=1}^nP(A_i)$$The Bonferroni's inequality says that, for positive integer $l,m$, we have$$\sum_{k=1}^{2l}(-1)^{k-1}S_{k}\leq P\left( \bigcup_{i=1}^nA_{i} \right)\leq \sum_{k=1}^{2m-1}(-1)^{k-1}S_{k}$$where $S_k$ is the sum of probability of all possible intersection of $k$ events $A_i$$$S_{k}=\sum_{1\leq i_{1}<i_{2}<\dots<i_{k}\leq n}P(A_{i_{1}}\cap A_{i_{2}}\cap\dots\cap A_{i_{k}})$$
#### Convergence
##### Convergence in Distribution
It's the most **weak convergence** and contained in every other types of convergence. A sequence of random variables $X_1,X_2,\ldots$ converges in distribution (denoted as $X_n\xrightarrow{d}$ $X)$ to a random variable $X$ if the cumulative distribution function (CDF) of $X_n$ converges to the CDF of $X$ at all points where $F_X$ is continuous:$$F_{n}(x)\to F_X(x)\quad\mathrm{for~all}\quad x\in\mathbb{R}$$This is also known as weak convergence or convergence in law.
**Example**: For uniform distribution $f(x)=\frac{1}{n},\ x\in\left\{0, \frac{1}{n},\dots,\frac{n-1}{n}\right\}$, the CDF is$$F(x)=\frac{\lfloor  nx \rfloor}{n}$$because we know $nx-1\leq \lfloor nx \rfloor\leq nx$$$x-\frac{1}{n}\leq F_{n}(x)\leq x$$According to the Squeeze theorem, $$\lim_{ n \to \infty } F_{n}(x)=x$$
##### Convergence in Probability
A sequence of random variables $X_1,X_2,\ldots$ converges in probability to a random variable $X$ (denoted as $X_n\xrightarrow{P}X)$ if, for every $\varepsilon>0$, the probability that the absolute difference between $X_n$ and $X$ is greater than $\varepsilon$ goes to zero as $n$ approaches infinity:$$P(|X_n-X|\geq\varepsilon)\to0\quad\mathrm{as}\quad n\to\infty$$**Example**: considering the constant random variable $\delta_{c}$: $P(X=c)=1$, and the normal distribution $N\left( c, \frac{1}{n^2} \right)$. According to Chebyshev's inequality, we have$$0<P(|X_{n}-c|\geq k\sigma)\leq\frac{1}{k^2}$$Because $\sigma=\frac{1}{n}$, let $k=n\varepsilon$.$$P(|X_{n}-c|\geq \varepsilon)\leq \frac{1}{n^2\varepsilon^2}$$when $n\to \infty$, $P(|X_{n}-c|\geq \varepsilon)\to0$
##### Convergence Almost Surely and Surely
Considering a probability space ($\Omega,\mathcal{F},P$),  a sequence of random variables $X_1,X_2,\ldots$ converges almost surely (denoted as $X_n\xrightarrow{a.s.}X)$ to a random variable $X$ if:$$P\left(\lim_{n\to\infty}X_n=X\right)=1$$That is, the sequence $X_n$ converges to $X$ with probability 1. If $$\lim_{ n \to \infty }X_{n}(\omega)=X(\omega),\quad \text{for all }\omega\in \Omega$$then $\{X_{n}\}_{n=1}^{\infty}$ surely converges to $X$.
#### Law of Large Number
Let $X_1,X_2,\ldots$ be a sequence of iid random variables. **The Weak Law of Large Numbers states** that for any $\epsilon>0$, the probability that the sample mean $\bar{X}_{n}$ deviates from the true mean $\mu$ by more than $\epsilon$ tends to zero as the sample size $n$ increases$$P\left(\left|\frac1n\sum_{i=1}^nX_i-\mu\right|\geq\epsilon\right)\to0\quad\mathrm{as}\quad n\to\infty $$In other words, the sample mean converges to the true mean $\mu$ **in probability** as $n\to\infty$.

**The Strong Law of Large Numbers** is a stronger version of the weak law. It states that,
under the same conditions, the sample mean $X_n$ converges to the expected value $\mu$ almost surely (with probability 1):$$P\left(\lim_{n\to\infty}\frac1n\sum_{i=1}^nX_i=\mu\right)=1$$For weak law, large deviations from $\mu$ may occur with small probability, but they never disappear completely. For strong law, large deviations from $\mu$ happen with probability 0 after a certain point.
### Stirling's approximation
While $n\to \infty$, the Stirling's approximation states that$$n!\approx n^ne^{-n}\sqrt{ 2\pi n }\quad\text{or}\quad\lim_{ n \to \infty } \frac{n!}{n^ne^{-n}\sqrt{ 2\pi n }} $$and we have the expansion$$n!=n^ne^{-n}\sqrt{ 2\pi n }\left(1+\frac{1}{12n}+\frac{1}{288n^2}-\frac{139}{51840n^3}-\cdots\right)$$this series does not converge. It's an **asymptotic series**. Unlike a **convergent series**, an asymptotic series doesn't necessarily converge to the function for large values of the parameter. Instead, it gives an increasingly accurate approximation for a sufficiently large value of the parameter, even though the series may not converge in the traditional sense. 
### Convolution
The generating function for $\{a_{n}\}_{n=0}^{\infty}$ is defined as$$G_{a}(s)=\sum_{n=0}^{\infty}a_{n}s^n$$where $s$ is any number that makes this series convergent. There are some types of generating functions. The **probability generating function** of a discrete random variable $X$ takes the form of a power series that generates the probabilities of the outcomes of $X$.$$G_X(s)=E[s^X]=\sum_{k=0}^\infty P(X=k)s^k$$If $X_{1},X_{2},\dots,X_{n}$ are independent and non-negative random variables, and $Y=\sum_{i=1}^nX_{i}$, we have:$$G_{Y}(s)=\prod_{i=1}^nG_{X_{i}}(s)$$which means the PDF of the sum of independent random variables is the convolution of each PDF. If $X$ is a continuous random variable, the the probability generating function is defined as$$G_{X}(s)=\int_{-\infty}^{\infty}s^x f(x)\mathrm{d}x$$The Moment Generating Function (MGF) of a random variable $X$ is defined as the expected
value of the exponential function of the random variable $X:$$$M_X(t)=E[e^{tX}]=\begin{cases}
\sum_{i=0}^{\infty}e^{tx_{i}}f(x_{i})\quad \text{discrete}\\
\int_{-\infty}^\infty e^{tx}f(x)dx\quad\text{continuous}
\end{cases}$$where $t$ is a real (or complex) parameter, and $X$ is a random variable. The function $M_X(t)$ is
typically a function of $t$,and it is used to generate the moments of $X.$
#### Properties of MGF
Let $\mu_{k}$ be the moment of a random variable, we have$$M_{X}(t)=1+\mu_{1}t+\frac{\mu_{2}t^2}{2!}+\dots=\sum_{n=0}^{\infty}\frac{\mu_{n}t^n}{n!}$$and we can see that$$\frac{\mathrm{d}^n}{\mathrm{d}t^n}M_{X}(0)=E(X^n)=\mu_{n} $$The linearity of MGF is given by$$M_{\alpha X+\beta}(t)=e^{\beta t}M_{X}(\alpha t)$$and MGF is unique for discrete random variables. However, you can not say that to continuous RV. There is different distribution with the same moments.
### Central Limit Theorem
#### Statement
Let $X_1,X_2,\ldots,X_n$ be a sequence of iid random variables with mean $\mu$ and variance $\sigma^2$, and let $S_n=X_1+X_2+\cdots+X_n$ be their sum. Then, the Central Limit Theorem states that as $n\to\infty$, the distribution of the normalized sum approaches the standard normal distribution:$$\frac{S_n-n\mu}{\sigma\sqrt{n}}\xrightarrow{d}N(0,1)$$and for continuous case, the distribution of **standardized sample mean** converges to the standard normal distribution$$\frac{\overline{X}_n-\mu}{\frac{\sigma}{\sqrt n}}\xrightarrow{d}N(0,1)$$Special case is for Poisson distribution with parameter $\lambda$, the sum converges to $N(\lambda,\lambda)$.