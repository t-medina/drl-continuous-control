[//]: # (Image References)

[rewards_plot]: rewards-plot.png "Rewards Plot"
[trained_agent]: trained.gif "Trained Agent"

# Project report

## Learning algorithm

The learning algorithm used is DDPG, very similar to the one used to solve the `Pendulum` Gym environment in the [implementation](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum) provided by Udacity.

The algorithm implments an actor-critic method, so two neural network were implemented. 

The actor neural network consists of three layers:

- Fully connected layer - input: 33, output: 128
- Fully connected layer - input: 128, output: 128
- Fully connected layer - input: 128, output: 4

The input and output correspond to the state space size (33) and action space size (4)

The crtic neural network also consists of three layers, with an slightly different structure:

- Fully connected layer - input: 33, output: 128
- Fully connected layer - input: 128 + 4, output: 128
- Fully connected layer - input: 128, output: 1

Batch normalization was added after the first layer of both the actor and the critic.

### Hyperparameters
Parameter | Value
--- | ---
replay buffer size | 100000
batch size | 128
gamma | 0.99
tau | 0.001
actor learning rate | 0.0002
critic learning rate | 0.0002
num episodes | 1000
weight decay | 0

## Results

### Plot of Rewards

The environment was solved in 210 episodes:

![Rewards Plot][rewards_plot]

```
Episode 25	Average Score: 1.32
Episode 50	Average Score: 1.90
Episode 75	Average Score: 2.90
Episode 100	Average Score: 3.90
Episode 125	Average Score: 6.92
Episode 150	Average Score: 13.24
Episode 175	Average Score: 20.70
Episode 200	Average Score: 27.93
Episode 210	Average Score: 30.13
Environment solved in 210 episodes!	Average Score: 30.13
```

### Trained agent

![Trained Agent][trained_agent]

## Ideas for future work

I've a passion for distributed systems, so I would love to try and solve the environment with 20 agents, leveraging on distributed learning using algorithms like PPO, A3C and D4PG.