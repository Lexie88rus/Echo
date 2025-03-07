<p align="left">
  <img width="270" src="Observations/logo_transparent.png">
</p>

[![Donate](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

# Echo

Python package containing all mathematical backend algorithms used in Machine Learning.

## Table of Contents
* [About the Project](#about)
  * [Activation Functions](#activation-functions)
* [Repository Structure](#repository-structure)
* [Setup Instructions](#setup-instructions)

## About
**Echo Package** is created to provide an implementation of the most promising mathematical algorithms, which are missing in the most popular deep learning libraries, such as [PyTorch](https://pytorch.org/), [Keras](https://keras.io/) and
[TensorFlow](https://www.tensorflow.org/).

### Activation Functions
The package contains implementation for following activation functions (:white_check_mark: - implemented functions, :clock9: - functions to be implemented soon, :white_large_square: - function is implemented in the original deep learning package):

|#| Function | Equation | Keras | PyTorch | TensorFlow |
| --- | --- | --- | --- | --- | --- |
|1| Weighted Tanh | ![equation](https://latex.codecogs.com/gif.latex?weightedtanh%28x%29%20%3D%20tanh%28x%20*%20weight%29) | :white_check_mark: | :white_check_mark: | :clock9: |
|2| [Swish](https://arxiv.org/pdf/1710.05941.pdf) | ![equation](https://latex.codecogs.com/gif.latex?SwishX%28x%2C%20%5Cbeta%29%20%3D%20x*sigmoid%28%5Cbeta*x%29%20%3D%20%5Cfrac%7Bx%7D%7B%281&plus;e%5E%7B-%5Cbeta*x%7D%29%7D) | :white_check_mark: | :white_check_mark: | :clock9: |
|3| [ESwish](https://arxiv.org/abs/1801.07145) | ![equation](https://latex.codecogs.com/gif.latex?ESwish%28x%2C%20%5Cbeta%29%20%3D%20%5Cbeta*x*sigmoid%28x%29) | :white_check_mark: | :white_check_mark: | :clock9: |
|4| [Aria2](https://arxiv.org/abs/1805.08878) | ![equation](https://latex.codecogs.com/gif.latex?Aria2%28x%2C%20%5Calpha%2C%20%5Cbeta%29%20%3D%20%281&plus;e%5E%7B-%5Cbeta*x%7D%29%5E%7B-%5Calpha%7D) |:white_check_mark:| :white_check_mark: | :clock9: |
|5| [ELiSH](https://arxiv.org/pdf/1808.00783.pdf) | ![equation](https://latex.codecogs.com/gif.latex?ELiSH%28x%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%20/%20%281&plus;e%5E%7B-x%7D%29%2C%20x%20%5Cgeq%200%20%5C%5C%20%28e%5E%7Bx%7D%20-%201%29%20/%20%281%20&plus;%20e%5E%7B-x%7D%29%2C%20x%20%3C%200%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark:  | :white_check_mark: | :clock9: |
|6| [HardELiSH](https://arxiv.org/pdf/1808.00783.pdf) | ![equation](https://latex.codecogs.com/gif.latex?HardELiSH%28x%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%20%5Ctimes%20max%280%2C%20min%281%2C%20%28x%20&plus;%201%29%20/%202%29%29%2C%20x%20%5Cgeq%200%20%5C%5C%20%28e%5E%7Bx%7D%20-%201%29%5Ctimes%20max%280%2C%20min%281%2C%20%28x%20&plus;%201%29%20/%202%29%29%2C%20x%20%3C%200%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark:  | :white_check_mark: | :clock9: |
|7| [Mila](https://github.com/digantamisra98/Mila) | ![equation](https://latex.codecogs.com/gif.latex?mila%28x%29%20%3D%20x%20*%20tanh%28ln%281%20&plus;%20e%5E%7B%5Cbeta%20&plus;%20x%7D%29%29%20%3D%20x%20*%20tanh%28softplus%28%5Cbeta%20&plus;%20x%29%29) | :white_check_mark:  | :white_check_mark: | :clock9: |
|8| [SineReLU](https://medium.com/@wilder.rodrigues/sinerelu-an-alternative-to-the-relu-activation-function-e46a6199997d) | ![equation](https://latex.codecogs.com/gif.latex?SineReLU%28x%2C%20%5Cepsilon%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%20%2C%20x%20%3E%200%20%5C%5C%20%5Cepsilon%20*%20%28sin%28x%29%20-%20cos%28x%29%29%2C%20x%20%5Cleq%200%20%5Cend%7Bmatrix%7D%5Cright) | :white_check_mark: | :white_check_mark: | :clock9: |
|9| [Flatten T-Swish](https://arxiv.org/pdf/1812.06247.pdf) | ![equation](https://latex.codecogs.com/gif.latex?FTS%28x%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20%5Cfrac%7Bx%7D%7B1%20&plus;%20e%5E%7B-x%7D%7D%20%2C%20x%20%5Cgeq%200%20%5C%5C%200%2C%20x%20%3C%200%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark:  | :white_check_mark: | :clock9: |
|10| [SQNL](https://ieeexplore.ieee.org/document/8489043) | ![equation](https://latex.codecogs.com/gif.latex?SQNL%28x%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%201%2C%20x%20%3E%202%20%5C%5C%20x%20-%20%5Cfrac%7Bx%5E2%7D%7B4%7D%2C%200%20%5Cleq%20x%20%5Cleq%202%20%5C%5C%20x%20&plus;%20%5Cfrac%7Bx%5E2%7D%7B4%7D%2C%20-2%20%5Cleq%20x%20%3C%200%20%5C%5C%20-1%2C%20x%20%3C%20-2%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark:  | :white_check_mark: | :clock9: |
|11| [ISRU](https://arxiv.org/pdf/1710.09967.pdf) | ![equation](https://latex.codecogs.com/gif.latex?ISRU%28x%29%20%3D%20%5Cfrac%7Bx%7D%7B%5Csqrt%7B1%20&plus;%20%5Calpha%20*%20x%5E2%7D%7D) | :white_check_mark:  | :white_check_mark: | :clock9: |
|12| [ISRLU](https://arxiv.org/pdf/1710.09967.pdf) | ![equation](https://latex.codecogs.com/gif.latex?ISRLU%28x%29%3D%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%2C%20x%5Cgeq%200%20%5C%5C%20x%20*%20%28%5Cfrac%7B1%7D%7B%5Csqrt%7B1%20&plus;%20%5Calpha*x%5E2%7D%7D%29%2C%20x%20%3C0%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark: | :white_check_mark: | :clock9: |
|13| Bent's identity | ![equation](https://latex.codecogs.com/gif.latex?bentId%28x%29%20%3D%20x%20&plus;%20%5Cfrac%7B%5Csqrt%7Bx%5E%7B2%7D&plus;1%7D-1%7D%7B2%7D) | :white_check_mark:  | :white_check_mark: | :clock9: |
|14| [Soft Clipping](https://arxiv.org/pdf/1810.11509.pdf) | ![equation](https://latex.codecogs.com/gif.latex?SC%28x%29%20%3D%201%20/%20%5Calpha%20*%20log%28%5Cfrac%7B1%20&plus;%20e%5E%7B%5Calpha%20*%20x%7D%7D%7B1%20&plus;%20e%5E%7B%5Calpha%20*%20%28x-1%29%7D%7D%29) |  :white_check_mark:  | :white_check_mark: | :clock9: |
|15| [SReLU](https://arxiv.org/pdf/1512.07030.pdf) | ![equation](https://latex.codecogs.com/gif.latex?SReLU%28x_i%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20t_i%5Er%20&plus;%20a_i%5Er%28x_i%20-%20t_i%5Er%29%2C%20x_i%20%5Cgeq%20t_i%5Er%20%5C%5C%20x_i%2C%20t_i%5Er%20%3E%20x_i%20%3E%20t_i%5El%5C%5C%20t_i%5El%20&plus;%20a_i%5El%28x_i%20-%20t_i%5El%29%2C%20x_i%20%5Cleq%20t_i%5El%20%5C%5C%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark: | :white_check_mark: | :clock9: |
|15| [BReLU](https://arxiv.org/pdf/1709.04054.pdf) | ![equation](https://latex.codecogs.com/gif.latex?BReLU%28x_i%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20f%28x_i%29%2C%20i%20%5Cmod%202%20%3D%200%5C%5C%20-%20f%28-x_i%29%2C%20i%20%5Cmod%202%20%5Cneq%200%20%5Cend%7Bmatrix%7D%5Cright.) | :clock9: | :white_check_mark: | :clock9: |
|16| [APL](https://arxiv.org/pdf/1412.6830.pdf) | ![equation](https://latex.codecogs.com/gif.latex?APL%28x_i%29%20%3D%20max%280%2Cx%29%20&plus;%20%5Csum_%7Bs%3D1%7D%5E%7BS%7D%7Ba_i%5Es%20*%20max%280%2C%20-x%20&plus;%20b_i%5Es%29%7D) | :clock9: | :white_check_mark: | :clock9: |
|17| [Soft Exponential](https://arxiv.org/pdf/1602.01321.pdf) | ![equation](https://latex.codecogs.com/gif.latex?SoftExponential%28x%2C%20%5Calpha%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20-%20%5Cfrac%7Blog%281%20-%20%5Calpha%28x%20&plus;%20%5Calpha%29%29%7D%7B%5Calpha%7D%2C%20%5Calpha%20%3C%200%5C%5C%20x%2C%20%5Calpha%20%3D%200%5C%5C%20%5Cfrac%7Be%5E%7B%5Calpha%20*%20x%7D%20-%201%7D%7B%5Calpha%7D%20&plus;%20%5Calpha%2C%20%5Calpha%20%3E%200%20%5Cend%7Bmatrix%7D%5Cright.) | :white_check_mark:| :white_check_mark: | :clock9: |
|18| [Maxout](https://arxiv.org/pdf/1302.4389.pdf) | ![equation](https://latex.codecogs.com/gif.latex?maxout%28%5Cvec%7Bx%7D%29%20%3D%20max_i%28x_i%29) | :clock9: | :white_check_mark: | :clock9: |
|19| Mish | - | :white_check_mark: | :white_check_mark: | :clock9: |
|20| [Beta Mish](https://github.com/digantamisra98/Beta-Mish) | ![equation](https://latex.codecogs.com/gif.latex?%5Cbeta%20mish%28x%29%20%3D%20x%20*%20tanh%28ln%28%281%20&plus;%20e%5E%7Bx%7D%29%5E%7B%5Cbeta%7D%29%29)| :white_check_mark: | :white_check_mark: | :clock9: |
|21| [RReLU](https://arxiv.org/pdf/1505.00853.pdf) | ![equation](https://latex.codecogs.com/gif.latex?RReLU_j_i%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x_j_i%20%2C%5Cif%20%5C%20x_j_i%5Cgeq%200%5C%5C%20a_j_i%20*%20x_j_i%2C%20%5Cif%20%5C%20x_j_i%20%3C%200%20%5Cend%7Bmatrix%7D%5Cright.%20a_j_i%20%5Csim%20U%28l%2C%20u%29%2C%20%5Cl%3C%20u%20%5Cand%20%5C%20l%2C%20u%20%5Cin%20%5B0%2C1%29)| :clock9: | :white_large_square: | :clock9: |
|22| [CELU](https://arxiv.org/pdf/1704.07483.pdf) | ![equation](https://latex.codecogs.com/gif.latex?CELU%28x%2C%20%5Calpha%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%20%2C%20x%20%5Cgeq%200%5C%5C%20%5Calpha%20*%20%28e%5E%7B%5Cfrac%7Bx%7D%7B%5Calpha%7D%7D%20-%201%29%2C%20x%20%3C%200%20%5Cend%7Bmatrix%7D%5Cright.)|  :white_check_mark:  | :white_large_square: | :clock9: |
|23| ReLU6 | ![equation](https://latex.codecogs.com/gif.latex?ReLU6%28x%29%3Dmin%28max%280%2Cx%29%2C6%29)|  :white_check_mark:  | :white_large_square: | :clock9: |
|24| HardTanh | ![equation](https://latex.codecogs.com/gif.latex?HardTanh%28x%29%3D%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%201%2C%20x%20%3E%201%5C%5C%20-1%2C%20x%20%3C%20-1%5C%5C%20x%2C%20-1%20%5Cleq%20x%20%5Cleq%201%20%5Cend%7Bmatrix%7D%5Cright.)|  :white_check_mark:  | :white_large_square: | :clock9: |
|25| [GLU](https://arxiv.org/pdf/1612.08083.pdf) | ![equation](https://latex.codecogs.com/gif.latex?GLU%28a%2Cb%29%3Da%20%5Cotimes%20%5Csigma%28b%29%2C%20%5Cotimes%20-%20element%20%5C%20wise%20%5C%20product)| :clock9: | :white_large_square: | :clock9: |
|26| LogSigmoid | ![equation](https://latex.codecogs.com/gif.latex?LogSigmoid%28x%29%3Dlog%28%5Cfrac%7B1%7D%7B1%20&plus;%20e%5E%7B-x%7D%7D%29)|  :white_check_mark:  | :white_large_square: | :clock9: |
|27| TanhShrink | ![equation](https://latex.codecogs.com/gif.latex?TanhShrink%28x%29%3Dx%20-%20Tanh%28x%29)|  :white_check_mark:  | :white_large_square: | :clock9: |
|28| HardShrink | ![equation](https://latex.codecogs.com/gif.latex?HardShrink%28x%29%3D%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%2C%20x%20%3E%20%5Clambda%20%5C%5C%20x%2C%20x%20%3C%20-%20%5Clambda%20%5C%5C%200%2C%20-%20%5Clambda%20%5Cleq%20x%20%5Cleq%20%5Clambda%20%5Cend%7Bmatrix%7D%5Cright.)|  :white_check_mark:  | :white_large_square: | :clock9: |
|29| SoftShrink | ![equation](https://latex.codecogs.com/gif.latex?SoftShrinkage%28x%29%3D%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x%20-%20%5Clambda%2C%20x%20%3E%20%5Clambda%20%5C%5C%20x%20&plus;%20%5Clambda%2C%20x%20%3C%20-%20%5Clambda%20%5C%5C%200%2C%20-%20%5Clambda%20%5Cleq%20x%20%5Cleq%20%5Clambda%20%5Cend%7Bmatrix%7D%5Cright.)|  :white_check_mark:  | :white_large_square: | :clock9: |
|30| SoftMin | ![equation](https://latex.codecogs.com/gif.latex?Softmin%28x_i%29%3D%5Cfrac%7Be%5E%7B-x_i%7D%7D%7B%5Csum%20_j%20e%5E%7B-x_j%7D%7D)| :white_check_mark: | :white_large_square: | :clock9: |
|31| LogSoftmax | ![equation](https://latex.codecogs.com/gif.latex?LogSoftmax%28x_i%29%3Dlog%28%5Cfrac%7Be%5E%7Bx_i%7D%7D%7B%5Csum%20_j%20e%5E%7Bx_j%7D%7D%29)| :white_check_mark: | :white_large_square: | :clock9: |
|32| [Gumbel-Softmax](https://arxiv.org/pdf/1611.01144.pdf) | | :clock9: | :white_large_square: | :clock9: |

## Repository Structure
The repository has the following structure:
```python
- Echo # main package directory
| - Activation # sub-package containing activation functions implementation
| |- Torch  # sub-package containing implementation for PyTorch
| | | - functional.py # script which contains implementation of activation functions
| | | - weightedTanh.py # activation functions wrapper class for PyTorch
| | | - ... # PyTorch activation functions wrappers
| |- Keras  # sub-package containing implementation for Keras
| | | - custom_activations.py # script which contains implementation of activation functions
| - __init__.py

- Observations # Folder containing other assets

- docs # Sphinx documentation folder

- LICENSE # license file
- README.md
- setup.py # package setup file
- Smoke_tests # folder, which contains scripts with demonstration of activation functions usage
- Unit_tests # folder, which contains unit test scripts
```

## Setup Instructions
### To install Echo package follow the instructions below:

1. Clone or download [GitHub repository](https://github.com/digantamisra98/Echo).

2. Navigate to **Echo** folder:

  ```$ cd Echo```

3. Install the package with pip:

  ```$ pip install . ```

### To run the demo scripts:

1. From root folder navigate to **Smoke_tests** folder:

```$ cd Smoke_tests ```

2. Run demo script:

```$ python keras_activations_demo.py --activation aria2 ```

### To run unit tests:

1. From root folder navigate to **Unit_tests** folder:

```$ cd Unit_tests ```

2. Run unit test script:

```$ python -m unittest torch_activation_tests ```
