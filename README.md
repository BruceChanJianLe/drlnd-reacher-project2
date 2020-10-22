# Deep Reinforcement Learning - Reacher - Project 2

This repository stores the solution to the udacity deep reinforcement learning nanodegree second project which is the reacher project. 

## Project Overview

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

**Aim**
The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.

**State Space**
The state space is 33 which are variables corresponding to position, rotation, velocity, and angular velocities of the arm.

**Action Space**
The action space is 4 which are torques that applies to the arm's two joints. Each entry in the action vector is a number between [-1, 1].

## Getting Started

Please make sure `python3.6` is installed in your conda environment. And run the install script.
```bash
source ./install.sh
```

## Running

Please run `My_Continuous_Control.ipynb` jupyter notebook. You will need to be able to connect to the jupyter notebook server before you can run it.

## Local Setup

Download unity program for reacher here or use the one provided in the repository.  

Version 1: One (1) Agent

   - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
   - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
   - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
   - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

Version 2: Twenty (20) Agents

   - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
   - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
   - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
   - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
