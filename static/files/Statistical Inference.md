# Properties of Random Samples
## Random Sampling
### Sampling Distribution and Statistic
Sampling distribution refers to the probability distribution of a statistic in repeated sampling. For large sample sizes, the sampling distribution of the sample mean approximately obeys a normal distribution. The standard deviation of the sampling distribution is called the **standard error (SE)**. 

Common sampling distribution:
1. If the population obeys a normal distribution $N(\mu,\sigma^2)$, then the mean value $\bar{X}$ of samples obeys a normal distribution $N(\mu,\frac{\sigma^2}{n})$. If the population distribution is unknown, but the sample size is large, according to the central limit theorem, $\bar{X}$ approximately obeys the normal distribution $N\left(\mu, \frac{S^2}{n} \right)$.
2. For large samples, sample proportion $\hat{p}$ obeys $N(p,\frac{p(1-p)}{n})$, where $p$ is the population proportion.
3. When the population standard deviation is unknown and the sample size is small, the normalized form of the sample mean obeys a t-distribution.
4. The normalized form of sample variance obeys a chi-square distribution
**Theorem:** Let $x_{1},x_{2},\dots,x_{n}$ to be a sample, $\bar{x}= \frac{x_{1}+x_{2}+\cdots+x_{n}}{n}$, then:$$\min\sum_{i=1}^n(x_i-a)^2=\sum_{i=1}^n(x_i-\overline{x})^2;$$and$$(n-1)s^2=\sum_{i=1}^n(x_i-\overline{x})^2=\sum_{i=1}^nx_i^2-n\overline{x}^2.$$Note that $n-1$ is the **Bessel's correction** to achieve the unbiased estimation. Statistic is said to be unbiased if its expected value is equal to the population parameters it estimates. When we take a sample from a population and calculate the sample variance, the sample mean is calculated based on the sample data. Since the sample mean itself is estimated from the sample data, it introduces a certain bias. Specifically, the sample mean makes the sample data points less discrete relative to the sample mean than they are relative to the population mean. Therefore, if n is used as the denominator to calculate the sample variance directly, it will lead to an underestimation of the population variance. 

It can also be understood in terms of degrees of freedom. When calculating the sample variance, we use the sample mean, which is equivalent to using one degree of freedom. Therefore, the remaining n−1 data points can be freely varied, while the nth data point is determined by the first n−1 data point and the sample mean. Thus, Bessel correction reflects the actual degrees of freedom available.

If $X_1,X_2,\ldots,X_n$ are independent and identically distributed (i.i.d.) random variables, each with moment generating function $M_X(t)$,then the moment generating function of the sample mean $\overline{X}$ is:$$M_{\overline{X}}(t)=\left[M_X\left(\frac tn\right)\right]^n$$This formula shows that the moment generating function of the sample mean is a transformation of the population moment generating function.
## Two Important Distributions
### Student's t-Distribution
The t-distribution is a continuous probability distribution commonly used for statistical inference
with small samples. :
$$f(t)=\frac{\Gamma\left(\frac{\nu+1}2\right)}{\sqrt{\nu\pi\Gamma\left(\frac\nu2\right)}}\left(1+\frac{t^2}\nu\right)^{-\frac{\nu+1}2}$$where $\nu$ is the degrees of freedom, and $\Gamma$ is the gamma function.

**Properties:**
1. Shape: The shape of the t-distribution is similar to the standard normal distribution but with thicker tails. As the degrees of freedom $\nu$ increase, the t-distribution approaches the standard normal distribution.
2. Mean and Variance: For t-distribution with degree of freedom $\nu$, only $\nu-1$ moments exist.
- When $\nu>1$,the mean of the t-distribution is 0.
- When $\nu>2$, the variance of the t-distribution is $\frac\nu{\nu-2}.$
### Snedecor F-Distribution
The F-distribution is a continuous probability distribution commonly used in hypothesis testing for
ANOVA and regression analysis. It is formed by the ratio of two independent chi-
squared distributions. The probability density function of the F-distribution is:$$f(x)=\frac{\Gamma\left(\frac{\nu_1+\nu_2}{2}\right)}{\Gamma\left(\frac{\nu_1}{2}\right)\Gamma\left(\frac{\nu_2}{2}\right)}\left(\frac{\nu_1}{\nu_2}\right)^{-\frac{\nu_1}{2}}x^{\frac{\nu_1}{2}-1}\left(1+\frac{\nu_1x}{\nu_2}\right)^{-\frac{\nu_1+\nu_2}{2}}$$where $\nu_1$ and $\nu_2$ are the degrees of freedom for the numerator and denominator, respectively.

