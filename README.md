# State-Transition-model

The state-transition model enable us to analyze the structure-function relationship in neuronal networks, mathematically. This model is developed by coarse-graining cultured neuronal networks and adapting them to the Markov chain model (The main paper is [here](https://arxiv.org/abs/2404.16582)).  This model has three advantages.

1. The occurrence probability of all networks states can be derived by eigen-decomposition of state-transition matrix $\mathrm{T}$. 
2. This model is able to derive the correlation coefficients $\langle \tilde{r}_{ij} \rangle$, corresponding the Pearson collation used in the wet experiments and spiking neural networks.
3. The network dynamics such as synchronization and complexity depending on the network structures can be inferred with the state-transition model without trial and error like the wet experiments and spiking neural networks.

Despite its high usefulness, this model also has a drawback that computational complexity increases exponentially, since  the size of state-transition matrix $\mathrm{T}$ is $2^N \times 2^N$  (For  example, the size of the state transition matrix in the network with 16 nodes is 32 GB). Along with that, the computational cost of eigen decomposition becomes heavy.  This is the general problems in the Markov chain model. By developing the theoretical methodologies,  these challenges can be overcome in the future.

## Methodology

The analysis of the state-transition model consists of three step, which are $(1)$ calculation of the state transition matrix $\mathrm{T}$ from the network structure $\tilde {\mathrm{W}}$, $(2)$ Obtaining the stationary distribution $\vec{p}(\infty) = (p_0(\infty),...,p_{2^N}(\infty))$  from eigendecompositon of $\mathrm{T}$, $(3)$ Inference of the network dynamics from correlation coefficients $\langle \tilde{r}_{ij} \rangle$. 

$(1)$ Calculation of the state transition matrix $\mathrm{T}$

The state transition model was developed by coarse-graining the engineered neuronal networks. The neuronal population in same module (i.e. population, cluster, etc.) was regarded as a single dynamical node. This node transition the firing and resting state ($s_k(i) = 1,0$). Then, network state is expressed as a vector, given by : 

$$
\vec{s}_k = (s_k(1),...,s_k(N)), 
$$

where $N$ is the number of node in the network.   The index $k$ is obtained from the decimal conversion of $\vec{s}_k$ $(e.g.\space k = 12 \space if \space \vec{s}_k = (0,0,1,1))$. 

　The transition probability from $\vec{s}_k$ to $\vec{s}_{k'}$ can be obtained by considering the all node transitions. If the node $i$ is resting state, the node is activated spontaneously at the probability of $\sigma$ . Additionally, synaptic input $\vec{f_k} = \tilde{\mathrm{W}}\vec{s}_k$ activate the resting neuron, given by: 

$$
 \vec{f}_k = (f_k(1),...,f_k(N))= \tilde{\mathrm{W}}\vec{s}_k
$$

 The activation probability depending on the synaptic input to node $i$, $\vec{f_k}$, is governed by the activation function $A$, given by;

$$
A(f_k(i)) = 
\begin{cases}
(1-\sigma)f_k(i) + \sigma & \text{if } 0 \leq f_k(i) < 1, \\
1 & \text{if } 1 \leq f_k(i),
\end{cases}
$$

The active node persists its state at the probability of $\gamma$ . To ensure irreducibility, active node transition its state independent of $f_k(i)$. In summary, the element of the state transition model $T_{k'k}$ is obtained from the following quadratic formulas, 

$$
T_{k'k} =  \prod_{i} \left( 1 - s_k(i) \right)\begin{bmatrix}1 - A(f_k(i)) & A(f_k(i)) \\1 - \gamma & \gamma\end{bmatrix}\begin{bmatrix}1 - s_{k'}(i) \\s_{k'}(i)\end{bmatrix}.
$$

By calculating the all transition probability from $s_k(i)$ to $s_{k'}(i)$, the state-transition matrix $\mathrm{T}$ can be obtained.

$(2)$ Obtaining the stationary distribution $\vec{p}(\infty)$  from eigendecompositon of $\mathrm{T}$

To calculate the occurrence probability of network state $\vec{s}_k$,  the stationary distribution $\vec{p}(\infty) = (p_0(\infty),...,p_{2^N}(\infty))$ was be derived the eigenvector of the state-transition  matrix $\mathrm{T}$corresponding to the eigenvalue equal to 1.  Each element of the stationary distribution $p_k(i)$ represents the occurrence probability of $\vec{s}_k$.

$(3)$ Inference of correlation coefficients $\langle \tilde{r}_{ij} \rangle$

 From the stationary distribution $\vec{p}(\infty)$, the correlation coefficients $\tilde{r}_{ij}$ was caluclated, given by;

$$
  \tilde{r}_{ij} = \frac{\sigma_{ij}}{\sqrt{\sigma_{ii}\sigma_{jj}}}, \sigma_{ij} = \sum_{k=0}^{2^N-1} p_k(\infty) \left( s_k(i) - \bar{s}(i) \right)\left( s_k(j) - \bar{s}(j) \right),
$$

$$
  \bar{s}(i) = \sum_{k=0}^{2^N-1} p_k(\infty)s_k(i).
$$

 For example, the synchronization can be inferred from the mean value of $\tilde{r}_{ij}$. The detail of the analysis is described in the main  [paper](https://arxiv.org/abs/2404.16582).

## Installation

All code is written in MATLAB. Please prepare for its license.

1. Clone this repository in command line.

```bash
git clone <https://github.com/MonmaNobuaki/State-transition-model.git>
```

1. Go into the repository.

```bash
cd State-transition-model
```

There are two repositories, which are 4-node and 16-node network model. I recommend you to do the four node model, firstly.

# Caution

You need huge size of RAM in your PC. For example, 32 GB of RAM is needed to analyze the network with more than 16-nodes as discussed in the introduction. 

## Usage

If you want to analyze the network with more than 16-nodes, you have to prepare enough RAM.

Please execute the script with the following command

## Contact

If you have any questions, please contact the author.

## License

Copyright (c) 2024 Nobuaki Monma

This software is released under the MIT License, see LICENSE.txt.
