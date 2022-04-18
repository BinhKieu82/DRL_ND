[//]: # (Image References)
[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"

# Project 2: Continuous Control

### Introduction

The second project of Deep Reinforcement Learning ND - Udacity. The target is build a model that enables an agent/20 agents (double-jointed arm) move to target locations. The goal of the agent is to maintain its position at the target location for as many time steps as possible.  

![Trained Agent][image1]

Environment:  
The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm.  
- A reward of +0.1 is provided for each step that the agent's hand is in the goal location.  
- State space has 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm..

Agent:  
Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
- Action space is a continuous range of -1, 1:  

#### Solving the Environment

Note that your project submission need only solve one of the two versions of the environment. 

##### Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.

##### Option 2: Solve the Second Version

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents.  In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).  Specifically,
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent.  This yields 20 (potentially different) scores.  We then take the average of these 20 scores. 
- This yields an **average score** for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 

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

#### Create an environment
If you want to work locally, please follow the [env setup from Udacity](https://github.com/udacity/deep-reinforcement-learning#dependencies). I prefer you working locally since it allows you view your agent live while training in the Banana environment.

#### Use the notebook
I refer here to the `Continuous_Control.ipynb` Jupyter Notebook file

#### Create your own model - Deep Deterministic Policiy Gradient (DDPG) algorithm: model.py
DDPG algorithm comprises two networks: Actor & Critic.  
- Actor network composes 1 linear hidden layer taking state_size (33) as input shape, number of units by default as 256, it is come after by *relu* activation functions. The linear output layer takes the second hidden layer out_channels & action_size as params, it is followed by *tank* activation function.
- Critic network composes 3 linear hidden layers taking state_size (33) as input shape, number of units by default as 256, 256 & 128 respectively. They are come after by *leaky_relu* activation functions that help to avoid *vanishing gradient* problem during training. The linear output layer takes the third hidden layer out_channels & action_size as params, it is also followed by *leaky_relu* activation function.
#### Create Agent class: ddpg_agent.py
Agent needs to be defined as an object which has its own properties, methods & functions that fit for project's purposes

#### Create Multi Agents class: multi_agents.py
More Agents are addes giving more interaction/noise to each other. Each is defined as an object which has its own properties, methods & functions that fit for project's purposes

##### Training
Reset your kernel first.

Execute the code in sections

* 1. Start the Environment
* 2. Define the State and Action Spaces
* 3. Train the agent with DDPG

The output files will be generated in the *save_models* directory for both two networks: `checkpoint_actor_20agents.pth` and `checkpoint_critic_20agents.pth`.

##### Testing
Execute the code in sections
* 1. Start the Environment
* 2. Examine the State and Action Spaces
* 4. Test the trained model