**Properties:**
3. Shape: The shape of the F-distribution depends on the degrees of freedom $\nu_1$ and $\nu_2.$ lt is typically asymmetric and right-skewed.
4. Mean and Variance:
- When $\nu_2>2$,the mean of the F-distribution is $\frac{\nu_{2}}{\nu_{2}-2}.$
- When $\nu_2>4$,the variance of the F-distribution is $\frac{2\nu_2^2(\nu_1+\nu_2-2)}{\nu_1(\nu_2-2)^2(\nu_2-4)}$.
5. Let $X_{1},X_{2},\dots,X_{n}$ to be sampled from $N(\mu_{X},\sigma_{X}^2)$, and $Y_{1},Y_{2},\dots,Y_{m}$ to be sampled from $N(\mu_{Y},\sigma_{Y}^2)$, then the ratio to variance $F=\frac{S^2_{X}/\sigma^2_{X}}{S^2_{Y}/\sigma^2_{Y}}$ obeys the F-distribution with $\nu_{1}=n-1$ and $\nu_{2}=m-1$. 
## Delta Method
The Delta Method is a technique in statistics used to approximate the expectation and variance of
functions of random variables.It is based on Taylor expansion and uses linear approximation to handle the statistical properties of nonlinear functions. The Delta Method is particularly useful in deriving the asymptotic distribution of estimators, especially when dealing with complex functions
### Basic ldea
Suppose we have a random variable $X_n$ with expectation $\mu$ and variance $\sigma^2.$ We are interested in the expectation and variance of some function $g(X_n).$ The Delta Method uses Taylor expansion to linearly approximate $g(X_n)$, simplifying the calculations.
### Univariate Case
Assume $X_n$ is a sequence of random variables satisfying:$$\sqrt{n}(X_n-\mu)\xrightarrow{D}N(0,\sigma^2)$$This means $X_n$ converges in distribution to $\mu$, and the standardized $X_n$ converges in distribution
to a normal distribution. We want to estimate the distribution of $g(X_n)$, where $g$ is a differentiable function. Using Taylor expansion, $g(X_n)$ can be approximated near $\mu$ as: $$g(X_n)\approx g(\mu)+g'(\mu)(X_n-\mu)$$Using this approximation, we obtain:$$\sqrt{n}(g(X_n)-g(\mu))\approx g'(\mu)\sqrt{n}(X_n-\mu)$$Since $\sqrt{n}(X_n-\mu)\xrightarrow{D}N(0,\sigma^2)$, by the continuous mapping theorem, we have:$$\sqrt{n}(g(X_n)-g(\mu))\xrightarrow{D}N(0,[g'(\mu)]^2\sigma^2)$$
### Multivariate Case
Assume $X_n$ is a sequence of random vectors satisfying:$$\sqrt{n}(X_n-\mu)\xrightarrow{D}N(0,\Sigma)$$where $\mu$ is the mean vector and $\Sigma$ is the covariance matrix. Using Taylor expansion, $g(X_{n})$ can be approximated near $\mu$ as:$$g(X_n)\approx g(\mu)+\nabla g(\mu)^T(X_n-\mu)$$where $\nabla g(\mu)$ is the gradient vector of $g$ at $\mu.$ Using this approximation, we obtain:$$\sqrt{n}(g(X_n)-g(\mu))\approx\nabla g(\mu)^T\sqrt{n}(X_n-\mu)$$Since $\sqrt{n}(X_n-\mu)\xrightarrow{D}N(0,\Sigma)$,by the continuous mapping theorem, we have:
$$\sqrt{n}(g(X_n)-g(\mu))\xrightarrow{D}N(0,\nabla g(\mu)^T\Sigma\nabla g(\mu))$$
# Data Reduction
## Sufficient Principle
The principle of adequacy states that if two samples have the same conditional distribution given a certain statistic, then the two samples are equivalent when it comes to inferring parameters. In other words, the adequacy statistic contains all the parameter-related information in the sample.
### Sufficient Statistic
Let $X=(X_1,X_2,\ldots,X_n)$ be a random sample drawn from a family of distributions $\{P_\theta:\theta\in\Theta\}$
,and let $T(X)$ be a statistic. If the conditional distribution of the sample $X$ given $T(X)=t$ does
not depend on the parameter $\theta$, then $T(X)$ is called a sufficient statistic. Mathematically, this is expressed as:$$P_\theta(X=x|T(X)=t)$$does not depend on $\theta.$
### Factorization Theorem
The Factorization Theorem is a key tool for determining sufficient statistics. It states that a statistic $T(X)$ is sufficient if and only if the joint probability density function (or probability mass function) of the sample can be factorized into two parts:$$f_\theta(x)=g_\theta(T(x))\cdot h(x),$$where:
- $g_\theta(T(x))$ depends only on $\theta$ and $T(x);$
- $h(x)$ does not depend on $\theta.$
### Complete Statistic
The likelihood principle is a fundamental principle in statistics that states that in the case of a given data, all the information about the parameters is contained in the likelihood function. Specifically, the likelihood principle suggests that if two different experiments produce a proportional likelihood function, then their inferences about the parameters should be the same.
## Likelihood
The likelihood function $L(\theta|X)$ represents the probability of observing data $X$ under parameter $\theta$:$$L(\theta|X)=P(X|\theta)\quad(\mathrm{or}=f(X|\theta)\ \mathrm{for\ continous})$$Suppose we have two experiments generating data $X$ and $Y$, with likelihood functions $L_X(\theta)$ and
$L_Y(\theta)$, respectively.If there exists a constant $c$ such that:$$L_X(\theta)=c\cdot L_Y(\theta)$$then, according to the **Likelihood Principle**, inferences about the parameter $\theta$ based on $X$ and $Y$
should be identical. 
# Parameter Estimation
### Point Estimation
Parameter estimation is a core concept in statistics that aims to infer the value of a population parameter from sample data. Population parameters are numerical features that describe the distribution of a population, such as mean, variance, etc.

### Moment Estimation
For $k$ sample moment $\hat{\mu}_k=\frac{1}{n}\sum_{i=1}^nX_i^k$ as an estimator of $\mu_{k}$, moment estimator use sample moment to express the parameter:$$\mathrm{If:}\quad \theta=f(\mu_{1},\mu_{2},\dots, \mu_{k}),\quad \mathrm{then:}\quad \hat{\theta}=f(\hat{\mu_{1}},\hat{\mu_{2}},\dots,\hat{\mu_{k}})$$
### Maximum Likelihood Estimation (MLE)
Maximum likelihood estimation is a commonly used parameter estimation method that maximizes the likelihood function to find the parameter values that are most likely to produce the observational data. MLE states that$$\hat{\theta}=\arg\max_\theta L(\theta|X)$$Suppose we have a set of independent and identically distributed (i.i.d.) observations $X_1,X_2,\ldots,X_n$ drawn from a normal distribution $N(\mu,\sigma^2).$ The likelihood function is given by:
$$L(\mu,\sigma^2|X)=\prod_{i=1}^n\frac1{\sqrt{2\pi\sigma^2}}\exp\left(-\frac{(X_i-\mu)^2}{2\sigma^2}\right)$$By taking the derivative of the log-likelihood function and solving for the parameters, we can obtain the maximum likelihood estimates (MLE) for $\mu$ and $\sigma^2.$

To assess the accuracy of the maximum likelihood estimate, we can construct confidence intervals.
#### Confidence intervals based on normal approximations
For large samples, MLE estimators usually obey asymptotic normal distribution $\hat{\theta}\sim N\left(\theta,\frac{1}{I(\theta)}\right)$, where $I(\theta)$ is the **Fisher Information**:$$I(\hat{\theta})=-\mathbb{E}\left[\frac{\partial^2\log L(\theta|X)}{\partial\theta^2}\right].$$The Standard error is given by$$\mathrm{SE}(\hat{\theta})=\sqrt{ \frac{1}{I(\hat{\theta})} }$$the confidence interval is given by$$\hat{\theta}\pm z_{\alpha/2}\cdot\mathrm{SE}(\hat{\theta}),$$where $z_{\alpha/2}$ is the quantile of the standard normal distribution, corresponding to the confidence level $1-\alpha$.
#### Confidence intervals based on likelihood ratios
The Likelihood Ratio Test (LRT) can be used to construct confidence intervals. This method does not rely on a normal approximation and is suitable for small samples and non-normal distributions. The LRT statistic is:$$\Lambda(\theta)=-2\log\left(\frac{L(\theta|X)}{L(\hat{\theta}|X)}\right)$$For large samples, $\Lambda(\theta)$ approximately obeys the $\chi^2_{n-1}$ distribution. The confidence interval is $\theta$ such that$$\Lambda(\theta)\leq \chi^2_{1-\alpha,n-1}$$
### Bayesian Estimation
For Bayesian estimation, parameter $\alpha$ is considered as a random variables with prior distribution $f_{\Theta}(\theta)$, and for a given parameter $\Theta=\theta$, the population has distribution (likelihood function) $f_{X|\Theta}(x|\theta)$. Therefore, the joint distribution of $X,\Theta$ is given by$$f_{X,\Theta}(x,\theta)=f_{X|\Theta}(x|\theta)f_{\Theta}(\theta).$$Marginal likelihood of $X$ is given by$$f_X(x)=\int f_{X,\Theta}(x,\theta)\mathrm{d}\theta=\int f_{X|\Theta}(x|\theta)f_\Theta(\theta)\mathrm{d}\theta.$$Therefore, according to Bayes's theorem, **Posterior Distribution** of parameter is given by$$f_{\Theta|X}(\theta|x)=\frac{f_{X,\Theta}(x,\theta)}{f_{X}(x)}=\frac{f_{X|\Theta}(x|\theta)f_{\Theta}(\theta)}{\int f_{X|\Theta}(x|\theta)f_{\Theta}(\theta)\mathrm{d}\theta}$$
##### Conjugate Priority
If the combination of the prior distribution $P(\theta)$ and the likelihood function $P(X|\theta)$ results in a
posterior distribution $P(\theta|X)$ that belongs to the same family of distributions as the prior, then the
prior distribution is said to be a conjugate prior for the likelihood function.
1. **Binomial Likelihood & Beta Prior** 
    - **Likelihood:** $X \mid p \sim \text{Binomial}(n, p)$
    - **Prior:** $p \sim \text{Beta}(\alpha, \beta)$
    - **Posterior:** $p \mid X \sim \text{Beta}(\alpha + X, \beta + n - X)$
    
    The Beta distribution is a conjugate prior for the Binomial likelihood.
    
2. **Poisson Likelihood & Gamma Prior**
    
    - **Likelihood:** $X \mid \lambda \sim \text{Poisson}(\lambda)$
    - **Prior:** $\lambda \sim \text{Gamma}(\alpha, \beta)$
    - **Posterior:** $\lambda \mid X \sim \text{Gamma}(\alpha + X, \beta + 1)$
    
    The Gamma distribution is a conjugate prior for the Poisson likelihood.
3. **Gaussian Likelihood & Gaussian Prior (for Mean)**
    
    - **Likelihood:** $X \mid \mu \sim \mathcal{N}(\mu, \sigma^2)$
    - **Prior:** $\mu \sim \mathcal{N}(\mu_0, \tau_0^2)$
    - **Posterior:** $\mu \mid X \sim \mathcal{N}(\mu_n, \tau_n^2)$ (where $\mu_n, \tau_n^2$​ are updated parameters)
    
    The Gaussian distribution is a conjugate prior for the mean of a normal likelihood.
# Hypothesis Test
## Neyman-Pearson Paradigm
The Neyman-Pearson Paradigm provides the most powerful framework for hypothesis test.
### Basic Concepts
1. **Hypothesis**
- Null Hypothesis ($H_{0}$): No effects or difference.
- Alternative Hypothesis ($H_{1}$): There is difference or effects.
2. **Error Types**
- Type I Error: Incorrectly rejecting the null hypothesis, with probability $\alpha$.
- Type II Error: Incorrectly accepting the null hypothesis, with probability $\beta$.
3. **Significance Level**
- Maximum tolerance $\alpha$ of Type I.
4. **Power of the Test** 
- The probability of correctly rejecting the null hypothesis ($1-\beta$)
5. p-value:
- The probability of observing samples given null hypothesis: $P(X|H_{0})$. 
### Neyman-Pearson Lemma
The lemma states that the most powerful test of size $\alpha$ (i.e, the test that maximizes the probability of detecting $H_{1}:\ \theta=\theta_{1}$ while keeping the probability of falsely rejecting $H_0:\ \theta_{0}$ at most $\alpha$) is based on the likelihood ratio test$$\Lambda(x)=\frac{L(x|\theta_{1})}{L(x|\theta_{0})}$$Specifically, the optimal test rejects $H_{0}$ in favor of $H_{1}$ if:$$\Lambda(x)>\eta $$for some threshold $\eta$, which is chosen to ensure the test has the desired significance level $\alpha.$
### Duality Between Hypothesis Test and Confidence interval
The confidence interval is completely composed by $\theta$ such that makes null hypothesis $H_{0}:\ \theta=\theta_{0}$ be accepted. Otherwise, if $\theta_{0}$ is not in confidence interval, then $H_{1}$ is accepted.
## Parametric Test
### t-Test
A **t-test** is used to determine whether there is a significant difference between:
1. **One sample and a known population mean** (one-sample t-test)
2. **Two independent samples** (independent two-sample t-test)
3. **Two related samples (paired data)** (paired t-test)
It is particularly useful when the **sample size is small** ($n < 30$) and the population variance is **unknown**.

**Assumptions:**
- The data is **normally distributed** (or approximately normal for large samples).
- The sample observations are **independent**.
- For two-sample t-tests, the two populations have **equal or unequal variances** (separate test types).
#### One-Sample t-Test
Tests whether the mean of a sample is significantly different from a known population mean $\mu_0$.
**Hypotheses:**
- $H_0: \mu = \mu _0$ (sample mean equals population mean)
- $H_1: \mu \neq \mu _0$ (sample mean differs from population mean)
**Test Statistic:**$$t=\frac{\bar{X}-\mu_0}{s/\sqrt{n}}$$**Degrees of Freedom (df):** $n - 1$.
#### Two-Sample t-Test
Tests whether the means of two independent samples are significantly different.
**Hypotheses:**
- $H_0: \mu _1= \mu _2$ (no difference in means)
- $H_1: \mu _1\neq \mu _2$ (difference in means)
**Test Statistic (Equal Variance Case, Pooled t-Test):**$$t=\frac{\bar{X}_1-\bar{X}_2}{s_p\sqrt{\frac1{n_1}+\frac1{n_2}}}$$where:$$s_p^2=\frac{(n_1-1)s_1^2+(n_2-1)s_2^2}{n_1+n_2-2}$$is the pooled variance.
**Degrees of Freedom (df)**: $n_1+n_2-2.$
For unequal variances (**Welch’s t-test**), the formula adjusts the denominator of $t$ to $\sqrt{\frac{s_{1}^2}{n_{1}} + \frac{s_{2}^2}{n_{2}}}$ with degree of freedom $df=(\frac{S_1^2}{n_1}+\frac{S_2^2}{n_2})^2/(\frac{S_1^4}{n_1^2(n_1-1)}+\frac{S_2^4}{n_2^2(n_2-1)})$.
#### Paired t-Test
Tests the difference between two dependent (paired) samples, such as pre-test and post-test scores.
**Hypotheses:**
- $H_0: \mu _D= 0$ (mean of differences is zero)
- $H_1: \mu _D\neq 0$ (mean of differences is not zero)
**Test Statistic:**$$t=\frac{\bar{D}}{s_D/\sqrt{n}}$$where:
- $\bar{D} =$mean of the differences,
- $s_D=$standard deviation of differences,
- $n=$number of pairs.
**Degree of freedom:** $df=n-1$.
#### Decision Rule
Compare the computed $t$ -statistic with the critical value from the t-distribution at a chosen significance level $\alpha$.
- If $|t|>t_\alpha,df$, reject $H_0.$
- If $|t|\leq t_\alpha,df$,fail to reject $H_0.$
### F-Test
An **F-test** is used to compare the variances of two populations or test the overall significance in regression models.
#### Variance Comparison Test (Two-Sample F-Test)
Tests whether two populations have equal variances.
**Hypotheses:**
- $H_0: \sigma _1^2= \sigma _2^2$ (equal variances)
- $H_1: \sigma _1^2\neq \sigma _2^2$ (unequal variances)
**Test Statistic:**$$F=\frac{s_1^2}{s_2^2}$$where:
- $s_1^2$ and $s_2^2$ are sample variances,
- By convention, $s_1^2>s_2^2$,so $F\geq1.$
**Degrees of Freedom:**$$df_1=n_1-1,\quad df_2=n_2-1.$$**Decision Rule:** Compare $F$ with the critical value $F_{\alpha,df_1,df_2}$ from the F-distribution.
#### Applications
Also used in ANOVA and Regression analysis.
### Generalized LRT
The **generalized likelihood ratio test (GLRT)** is an extension of the Neyman-Pearson lemma to cases where the alternative hypothesis $H_1$​ or the null hypothesis $H_0$ (or both) are **composite hypotheses** (i.e., they contain a range of parameter values rather than a single fixed value).

The test is based on comparing the **maximum likelihood estimates (MLEs)** under $H_0$​ and $H_1$​. **Generalized likelihood ratio** is given by$$\Lambda^*=\frac{\sup_{\theta \in\Theta_{0}}L(\theta|X)}{\sup_{\theta \in\Theta}L(\theta|X)}$$where $H_{0}:\ \theta\in\Theta_{0}$, $H_{1}:\ \theta\in\Theta_{1}$, and $\Theta=\Theta_{0}\cup\Theta_{1}$. To reject $H_{0}$ if$$-2\log\Lambda^*>c$$where c is a critical value determined from the $\chi^2$ distribution with degrees of freedom equal to the difference in the number of free parameters in $H_0$ and $H_1$​.
### Pearson's chi-square test
Chi-square test is a statistical test used to determine whether there is a significant association between two categorical variables or whether observed data fits an expected distribution. The test statistic is:$$\chi^2=\sum\frac{(O_i-E_i)^2}{E_i}$$where $O$ is the observed data, and $E$ is expected data. For a table with $r$ rows and $c$ columns, the degrees of freedom for the chi-square test of independence is:$$df=(r-1)(c-1).$$For a goodness-of-fit test with $k$ categories and $m$ estimated parameters, the degrees of freedom is:$$df=k-1-m.$$Reject $H_{0}$ if$$\chi^2>\chi^2_{\alpha,df}$$
# Generalized Linear Model
## Exponential Family of Distribution
### Definition
A distribution belongs to the exponential family of distribution if it can be written as$$f(y;\theta)=s(y)t(\theta)e^{ a(y)b(\theta) }$$where $a,b,s,t$ are known functions. It can also be written as $$f(y;\theta)=\exp\big(a(y)b(\theta)+c(\theta)+d(y)\big).$$The distribution is said to be canonical (standard) if $a(y)=y$. Common distributions of exponential family are Poisson distribution, Normal distribution, and Binomial distribution.
### Properties
$a(y)$ is a sufficient statistic for $\theta$. The likelihood function depends on $y$ **only** through $a(y)$.

According to the truth that $\int f(y;\theta)\mathrm{d}y=1$, we know $\int \frac{\mathrm{d}f(y;\theta)}{\mathrm{d}\theta}\mathrm{d}y=0$ and $\frac{\mathrm{d}f(y;\theta)}{\mathrm{d}\theta}=[a(y)b'(\theta)+c'(\theta)]f(y;\theta).$ Then we know:$$\int[a(y)b'(\theta)+c'(\theta)]f(y;\theta)\mathrm{d}y=b'(\theta)\mathrm{E}\big( a(y) \big)+c'(\theta)=0$$Therefore, we know $$\mathrm{E}\big( a(Y) \big)=-\frac{c'(\theta)}{b'(\theta)}$$Similarly, take the truth that $$\int\frac{\mathrm{d}^2f(y;\theta)}{\mathrm{d}\theta^2}\mathrm{d}y=b^{\prime\prime}(\theta)\mathrm{E}[a(Y)]+c^{\prime\prime}(\theta)+[b^{\prime}(\theta)]^2\mathrm{var}[a(Y)]=0$$we know$$\mathrm{var}[a(Y)]=\frac{b^{\prime\prime}(\theta)c^{\prime}(\theta)-c^{\prime\prime}(\theta)b^{\prime}(\theta)}{[b^{\prime}(\theta)]^3}.$$The log-likelihood function is simply$$l(\theta;y)=a(y)b(\theta)+c(\theta)+d(y).$$The **score statistic** is given by $$U(\theta;y)=\frac{\mathrm{d}l(\theta;y)}{\mathrm{d}\theta}=a(y)b^{\prime}(\theta)+c^{\prime}(\theta).$$The MLEs of $\theta$ is given by solving $U(\hat{\theta})=0$. Regrading it as a random variable, its expectation is$$\mathrm{E}(U)=b^{\prime}(\theta)\mathrm{E}[a(Y)]+c^{\prime}(\theta)=0.$$The variance of $U$ is called the **Fisher information** ($I(\theta)$)  and denoted by $\mathfrak{I}=var(U)=-E(U')$.
## Generalized Linear Models
### Definition
For a set of random response variables $Y_{1},Y_{2},\dots,Y_{N}$ and explanatory variables $X_{1},X_{2},\dots,X_{n}$, a **generalized linear model (GLM)** is an extension of linear regression that allows for **response variables** from the **exponential family of distributions**. Thus, the distribution of each $Y_i$ has the canonical and same form. Then the joint density function of $Y_i$ is given by$$\begin{aligned}f(y_{1},\ldots,y_{N};\theta_{1},\ldots,\theta_{N})&=\prod_{i=1}^N\exp\big(y_ib(\theta_i)+c(\theta_i)+d(y_i)\big)\\&\begin{aligned}=\exp\left(\sum_{i=1}^Ny_ib(\theta_i)+\sum_{i=1}^Nc(\theta_i)+\sum_{i=1}^Nd(y_i)\right)\end{aligned}\end{aligned}$$Then a monotone, differentiable **link function** $g(\cdot)$ is estimated to transfer the expectation of $Y$ to the linear predictor:$$g\big( \mathrm{E}(Y) \big)=X^T\beta$$
### Parameter Estimation: MLEs for Exponential Family
Recall that for each $Y_{i}$ the log-likelihood function is$$l_i=y_ib(\theta_i)+c(\theta_i)+d(y_i),$$and for all $i$, we have$$l=\sum_{i=1}^Nl_i=\sum y_ib(\theta_i)+\sum c(\theta_i)+\sum d(y_i).$$To obtain the maximum likelihood estimator for the parameter $\beta_{j}$ we need$$\frac{\partial l}{\partial\beta_j}=U_j=\sum_{i=1}^N\left[\frac{\partial l_i}{\partial\beta_j}\right]=\sum_{i=1}^N\left[\frac{\partial l_i}{\partial\theta_i}.\frac{\partial\theta_i}{\partial\mu_i}.\frac{\partial\mu_i}{\partial\beta_j}\right].$$Consider each term respectively. First, $$\frac{\partial l_i}{\partial\theta_i}=y_ib^{\prime}(\theta_i)+c^{\prime}(\theta_i)=b^{\prime}(\theta_i)(y_i-\mu_i).$$Second,$$\frac{\partial\mu_i}{\partial\theta_i}=\frac{-c^{\prime\prime}(\theta_i)}{b^{\prime}(\theta_i)}+\frac{c^{\prime}(\theta_i)b^{\prime\prime}(\theta_i)}{\left[b^{\prime}(\theta_i)\right]^2}=b^{\prime}(\theta_i)\mathrm{var}(Y_i)$$Third, $$\frac{\partial\mu_i}{\partial\beta_j}=\frac{\partial\mu_i}{\partial\eta_i}.\frac{\partial\eta_i}{\partial\beta_j}=\frac{\partial\mu_i}{\partial\eta_i}x_{ij.}$$Hence the score is given by$$U_j=\sum_{i=1}^N\left[\frac{(y_i-\mu_i)}{\mathrm{var}(Y_i)}x_{ij}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)\right].$$The information matrix $\mathfrak{I}$ has terms$$\begin{aligned}\mathfrak{J}_{jk}&=\operatorname{E}\left\{\sum_{i=1}^{N}\left[\frac{(Y_{i}-\mu_{i})}{\operatorname{var}(Y_{i})}x_{ij}\left(\frac{\partial\mu_{i}}{\partial\eta_{i}}\right)\right]\sum_{l=1}^{N}\left[\frac{(Y_{l}-\mu_{l})}{\operatorname{var}(Y_{l})}x_{lk}\left(\frac{\partial\mu_{l}}{\partial\eta_{l}}\right)\right]\right\}\\&=\sum_{i=1}^N\frac{\operatorname{E}\left[(Y_i-\mu_i)^2\right]x_{ij}x_{ik}}{\left[\operatorname{var}(Y_i)\right]^2}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)^2\end{aligned}$$Because $Y_{i}$ and $Y_{l}$ are independent for $i\neq l$, so the covariance is 0 for them. Then equation above can be simplified as$$\mathfrak{I}_{jk}=\sum_{i=1}^N\frac{x_{ij}x_{ik}}{\operatorname{var}(Y_i)}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)^2.$$Using **Newton-Raphson** iteration, the iterative estimating equation is$$\mathrm{b}^{(m)}=\mathrm{b}^{(m-1)}+\left[\mathfrak{I}^{(m-1)}\right]^{-1}\mathrm{U}^{(m-1)},$$where $b=[\beta_{i}]$. Let $W$ to be a diagonal matrix with elements$$w_{ii}=\frac{1}{\mathrm{var}(Y_i)}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)^2,$$$\mathfrak{I}$ can be written as:$$\mathfrak{I}=X^TWX.$$RHS can be written as a vector$$\sum_{k=1}^p\sum_{i=1}^N\frac{x_{ij}x_{ik}}{\mathrm{var}(Y_i)}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)^2b_k^{(m-1)}+\sum_{i=1}^N\frac{(y_i-\mu_i)x_{ij}}{\mathrm{var}(Y_i)}\left(\frac{\partial\mu_i}{\partial\eta_i}\right)=X^TW\mathbf{z}$$where $$\mathbf{z}=z_i=\sum_{k=1}^px_{ik}b_k^{(m-1)}+(y_i-\mu_i)\left(\frac{\partial\eta_i}{\partial\mu_i}\right)$$Hence the normal equation is given by$$\mathrm{X}^T\mathrm{WXb}^{(m)}=\mathrm{X}^T\mathrm{Wz}.$$It's the same with the normal equation derived by Least Squared Method.
# Normal GLM (Linear Regression)
## Basic Results
### Definition
The best known special case of a generalized linear model is the model$$\mathrm{E}(Y_i)=\mu_i=\mathrm{x}_i^T\beta+e;\quad Y_i\sim\mathrm{N}(\mu_i,\sigma^2),$$it can be written as:$$y=X\beta+e$$where $e$ are independent identically distributed random variables with $e_{i}\sim N(0,\sigma^2)$.
### Estimation
The maximum likelihood estimator of $\beta$ is given by$$\mathbf{b}=\left(\mathbf{X}^T\mathbf{X}\right)^{-1}\mathbf{X}^T\mathbf{y},$$which is quite similar to least square estimation. If $\mathrm{E}(y) =X\beta$ and $\mathrm{E}[(y-X\beta)(y-X\beta)^T]=V$, where $V$ is known, we can obtain the least squares estimator $\widetilde{\beta}$ of $\beta$ without making any further assumptions about the distribution of y. We minimize$$S_w=(\mathbf{y}-\mathbf{X}\beta)^T\mathbf{V}^{-1}(\mathbf{y}-\mathbf{X})\beta.$$The solution of$$\frac{\partial S_w}{\partial\beta}=-2\mathbf{X}^T\mathbf{V}^{-1}(\mathbf{y}-\mathbf{X}\beta)=0$$is$$\widetilde{\beta}=(\mathbf{X}^T\mathbf{V}^{-1}\mathbf{X})^{-1}\mathbf{X}^T\mathbf{V}^{-1}\mathbf{y},$$provided the matrix inverses exist. In particular, if $\mathbf{y}$ are independent and have a common variance then$$\widetilde{\beta}=(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}.$$So in this case, maximum likelihood estimators and least squares estimators are the same.
### Deviance
Deviance is a measure of how well a model fits the data. It is based on the log-likelihood of the model:$$D=-2\left(\log L(\hat{\beta}_\mathrm{full})-\log L(\hat{\beta}_\mathrm{reduced})\right)$$For normal models:
- The full model is the one including all predictors.
- The reduced model is a nested version with fewer predictors.
Using the normal log-likelihood:$$L(\beta)=-\frac n2\log(2\pi\sigma^2)-\frac1{2\sigma^2}(Y-X\beta)^T(Y-X\beta)$$the deviance simplifies to:$$D=n\log\left(\frac{\mathrm{RSS}_{\mathrm{reduced}}}{\mathrm{RSS}_{\mathrm{full}}}\right)$$where $\mathrm{RSS}=(Y-X\hat{\beta})^T(Y-X\hat{\beta})$ is the **residual sum of squares**.
### Hypothesis Testing
#### Tests for Regression Coefficients
For testing whether a specific coefficient $\beta_j=0,\ 10\leq j\leq p$ with $n$ samples, the null hypothesis is:$$H_0:\beta_j=0\quad\text{vs.}\quad H_1:\beta_j\neq0$$The test statistic follows a t-distribution$$t=\frac{\hat{\beta}_j}{\mathrm{SE}(\hat{\beta}_j)}\sim t_{n-p}$$where:
- $\hat{\beta } _j$ is the least squares estimate of $\beta_j$,
- $\mathrm{SE}(\hat{\beta}_j)=\sigma\sqrt{(X^TX)_{jj}^{-1}}$ is the standard error.
If $|t|>t_{\alpha/2,n-p}$, we reject $H_0.$
#### F-Test for Overall Model Fit
To test whether at least one predictor is significant:$$H_0:\beta_1=\beta_2=\cdots=\beta_p=0\quad\mathrm{vs.}\quad H_1:\text{at least one }\beta_j\neq0$$The test statistic is:$$F=\frac{(\mathrm{RSS}_\text{reduced }-\mathrm{RSS}_\text{full})/p}{\mathrm{RSS}_\text{full}/(n-p)}$$which follows an $F_{p,n-p}$ distribution. If $F>F_{\alpha,p,n-p}$, reject $H_0.$

