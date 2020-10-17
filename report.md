# Report

This report describes my implementation to solve the reacher project.

## Learning Algorithm

The implementation here is a Deep Deterministic Policy Gradient Algorithm. Some example code can be found on udacity's official github [repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-bipedal). Some alterations have been done on the example code provided on the deep reinforcement leanring repository.

## My Continuous Control

DDPG is a type of actor-critic methods which are applicable to continuous state space action. For more information about DDPG please read this [article](https://arxiv.org/pdf/1509.02971.pdf). DDPG trains simultaneously two networks: An actor (selects the optimal (deterministic) policy based on the current state) and a critic (approximates the value function of the state-action pair).

### Actor

The actor neural network consist of two hidden layer. The input layer has 33 neurons. The first hidden layer has 220 neurons and the second hidden layer has 130 neurons. The output layer has 4 neurons.

Batch normalization is performed after the first hidden layer and a tanh function is applied at the output layer so that the result can be in between [-1, 1].

The actor also add noise to its action as a Ornstein-Ulenbeck process with mu(0), theta(0.03) and sigma(0.02). 

### Hyper-Parameters

- Replay Buffer Size: 1000000
- Batch Size: 280
- Gamma (discount factor): 0.99
- Tau (soft update): 0.001
- Learning Rate (Actor): 0.00005
- Learning Rate (Critic): 0.00005
- Weight Decay: 0