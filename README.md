# Vaccine Development with Dynamic Programming and Monte Carlo Simulation

This repository contains a simulation of a vaccine development process modeled as a Markov Decision Process (MDP) using Monte Carlo methods to evaluate different investment policies. The biotech company is deciding whether to invest additional resources during various phases of vaccine development, and the goal is to compute the value of these decisions under different strategies.

The project uses **Monte Carlo Simulation** to estimate the value functions of two distinct policies:
- **Always Invest**
- **Never Invest**

The purpose is to understand the long-term value of each decision-making strategy and compare them.

## Problem Description

The vaccine development process is modeled as an MDP with the following characteristics:

### States:
- **State 0**: Initial phase (preclinical phase)
- **State 1**: Phase 1 with promising results
- **State 2**: Phase 1 with disappointing results
- **State 3**: Success (the vaccine is sold for $10 million)
- **State 4**: Failure

### Actions:
- **Action 0**: No additional investment (proceed with current phase)
- **Action 1**: Invest an additional $100,000 (increases chances of success)

### Transition Probabilities:
The probability of transitioning between states depends on the chosen action. There are two transition matrices:
- `P0`: Transition probabilities without additional investment
- `P1`: Transition probabilities with an additional investment

### Rewards:
Each state has a corresponding reward. The reward for reaching state 3 (success) is $10 million, while other states have no immediate monetary reward. The cost of investing an additional $100,000 is reflected in the reward as a negative reward of `-0.1` million.

### Discount Factor:
The future rewards are discounted with a factor of `gamma = 0.996`.

## Policies Evaluated

1. **Always Invest**: In this policy, the company chooses to always invest (action 1) during each phase of development.
2. **Never Invest**: In this policy, the company never invests (action 0) during any phase.

## Monte Carlo Simulation

The Monte Carlo method is used to estimate the value function for each state by simulating multiple episodes of vaccine development, following each policy. For each episode, the company starts at phase 0 and makes decisions according to the specified policy. The future rewards are discounted using the provided discount factor.

The program computes the value of each state under the two policies based on simulated episodes.

## Requirements

- Python 3.x
- NumPy
- Matplotlib (for visualization)

