# Description of transfer learning RNN models

## 1. Continuous Stirred Tank Reactor (CSTR) Example

- Let us consider a second-order, exothermic, irreversible reaction from A to B


<img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/c1337cf1-eb78-47d7-b95b-1ce399d0ad10" alt = " Figure: Schematic diagram of a CSTR" width="250" height="250">


- The First Principle equation for this system are as follows:
- $$\frac{dC_A}{dt} = \frac{F}{V} (C_{A0} - C_A) - k_0 e^{-\frac{E}{RT}} C_A^2$$
- $$\frac{dT}{dt} = \frac{F}{V} (T_0 - T) + \frac{-\Delta H}{\rho_L C_P} k_0 e^{-\frac{E}{RT}} C_A^2 + \frac{Q}{\rho_L C_P V} $$

- Where,

   - 𝐶_𝐴: Concentration of reactant A (kmol/m3)
   - 𝑇: Temperature of the reactor (K)
   - 𝐶_𝐴0: Concentration of reactant A in the feed
   - 𝑄 :  Heat input rate (kJ/h)
   - F: feed volumetric flow rate (m3/h)
   - 𝑇0: Inlet temperature (K)


- The State and Manipulated variable for this system is:

    - States variables: 𝐱=[𝐶_𝐴−𝐶_𝐴𝑠, 𝑇 −𝑇_𝑠 ]
    - Control / Manipulated variables: 𝐮=[𝐶_𝐴0−𝐶_𝐴0𝑠, 𝑄 −𝑄_𝑠 ]


> The full description of the process parameters can be found at [here](https://link.springer.com/book/10.1007/978-3-030-71183-2)

## 2.Development of transfer learning RNN model

- Select the source process with a similar configuration as the target process, and collect sufficient data from the source process
   > Please refer to the "source model." file

- The RNN model input and output are as follows:
    - Input: System initial state variable 𝐱_𝟎(𝑡_𝑘), and control variables 𝐮(𝑡_𝑘).
    - Output: Future state dynamics 𝐱(𝑡_𝑘+Δ) are predicted for one sampling period ∆.
<p align="center">
<img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/332a1da6-9b89-4e04-a6b3-1b5c90185319" width="600" height="250">
</p>


## 5. Libraries and Tools used

[PyTorch](https://pytorch.org/): Deep learning framework used for building and training neural networks.

[Matplotlib](https://matplotlib.org/): Python plotting library for creating visualizations.

[SciPy](https://www.scipy.org/): Open-source library used for scientific and technical computing.

[scikit-learn](https://scikit-learn.org/): Machine learning library for Python used for data analysis and modeling.

[similaritymeasures](https://github.com/similaritymeasures/similaritymeasures): Python library for computing similarity measures between curves or time series data.


## 6. Citation

The demonstration of these examples are adapted from the following literature work:

Zheng, Yingzhe, Cheng Hu, Xiaonan Wang, and Zhe Wu. "Physics-informed recurrent neural network modeling for predictive control of nonlinear processes." Journal of Process Control 128 (2023): 103005.

Additionally, you can find our paper [here](https://www.sciencedirect.com/science/article/pii/S0959152423000847)

