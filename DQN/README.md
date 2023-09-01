# Reinforcement Learning using DQN with Frozen Lake Environment

## Q-Learning

Q-Learning is a off-policy TD method.

![Pseudo code of Q-Learning](https://zitaoshen.rbind.io/img/Q-learning/q-learning.png)

TD learning is a combination of Monte Carlo ideas and Dynamic Programming (DP) ideas.

- Like Monte Carlo methods, TD methods can learn directly from raw experience without a model of the environment's dynamics.
- Like DP, TD methods update estimates based in part on other learned estimates, without waiting for a nal outcome (they bootstrap).

### Policy Evaluation

Estimate the value function $v_\pi$ for a given policy $\pi$.

### Policy Improvement
Find an optimal policy

### Dynamic Programming

Dynamic Programming refers to a collection of algorithms that can be used to compute optimal policies given a perfect model of the environment as a **Markov Decision Process (MDP)**.

### Monte Carlo

Monte Carlo requires no prior knowledge of the environment's dynamics and requires only experience sample sequences of states, actions, and rewards from actual or simulated interaction with an environment.

Monte Carlo methods can be incremental in an episode-by-episode sense, but not in a step-by-step (online) sense.

### Q-Table

Q-learning uses a table (Q-table) to store the Q values of the **state-action pair**, and updates the table at each step according to the following formula until convergence.

$$Q(S_t,A_t)\leftarrow Q(S_t,A_t)+\alpha [R_{t+1}+\gamma max_a Q(S_{t+1},a;\theta)-Q(S_t,A_t)]$$

where $\alpha$ is learning rate and $\gamma$ is discount factor which can control the importance of the new experience.

### Value Function Approximation

Since we cannot use a table to accurately store and represent Q-values, we can use a parameterized function to approximate the action value function $Q(s,a)$, i.e.

$$Q(s,a) \approx f(s,a,\theta)$$

## Deep Q-Network

DQN is the first application of Deep Reinforcement Learning. This method firstly came from DeepMind in 2013.[1] And then they improved the method in 2015.[2]

Deep learning is supervised learning, which requires labeled data to calculate the loss function and update the parameters of the neural network through gradient descent and error backpropagation, so how to obtain labels in reinforcement learning? As mentioned above, we used $R_{t+1}+\gamma max_a Q(S_{t+1},a)$ to update the Q-values. Similarly, we can use

$$R_{t+1}+\gamma max_a Q(S_{t+1},a;\theta)$$

to calculate the Q-value labels. Precisely, it is called **Target Net**.

### Target Net

Target Net is itself a neural network. However, it does not need to be trained. The parameters inside it are updated by copying the parameters from the neural network that we are mainly focus on, which is also called a **Policy Net**. When we are talking about "copying", we can basically copy the values directly. This is considered to be a **hard copy**.

Also, we can set a hyperparameter to control the importance of current policy net parameters when updating the parameters inside target net. This is considered to be a **soft copy**. 





## Reference

[1] [Playing Atari with Deep Reinforcement Learning](https://arxiv.org/pdf/1312.5602v1.pdf)
[2] [Human-level control through deep reinforcement learning](https://www.nature.com/articles/nature14236)
