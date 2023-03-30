# Project Report

## Learning Algorithm
The method choosen for this challenge was Deep Deterministic Policy Gradient, inspired by the ddpg-bipedal implementations, adatpted to the current enviroment. The algorithm DDPG is a combination of DQN and DPG, it is specifically adapted for enviroments with continuos action spaces, what it does is concurrently learn both an approximation of the optimal Q-function and optimal action.

### Arquitecture

The agent is composed of actor/critic networks with the following structure:

#### Actor Network
 * **First Layer.** 8 (state dimensions) input - 64 output
 * **Second Layer.** 64 input - 64 output
 * **Third Layer.** 64 input - 2 (actions) output

#### Critic Network
 * **First Layer.** 8 (state dimensions) input - 64 output
 * **Second Layer.** 66 (64 first layer + 2 actions) input - 64 output
 * **Third Layer.** 64 input - 1 (state value) output


### Parameters

 * replay buffer size: 10.000
 * minibatch size: 128
 * discount factor: 0.99
 * tau: 0.001
 * actor network learning rate: 0.0001
 * critic network learning rate: 0.001
 * L2 weight decay = 0

## Training Results

```
Episode 100	Average Score: 0.0000
Episode 200	Average Score: 0.0000
Episode 300	Average Score: 0.0010
Episode 400	Average Score: 0.0000
Episode 500	Average Score: 0.0028
Episode 600	Average Score: 0.0010
Episode 700	Average Score: 0.0000
Episode 800	Average Score: 0.0000
Episode 900	Average Score: 0.0252
Episode 1000	Average Score: 0.0344
Episode 1100	Average Score: 0.0020
Episode 1200	Average Score: 0.0459
Episode 1300	Average Score: 0.0904
Episode 1400	Average Score: 0.0926
Episode 1500	Average Score: 0.0987
Episode 1600	Average Score: 0.0998
Episode 1700	Average Score: 0.1119
Episode 1800	Average Score: 0.0957
Episode 1900	Average Score: 0.0957
Episode 2000	Average Score: 0.1006
Episode 2100	Average Score: 0.0988
Episode 2200	Average Score: 0.1225
Episode 2300	Average Score: 0.1689
Episode 2400	Average Score: 0.3246
Episode 2500	Average Score: 0.3524
Episode 2600	Average Score: 0.2931
Episode 2643	Average Score: 0.5063
Problem Solved in 2643 episodes.	Average Score: 0.5063
```
![results graph](https://github.com/lccrurod/continuous_control_drlnd/blob/main/training%20results.png)

Also there is a video of the trained agent performing the reacher task.

[<img src="https://github.com/lccrurod/collaboration_and_competition_drlnd/blob/main/thumbnail.PNG" width="272" height="151">](https://www.youtube.com/watch?v=mjcURqGMtow)

## Improvement Opportunities

In the video of the trained agents, it's seen they are achieving the task somewhat consistenly and developed a particular playstyle, waiting around the net for their pair to respond. Nonetheless there is plenty of room for improvement, some of the main ideas are:

- Implement A3C algorithm that would allow the agent to get insights of how good rewards were compared to it's expectation therefore enhancing the learning process.
- Explore with prioritized experience replays, or even hindsight experience replay that would definitely help extract the value in the episodes experimented by the agents by allowing sample-efficient learning from rewards.
- Also a scrutinous review and tuning of the hyperparameters will for sure translate into better performance.
