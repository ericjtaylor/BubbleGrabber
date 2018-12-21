# Project 2: Continuous Control

### Results

My trained agent was able to successfully meet specifications by performing 100 sessions with average scores of ~37 points, exceeding the project requirements of 30 points.  

### Solution

The agent was implemented as a DDPG agent with 3 fully connected hidden layers with 128 nodes each for both the actor and critic networks.  

ReLU non-linearities were used, except for the output layer where tanh was used in order to provide output control in the range of +\- 1.

Notable changes deviating from the template DDPG implementation of the course include:

* adding batch normalization after the first layer (following the non-linearity) of both the actor and critic networks  
* adding gradient clipping as recommended in the course project notes  

Training parameters were:  

BUFFER_SIZE = int(1e6)  # replay buffer size
BATCH_SIZE = 128        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 2e-4         # learning rate of the actor 
LR_CRITIC = 2e-4        # learning rate of the critic
WEIGHT_DECAY = 0        # L2 weight decay
UPDATE_EVERY = 1        # update steps

Training was performed for 2000 episodes. The target performance was achieved around 1000 episodes with further improvements continuing until leveling off around 1600 episodes.  

### Further Work

The above hyperparameters were not extensively explored, and could certainly be optimized.  

The network design is also not optimized, and the number of hidden units is certainly not optimal.  
