# MonteCarlo_simulation_average_treatment_effect

This is the code for a Monte Carlo simulation used to support findings of Farrell, M.H., Liang, T. and Misra, S., 2018: ``Deep neural networks for estimation and inference: Application to causal effects and other semiparametric estimands,'' arXiv preprint arXiv:1809.09953.

This code first creates an artificial dataset according to a Data Generating Process (DGP). Next, it generates a neural network with a prescribed architecture that estimates treatment effect coefficients and, in the case when treatment is not randomized, it also creates a neural network that estimates propensity scores. These neural networks are then trained and their outputs are used to build confidence intervals for the average treatment effect using a doubly robust estimator. Next, the code checks whether the true average treatment effect of the artificial dataset is contained within the estimated confidence interval. Finally, each run of the model is appended to a summary .csv file that contains information about all the relevant statistics recorded during the run.

### Installing the dependencies for the code

With Anaconda:

Create a new environment:
```sh
conda create --name=name_of_the_environment python=3.6.8
```
Activate new environment
```sh
conda activate name_of_the_environment
```
Next, cd to the directory with files from this repository.
```sh
cd path/to/files
```
Install all the libraries needed to run the code:
```sh
pip install -r requirements.txt
```
You can exit the environment by typing:
```sh
conda deactivate
```
With Linux/Mac: 

The steps to install the dependencies on Linux/Mac are analogous to Anaconda inatallation:
```sh
virtualenv --system-site-packages -p python3 ./name_of_the_environment
source ./name_of_the_environment/bin/activate
cd path/to/files
pip install -r requirements.txt
deactivate
```

Note: Tensorflow version 1.15 will be installed. It has CPU and GPU support combined in one package. However, to actually enable GPU support for tensorflow, appropriate versions of CUDA and cudann toolkit have to be installed as well. For tensorflow-gpu 1.15, the appropriate versions are CUDA 10 and cudnn 7.3. See more at: [<a href="https://www.tensorflow.org/install/gpu">GPU support</a>].

### Usage
Once you have created the virtual environment and installed the necessary libraries, you can interact with the code, by running the following command.
```sh
python MonteCarlo_simulation_for_average_treatment_effects_using_NNs.py
```
To change the default values of the parameters you can edit the code itself, or use flags in the following manner: 
```sh
python MonteCarlo_simulation_for_average_treatment_effects_using_NNs.py --nconsumer_characteristics=100 --update=True --model=simple
```
To see the list of parameters available and detailed description of the code, see the code instruction pdf file. 

### References

Farrell, M.H., Liang, T. and Misra, S., 2018:
'Deep neural networks for estimation and inference: Application to causal effects and other semiparametric estimands',
[<a href="https://arxiv.org/pdf/1809.09953.pdf">arxiv</a>]
