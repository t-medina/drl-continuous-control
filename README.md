[//]: # (Image References)

[trained_agent]: trained.gif "Trained Agent"
[untrained_agent]: untrained.gif "Untrained Agent"


# Project 2: Continuous Control

### Introduction

This project implements a DDPG agent capable of moving a double-jointed arm to target locations.

Untrained Agent             |  Trained Agent
:-------------------------:|:-------------------------:
![Untrained Agent][untrained_agent] | ![Trained Agent][trained_agent] 

 

For this project, the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment was used.

A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to **position**, **rotation**, **velocity**, and **angular velocities** of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between **-1** and **1**.

The task is episodic, and in order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip). You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the same folder as the `Continuous_Control.ipynb` file, and unzip (or decompress) the file. 

### Instructions

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drl python=3.6
	conda activate drl
	```
	- __Windows__: 
	```bash
	conda create --name drl python=3.6 
	activate drl
	```
	
2. Navigate to the location where you cloned this repository, and install the python dependencies.
    ```bash
    pip install .
    ```

3. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drl` environment.  
    ```bash
    python -m ipykernel install --user --name drl --display-name "drl"
    ```

4. Before running code in a notebook, change the kernel to match the `drl` environment by using the drop-down `Kernel` menu. 

5. Follow the instructions in `Continuous_Control.ipynb`:
    - Cells in sections 1, 2 and 3 will allow you to initialize and explore the environment
    - Cells in section 4 include the training of the agent
    - Cells in section 5 include the testing of the trained agent. Saved model weights of a successfully trained agent are included in this repository as well (both actor and critic: `actor_weights.pth` and `critic_weights.pth`), so you can skip training and go straight to this section to see a trained agent perform.