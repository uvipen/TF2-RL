# Reinforcement Learning Agents 
Implemented for Tensorflow 2.0+ (use version 2.1+ to avoid memory leak issues)

## Usage
- Install dependancies imported in python file (including tensorflow 2.0+, gym, numpy, matplotlib)
- Each file contains example code that runs training on CartPole env
- Training: `python3 TF2_DDPG_LSTM.py`
- Tensorboard: `tensorboard --logdir=DDPG/logs`

## Hyperparameter tuning
- Install hyperopt https://github.com/hyperopt/hyperopt
- Optional: switch agent used and configure param space in `hyperparam_tune.py` 
- Run: `python3 hyperparam_tune.py`

## Agents
All agents tested using CartPole env with modified reward

| Name | On/off policy | Model | Action space support | Exploration method |
| --- | --- | --- | --- | --- |
| [DQN](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf) | off-policy | Dense, LSTM | discrete | e-greedy |
| [DDPG](https://arxiv.org/pdf/1509.02971.pdf) | off-policy | Dense, LSTM | discrete, continuous | Gaussian noise |
| [AE-DDPG](https://arxiv.org/pdf/1903.00827.pdf) | off-policy | Dense | discrete, continuous | Random walk noise |
| [SAC*](https://arxiv.org/pdf/1812.05905.pdf) | off-policy | Dense | continuous | Maximum entropy |

*work in progress

## Models
Models used to generate the demos are included in the repo, you can also find q value and reward graphs that were generated after training

UPDATE: Slowly moving towards tensorboard :D

## Demos
| DQN Basic, time step = 4, 500 reward | DQN LSTM, time step = 4, 500 reward |
| --- | --- |
| <img src="DQN/gifs/test_render_basic_time_step4_reward500.gif" height="200"> | <img src="DQN/gifs/test_render_lstm_time_step4_reward500.gif" height="200"> |

| DDPG Basic, 222 reward | DDPG LSTM, time step = 5, 500 reward |
| --- | --- |
| <img src="DDPG/gifs/test_render_basic_reward222.gif" height="200"> | <img src="DDPG/gifs/test_render_lstm_time_step5_reward500.gif" height="200"> |

| AE-DDPG Basic, 500 reward |
| --- |
| <img src="AE-DDPG/gifs/test_render_basic_reward500.gif" height="200"> |
