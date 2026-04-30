# Introduction to Survival Analysis
## Basic concepts
### Survival Time, Event, and Censoring
**Survival time** is the outcome variable of survival analysis, which represents the time until an event occur on an individual. **Event** is an observed occurrence of the outcome of interest (e.g., death)， denoted as $\delta=1$. If we don't know survival time exactly due to study **ends with no event**, **lost of follow-up**, or **withdraw**, we would consider **censoring**, denoted as $\delta=0$. Censoring with unknown event occurrence names right-censoring, while data can also be left-censored (e.g., follow-up of a HIV patient must begin with positive test outcome, but infection started before testing). 
### Survivor Function and Hazard Function
Let $P(T>t)$ be the probability of event from time point $t$ to infinity. The **survivor function** $S(t)$ gives the probability of a person survives longer than a specific time $t$, which is defined as$$S(t)=P(T>t).$$Theoretically, $S(t)$ is nonincreasing, and $S(0)=1$, $\lim_{ t \to \infty }S(t)=0$. In practice, we usually obtain graphs that are step functions.

**Hazard function** $h(t)$ gives the instantaneous rate at which the event occurs at time $t$, given survival up to $t$:$$h(t)=\lim_{\Delta t\to0}\frac{P(t\leq T<t+\Delta t\mid T\geq t)}{\Delta t}.$$Sometimes, it's also called **conditional failure rate**. It's a measure of instantaneous potential, whereas $S(t)$ is a cumulative measure over time. Generally, we can see the following relationship: $$\begin{align}
S(t)&=-\exp\left[\int_{0}^{t}h(u)\mathrm{d}u\right] \\
h(t)&=-\left[\frac{\mathrm{d}S(t)/\mathrm{d}t}{S(t)} \right]
\end{align}$$
### Goals of Survival Analysis
1. To estimate and interpret survivor and hazard functions from survival data.
2. To compare survivor and hazard functions.
3. To assess the relationship of explanatory variables to survival time.
# Kaplan-Meier Survival Curves and Log-Rank Test
## Kaplan-Meier Survival Curves
### Definition and Property
The Kaplan–Meier (KM) estimator is a non-parametric estimate of the survivor function where data is right-censored. 

Let observed times be $t_1 < t_2 < \dots < t_k$​ - ordered distinct event times excluding censored observations. At each time $t_{j}$, let $d_{j}$ be the number of events and $n_{j}$ be the number of individuals at risk just before. The Kaplan–Meier estimator of the survivor function is given by:$$\begin{align}
\hat{S}(t_{j})&=\hat{S}(t_{j-1})\times \hat{P}(T>t_{j}|T\geq t_{j})\\&=\prod_{i=1}^{j}\hat{P}(T>t_{i}|T\geq t_{i})\\&=\prod_{t_{j}<t}\left( 1-\frac{d_{j}}{n_{j}} \right)
\end{align}$$where $d_j$ and $n_j$ is the number of events and individuals in risk set at time $j$. KM curve has the following properties.
- It's a step function that changes only at event times, and remain constant between events.
- $\hat{S}(0)=1$.
- Monotonically decreasing.
- Censored observations do **not** cause vertical drops, but adjust the risk set size $n_j$.
In fact, the KM estimator is a maximum likelihood estimation of the discrete hazard function.  
### Greenwood's formula
As an estimator, the variance of KM method is given by the Greenwood's formula.$$\widehat{\mathrm{Var}}[\hat{S}(t)]=\hat{S}(t)^2\sum_{t_j\leq t}\frac{d_j}{n_j(n_j-d_j)}.$$Thus the confidence interval is$$\hat{S}(t)\pm z_{\alpha/2}\cdot\sqrt{\widehat{\mathrm{Var}}[\hat{S}(t)]}.$$
## Log-Rank Test
The Log-Rank Test is a non-parametric hypothesis test used to compare two or more survival distributions. It tests whether there is a statistically significant difference between survival curves of different groups. That is:$$\begin{align}
&H_{0}: \text{The survival functions of the groups are identical }(S_{1}(t)=S_{2}(t),\text{ for all }t) \\
&H_{1}: \text{The survival functions differ }(S_{1}(t)\neq S_{2}(t), \text{for some } t)
\end{align}$$Under $H_0$, the expected number of events in group $i$ on time $j$ is$$E_{ij}=\frac{n_{ij}}{n_{j}}d_j,$$where $n_{j}=\sum n_{ij}$, the total number of survived individuals on time $j$, and $d_{j}=\sum d_{ij}$, the total number of events on time $j$. And the variance of $d_{ij}$ under $H_0$ is$$V_{ij}=\frac{n_{ij}(n_j-n_{ij})d_j(n_j-d_j)}{n_j^2(n_j-1)}.$$Also, we know the observed amount of events is $$O_{i}=\sum d_{ij},$$then the the Chi-squared test can be apply:$$\chi^2=\frac{(O_i-E_i)^2}{V_i}\sim\chi_1^2.$$f there are $g > 2$ groups, construct $g - 1$ degrees of freedom test:$$\chi^2=(\mathbf{O}-\mathbf{E})^\top\mathbf{V}^{-1}(\mathbf{O}-\mathbf{E})\sim\chi_{g-1}^2.$$where $\mathbf{V}$ is the covariance matric.

