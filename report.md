# Report

This report describes my implementation to solve the reacher project.

## Learning Algorithm

The implementation here is a Deep Deterministic Policy Gradient Algorithm. Some example code can be found on udacity's official github [repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-bipedal). Some alterations have been done on the example code provided on the deep reinforcement leanring repository.

## My Continuous Control

DDPG is a type of actor-critic methods which are applicable to continuous state space action. For more information about DDPG please read this [article](https://arxiv.org/pdf/1509.02971.pdf). DDPG trains simultaneously two networks: An actor (selects the optimal (deterministic) policy based on the current state) and a critic (approximates the value function of the state-action pair).

### Actor

The actor neural network consist of two hidden layer with ReLu function as activation function. The input layer has 33 neurons. The first hidden layer has 220 neurons and the second hidden layer has 130 neurons. The output layer has 4 neurons.

Batch normalization is performed after the first hidden layer and a tanh function is applied at the output layer so that the result can be in between [-1, 1].

The actor also add noise to its action as a Ornstein-Ulenbeck process with mu(0), theta(0.03) and sigma(0.02). 

### Critic

The critic neural network consist of two hidden layer with ReLu function as activation function. the input layer is 33 neurons. The first hidden has 220 neurons, however, 4 additional input (equal to the action space) is added as input to the second hidden layer. The second hidden layer has 130 neurons whereas the output layer only has 1 neuron.

Batch normalization is performed after the first hidden layer as well.

### Hyper-Parameters

- Replay Buffer Size: 1000000
- Batch Size: 280
- Gamma (discount factor): 0.99
- Tau (soft update): 0.001
- Learning Rate (Actor): 0.0001
- Learning Rate (Critic): 0.0001
- Weight Decay: 0

Training Results:
```bash
Average score of episodes 1-11: 0.6869999846443534
Average score of episodes 11-21: 1.3129999706521631
Average score of episodes 21-31: 1.6949999621137977
Average score of episodes 31-41: 2.064999953843653
Average score of episodes 41-51: 2.787999937683344
Average score of episodes 51-61: 3.19199992865324
Average score of episodes 61-71: 4.3329999031499025
Average score of episodes 71-81: 3.823999914526939
Average score of episodes 81-91: 5.908999867923558
Average score of episodes 91-101: 5.230999883078039
Average score of episodes 101-111: 5.531999876350165
Average score of episodes 111-121: 7.218999838642776
Average score of episodes 121-131: 8.644999806769192
Average score of episodes 131-141: 8.627999807149171
Average score of episodes 141-151: 9.133999795839191
Average score of episodes 151-161: 10.217999771609902
Average score of episodes 161-171: 11.64899973962456
Average score of episodes 171-181: 10.953999755159021
Average score of episodes 181-191: 13.431999699771405
Average score of episodes 191-201: 12.79099971409887
Average score of episodes 201-211: 11.67099973913282
Average score of episodes 211-221: 10.716999760456384
Average score of episodes 221-231: 12.322999724559486
Average score of episodes 231-241: 15.163999661058188
Average score of episodes 241-251: 16.883999622613192
Average score of episodes 251-261: 21.58299951758236
Average score of episodes 261-271: 20.450999542884528
Average score of episodes 271-281: 21.723999514430762
Average score of episodes 281-291: 20.82199953459203
Average score of episodes 291-301: 19.03699957448989
Average score of episodes 301-311: 25.67999942600727
Average score of episodes 311-321: 24.264999457634985
Average score of episodes 321-331: 25.6639994263649
Average score of episodes 331-341: 30.066999327950178
Average score of episodes 341-351: 28.47099936362356
Average score of episodes 351-361: 30.053999328240753
Average score of episodes 361-371: 32.01499928440899
Average score of episodes 371-381: 31.61799929328263
Average score of episodes 381-391: 33.02299926187843
Average score of episodes 391-401: 33.43699925262481
Solved in 407 steps!
```

![image](/data/images/average_score_new.png)

The number of episodes needed to solve the environment is 456 episodes.

### The Weights

The weights for both the neural network is saved in my_weights_2.pth.

## Future Works

- Implement multi agents training