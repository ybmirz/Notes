A pushdown automata here goes beyond the finite limitation by having an **infinte pushdown stack**; so basically it is an NFA with an unlimited stack and $\epsilon$-transition stack (empty word transition)
Basically two components:
- An infinite memory in the structure of a stack (LIFO)
- and transitions that can be made without reading an input ($\epsilon$)

They are non-deterministic hence they can accept any route that leads to an accepting/final state 
How does the stack work?
		- Every transition done within the automate **pops** the stack, and if the stack is empty, the automaton stops. 
		- if the input remains after when the stack is empty, or when it has not reached an accepting state, it is rejected.
- Remember that empty word transition, this means that a pushdown automata accepts an empty word at any point, or a transition without any input, as long as the stack symbol is accepted and an operation is done to the stack; the remaining input does not have to be empty

#### Acceptance
To simply, the automata can only accept a word in two manners:
-  if the automaton is in the accepting state when the input/word has been consumed
- or if the automaton's stack is empty after consuming the input word

#### Formal Definition
- Based on the conditions of acceptance;
	- A **final-state PDA** is a **7-tuple**: $(Q, \sum, \Gamma,\delta, q_{0}, Z_{0}, F)$
		- where $Q$ is the finite set of states
		- $\sum$ is the finite set of *input alphabet
		- $\Gamma$ is the finite set of *stack alphabet*
		- $\delta \in Q \times (\sum \cup \{ \epsilon \}) \times \Gamma \to P_{FIN}(Q \times \Gamma ^{*})$ is a transition function
		- $q_{0} \in Q$ is the initial state
		- $Z_{0} \in \Gamma$ is the initial stack symbol set in the stack alphabet
		- with $F \subset Q$ is the set of accepting states
> $P_{FIN}(A)$ is the finite subsets of a set A 

> An empty stack PDA is a 6 tuple where there's no set of accepting state, as the only accepting state is an empty stack!

After defining a pushdown automata, we can further develop the understanding by looking at the [[Language of a PDA]]; This is not the *languages* accepted by a PDA, but rather the terminologies that can be used to further understand a pushdown automata

[[Language of a PDA#Common Languages]] notes some common languages that a PDA could have; with its formal definitions

- Pushdown Automatas are also able to *express* [[Context Free Languages]]

As noted above, a PDA is simply an NFA with an unlimited stack memory; what about a deterministic version of this; more on [[Deterministic Pushdown Automata]]

## Conversion
- As stated above, a PDA can be accepted by either an empty stack or a final state; they are equivalent in the sense that the Language $L$ has a PDA that accepts it by *final state* if and only if $L$ has a PDA that accepts it by *empty stack*
	- Now this mean that it would be possible to *convert* a PDA $P_{N}$ that accepts by empty stack to a PDA that accepts by final state $P_{F}$, and vice versa

**Empty Stack to Final State**
Given an Empty Stack PDA $$
P_{N}= \left( Q_{N}, \sum, \Gamma_{N}, \delta_{N}, q_{0}, Z_{0} \right)
$$
an equivalent **final state** PDA $$
\begin{align}
P_{F} &= \left( Q_{N} \cup \{ p_{0}, p_{f} \}, \sum, \Gamma_{N} \cup \{ X_{_{0}} \}, \delta_{F}, p_{0}, X_{0}, \{ p_{f} \} \right) \\
&\delta_{F}(p_{0}, \epsilon, X_{0}) = \{ (q_{0}, Z_{0}X_{0}) \} \\
&\delta_{F}(q, \epsilon, X_{0}) | q \in Q_{N} = \{ (p_{f}, \epsilon) \}

\end{align}
$$
> To simplify it; Converting it requires to ensure that a final state and initial state is added into the set of states; there also has to be an initial stack symbol hence $X_{0}$, and a specified initial state is given, with an a specified final state; and apart of this final state, is the initial stack symbol

**Final State to Empty Stack**
Given a Final State PDA
$$
P_{F} = \left( Q_{F}, \sum, \Gamma_{F}, \delta_{F}, q_{0}, Z_{0}, F \right)
$$
an equivalent **empty stack** PDA
$$
\begin{align}
P_{N} &= \left( Q_{N} \cup \{ p_{0}, p \}, \sum, \Gamma_{N} \cup \{ X_{0} \}, \delta_{N}, p_{0}, X_{0} \right) \\
&\delta_{N} (p_{0}, \epsilon, X_{0}) = \{ (q_{0}, Z_{0}X_{0}) \} \\
&\delta_{N} (q, \epsilon, \_) | q \in (F \cup \{ p \}) = \{  (p, \epsilon) \}
\end{align}
$$
> The main idea here is when reach final state; empty the stack! That's why the transition function moves from the initial state with a word and initial state symbol,

Converting requires an understanding of the components and requirements of acceptance in the PDAs, and a transistion function that can further build ontop of to complete the PDA

#languages-computation #semester4 