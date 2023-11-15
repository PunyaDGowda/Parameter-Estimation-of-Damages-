# Parameter-Estimation-of-Damages-
PINNs leverages the governing physical laws that dictate the behavior of time-dependent systems to act as a regularization agent. Parametric PINNs are used to identify
and characterize damage parameters within the structural domain. Ultrasonic imaging with a two-dimensional wave equation for isotropic material is used for simplicity. The stationary ultrasound excitation source is modelled with a five-cycle Hanning window sinusoidal burst which is applied at the center of the plate. The damage parameters are modelled using Gaussian function with critical parameters such as location, size and extent of damage which are to be detected. For simplicity,
only the damage location is parameterized, while damage size and magnitude is kept fixed. The underlying physics governing the behavior of the damage model is
encoded into the loss function in the form of damage equation, complemented by the inclusion of boundary and initial loss terms. The parametric PINN approach is summarized as follows:

![image](https://github.com/PunyaDGowda/Parameter-Estimation-of-Damages-/assets/91265967/3f815e3f-e1b2-49af-92ed-3fb6ac793430)

The repository currently contains forward PINN and parametric PINN for one location parameter (1 pair = 2 damage locations along x and y directions). Traditional PINN implementation faces difficulty to converge, and due to the very low order of displacement field of magnitude, 1e-26 causes exploding loss value. This makes the model optimize for a long duration of about 2-3 days. Hence, two alternative scaling approach is used to achieve convergence. One is the scaling the governing PDE and other is scaling the inputs and outputs of the neural network keeping the PDE same. 

The scaled PDE is obtained as below :

![image](https://github.com/PunyaDGowda/Parameter-Estimation-of-Damages-/assets/91265967/d1b0d302-775b-4e81-8c62-df7d69af28d4)

The scaling of inputs and outputs of the network is summarized as follows:

![image](https://github.com/PunyaDGowda/Parameter-Estimation-of-Damages-/assets/91265967/62da7f7e-c397-49bb-a313-92de46ff1981)

Nevertheless, the PINN needed additional sampling points near source region to initiate the source accurately. The results obtained are attached in this repository.

The parametric PINN implementation is working fine with only one damage parameter. Additional damage parameters should be added into the network to check the training capability of the model. Currently working to incorporate 2 damage parameters (2 pairs of damage location).



