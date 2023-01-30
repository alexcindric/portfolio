How to run the software: 
First code in notebook contains all functions and imports needed, this needs to be run first but is only required to run once.
There are three code blocks after this:
The first contains the required commands to run the best case
The second contains the commands for the overshoot case
The third contains the commands for the new task case
Running any of these three blocks will generate the desired trajectories and run the controller. This will output the simulation matrix and the error matrix as well as an error plot. If you uncomment the last three lines of any of these blocks, it will save two csv files, one of the simulation matrix and one of the error matrix. 

Key Parameters:
velocity limits: 20

Results: 
Generally, the software works as expected, but is not perfectly computed. I am able to generate simulations with varying initial configurations of the youBot and the cube that yields the robot picking up the cube and placing it in the end position, but there are some less than ideal behaviors present (see remaining problems). Generally, tuned controllers have an error convergence to zero for most of the simulation, and the block does not fall from the grasp. 

Remaining problems in the code: 
-The transformation to/from the block frame stopped working as expected somewhere in the transition from trajectory generation to controller design. I adjusted the grasp configuration to account for it (below what should be the bottom of the cube aligns with near the center of the cube with the error). 

-Possibly due to this transformation issue, the error at the very last few seconds of the simulation begins to diverge from zero, regardless of the controller parameters.

-I could not find controller parameters that kept the error from momentarily diverging from zero around the midpoint of the simulation.

-The youBot placing the block through the chassis (no joint limits)
