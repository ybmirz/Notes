- The module highly focuses on understanding the language of machines, and the basics of computation.
- This module is **100% examination** hence *theory-based* and it is the heart of computer science logic.

> Personal assumption: The module would enhance how we should think as a computer scientist, and probably a research.

- Things covered:
	- **[[Automata Theory]]**
	- **[[Formal Languages]]**
	- **[[Models of Computation]]**
		- The limits of computatbility and relevance of the machines

#### The Chomsky Hierarchy
- A hierarchy that describes the hierarchy of languages (or **classes of formal grammar**), each level builds ontop of the fundamentals of the one underneath.
![[-images/Pasted image 20230131112822.png]]
- The entire module focuses on going through this hierarchy to build and understand formal languages.
	- These formal languages build upon [[Terminology]]'s specified within the field

#### Automata Theory
- A model for important kinds of hardware and software such as:
	- [[#Lexical Analysers]] and [[#Parsers]] for compilers
	- Software for designing and checking digital circuits
	- Finding words and patterns in large bodies of text 
	- Verification of systems with finite numbers of states
- The study of this connect deeply with [[Formal Languages]], as it creates methods for *specifying* formal languages are very important in many areas of CS;
	- [[Context Free Languages#Context-Free Grammar]] are very useful when designing software that processes data with *recursion*, like the parser in a compiler.
	- [[Regular Expression]] are very useful for specifying lexical aspects of programming languages and search patterns.
- More on [[Automata Theory]]

## The fundamental question

> Given a language $L \subset \sum^{*}$ and a word $w \in \sum^{*}$, can we determine if $w \in L$;

- The above question, *inductively* as a human being can understand that *it might be true*. This whole module bases off us trying to understand information and knowledge theory, using based languages and computation to construct a proper argument against the fundamental question

- Hence so, let's say $L$ is **finite**, it's simple, we simply prove its existence in L given the words in the alphabet
- however, let's say it's **infinite**, it gets a little complicated because we would need:
	- a *finite and concise* description of the *rather infinite* language
	- and also a *method* to **decide** if $w \in L$ or not, given the description

#semester4 #languages-computation