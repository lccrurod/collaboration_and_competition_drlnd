# collaboration_and_competition_drlnd

This repository corresponds to the third project in Udacity's Deep Reinforcement Learning Nanodegree. The goal is to train two agents to play tennis between themselves.

## The enviroment:

![env screenshot](https://github.com/lccrurod/collaboration_and_competition_drlnd/blob/main/enviroment_intro.png)

In this enviroment two agents are in control of tennis rackets and have the objective to keep the ball in play. They can observe 8 variables corresponding to the position and velocity of the ball and racket and, each agent receives their own information and as action they can move in two dimension, towards or away from the net and jumping. For each time an agent hits the ball an sends it over the net it recieves +0.1 reward and if the ball touches the ground the agents recieves a reward of -0.01, to assign a score to each episode the maximum reward from the two agents is taken.

The enviroment is solved when the average score over 100 consecutive episodes is at least 0.5.

## Getting Started:

This project is aided by the [deep-reinforcement-learning](https://github.com/udacity/deep-reinforcement-learning/blob/master/README.md) repository where in the `/python` folder are the necesary files for unity enviroments, and, Separately in the `Tennis_Windows_x86_64` is located the specific enviroment for the project. The additional prerrequisites are specified in the `requirements.txt` file.

The files `model.py` and `mddpg.py` are based on the available content for the course for defining a Deep Deterministic Policy Gradient and a trainable multi-agent model based on the choosen algorithm.

The process of training the agent, as well as enviroment exploration is done in the `Tennis.ipynb` notebook.
