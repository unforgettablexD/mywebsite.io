---
layout: project_post
title: "Autonomous Decision-Making Maze Game"
summary: "Explore how an agent is trained for autonomous decision-making within a maze using reinforcement learning techniques."
author: arnav
date: '2024-04-28'
category: ['AI', 'Machine Learning', 'Reinforcement Learning']
tags: reinforcement_learning, decision_making, AI, python, jekyll
thumbnail: /assets/img/posts/autonomous-maze-game-logo.png
keywords: autonomous decision-making, reinforcement learning, maze game, AI agent, python, machine learning
usemathjax: false
permalink: /project/autonomous-decision-making-maze-game/
---

# Autonomous Decision-Making Maze Game

In this project, an autonomous agent is trained to navigate a maze and make decisions using reinforcement learning techniques. The model can be trained and tested across multiple difficulty levels using predefined layouts. The training process uses reward signals to optimize decision-making for efficient pathfinding within the maze.

## Setup

To run the project, first set up a virtual environment as recommended below (or consult [Visual Code](https://code.visualstudio.com/docs/python/environments) for additional guidance).

```bash
python -m venv path/to/env
```

Activate the virtual environment:

```bash
source path/to/env/bin/activate
```

Next, install the required dependencies:

```bash
cd code
pip install -r requirements.txt
```

## Available Maps

The project includes a variety of maps for testing the agent, which are located in the `code/layouts` folder:

| Map   		| File                      |
|---------------|---------------------------|
| `easy_0`      | `code/layouts/easy_0.txt` |
| `easy_1`      | `code/layouts/easy_1.txt` |
| `medium_0`    | `code/layouts/medium_0.txt` |
| `medium_1`    | `code/layouts/medium_1.txt` |
| `hard_0`      | `code/layouts/hard_0.txt` |
| `hard_1`      | `code/layouts/hard_1.txt` |

## Usage

### Training and Testing the Model

The trained model is saved in the `agent.pkl` file and can be accessed as follows:

```python
with open('agent.pkl', 'rb') as file:
    agent = pickle.load(file)
```

Set the agent to test mode:

```python
agent.test_mode()
```

To train the model, run the following command (replacing `hard_0` with your desired map):

```bash
python main.py hard_0
```

To test the agent, run:

```bash
python test.py hard_0
```

You can use any other available map, but ensure the agent is trained on the same map used in the test.

### Results

Here are some sample videos showing the agent's performance on different maps:

**Easy_1 map:**

<video width="720" height="480" controls>
  <source src="https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/3a75d903-6edc-4a4a-85b8-f7e28f272b7f" type="video/mp4">
  Your browser does not support the video tag.
</video>

**Medium_0 map:**

<video width="720" height="480" controls>
  <source src="https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/44875ec3-4211-4e88-8002-50528456bc3c" type="video/mp4">
  Your browser does not support the video tag.
</video>

**Hard_0 map:**

<video width="720" height="480" controls>
  <source src="https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/2f5e5426-3802-44a6-b152-345a1ff19876" type="video/mp4">
  Your browser does not support the video tag.
</video>

**Medium_1 map:**

<video width="720" height="480" controls>
  <source src="https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/30d67dab-c630-4f58-917f-a0935be9ccb5" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Compare

To compare the performance across maps, run the following command:

```bash
cd code
python compare.py <map-name>
```

### Results:

#### Simple TDLambda:
![smoothed_agent_performance_comparison](https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/1a9e841a-6797-4dc6-9746-30398aaf117d)

#### Modified TDLambda:
![combined_agent_performance](https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/2351c06b-1a05-4dc4-a8cd-996cd279509d)

#### Comparison with Other Models:
![smoothed_discounted_return_comparison](https://github.com/unforgettablexD/Autonomous-decision-making-maze-game-/assets/49744841/80ea0d2c-fa10-4f30-af91-73b3da1077aa)
```