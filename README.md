# Description of transfer learning RNN models

## 1. Continuous Stirred Tank Reactor (CSTR) Example

- Let us consider a second-order, exothermic, irreversible reaction from A to B


<img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/c1337cf1-eb78-47d7-b95b-1ce399d0ad10" alt = " Figure: Schematic diagram of a CSTR" width="250" height="250">


- The First Principle equation for this system are as follows:
- $$\frac{dC_A}{dt} = \frac{F}{V} (C_{A0} - C_A) - k_0 e^{-\frac{E}{RT}} C_A^2$$
- $$\frac{dT}{dt} = \frac{F}{V} (T_0 - T) + \frac{-\Delta H}{\rho_L C_P} k_0 e^{-\frac{E}{RT}} C_A^2 + \frac{Q}{\rho_L C_P V} $$

- Where,

    - 𝐶<sub>𝐴</sub>: Concentration of reactant A (kmol/m<sup>3</sup>)
   - 𝑇: Temperature of the reactor (K)
   - 𝐶<sub>𝐴0</sub>: Concentration of reactant A in the feed
   - 𝑄 :  Heat input rate (kJ/h)
   - F: feed volumetric flow rate (m<sup>3</sup>/h)
   - 𝑇<sub>0</sub>: Inlet temperature (K)

- The State and Manipulated variable for this system is:

    - States variables: _𝐱_=[𝐶<sub>A</sub>−𝐶<sub>As</sub>, 𝑇−𝑇<sub>s</sub>]
    - Control / Manipulated variables: _𝐮_=[𝐶<sub>A0</sub>−𝐶<sub>A0s</sub>, 𝑄−𝑄<sub>s</sub>]


> The full description of the process parameters can be found at [here](https://link.springer.com/book/10.1007/978-3-030-71183-2)

## 2.Development of transfer learning RNN model

- Select the source process with a similar configuration as the target process, and collect sufficient data from the source process
   > Please refer to the "source_model.ipynb" file
- Collect data from the target process, and adapt the pre-trained model to the target domain
   > Please refer to the "target_model_sufficient.ipynb" and "target_model_insufficient.ipynb" file
- Adaptation can be achieved via adapter-tuning or fine-tuning method
  > Adapter-tuning: adapt pre-trained model to the target domain via adaptation layer and fine-tuning
  > Fine-tuning: fine tuning pre-trained model with target data directly
  
## 3. Simulation results
![Testing error](https://github.com/user-attachments/assets/c8a68240-0dcb-4faf-a64c-101782c1224b)


## 4. Libraries and Tools used

[Tensorflow](https://www.tensorflow.org/): Deep learning framework used for building and training neural networks.

[Matplotlib](https://matplotlib.org/): Python plotting library for creating visualizations.

[SciPy](https://www.scipy.org/): Open-source library used for scientific and technical computing.

[scikit-learn](https://scikit-learn.org/): Machine learning library for Python used for data analysis and modeling.


## 5. Citation

The demonstration of these examples are adapted from the following literature work:

Xiao, M., C. Hu, and Z. Wu, “Modeling and Predictive Control of Nonlinear Processes Using Transfer Learning Method“, AIChE J., 69, e18076, 2023.

Additionally, you can find our paper [here](https://aiche.onlinelibrary.wiley.com/doi/full/10.1002/aic.18076)

