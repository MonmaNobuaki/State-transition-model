# State-Transition-model
This is the mathematical model for analyzing the structue-function relationship in neuronal networks. The main paper is [here](https://arxiv.org/abs/2404.16582).
The state-transition model is based on the Markov chain model. Note 

## Installation

1. Clone this repository in command line.
```bash
git clone https://github.com/MonmaNobuaki/State-Transition-model.git
```

2. Go into the repository.
```bash
cd State-Transition-model
```

## Usage
This script is designed to extract dcimg format files from a specified folder and convert them into btf format. Additionally, it allows for the selection of a destination folder to save the converted files. With several optimizations, the conversion process is executed at a high speed.

Before executing,set the number of pixels in height and width of the file you want to convert in line 9 of the script. 

Please execute the script with the following command
```bash
python dcimg2btf.py
```
When you execute the script, a window will appear. Please select the folder containing the dcimg files you want to convert.

![Test Image 1](images/input.png)

After specifying the folder you want to read from, the next step is to specify the folder where you want to save the converted files. A similar window will appear, so please select the folder you want to use for saving.

![Test Image 2](images/output.png)

After specifying the input and output folders, please wait for the conversion to finish. This may take some time depending on the number of files and the size of the files being converted.

## Contact
If you have any questions, please contact the author (not Hamamatsu Photonics). 

## License

Copyright (c) 2024 Nobuaki Monma 

This software is released under the MIT License, see LICENSE.txt.
