# State-Transition-model

The state-transition model enable us to analyze the structure-function relationship in neuronal networks, mathematically. This model is developed by coarse-graining cultured neuronal networks and adapting them to the Markov chain model (The main paper is [here](https://arxiv.org/abs/2404.16582)).  This model has three advantages.

1. The occurrence probability of all networks states can be derived by eigen-decomposition of state-transition matrix $\mathrm{T}$. 
2. This model is able to derive the correlation coefficients $\langle \tilde{r}_{ij} \rangle$, corresponding the Pearson collation used in the wet experiments and spiking neural networks.
3. The network dynamics such as synchronization and complexity depending on the network structures can be inferred with the state-transition model without trial and error like the wet experiments and spiking neural networks.

Despite its high usefulness, this model also has a drawback that computational complexity increases exponentially, since  the size of state-transition matrix $\mathrm{T}$ is $2^N \times 2^N$  (For  example, the size of the state transition matrix in the network with 16 nodes is 32 GB). Along with that, the computational cost of eigen decomposition becomes heavy.  This is the general problems in the Markov chain model. By developing the theoretical methodologies,  these challenges can be overcome in the future.

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
