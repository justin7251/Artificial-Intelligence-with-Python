# Artificial-Intelligence-with-Python

# Terminology


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
A breadth-first search algorithm will follow multiple directions at the same time, taking one step in each possible direction before taking the second step in each direction. In this case, the frontier is managed as a queue data structure. The catchphrase you need to remember here is “first-in first-out.” In this case, all the new nodes add up in line, and nodes are being considered based on which one was added first (first come first served!). This results in a search algorithm that takes one step in each possible direction before taking a second step in any one direction.

Queue
first in first out 

Greedy Best-First Search
The opposite of depth-first search would be breadth-first search (BFS).

Minimax
A type of algorithm in adversarial search, Minimax represents winning conditions as (-1) for one side and (+1) for the other side. Further actions will be driven by these conditions, with the minimizing side trying to get the lowest score, and the maximizer trying to get the highest score.


Knowledge-Based Agents
These are agents that reason by operating on internal representations of knowledge.

# Propositional Logic

Propositional logic is based on propositions, statements about the world that can be either true or false, as in sentences 1-5 above.

Propositional Symbols
Propositional symbols are most often letters (P, Q, R) that are used to represent a proposition.

Logical connectives play a crucial role in Artificial Intelligence (AI), particularly in knowledge representation, decision-making, and reasoning systems. They help formalize complex statements and relationships between facts in a machine-understandable way.

Logical Connectives in AI
Logical connectives play a crucial role in Artificial Intelligence (AI), particularly in knowledge representation, decision-making, and reasoning systems. They help formalize complex statements and relationships between facts in a machine-understandable way.

Key "Logical Connectives":
AND (∧): True if both conditions are true.
Example: A ∧ B → Both A and B must be true.
OR (∨): True if at least one condition is true.
Example: A ∨ B → Either A or B (or both) must be true.
NOT (¬): Negates a statement.
Example: ¬A → True if A is false.
XOR (Exclusive OR): True if exactly one condition is true.
Example: A ⊕ B → True if either A or B is true, but not both.
Implication (→): "If A, then B." False only if A is true and B is false.
Example: A → B
Bi-implication (↔): True if both sides have the same truth value.
Example: A ↔ B

Entailment (⊨)

If α ⊨ β (α entails β), then in any world where α is true, β is true, too.

For example, if α: “It is a Tuesday in January” and β: “It is January,” then we know that α ⊨ β. If it is true that it is a Tuesday in January, we also know that it is January. Entailment is different from implication. Implication is a logical connective between two propositions. Entailment, on the other hand, is a relation that means that if all the information in α is true, then all the information in β is true.

Inference

Inference is the process of deriving new sentences from old ones.

For instance, in the Harry Potter example earlier, sentences 4 and 5 were inferred from sentences 1, 2, and 3.

There are multiple ways to infer new knowledge based on existing knowledge. First, we will consider the Model Checking algorithm.

To determine if KB ⊨ α (in other words, answering the question: “can we conclude that α is true based on our knowledge base”)
Enumerate all possible models.
If in every model where KB is true, α is true as well, then KB entails α (KB ⊨ α).

Knowledge Engineering
Knowledge engineering is the process of figuring out how to represent propositions and logic in AI.

Inference Rules
Model Checking is not an efficient algorithm because it has to consider every possible model before giving the answer (a reminder: a query R is true if under all the models (truth assignments) where the KB is true, R is true as well). Inference rules allow us to generate new information based on existing knowledge without considering every possible model.

Inference rules are usually represented using a horizontal bar that separates the top part, the premise, from the bottom part, the conclusion. The premise is whatever knowledge we have, and the conclusion is what knowledge can be generated based on the premise.

Modus Ponens

The type of inference rule we use in this example is Modus Ponens, which is a fancy way of saying that if we know an implication and its antecedent to be true, then the consequent is true as well.

And Elimination

If an And proposition is true, then any one atomic proposition within it is true as well. For example, if we know that Harry is friends with Ron and Hermione, we can conclude that Harry is friends with Hermione.

Double Negation Elimination

A proposition that is negated twice is true. For example, consider the proposition “It is not true that Harry did not pass the test”. We can parse it the following way: “It is not true that (Harry did not pass the test)”, or “¬(Harry did not pass the test)”, and, finally “¬(¬(Harry passed the test)).” The two negations cancel each other, marking the proposition “Harry passed the test” as true.

Implication Elimination

An implication is equivalent to an Or relation between the negated antecedent and the consequent. As an example, the proposition “If it is raining, Harry is inside” is equivalent to the proposition “(it is not raining) or (Harry is inside).”

Biconditional Elimination

A biconditional proposition is equivalent to an implication and its inverse with an And connective. For example, “It is raining if and only if Harry is inside” is equivalent to (“If it is raining, Harry is inside” And “If Harry is inside, it is raining”).

De Morgan’s Law

It is possible to turn an And connective into an Or connective. Consider the following proposition: “It is not true that both Harry and Ron passed the test.” From this, it is possible to conclude that “It is not true that Harry passed the test” Or “It is not true that Ron passed the test.” That is, for the And proposition earlier to be true, at least one of the propositions in the Or propositions must be true.

Distributive Property

A proposition with two elements that are grouped with And or Or connectives can be distributed, or broken down into, smaller units consisting of And and Or.