### Assumptions of Log-Rank Test
- Censoring is **non-informative** and **independent of group**
- Hazard functions are **proportional over time** (like in Cox model)
- Groups are **mutually exclusive**

## Alternatives to the Log-Rank Test
All these tests are based on the general idea:$$Z=\frac{\sum_jw_j(d_{1j}-E_{1j})}{\sqrt{\sum_jw_j^2V_{1j}}}$$where $w_j$ is the weight on time $j$, and its choice is the only difference between these tests.
### Wilcoxon–Breslow–Gehan Test
- **Weight**: $w_j = n_j$​ (number at risk at time $t_j$​)
- **Emphasis**: **Early** events receive more weight.
- **Pros**: More sensitive to early survival differences.
- **Cons**: Less powerful when hazards are proportional and constant over time.
### Tarone–Ware Test
- **Weight**: $w_j = \sqrt{n_j}$    
- **Emphasis**: Intermediate between Log-Rank (constant weight) and Wilcoxon (linear weight)
- **Use case**: When we suspect non-proportional hazards and want moderate sensitivity to early and late differences.
### Peto–Peto (Modified Wilcoxon) Test

- **Weight**: Based on estimated survival probability $\hat{S}(t_j)$ using **KM estimate** from pooled data:$$w_j = \hat{S}(t_j)$$
- **Emphasis**: Downweights later time points more **gradually** than Wilcoxon.
- **Advantage**: More robust under non-proportional hazards and **informative censoring**.
### Fleming–Harrington Test $G^{\rho,\gamma}$
- **Weight**:$$w_j = \hat{S}(t_j)^\rho (1 - \hat{S}(t_j))^\gamma$$where $\hat{S}(t_j)$ is KM estimate at time $t_j$.
- **Tunable Parameters**:
    - $\rho > 0$: more weight to **early** time points
    - $\gamma > 0$: more weight to **late** time points
- **Common choices**:
    - $(\rho=1, \gamma=0)$: Wilcoxon-type
    - $(\rho=0, \gamma=0)$: Log-rank
    - $(\rho=1, \gamma=1)$: sensitive to **middle-range** differences
- **Strength**: Highly flexible for detecting **non-proportional hazards**.
# Cox Proportional Hazard Model
## Cox PH Model
Let $T$ be the survival time and $\boldsymbol{X} = (X_1, X_2, \dots, X_p) \in \mathbb{R}^p$ be a vector of covariates. The Cox model specifies the hazard function as:$$h(t\mid X)=h_0(t)\exp(\beta^T X)$$where $h(t\mid X)$ is the hazard at time $t$ given covariates $X$, and $h(t)$ is the baseline hazard function. 

