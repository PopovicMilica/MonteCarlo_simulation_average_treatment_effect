# MonteCarlo_simulation_average_treatment_effect

This is the code for a Monte Carlo simulation used to support findings of Farrell, M.H., Liang, T. and Misra, S., 2018: ``Deep neural networks for estimation and inference: Application to causal effects and other semiparametric estimands,'' arXiv preprint arXiv:1809.09953.

This code first creates an artificial dataset according to a Data Generating Process (DGP) prescribed in the code. Next, it generates a neural network with prescribed architecture that estimate treatment effect coefficients and a neural network for estimation of propensity scores in case treatment is not randomized. These neural networks are then trained and their outputs are used to build confidence intervals for the average treatment effect using a doubly robust estimator. Next, the code checks whether the true average treatment effect of the artificial dataset is contained within the estimated confidence interval. Finally, each run of the model is appended to a summary .csv file that contains information about all the relevant statistics recorded during the run

### Installation of all the dependencies for code to run smoothly

With Anaconda:

Open the terminal that has anaconda installed and create a new environment:
```sh
conda create --name=name_of_the_environment python=3.6.8
```
Activate new environment
```sh
conda activate name_of_the_environment
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

cd to folder where you downloaded the python file.
Run it by typing:  

Note: Tensorflow version 1.15 is installed. It has CPU and GPU support combined in one package. However, to actually enable GPU support for tensorflow, appropriate versions of CUDA and cudann toolkit have to be installed as well. For tensorflow-gpu 1.15 version CUDA 10 and cudnn 7.3. See more at: [<a href="https://www.tensorflow.org/install/gpu">GPU support</a>].



### Usage

### References

Farrell, M.H., Liang, T. and Misra, S., 2018:
'Deep neural networks for estimation and inference: Application to causal effects and other semiparametric estimands',
[<a href="https://arxiv.org/pdf/1809.09953.pdf">arxiv</a>]
