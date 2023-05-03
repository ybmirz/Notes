 The study of this connect deeply with [[Formal Languages]], as it creates methods for *specifying* formal languages are very important in many areas of CS;
	- [[Context Free Languages#Context-Free Grammar]] are very useful when designing software that processes data with *recursion*, like the parser in a compiler.
	- [[Regular Expression]] are very useful for specifying lexical aspects of programming languages and search patterns

>  A study of abstract machines and automata, as well as the computational problems that can be solved using them

- We can further use this theory to understand the **limits of computation** with *two main issues*
	- **What** can a **computer** do *at all*? -- **Decidability**
	- **What** can a computer do *efficiently* -- **Interactability**

### The Halting Problem
- The problem describes if given a program and an einput, can we possibly determine whether the program will eventually halt ?
- In simpler cases, it is possible by simple procedural deduction that it could be determined whether a program would halt or not, but is it possible to **create another program** to determine the halt?
	- Formally, Can we write a program that will always be able to tell us (i.e. decide) whether ANY arbitrary program with ANY input, will terminate (or halt) or not?
- The problem relates with **Decidability** where it's decided that:
	- `It is impossible to write a program that decides if another, arbitrary program with any input terminates (halts) or not.`

- However, this could even be **further proved** where it is impossible to write such a program, and this was first done by **Alan Turing**

## Finite Automata
- The most basic machine (automata) to recognise patterns. An abstract machine that has five elements or tuples. 
	- It has **a set of states** and **rules for moving** from one state to another, but it depends upon the *applied input symbol*
	- This automata deals heavily with [[Regular Languages]]

#### The Problem
- An important question that is taken from understanding languages, is that
> Given a *language* $L \subseteq \sum^{*}$ and a *word* $w \in \sum^{*}$, can we determine if $w \in L$ ?

- A possible solution is to *construct* a machine that **accepts a word w** $\iff w \in L$
	- These machines could abstractly be studied as automata

- There's two types of finite automata that could be further developed:
	- [[Deterministic Finite Automata]] (DFA)
	- [[Nondeterministic Finite Automata]] (NFA)

> The main difference between a DFA and an NFA is that NFAS can have **multiple start states** instead of a *single one* and the **type of transition function**

- By understanding the main *single* difference between NFAs and DFAs, it could be seen that they can easily be **converted** to one another. More here [[DFAs are NFAs]]

	The main problem with a finite automata is that it requires a *finite* memory, so we can further develop an automaton that goes beyond this limitiatoin.

## Pushdown Automata
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

#semester4 #languages-computation