### Diagnostic
- Leverage $(h_i)$: Measures the influence of $X_i$ on $\hat{Y}_i.$ High leverage points have $h_i>2p/n$
- Cook's Distance $(D_i)$: Measures the impact of a point on regression coefficients:$$D_i=\frac{e_i^2}{p\hat{\sigma}^2}\cdot\frac{h_i}{(1-h_i)^2}$$If $D_i>1$, the observation is influential.
- Variance Inflation Factor (VIF): Detects multi-col-linearity:$$\mathrm{VIF}_j=\frac1{1-R_j^2}$$where $R_j^2$ is the $R^2$ from regressing $X_j$ on the other predictors.
- Durbin-Watson (DW test): For time-series data, it's used for test the auto-correlation of residuals.The statistic:$$DW=\frac{\sum_{i=2}^n\left(e_i-e_{i-1}\right)^2}{\sum_{i=1}^n\left(e_i-\bar{e}\right)^2}$$$DW\approx 2$ then residual and independent variables are independent.
## Analysis of Variance
### Definition
**Analysis of Variance (ANOVA)** is a statistical method used to compare **means across multiple groups**. It generalizes the **t-test** to more than two groups and determines whether group differences are statistically significant.

For $k$ groups with means $\mu_1,\mu_2,...,\mu_k$, ANOVA tests:
-  Null Hypothesis: $H_0:\mu_1=\mu_2=\cdots=\mu_k$ (All groups have the same mean)
- Alternative Hypothesis: $H_1:$ At least one mean is different.

