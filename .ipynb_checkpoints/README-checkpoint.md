# udacity-drl-ddpg

This is a project as part of the Udacity Deep Reinforcement Learning nanodegree.

## Introduction

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

There were 2 options for this project based on the number of agents, either 1 agent or 20 agents.  The option selected for this project is the configuration with 20 simultaneous agents.  The problem is considered solved when the average score over all the agents is above 30, where the average is over all 20 agents and 100 consecutive episodes. 

## Requirements

The work for this project was done in AWS SageMaker Sudio (classic).  This requires you to clone the [deep-reinforcement-learning repo](https://github.com/udacity/deep-reinforcement-learning), and get the unity environment with visualization, found [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip).  The zip file should be unzipped and placed in the p2_continuous-control folder.

The ddpg_agent.py file contains the agent code used in the environment, and the model.py file contains the Q actor and critic network code used by the agent.  Note that both of these files are adapted from the solutions to the ddpg-pendulum section of this course ([see here](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum)).

## Environment setup

The work for this project was performed in AWS SageMaker Studio (Classic).  This takes a bit of setup to prepare.  The steps to run the main notebook (Navigation.ipynb) are as follows:

0. To use the unityagents package, there needs to be one modification made to the requirements.txt file in the path Value-based-methods/python/requirements.txt.  The torch version needs to be changed from torch==0.4.0 to torch>=0.4.0.
1. Open the notebook Navigation.ipynb, and select the following parameters
    - Image: "Data Science 2.0"
    - Kernel: Python 3
    - Instance type: ml.g4dn.xlarge
    - Start-up script: No script
2. Once that instance starts up, go into the image terminal of that instance and execute the shell script build_env.sh. This will create the drlnd virtual environment.
3. Once that is complete, close the image terminal and go back to the notebook.  Select change the notebook environment, and you should now be able to select the kernel associated with the drlnd conda virtual environment.
4. Now the Navigation notebook is ready to be executed!

## Output

The main continuou-control-ddpg.ipynb notebook will output a figure of the scores vs epsiode number.