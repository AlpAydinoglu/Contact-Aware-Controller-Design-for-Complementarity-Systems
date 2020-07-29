Here, you can find the code for the conference paper 'Contact-Aware Controller design for Coplementarity Systems' that was presented in ICRA2020 and also the code for the extended version of the paper that was recently submitted to T-R0.

# Dependencies

The linear complementarity problems (LCPs) generated by this library are solved using [http://pages.cs.wisc.edu/~ferris/path.html](PATH). 

The bilinear matrix inequalities are solved using http://www.penopt.com/penbmi.html (PenBMI). Please contact the creators in order to obtain the license.

Optimization problems are formulated using https://yalmip.github.io/ (YALMIP).

`pathlcp`, `PenBMI`, `yalmip` will need to be in the MATLAB path for the examples to run.

# Extended Version
# Stabilization of Linear Complementarity Systems via Contact-Aware Controllers
Submitted to T-RO

arXiv link: Fill

Video: Fill

## Functionality
The library can be used to design contact-aware controllers for linear complementarity systems (requires YALMIP and PenBMI). The code can be used to design controllers for any linear complementarity system model and does not require the P-matrix assumption. If F is a P-matrix, pick W=I and design the controller. For the cases where the P-matrix assumption does not hold, we provide an algorithm to find the matrix W and use it in the controller design. If the algorithm fails, pick W=0 and do the controller design.

The designed controller can be tested on the linear complementarity system (recommended as a sanity check). The code can be used to evaluate the dynamics of any linear complementarity model as long as the x-trajectory is unique (requires PATH).

After finding a W, you can just plug in your system parameters using the code provided in `design_algorithm` and design a controller. In general, it is recommended to verify the controller solving an SDP (after fixing the gain matrices).

## Examples
`acrobot`: Controller design and its implementation on an acrobot with soft joint limits

`cartpole`: Controller design and its implementation on a cartpole with soft walls

`partial_feedback`: Controller design and its implementation on a model with a cartpole and two carts, where the cart in the middle is not observed

`box_with_friction`: Controller design and its implementation on a quasi-static model of a box standing on a surface with Coulomb friction

`3_legged_table`: Controller design and its implementation on a quasi-static model of a 3-legged table standing on a surface with Coulomb friction

`2D_simple_manipulation`: Controller design and its implementation on a quasi-static model of a box standing on a surface with Coulomb friction manipulated by two robotic arms

`high_dimensional`: Controller design and its implementation on a high dimensional example with 8 states and 10 contacts (four carts example)

# ICRA2020 Conference Paper
# Contact-Aware-Controller-Design-for-Complementarity-Systems
Presented in ICRA2020

arXiv link: https://arxiv.org/abs/1909.11221

Video: https://www.youtube.com/watch?v=WS4nMXtCxcQ

## Functionality
The library can be used to design contact-aware controllers for linear complementarity systems (requires YALMIP and PenBMI). The code can be used to design controllers for any linear complementarity system model as long as the P-matrix assumption holds. It is important to note that the set related to `\bar{\lambda}` needs to be generated specifically wrt the system at hand. Make sure the S-procedure terms related to that set is correct for your model before running the code to design a controller.

The designed controller can be tested on the linear complementarity system (recommended as a sanity check). The code can be used to evaluate the dynamics of any linear complementarity model as long as the P-matrix assumption holds (requires PATH).

The designed controller can be tested on the nonlinear complementarity system model (requires PATH).

## Examples
`acrobot`: Controller design and its implementation on an acrobot with soft joint limits

`cartpole`: Controller design and its implementation on a cartpole with soft walls

`partial_feedback`: Controller design and its implementation on a model with a cartpole and two carts, where the cart in the middle is not observed


