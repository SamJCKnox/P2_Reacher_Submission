# Project 2: Reacher - Continuous control
Submission of Reached problem using DDPG
## The Environment
In this problem, the environment is a robotic arm with two pivots, each of which have 2 motors. The aim is for the agent to maintain the end of the arm (dark blue sphere) inside the target (translucent sphere).

### State
The state space is 33 variables corresponding to position, rotation, velocity, and angular velocities for each robotic arm. 
### Actions
Each robotic arm has 4 motors which can be given a torque value of betweeon -1 and 1, hence the environment must be given a vector of length 4.
### Rewards
The agent recieves a +0.1 reward for each timestep that the agent remains in contact with the target sphere.
### Solution
The aim of the environment is to keep the end of the robotic arm inside a target sphere so that the average score across all 20 arms for 100 consequtive episodes is above 30.

## Getting Started
The dependencies that are required can be installed using the following:

First, install conda: https://www.anaconda.com/distribution/#download-section

Next, create a new conda enviornment and activate

`conda create -n Reacher python=3.6.3 anaconda`

`conda activate Reacher`

Next install pytorch using:
`conda install pytorch=0.4.0 cuda80 -c pytorch`

And ml-agents ugin:
`pip install mlagents==0.4.0`

Finally, the environment and scripts are downloaded from

`git clone https://github.com/SamJCKnox/P2_Reacher_Submission.git`

## Instructions
The `DDPGMultiAgent` script is the header which calls all scripts required to run. Run all sections to train the agent. Outputs will show how the agent is performing. The last section shows the agent evaluation.

The networks trained in the current outputs of the Jupyter Notebook are in `BenchmarkNetworks`, copy these into the root directory to view in the evaluation section.

`Report.md` shows the architecture of the networks with the hyperparamteres.






