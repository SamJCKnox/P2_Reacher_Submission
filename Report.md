# Report: Reacher - Continuous Control

The method used to solve this is DDPG, a method analogous to an actor-critic method, where there is an acotr neural network which maps the state directly to actions for each motor. This is performed using a double fully connected hidden layer network with relu activation functions and an output fully connected layer with a tanh activation function. This network during the update, is performing **gradient ascent** where the agent is trying to maximise the reward.
This method also has a critic which is a value based method, which judges the output of the actor and is used to calculate the updates for the actor. The network used in the critic is a fully connected layer, which then goes through a batch normalization and then is concatinated with the actor output, before going through another hidden layer and an output layer. All the activation functions are linear and relu functions as shown in the below figure.

![alt text](https://github.com/SamJCKnox/P2_Reacher_Submission/blob/master/ActorCriticDrawing.png)

##Hyperparameters
Network parameters apply to both actor and critic networks:
fc1_units = 400
fc2_units = 300

Agent parameters:
tau = 1e-3
gamma = 0.9
buffer_size = int(2e6)
batch_size = 1024
batches_per_update = 10
lr_actor = 1e-3
lr_critic = 1e-3
weight_decay = 0




## Modifications
Many modifications were made as it was found that this method did not naturally want to find a solution without a lot of help!

### Negative reward
Small negative rewards are given to all timesteps where the arm is not inside the sphere. This didn't make a huge impact but it 'feels' right. This small negative reward was not used in calculating the average reward at the end.

### Batch normalisation
A batch normalisation step was introduced in the critic network which seemed to make the agent function much better.

### Sparse Learning
The 



![alt text](https://github.com/SamJCKnox/P2_Reacher_Submission/blob/master/ScoresDDPG.png)


