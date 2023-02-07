# Euler Method Automated Learning Rate

Proposal:

We propose an algorithm that utilizes Euler's method for autonomous systems to find the step-size parameter for an RL agent's learning rate. The algorithm will utilize the current gradient information from the agent's policy to determine the optimal step-size to control the learning rate. Specifically, the algorithm will utilize the current gradient to calculate the step-size, and then the step-size will be adjusted based on the performance of the agent.

- Backwards Euler Method
$y_{n+1} = y_{n} + hf(t_{n+1},y_{n+1}) \del t$

Where y is the value function (State-Action, State, or Action)

Methods:

1. Calculate the gradient of the policy using the current state-action pairs.
2. Use Euler's method to calculate the step-size for the learning rate.
3. Adjust the step-size based on the performance of the agent.
4. Repeat steps 1-3 until the learning rate step-size is optimal.

This algorithm has the potential to significantly improve the performance of RL agents by allowing them to adaptively tune the learning rate based on their current policy gradient. Currently testing this algorithm in a simulated environment and real environments and are comparing its results to those of standard RL algorithms.

## Finding the step-size in the Euler Method
Some might wonder about finding the step size parameter h in the Euler method and this is where a Taylor series expansion with the Lagrange remainder is utilized, the error at each step is bound by the remainder, since a new error $\delta$ is introduced at each step, then a bound must be put x to estimate the error. If there are n steps then n = 1/h, but numerical approximations would likely give a tighter approximation. 

## Adaptability
To ensure that the algorithm is able to adapt to changes in the underlying environment, we will also incorporate a moving average of the performance metric over time. This will allow the algorithm to adjust the learning rate step-size in response to changing conditions.

Finally, we will use a validation set to test the accuracy of our algorithm and ensure that it is able to adapt to changing conditions in an effective manner. Once this is done, we can evaluate the algorithm's performance and make any necessary adjustments to improve its effectiveness.
