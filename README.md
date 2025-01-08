# Artificial-Intelligence-with-Python

#Terminology


Agent

An entity that perceives its environment and acts upon that environment. In a navigator app, for example, the agent would be a representation of a car that needs to decide on which actions to take to arrive at the destination.

State

A configuration of an agent in its environment. For example, in a 15 puzzle, a state is any one way that all the numbers are arranged on the board.

Initial State

The state from which the search algorithm starts. In a navigator app, that would be the current location.

Actions

Choices that can be made in a state. More precisely, actions can be defined as a function. Upon receiving state s as input, Actions(s) returns as output the set of actions that can be executed in state s. For example, in a 15 puzzle, the actions of a given state are the ways you can slide squares in the current configuration (4 if the empty square is in the middle, 3 if next to a side, 2 if in the corner).

Transition Model

A description of what state results from performing any applicable action in any state. More precisely, the transition model can be defined as a function. Upon receiving state s and action a as input, Results(s, a) returns the state resulting from performing action a in state s. For example, given a certain configuration of a 15 puzzle (state s), moving a square in any direction (action a) will bring to a new configuration of the puzzle (the new state).

State Space

The set of all states reachable from the initial state by any sequence of actions. For example, in a 15 puzzle, the state space consists of all the 16!/2 configurations on the board that can be reached from any initial state. The state space can be visualized as a directed graph with states, represented as nodes, and actions, represented as arrows between nodes.

#Search

DFS
Depth-First Search
A depth-first search algorithm exhausts each one direction before trying another direction. In these cases, the frontier is managed as a stack data structure. The catchphrase you need to remember here is “last-in first-out.” After nodes are being added to the frontier, the first node to remove and consider is the last one to be added. This results in a search algorithm that goes as deep as possible in the first direction that gets in its way while leaving all other directions for later.

BFS
Breadth-First Search

Queue
first in first out 

Greedy Best-First Search
The opposite of depth-first search would be breadth-first search (BFS).