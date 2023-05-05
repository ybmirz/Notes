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

After defining a pushdown automata, we can further develop the understanding by looking at the [[Language of a PDA]]; This is not the *languages* accepted by a PDA, but rather the terminologies that can be used to further understand a pushdown automata

[[Language of a PDA#Common Languages]] notes some common languages that a PDA could have; with its formal definitions

- Pushdown Automatas are also able to *express* [[Context Free Languages]]

As noted above, a PDA is simply an NFA with an unlimited stack memory; what about a deterministic version of this; more on [[Deterministic Pushdown Automata]]

## Conversion
- As stated above, a PDA can be accepted by either an empty stack or a final state; they are equivalent in the sense that the Language $L$ has a PDA that accepts it by *final state* if and only if $L$ has a PDA that accepts it by *empty stack*
	- Now this mean that it would be possible to *convert* a PDA $P_{N}$ that accepts by empty stack to a PDA that accepts by final state $P_{F}$, and vice versa
- 


#languages-computation #semester4 