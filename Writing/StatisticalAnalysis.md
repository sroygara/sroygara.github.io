---
layout: default
title: Statistical Analysis
date: May 2025
---
This is *italic* text on the same line.


<p>In search for new physics we employ two hypothesis tests: the null hypothesis ($H_0$), which posits that the observed data is explained by background only, and the alternate hypothesis ($H_1$), which suggests the observation is explained by the presence of a new signal amongst the background. This formalism is essential for the discovery of new physics as it allows us to first reject the null hypothesis in favour of the *alternative*.</p>

The basis of hypothesis testing begins with the construction of a likelihood. To illustrate the use of a likelihood, we can begin with a toy example. Consider a counting experiment. The likelihood measuring $n$ events is,

$$
L(n_\text{obs}|\nu) = \frac{\nu^{n_\text{obs}} e^{-\nu}}{n_\text{obs}!}
$$

where $\nu$ is the number of expected events predicted by the underlying hypothesis. The basis of either hypothesis is the number of expected events which can be written as,

$$
\nu = \mu S + B
$$

where $\nu$ is the expected yield, $B$ is the predicted background, $S$ is the nominally predicted signal and $\mu$ is the scaling factor for the signal. The parameter $\mu$, referred to as the signal strength, allows for different signal hypotheses to be tested, including the background-only hypothesis of $\mu = 0$.

In reality the predictions of the signal and background contain underlying uncertainties. Consider a Gaussian uncertainty on the signal of 20%. In the likelihood, we allow the uncertainty to modify the signal as $S(\theta) = (1 + 0.2\theta)S_\text{nom}$, where $S_\text{nom}$ is the nominal prediction for the number of signal events and $\theta$ is the _nuisance parameter_ (NP), which follows a standardized[^1] Gaussian distribution. Correspondingly, a Gaussian distribution is appended to the likelihood. This term is known as a constraint as it penalizes non-nominal values of $\theta$. With this information, the likelihood is thus modified as:

$$
L(n_\text{obs}|\nu, \theta) = \frac{(\mu S(\theta)+B)^{n_\text{obs}} e^{-(\mu S(\theta)+B)}}{n_\text{obs}!} \cdot \frac{e^{-\theta^2/2}}{\sqrt{2\pi}}
$$

With the likelihood constructed, a *fit* can be conducted by finding the values of $\mu$ and $\theta$ which maximize the likelihood. Typically, it is computationally simpler to minimize the negative-log of the likelihood, hence this formalism will appear later on.

[^1]: As the uncertainty manifests in the modifying term, the Gaussian is *standardized*, meaning it has standard deviation of 1.