Key assumption:
- The **hazard ratio** between two individuals is constant over time:$$\frac{h(t\mid\boldsymbol{X}_1)}{h(t\mid\boldsymbol{X}_2)}=\exp\left(\boldsymbol{\beta}^T(\boldsymbol{X}_1-\boldsymbol{X}_2)\right)$$Therefore no interaction between time or covariates.
- Log-hazard is a linear function of covariates:$$\ln h(t\mid X)=\ln h_{0}(t)+\beta^T$$
### Estimation of Cox Model by Partial Likelihood
The **partial likelihood** focuses **only on the relative risk** between individuals **at each event time**, and **not** on the full probability distribution of $T$. $$L(\boldsymbol{\beta})=\prod_{j=1}^D\frac{\exp(\boldsymbol{\beta}^T\boldsymbol{X}_{(j)})}{\sum_{i\in\mathcal{R}(t_j)}\exp(\boldsymbol{\beta}^T\boldsymbol{X}_i)}$$And the log-partial likelihood is:$$\ell(\boldsymbol{\beta})=\sum_{j=1}^D\left[\boldsymbol{\beta}^T\boldsymbol{X}_{(j)}-\log\left(\sum_{i\in\mathcal{R}(t_j)}\exp(\boldsymbol{\beta}^T\boldsymbol{X}_i)\right)\right]$$By maximizing $\ell(\boldsymbol{\beta})$, coefficients $\beta$ can be estimated. After that, we can estimate the **baseline cumulative hazard** by **Breslow estimator**:$$\hat{H}_0(t)=\sum_{t_j\leq t}\frac{1}{\sum_{i\in\mathcal{R}(t_j)}\exp(\hat{\boldsymbol{\beta}}^T\boldsymbol{X}_i)},$$then adjusted survival function is given by$$\hat{S}(t\mid\boldsymbol{X})=\exp\left(-\hat{H}_0(t)\cdot\exp(\hat{\boldsymbol{\beta}}^T\boldsymbol{X})\right).$$
### Evaluating the Proportional Hazards Assumption
If the assumption that hazard ratio is constant fails, estimates from the Cox model can be misleading. 
#### Graphical Approach
For **each group** or covariate level, do the following plot:$$\log\left(-\log\hat{S}(t\mid\mathrm{group})\right)\mathrm{~vs.~}\log(t),$$where $\hat{S}$ is KM estimator. Under PH assumption, these curves should be **roughly parallel**.

#### Goodness-of-Fit Test
It's also called Grambsch–Therneau Test or Schoenfeld Test. The Schoenfeld residual for covariate $X_{k}$ is defined as$$r_{kj}=x_{ik}-\bar{x}_k(t_j)$$where $x_{ik}$ is the observed covariate value of subject who fails at $t_{j}$, and $\bar{x}_{ik}$ is the risk set weighted average: $$\bar{x}_k(t_j)=\frac{\sum_{l\in\mathcal{R}(t_j)}x_{lk}\exp(\boldsymbol{\beta}^\top\boldsymbol{X}_l)}{\sum_{l\in\mathcal{R}(t_j)}\exp(\boldsymbol{\beta}^\top\boldsymbol{X}_l)}$$then regress it against time$$r_{kj}=\theta_kt_j+\epsilon_j$$Null hypothesis: $\theta_{k}=0 \iff$ PH holds.
# Time-dependent Covariable
## Stratified Cox Model
Used when a categorical variable violates the PH assumption. It excludes this variable from linear regression, but reflect it by baseline hazard function.

Let $Z \in \{1, 2, \ldots, S\}$ denote strata (e.g., different hospitals). The hazard function becomes:
$$h(t \mid \boldsymbol{X}, Z = s) = h_{0s}(t) \exp(\boldsymbol{\beta}^\top \boldsymbol{X})$$
- Each stratum $s$ has its own baseline hazard $h_{0s}(t)$
- Covariate effects $\boldsymbol{\beta}$ are assumed common across strata
- Partial likelihood is computed within each stratum and then multiplied:
$$
L(\boldsymbol{\beta}) = \prod_{s=1}^{S} \prod_{j \in \text{events in stratum } s} \frac{\exp(\boldsymbol{\beta}^\top \boldsymbol{X}_j)}{\sum_{i \in \mathcal{R}_s(t_j)} \exp(\boldsymbol{\beta}^\top \boldsymbol{X}_i)}$$
## Extended Cox Model
Used when the effect of covariates changes over time, violating PH.
Time-varying coefficients:
$$h(t \mid \boldsymbol{X}) = h_0(t) \exp \left( \sum_{k=1}^{p} \beta_k(t) X_k \right)$$
Example: $\beta_k(t) = \beta_k + \theta_k g(t)$, where $g(t) = \log(t)$, $t$, etc.
Time-varying covariates:
Allow covariates themselves to change with time: $X_k = X_k(t)$
$$
h(t \mid \boldsymbol{X}(t)) = h_0(t) \exp \left( \boldsymbol{\beta}^\top \boldsymbol{X}(t) \right)$$
Requires splitting each subject’s timeline into multiple intervals and updating covariates accordingly.