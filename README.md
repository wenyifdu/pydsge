# pydsge
This is a Python library to calibrate, estimate and analyze linearized DSGE models. The interface is inpired by the 
dynare interface which allows for symbolic declarations of the variables and equations. The implemented bayesian 
estimation method uses markov chain monte carlo (MCMC) to simulate the posterior distributions of the parameters. This 
library is an effort to bring the DSGE toolset into the open-source world in a fully python implementation, which allows 
to fully embrace the advantages of the programming language when working with DSGEs.

---
# Installation
* INSTAL HERE

---
# Usage
A full example on how to use this library with a small New Keynesian model is available in 
[this Jupyter notebook](https://github.com/gusamarante/pydsge/blob/master/Example/example_snkm.ipynb). The model used 
in the example is descibred by the following equations: 

$$
\begin{align*}
\tilde{y}_{t} & =E_{t}\left(\tilde{y}_{t+1}\right)-\frac{1}{\sigma}\left[\hat{i}_{t}-E_{t}\left(\pi_{t+1}\right)\right]+\psi_{ya}^{n}\left(\rho_{a}-1\right)a_{t}\\
\pi_{t} & =\beta E_{t}\left(\pi_{t+1}\right)+\kappa\tilde{y}_{t}+\sigma_{\pi}\varepsilon_{t}^{\pi}\\
\hat{i}_{t} & =\phi_{\pi}\pi_{t}+\phi_{y}\tilde{y}_{t}+v_{t}\\
a_{t} & =\rho_{a}a_{t-1}+\sigma_{a}\varepsilon_{t}^{a}\\
v_{t} & =\rho_{v}v_{t-1}+\sigma_{v}\varepsilon_{t}^{v}
\end{align*}
$$

## Model Especification
For now, the model equations have to be linearized around its steady-state. Soon, there will be a functionality that 
allows for non-linearized declaration of the equilibrium conditions and simplified variable name declaration.

## Model Solution
The solution method used is based on the implementation of Christopher A. Sims' `gensys` function. You can find the 
author's original matlab code [here](https://dge.repec.org/codes/sims/linre3a/). The paper explaining the solution 
method is [this one](https://dge.repec.org/codes/sims/linre3a/LINRE3A.pdf).

---
# Model Estimation
The models are estimated using Bayesian methdos, specifically, by simulating the posterior distribution using MCMC 
sampling. Simulations are typically long, so there is a functionality that allows you to stop a simulation and continue 
it later from where it stoped.

---
# Drawbacks
Since there is symbolic declaration of variables and equations, methdos involving them are slow, so the MCMC methods 
typically take a long time to run. Although there is a lot room for improvement for the efficiency of these estimation
algorithms. 

---
# Contributing
If you would like to contribute to this repository, plese check the 
[contributing guidelines](https://github.com/gusamarante/pydsge/blob/master/CONTRIBUTING.md) here. A 
[list of feature suggestions](https://github.com/gusamarante/pydsge/projects) is available on the projects page of this
repository.

---
# More Information and Help
support@pydsge.com