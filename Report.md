# Report

## Learning Algorithm

The continous control problem was framed as a reinforcement learning task. To solve it the Deep Deterministic Gradient Policy was chosen.

The basis for the implementation was the research paper [*'Continuous control with deep reinforcement learning'*](https://arxiv.org/abs/1509.02971).

The DDPG algorithm is an actor critic algorithm, that uses two separate neural networks. The actor network is used to find a deterministic policy and choose the best action. The critic network uses this action to count the action-value and provide feedback for the actor network.
As the algorithm needs to run on a continous action space, the exploration is a challange. To provide means of exploration for the actor network, a noise is added to the weights.
To maximze the use of already examined experience tuples a so called Experience Replay mechanism is used. It basically puts the experience tuples in a fixed size pool, from which they are sampled randomly. This also helps to avoid any unwanted correlation between chronologically adjacent actions.
Both actor and critic networks have their weights optimised on the basis of temporal difference. Each network respectively has a local and target copy. The target copy is what we use as a target for the weights optimisation of the local network. When the new valu for the local weights is established, the previous value of the local weights is used to update the target. However the target weights are not updated all at once, but so called 'soft updates' are used, that are a way of gradually making the target weights closer to the local weights (the process is controlled by the factor TAU).

The actor network consists of three fully connected laers, out of which first two use ReLu activation functions, and the last one uses TanH activation function, to keep the output values in the range between -1 and 1. Also the batch normalisation is used to prevent different orders of magnitude of input parameters to influence the learning process.

The critic network differs from the actor network only in this, that the last fully connected layer has no activation function.
The definitions of both networks can be found in the model.py file.

### Hyperparameter values

Hyperparameter values were mainly set according to the research paper 'Continuous control with deep reinforcement learning', with main difference being higher value of actor network learning rate, to make the model converge faster. Also the values for the noise parameter were changed to give more space for exploration.

```python
BUFFER_SIZE = int(1e6)  # replay buffer size
BATCH_SIZE = 128        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 1e-3         # learning rate of the actor
LR_CRITIC = 1e-3        # learning rate of the critic
WEIGHT_DECAY = 0        # L2 weight decay
LEARN_EVERY = 20        # learning timestep interval
LEARN_NUM   = 10        # number of learning passes
GRAD_CLIPPING = 1.0     # Gradient Clipping

# Ornstein-Uhlenbeck noise parameters
OU_SIGMA  = 0.15
OU_THETA  = 0.05
# 
EPSILON       = 1.0     # for epsilon in the noise process (act step)
EPSILON_DECAY = 1e-6```

## Plot of Rewards

## Ideas for Future Work
