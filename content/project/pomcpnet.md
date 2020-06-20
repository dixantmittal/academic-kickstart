---
title: "Learning to Search in Partially-Observable Environments"
date: 2020-06-19
authors: ["Dixant Mittal", "Wee Sun Lee"]
draft: false
---

Partial observability is fundamental to our uncertain world, and we need to reason about it while making decisions. Partially Observable Markov Decision Processes (POMDP) presents a principled approach to model sequential decision-making problems for partially observable domains. Online planning algorithms, such as POMCP or DESPOT, are the most preferred algorithms to solve large POMDPs. They find the optimal action for the current belief by searching the most promising part of the search tree guided by a heuristic function. Designing the optimal heuristics for a task requires a considerable amount of human effort and expert domain knowledge, which may be challenging to acquire. Further, a sub-optimal heuristic function degrades the performance of these approximate online planners.

We propose to let a planning algorithm learn the optimal heuristics and how to use it for search, itself, by embedding it inside a neural network and jointly optimising it in an end-to-end approach. We design a differentiable version of POMCP, named POMCPnet, by approximating the simulation, rollout and backup phases of POMCP as different neural networks. These networks guide the search by using a memory embedding and updating it when new information is available, resulting in the creation of a dynamic computation graph in parallel to the regular search. The networks are optimised using stochastic gradient descent.

POMCPnet, with its richer, learnt heuristics along with the jointly learnt search mechanism, makes better use of the information available from the partially explored search tree.
