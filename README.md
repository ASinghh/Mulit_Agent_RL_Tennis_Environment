# Mulit_Agent_RL_Tennis_Environment
Collaboration between two Identical RL agents
## Introduction
The project is the second one of the three projects required for graduating [Udacity's Deep Reinforcement Learning Nano Degree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893). The project is to train the agent/agents using the Deep Deterministic Policy Gradient(DDPG) to solve the Unity ML Reacher environment. The base code for implementation is borrowed from [Udacity's implementation of DDPG](https://github.com/udacity/deep-reinforcement-learning/blob/master/ddpg-bipedal/DDPG.ipynb), which I have modified and finetuned to solve the environment under consideration. 


## Project details
### Environment 
The environment under consideration is on of the many [Unity ML-Agents Toolkit's](https://github.com/Unity-Technologies/ml-agents) game environments. These environments enable games and simulations to serve as environments for training intelligent agents. The environment is called the Reacher Environment. In this environment, a double-jointed arm can move to target locations.The goal of the agent is to maintain its position at the target location for as many time steps as possible. Two separate versions of the Unity environment are considered for the project,<br/><br/>
    1. Environment with a single agent.<br/>
    2. Environment with 20 identical agents, each with its own copy of the environment.<br/><br/>
 A graphic rendering of the environment looks like the following GIF. <br/> <br/> <br/> ![Reacher](gifs/reacher.gif)

#### State Space
The Vector Observation space contains 33 variables corresponding to position, rotation, velocity, and angular velocities of the two arm Rigidbodies.

#### Action Space
The Vector Action space is Continuous and has a Size of 4, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
#### Rewards
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.

### Completion Criteria
Based on the instructions provided in the study material, in order to consider the environment solved, the agent must get an average score of +30 over 100 consecutive episodes for the 1st environment with a single agent or, must get an average score of +30 over 100 consecutive episodes over all agents of the second environment.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `p2_continuous-control/` folder, and unzip (or decompress) the file.

### Instructions
The file `ddpg_agent.py` contains the class required for creating the Deep Deterministic Policy Gradient agent that is used to solve the environment. It also contains a calss for creating Replay Buffers. The file `model.py` contains the Neural Network classes for creating the Actor and the Critic. These Network classes are used to define the Agent class in the file `ddpg_agent.py`. To understand the implementation of training iterations, read through the `Continuous_Control.ipynb` notebook. The parameters that solve the environment are saved in the checkpoint files `actor_ckpt.pth` and `critic_ckpt.pth`, for the Actor and the Critic, respectively.

### Report
The file `Report.pdf` contains information regarding the Learning Algorithm used for defining the agent, Plot of Rewards and Ideas for Future Work.

