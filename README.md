# MonteCarlo_simulation_average_treatment_effect

This is the code for a Monte Carlo simulation used to support findings of Farrell, M.H., Liang, T. and Misra, S., 2019: ``Deep neural networks for estimation and inference'', arXiv preprint arXiv:1809.09953.

This code first creates an artificial dataset according to a Data Generating Process (DGP). Next, it generates a neural network with a prescribed architecture that estimates treatment effect coefficients and, in the case when treatment is not randomized, it also creates a neural network that estimates propensity scores. These neural networks are then trained and their outputs are fed to influence functions which estimates are used to build 95% confidence interval for average treatment effect. Next, the code checks whether the true average treatment effect of the artificial dataset is contained within the estimated confidence interval. Finally, each run of the model is appended to a summary .csv file that contains information about all the relevant statistics recorded during the run.

## Installing the dependencies for the code

**With Anaconda:**

First, create a new virtual environment:
```sh
conda create --name=name_of_the_environment python=3.6.8
```
Then, activate new virtual environment:
```sh
conda activate name_of_the_environment
```
Next, download the files from this repository to your computer and from your terminal cd to the directory that contains them.
```sh
cd path/to/files
```
Finally, install all the libraries needed to run the code:
```sh
pip install -r requirements.txt
```
Now that all the necessary dependencies are installed, you can run the main Python code(see `Usage` section below).
When you are done, you can exit the virtual environment by typing:
```sh
conda deactivate
```
*Note:
`conda activate` and `conda deactivate` only work on conda 4.6 and later versions. For conda versions prior to 4.6, run:

 * Windows: `activate` or `deactivate`

 * Linux and macOS: `source activate` or `source deactivate`  

**With Linux/Mac:**

The steps to install the dependencies on Linux/Mac, if you don't have Anaconda distribution, are analogous to Anaconda installation:
```sh
virtualenv --system-site-packages -p python3 ./name_of_the_environment
source ./name_of_the_environment/bin/activate
cd path/to/files
pip install -r requirements.txt
deactivate
```

## Usage
Once you have created the virtual environment and installed the necessary libraries, you can interact with the code, by running the following command:

```sh
python MonteCarlo_simulation_for_average_treatment_effects_using_NNs.py
```
To change the default values of the parameters you can edit the code itself, or use flags in the following manner: 
```sh
python MonteCarlo_simulation_for_average_treatment_effects_using_NNs.py --nconsumer_characteristics=100 --update=True --model=simple
```
To see the list of parameters available and detailed description of the code, see the file code_instructions.pdf. 

## References

Farrell, M.H., Liang, T. and Misra, S., 2019:
'Deep neural networks for estimation and inference', [<a href="https://arxiv.org/pdf/1809.09953.pdf">arxiv</a>]
