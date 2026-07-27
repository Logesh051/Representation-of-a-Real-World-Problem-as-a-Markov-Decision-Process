# Representation-of-a-Real-World-Problem-as-a-Markov-Decision-Process

## Aim

To represent a Smart Plant Watering System as a Markov Decision Process (MDP) by defining its states, actions, rewards, transition probabilities, and Python representation.

---

## Problem Statement

### Problem Description

A Smart Plant Watering System monitors the moisture level of the soil and decides whether to water the plant or wait. The objective is to maintain healthy soil moisture while avoiding overwatering and conserving water. The system makes decisions based on the current state of the soil.

---

## MDP Components

A Markov Decision Process is represented as:

$$
MDP = (S, A, P, R, \gamma)
$$

Where:

| Symbol | Meaning |
|---|---|
| $S$ | Set of states |
| $A$ | Set of actions |
| $P$ | Transition probability function |
| $R$ | Reward function |
| $\gamma$ | Discount factor |

---

## State Space

```text
S = {
    Dry Soil,
    Moist Soil,
    Wet Soil
}
```

---

## Sample State

```text
Dry Soil
```

---

## Action Space

```text
A = {
    Water Plant,
    Wait
}
```

---

## Sample Action

```text
Water Plant
```

---

## Transition Probability

The transition probability is represented as:

$$
P(s' \mid s,a)
$$

Example transitions:

- Dry Soil + Water Plant → Moist Soil (0.9)
- Dry Soil + Wait → Dry Soil (1.0)
- Moist Soil + Water Plant → Wet Soil (0.8)
- Moist Soil + Wait → Dry Soil (0.3)
- Wet Soil + Wait → Moist Soil (0.7)

---

## Reward Function

The reward function is represented as:

$$
R(s,a,s')
$$

Rewards:

- Watering dry soil → **+5**
- Keeping soil moist → **+10**
- Overwatering the soil → **−5**
- Ignoring dry soil → **−3**

---

## Graphical Representation

<img width="1018" height="447" alt="image" src="https://github.com/user-attachments/assets/64df19ca-766c-4413-9939-479a10e62a39" />


## Python Representation

```python
# MDP Representation using Python

states = ["Dry Soil", "Moist Soil", "Wet Soil"]

actions = {
    "Dry Soil": ["Water Plant", "Wait"],
    "Moist Soil": ["Water Plant", "Wait"],
    "Wet Soil": ["Wait"]
}

transitions = {
    ("Dry Soil", "Water Plant"): ("Moist Soil", 0.9),
    ("Dry Soil", "Wait"): ("Dry Soil", 1.0),
    ("Moist Soil", "Water Plant"): ("Wet Soil", 0.8),
    ("Moist Soil", "Wait"): ("Dry Soil", 0.3),
    ("Wet Soil", "Wait"): ("Moist Soil", 0.7)
}

rewards = {
    ("Dry Soil", "Water Plant"): 5,
    ("Moist Soil", "Wait"): 10,
    ("Moist Soil", "Water Plant"): -5,
    ("Dry Soil", "Wait"): -3
}

print("States:", states)
print("Actions:", actions)
print("Transitions:", transitions)
print("Rewards:", rewards)
```

---

## Output

```text
States: ['Dry Soil', 'Moist Soil', 'Wet Soil']

Actions:
{
 'Dry Soil': ['Water Plant', 'Wait'],
 'Moist Soil': ['Water Plant', 'Wait'],
 'Wet Soil': ['Wait']
}

Transitions:
{
 ('Dry Soil', 'Water Plant'): ('Moist Soil', 0.9),
 ('Dry Soil', 'Wait'): ('Dry Soil', 1.0),
 ('Moist Soil', 'Water Plant'): ('Wet Soil', 0.8),
 ('Moist Soil', 'Wait'): ('Dry Soil', 0.3),
 ('Wet Soil', 'Wait'): ('Moist Soil', 0.7)
}

Rewards:
{
 ('Dry Soil', 'Water Plant'): 5,
 ('Moist Soil', 'Wait'): 10,
 ('Moist Soil', 'Water Plant'): -5,
 ('Dry Soil', 'Wait'): -3
}
```

---

## Result

The Smart Plant Watering System was successfully represented as a Markov Decision Process by defining its states, actions, transition probabilities, reward function, graphical representation, and Python representation.

---
