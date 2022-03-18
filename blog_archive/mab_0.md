---
title: "Introduction of Multi-Armed Bandits"
layout: single
permalink: /blog_archive/mab_0
classes: wide
author_profile: true
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


{% include figure image_path="/assets/images/mab_illustration.jpg" alt="this is a placeholder image" caption="image from \"https://vwo.com/blog/multi-armed-bandit-algorithm/\" " %} 


**MAB (multi-armed bandits)** is a simple yet powerful framework for algorithms making decisions over time under uncertainty. Its name was inspired by the scenario of gamblers facing several slot machines, a.k.a. one-armed bandits, in casinos, where each lever has an identical appearance but yields a different payoff. 

In the basic MAB problem, each arm (action) inherently obtains a stationary reward distribution unknown to the algorithm. The objective is to maximize the total reward within a certain period, e.g., over 1000 action selections. In each play, the algorithm will choose an arm and observe the reward for it, but not for the other arms that could have been chosen. By repeating this process, an agent explores a variety of actions and exploits acquired information to maximize cumulative action values. If we had full knowledge about the distributions, the problem could be solved trivially by always pulling the arm with the highest expected value. Nonetheless, estimating expected rewards by the Law of Large Number is infeasible (every single chance to pull an arm is valuable!). 

Before we dive deeper into the problem, let us define what a greedy action is. We call an action *greedy* if it has the highest action value among the estimates at the current time step. 

$$
a_{greedy} = \arg\max_{a} Q(a)
$$

$Q(a)$ denotes the estimated value of action $a$. If you select a greedy action in this round, we say that you are exploiting. Otherwise, we say you are exploring because it enables you to improve your estimates. The uncertainty in such a problem is that we can hardly determine if some non-greedy actions are actually better than the greedy one. Essentially, one should balance the tradeoff between exploitation and exploration. During exploration, the reward could be lower in the short run but increased in the long term since after you have discovered the better actions, you can exploit them many times. 

to be continued ...

