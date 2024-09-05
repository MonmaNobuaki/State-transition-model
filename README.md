# State-Transition-model
The state-transiton model enable us to analyze the structue-function relationship in neuronal networks, based on the Markov chain model. The main paper is [here](https://arxiv.org/abs/2404.16582).  

## Installation
All code is writen in MATLAB. Plese prepare the its lisence.

1. Clone this repository in command line.
```bash
git clone https://github.com/MonmaNobuaki/State-transition-model.git
```

2. Go into the repository.
```bash
cd State-transition-model
```
There are two repogitories, which are 4-node and 16-node network model. I reccomend you to do the four node model, firstly. 

# Caution 
You need huge size of RAM in your PC. For example, 32 GB of RAM is neeeded to analyze the network with more than 16-nodes. This is because the elements of the steta-transition matrix **T** exponentially increase with the number of nodes _N_.


## Usage
If you want to analuze the network with more than 16-nodes, you have to prepare enough RAM.

Please execute the script with the following command

```bash
python dcimg2btf.py
```


## Contact
If you have any questions, please contact the author. 

## License

Copyright (c) 2024 Nobuaki Monma 

This software is released under the MIT License, see LICENSE.txt.
