# Mulit Agent RL- Tennis Environment

## Introduction
The project is the second one of the three projects required for graduating [Udacity's Deep Reinforcement Learning Nano Degree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893). The project is to train two agents using the Deep Deterministic Policy Gradient(DDPG) to solve the Unity ML Tennis environment. The base code for implementation is borrowed from [Udacity's implementation of DDPG](https://github.com/udacity/deep-reinforcement-learning/blob/master/ddpg-bipedal/DDPG.ipynb), which I have modified and finetuned to solve the environment under consideration. 


## Project details
### Environment 
The environment under consideration is on of the many [Unity ML-Agents Toolkit's](https://github.com/Unity-Technologies/ml-agents) game environments. These environments enable games and simulations to serve as environments for training intelligent agents. In the environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. The goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.<br/> <br/> <br/> ![Tennis Collaboration](gifs/tennis.gif)

#### State Space
The Vector Observation space contains 33 variables corresponding to position, rotation, velocity, and angular velocities of the two arm Rigidbodies.

#### Action Space
The Vector Action space is Continuous and has a Size of 4, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
#### Rewards
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.

### Completion Criteria
After each episode, the rewards received by each agent should be added(without discounting), to get a score for each agent. This should yield 2 (potentially different) scores. Taking the maximum of these 2 scores yields a single score for each episode. The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `p3_collab-compet/` folder, and unzip (or decompress) the file.


### Instructions
The file `ddpg_agent.py` contains the class required for creating both the Deep Deterministic Policy Gradient agents that are used to solve the environment. It also contains a calss for creating Replay Buffers. The file `model.py` contains the Neural Network classes for creating the Actor and the Critic. These Network classes are used to define the Agent class in the file `ddpg_agent.py`. To understand the implementation of training iterations, read through the `Tennis.ipynb` notebook. The parameters that solve the environment are saved in the checkpoint files `checkpoint_actor1.pth`, `checkpoint_actor2.pth`, `checkpoint_critic1.pth` and `checkpoint_critic2.pth`.

### Report
The file `Report.pdf` contains information regarding the Learning Algorithm used for defining the agent, Plot of Rewards and Ideas for Future Work.

