 The study of this connect deeply with [[Formal Languages]], as it creates methods for *specifying* formal languages are very important in many areas of CS;
	- [[Context Free Grammar]] are very useful when designing software that processes data with *recursion*, like the parser in a compiler.
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



#semester4 #languages-computation