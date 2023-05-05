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


#semester4 #languages-computation