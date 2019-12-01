# Continous Control 

Continous control problem in a Unity environment solved with Deep Deterministic Policy Gradient

## Project details

In this Unity environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

he task is episodic, and in order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes.

## Getting Started

To run this repo on your local machine, first clone this repository https://github.com/udacity/deep-reinforcement-learning

Follow the instruction in the README file in the root of the folder to install the Python environment needed to run the whole project. 

Follow the instructions in the README of p2_continuous-control (https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control) to install the correct environment for Your operating system. 
Note that there are two versions of the environment - with a single agent and with twenty agents acting simoultanously. In this repo the One agent version is used).
You don't need to install Unity separately, as Unity Agents are already configured in the environment. 

Make sure you have CUDA Drivers installed.

Finally place the files from this repo into the p2_continuous-control folder of the deep-reinforcement-learning repository and run the Jupyter Notebook Navigation.ipynb. Make sure the name of the environment you downloaded matches the one specified in the code 
`env = UnityEnvironment(file_name='/data/Reacher_One_Linux_NoVis/Reacher_One_Linux_NoVis.x86_64')`

## Instructions

To train the agent from scratch just run the ddpg function.
