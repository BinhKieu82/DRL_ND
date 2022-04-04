# Project 1: Navigation

### Introduction

The first project of Deep Reinforcement Learning ND - Udacity. The target is build a model that enables an agent to navigate and collect at least 13 yellow bananas in a row of 100 episodes, in a large & square world.  

![](pics/BananaGIF_20200707113405_slvd_15.gif)

Environment:  
Enviroment is a large & square world that contains yellow & blue bananas, any banana collected from agent will be added accordingly.  
- Reward scheme: +1 for collecting a yellow banana; -1 for collecting a blue banana. The goal of the agent is to collect as many yellow bananas as possible while avoiding blue bananas.
- State space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.

Agent:  
The agent has to learn how to best select actions to solve project's task.
- Action space:  
    - **`0`** - move forward.
    - **`1`** - move backward.
    - **`2`** - turn left.
    - **`3`** - turn right.

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

2. For Win10 64bit user:  Place the file in the `~/RL/` folder, unzip the file. Copy the Navigation.ipynb in DRLND GitHub repository, in the `p1_navigation/` folder & place into `~/RL/` folder then edit the following line to ignite Banana Unity environment:
 `env = UnityEnvironment( os.path.join( os.environ['HOME'], './Banana.x86_64/Banana.exe' ) )` 

### Instructions

#### Create an environment
If you want to work locally, please follow the [env setup from Udacity](https://github.com/udacity/deep-reinforcement-learning#dependencies). I prefer you working locally since it allows you view your agent live while training in the Banana environment.

#### Use the notebook
I refer here to the `Navigation.ipynb` Jupyter Notebook file

#### Create your own model - QNetwork: model.py
A deep learning model with 2 linear hidden layers taking state_size as input shape, number of units by default as 128 & 64 respectively, they are come after by relu activation functions. The linear output layer takes the second hidden layer out_channels & action_size as params, it is also followed by relu activation function.
#### Create Agent class: dqn_agent.py
Agent needs to be defined as an object which has its own properties, methods & functions that fit for project's purposes

##### Training
Reset your kernel first.

If you wish you can adapt the requirement when the environment is considered as solved in section four: `CRIT_SOLVED = 13 #How many Bananas must be collected to succeed?`

Execute the code in sections

* 1. Start the Environment
* 2. Define the State and Action Spaces
* 3. Train the agent with DQN

The output file will be generated in the current directory with a current time stamp as prefix of the `navigation.pth`.

##### Testing
Execute the code in sections
* 1. Start the Environment
* 2. Examine the State and Action Spaces
* 4. Testing the trained Agent in action



