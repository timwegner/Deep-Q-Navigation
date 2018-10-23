# Deep Q Navigation Project

Solving a simulation task of collecting bananas using a DQN agent.

## Environment details
The objective of the Unity simulation is to collect as many yellow bananas as possible while avoiding the blue bananas. 

**Action space:** This simulation contains a single agent that navigates the environment. It can perform four actions at each time step:
* 0 - walk forward
* 1 - walk backward
* 2 - turn left
* 3 - turn right

**State space:** The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction.

**Reward function:** A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

**DQN structure:** Similar to Google DeepMind's DQN Nature paper, "Human-level control through deep reinforcement learning", the adopted learning algorithm is a Deep Q-Learning algorithm. As the input vector is a state space instead of raw pixel data, a fully connected layer is used in the first layer instead of a convolutional neural network:
* Fully connected layer 1: with input = 37 state spaces and output = 128 state spaces
* Fully connected layer 2: with input = 128 and output = 64
* Fully connected layer 3: with input = 64 and output = 4, (for each of the 4 actions)

**Parameters used in the DQN algorithm:**
* Maximum steps per episode: 1000
* Starting epsilion: 1.0
* Ending epsilion: 0.01
* Epsilion decay rates: 0.7, 0.8, 0.9 and 0.99

## Installation Instruction

Python 3.6 is required. The program requires PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

```
git clone https://github.com/udacity/deep-reinforcement-learning.git  
cd deep-reinforcement-learning/python  
pip install .
```

Run the following to create drlnd kernel in ipython so that the right unity environment is loaded correctly:  


```python -m ipykernel install --user --name drlnd --display-name "drlnd"```

## Getting Started

Place <mark>report.ipynb</mark> in the folder <mark>p1_navigation/</mark> together with the following two files:

* dqn_agent.py - contains the DQN agent code. 
* model.py - contains neural network class for used as Q function

The Unity Banana collection environment can be downloaded from here: 

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)  
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)  
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)  
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)  

Choose the environment suitable for your machine. Unzipping will create another Banana_xxxx folder. For example, if the Linux Banana environment is downloaded, ```Banana_Linux``` will be created. 

Run ```p1_navigation/report.ipynb```

Enter the right path for the Unity Banana environment in report.ipynb. 

Run the remaining cell as ordered in ```report.ipynb``` to train the DQN agent. 
