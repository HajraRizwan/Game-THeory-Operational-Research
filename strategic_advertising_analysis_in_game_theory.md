## Simulating Advertising Competition Using Game Theory
## Table of Content

1. [Introduction](#1-introduction)
2. [Problem Understanding](#2-problem-understanding)
    - [2.1 The Market Competition Scenario](#21-the-market-competition-scenario)
    - [2.2 Key Game Theory Concepts](#22-key-game-theory-concepts)
3. [Algorithm Design and Implementation](#3-algorithm-design-and-implementation)
    - [3.1 Steps to Solve the Problem](#31-steps-to-solve-the-problem)
    - [3.2 Python Code](#32-python-code)
4. [Creativity and Innovation](#4-creativity-and-innovation)
5. [Visualization and Analysis](#5-visualization-and-analysis)
    - [5.1 Heatmaps for Payoff Matrices](#51-heatmaps-for-payoff-matrices)
    - [5.2 Results](#52-results)
6. [Testing and Validation](#6-testing-and-validation)
    - [6.1 Test Cases](#61-test-cases)
    - [6.2 Validation](#62-validation)
7. [Real-World Applicability](#7-real-world-applicability)
8. [Scope and Complexity](#8-scope-and-complexity)
9. [Conclusion](#9-conclusion)
10. [Program File Link](#10-program-file-link)

---

## 1. Introduction

In today’s dynamic and competitive business landscape, companies constantly strive to optimize their strategies to maximize profits and secure a strong market presence. One of the critical elements that businesses leverage to influence consumer behavior and gain market share is advertising. However, the decision of how much to spend on advertising can be challenging, as companies must not only consider their own budgets but also anticipate and react to their competitors' strategies.

Game theory, a mathematical framework for modeling strategic interactions, provides valuable insights into this competitive decision-making process. By applying game theory to advertising competition, companies can identify optimal spending strategies that help achieve a market equilibrium—where no player benefits from changing their strategy unilaterally. This report delves into the use of game theory to model advertising competition between two companies, calculates the Nash equilibrium for various advertising strategies, and visualizes the results through a Python-based simulation.

The goal of this project is to provide a deeper understanding of competitive advertising strategies and how game theory can be employed to make informed decisions in an environment of interdependent choices.

---

## 2. Problem Understanding

### 2.1 The Market Competition Scenario

In a competitive market, two companies, A and B, must decide how much to allocate to advertising. This advertising spend is directly tied to both their individual profits and the distribution of market share between them. The companies are competing for consumer attention, and their spending decisions can influence not only their own market position but also that of their competitor.

The competition is dynamic, as each company's decision impacts both their own outcome and the other company's outcome. For example:

- If Company A spends heavily on advertising, it could potentially capture a larger share of the market, but this also encourages Company B to increase their advertising spend to maintain their competitive position.
- Conversely, if a company underinvests in advertising, it risks losing market share to the competitor, which could reduce profits.

Thus, both companies are faced with a strategic dilemma: They must decide how much to invest in advertising while considering their competitor’s potential moves. This situation is modeled as a two-player game in game theory, where the objective for both companies is to choose an advertising budget that maximizes their profit while anticipating the competitor's response.

### 2.2 Key Game Theory Concepts

- **Payoff Matrix:** Represents the outcomes (profits) for each player based on the combination of their strategies. Rows represent Company A’s strategies, and columns represent Company B’s strategies.
- **Nash Equilibrium:** A stable state where no player can improve their payoff by unilaterally changing their strategy. It reflects optimal decision-making in competitive scenarios.

For example, if both companies have three possible budgets ([0, 1, 2] in millions), a payoff matrix might look like this:

```
+-----------+------------+------------+
| Company A | Company B1 | Company B2 |
+-----------+------------+------------+
```

---

## 3. Algorithm Design and Implementation

### 3.1 Steps to Solve the Problem

1. Define Payoff Matrices: Create matrices representing payoffs for both companies based on their advertising budgets.
2. Model the Game: Use the `nashpy` library to simulate the two-player game.
3. Calculate Nash Equilibria: Identify equilibrium points where neither company benefits from changing its strategy unilaterally.
4. Simulate Payoffs: Evaluate profits for both companies under the equilibrium strategies.
5. Visualize Results: Use heatmaps and charts to present the strategies and outcomes.

### 3.2 Python Code

Below is the Python implementation of the problem, with added details for readability and testing:

```python
# Python Implementation
import numpy as np
import nashpy as nash
import matplotlib.pyplot as plt
import seaborn as sns

# Define payoff matrices
A_payoff = np.array([[3, 1], [0, 2]])
B_payoff = np.array([[2, 0], [1, 3]])

# Initialize the game
game = nash.Game(A_payoff, B_payoff)

# Calculate Nash equilibria
equilibria = list(game.support_enumeration())
print("Nash Equilibria:", equilibria)

# Heatmap visualization
sns.heatmap(A_payoff, annot=True, fmt="d", cmap="coolwarm", xticklabels=["B1", "B2"], yticklabels=["A1", "A2"])
plt.title("Company A Payoff Matrix")
plt.show()
```

---

## 4. Creativity and Innovation

### 4.1 Key Innovations

1. Game theory analysis for real-world scenarios.
2. Use of support enumeration for Nash equilibria.
3. Heatmap visualization for payoff matrices.
4. Simulation of payoffs for theoretical conclusions.

---

## 5. Visualization and Analysis

### 5.1 Heatmaps for Payoff Matrices

Heatmaps provide a clear representation of payoffs for each strategy combination.

### 5.2 Results

- Nash equilibria highlight optimal strategies for both companies.
- Simulated payoffs indicate potential profits for each equilibrium point.

---

## 6. Testing and Validation

### 6.1 Test Cases

We test the program with different payoff matrices to validate the Nash equilibrium calculations.

### 6.2 Validation

We verify results by cross-referencing with manual calculations and theoretical expectations.

---

## 7. Real-World Applicability

- **Market Analysis:** Enhance analysis by simulating competitive strategies.
- **Strategic Planning:** Predict competitor moves and plan accordingly.
- **Economic Modeling:** Use in industries like retail, tech, and media.

---

## 8. Scope and Complexity

The project models advertising competition, calculates Nash equilibria, and provides actionable insights into optimal strategies.

---

## 9. Conclusion

This report demonstrates the use of game theory to model advertising competition. The Python implementation efficiently calculates Nash equilibria, providing actionable insights into optimal strategies.

---

## 10. Program File Link

[Google Colab Link](https://colab.research.google.com/drive/1_xhgRPRtZXDylTJwsJtbvbXYElTq3IBZ#scrollTo=b4TJePkAcIDb)
