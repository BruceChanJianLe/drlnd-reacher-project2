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
- Learning Rate (Actor): 0.00005
- Learning Rate (Critic): 0.00005
- Weight Decay: 0

Training Results:
```bash
Average score of episodes 1-11: 0.8929999800398946
Average score of episodes 11-21: 1.1369999745860695
Average score of episodes 21-31: 1.2379999723285438
Average score of episodes 31-41: 2.428999945707619
Average score of episodes 41-51: 2.3449999475851655
Average score of episodes 51-61: 3.5679999202489854
Average score of episodes 61-71: 2.597999941930175
Average score of episodes 71-81: 3.129999930039048
Average score of episodes 81-91: 4.038999909721315
Average score of episodes 91-101: 3.9009999128058555
Average score of episodes 101-111: 4.999999888241291
Average score of episodes 111-121: 5.176999884285033
Average score of episodes 121-131: 4.644999896176159
Average score of episodes 131-141: 5.20199988372624
Average score of episodes 141-151: 8.695999805629253
Average score of episodes 151-161: 8.05499981995672
Average score of episodes 161-171: 11.484999743290246
Average score of episodes 171-181: 9.27199979275465
Average score of episodes 181-191: 13.219999704509974
Average score of episodes 191-201: 12.144999728538096
Average score of episodes 201-211: 13.636999695189298
Average score of episodes 211-221: 14.16299968343228
Average score of episodes 221-231: 15.252999659068882
Average score of episodes 231-241: 15.880999645031988
Average score of episodes 241-251: 20.003999552875758
Average score of episodes 251-261: 18.307999590784313
Average score of episodes 261-271: 19.07899957355112
Average score of episodes 271-281: 23.032999485172333
Average score of episodes 281-291: 22.11999950557947
Average score of episodes 291-301: 23.233999480679632
Average score of episodes 301-311: 23.472999475337566
Average score of episodes 311-321: 25.726999424956738
Average score of episodes 321-331: 24.513999452069402
Average score of episodes 331-341: 27.371999388188122
Average score of episodes 341-351: 24.25799945779145
Average score of episodes 351-361: 26.77299940157682
Average score of episodes 361-371: 26.33999941125512
Average score of episodes 371-381: 25.488999430276454
Average score of episodes 381-391: 26.240999413467943
Average score of episodes 391-401: 29.35499934386462
Average score of episodes 401-411: 32.62799927070737
Average score of episodes 411-421: 34.05199923887849
Average score of episodes 421-431: 31.060999305732548
Average score of episodes 431-441: 31.10499930474907
Average score of episodes 441-451: 32.903999264538285
Solved in 456 steps!
```

![image](/data/images/average_score.png)

## Future Works

- Implement multi agents training