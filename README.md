
# State-Transition Model

The State-Transition Model enables the mathematical analysis of the structure-function relationship in neuronal networks. This model was developed by coarse-graining cultured neuronal networks and adapting them to the Markov chain model. You can find the main paper [here](https://arxiv.org/abs/2404.16582). The model offers two key advantages:

1. **State Probability Calculation**: The occurrence probability of all network states can be derived through the eigen-decomposition of the state-transition matrix, denoted as $\mathrm{T}$.
2. **Network Dynamics Inference**: Dynamics such as synchronization and complexity, which depend on the network structure, can be inferred using the correlation coefficients $\langle \tilde{r}_{ij} \rangle$, corresponding to the Pearson correlation.

Despite its usefulness, the model's computational complexity grows exponentially due to the size of the state-transition matrix $\mathrm{T}$, which is $2^N \times 2^N$. For instance, in a network with 16 nodes, the state-transition matrix requires 32 GB of memory. Additionally, the computational cost of eigen-decomposition becomes significant. These challenges are typical of the Markov chain model, but future theoretical advancements could help mitigate them.

## Installation

This repository is written in MATLAB. Please ensure you have access to a MATLAB license.

1. Clone the repository via the command line:
   ```bash
   git clone https://github.com/MonmaNobuaki/State-transition-model.git
   ```

2. Navigate to the repository:
   ```bash
   cd State-transition-model
   ```
The repository contains models for both 4-node and 16-node networks. It is recommended to start with the 4-node model before scaling up.

1. **4-node network**

2. **16-node network**


## System Requirements

A significant amount of RAM is required for larger networks. For example, analyzing a network with more than 16 nodes requires at least 32 GB of RAM, as mentioned earlier.

## Usage

To analyze networks with more than 16 nodes, ensure that your system has sufficient RAM. You can run the model by executing the provided MATLAB script:

```matlab
% Example command to run the script
run('your_script.m')
```

## Contact

If you have any questions or issues, feel free to reach out to the author.

## License

This software is released under the MIT License. For more details, see [LICENSE.txt](LICENSE.txt).