**Assumption:**
- **Independence**: Observations are independent within and across groups.
- **Normality**: Residuals follow a normal distribution.
- **Homogeneity of Variance**: All groups have equal variance (checked with Levene’s Test).
### One-way ANOVA
#### Model
For a one-factor experiment with $k$ groups and $n_{i}$ times replications for group $i$ generating $N$ samples, a one-way ANOVA model can be written as:$$Y_{ij}=\mu+\alpha_i+\epsilon_{ij},$$where 
- $Y_{ij}$​ is the response variable for replication $j$ in group $i$,
- $\mu$ is the overall mean,
- $\alpha_i$​ is the effect of group $i$,
- $\epsilon_{ij}$ is the random error.
#### Variance Decomposition
The total deviance can be decomposed into 3 parts.
- Deviance between all data and overall mean:$$SST=\sum_{i=1}^k\sum_{j=1}^{n_{i}}(Y_{ij}-\bar{Y})^2$$
- Deviance between the total mean and the mean for each group:$$SSB=\sum_{i=1}^kn_i(\bar{Y}_i-\bar{Y})^2$$
- Deviance between data in each group and their mean:$$SSW=\sum_{i=1}^k\sum_{j=1}^{n_i}(Y_{ij}-\bar{Y}_i)^2$$
such that $SST=SSB+SSW$. 
#### F Statistic
- Mean Square Between groups ($df=k-1$):$$MSB=\frac{SSB}{k-1}$$
- Mean Square Within groups ($df=N-k$):$$MSW=\frac{SSW}{N-k}$$
- F Statistic:$$F=\frac{MSB}{MSW}\sim F_{k-1,N-k}$$
If $F>F_{\alpha;k-1,N-k}$, reject $H_{0}$.
### Two-way ANOVA
#### Model
For a experiment with more than two factors, two-way ANOVA is applied to determine the effects of each factor and their interaction. Model is given by$$Y_{ijk}=\mu+\alpha_i+\beta_j+(\alpha\beta)_{ij}+\epsilon_{ijk}$$
#### Variance Decomposition
For example, consider a two-factor experiment with $a$ groups for factor $A$ and $b$ groups for factor $B$, the decomposition is given by$$SST=SSA+SSB+SSAB+SSE$$where $SSA,\ SSB,$ and $SSAB$ are calculated similarly as $SSB$ in one-way ANOVA. Statistic is given by$$F_{A}=\frac{MSA}{MSE},\quad F_{B}=\frac{MSB}{MSE},\ (\text{main effect})\quad F_{AB}=\frac{MSAB}{MSE}\ (\text{interactive effect})$$with degree of freedom$df_A=a-1,df_B=b-1,df_{AB}=(a-1)(b-1),df_E=N-ab$.
# Binomial GLM (Logistic Regression)
## Probability Distribution
Consider $n$ Bernoulli random variables $Z_{i}\sim \mathrm{B}(\pi_{i})$, their joint probability is$$\prod_{j=1}^n\pi_j^{z_j}(1-\pi_j)^{1-z_j}=\exp\left[\sum_{j=1}^nz_j\log\left(\frac{\pi_j}{1-\pi_j}\right)+\sum_{j=1}^n\log(1-\pi_j)\right].$$which is a member of the exponential family. We can define that$$Y=\sum_{j=1}^nZ_j$$which is a binomial random variable $\mathrm{P}(Y=y)=\begin{pmatrix}n\\y\end{pmatrix}\pi^y(1-\pi)^{n-y},\quad y=0,1,\ldots,n$ if $\pi_{j}$ are **equal**. Finally, we consider the general case of $N$ independent random variables $Y_1,Y_2,\ldots,Y_N$ corresponding to the numbers of successes in $N$ different subgroups. If $Y_i\sim \mathrm{Bino}(n_i,\pi_i)$, the log-likelihood function:$$\begin{aligned}&l(\pi_1,\ldots,\pi_N;y_1,\ldots,y_N)\\&=\sum_{i=1}^N\left[y_i\ln\left(\frac{\pi_i}{1-\pi_i}\right)+n_i\ln(1-\pi_i)+\ln\left(\frac{n_i}{y_i}\right)\right].\end{aligned}$$
## Logistic Regression
For a discrete response variables $Y_{i}$, the model is given by$$g(\mu)=\ln \frac{\mu}{1-\mu}=X^T\beta+e$$where $Y_{i}$ obeys the binomial distribution. 
# Poisson Regression
If $Y_{i}\sim \mathrm{Pois}(\lambda)$, the model is given by$$g(\mu)=\ln\lambda=X^T\beta+e$$