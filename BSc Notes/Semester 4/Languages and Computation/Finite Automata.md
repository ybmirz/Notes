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

	The main problem with a finite automata is that it requires a *finite* memory, so we can further develop an automaton that goes beyond this limitiation.


#languages-computation #semester4 