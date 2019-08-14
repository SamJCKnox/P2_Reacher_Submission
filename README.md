# P2_Reacher_Submission
In this problem, the environment is a robotic arm with two pivots, each of which have 2 motors which can be given a torque value of betweeon -1 and 1. The state space is 33 values for each robotic arm. In the single directory, the agent works solely on a single arm, whereas, in multi, the agent works on 20 arms simultaneously, storing all the (S,A,R,S') tuples in one large replay buffer. The aim of the environment is to keep the end of the robotic arm inside a floating sphere for as long as possible.

The method used to solve this is DDPG, a method analogous to an actor-critic method, where there is an acotr neural network which maps the state directly to actions for each motor. This is performed using a double fully connected hidden layer network with relu activation functions and an output fully connected layer with a tanh activation function. This network during the update, is performing **gradient ascent** where the agent is trying to maximise the reward.
This method also has a critic which is a value based method, which judges the output of the actor and is used to calculate the updates for the actor. The network used in the critic is a fully connected layer, which then goes through a batch normalization and then is concatinated with the actor output, before going through another hidden layer and an output layer. All the activation functions are relu functions.

## Modifications
Many modifications were made as it was found that this method did not naturally want to find a solution without a lot of help!

### Negative reward
Small negative rewards are given to all timesteps where the arm is not inside the sphere. This didn't make a huge impact but it 'feels' right. This small negative reward was not used in calculating the average reward at the end.

### Batch normalisation
A batch normalisation step was introduced in the critic network which seemed to make the agent function much better.

### 
