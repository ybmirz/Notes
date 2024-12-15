- Most of the terminologies given shall be taken in a very **technical manner**. Below are some important terms that are mostly used within the definition of this module.

1. **Alphabet** is a **finite set** of *symbols*
2. **Word** is a **finite sequence** of *symbols*
	- the term **string** is often used *interchangably* with the term **word**
1. A **language** is a **set** of [[Word]]
	- [[Languages]] can be finite *or* infinite

### Sigma
$\sum$ is usually taken as a *representation* of an **alphabet** and it denotes the set of the symbols, such as:
$$ \sum_{a} = \{0, 1\} $$
> The above shows an alphabet set of `0 and 1`
> There's an exception that $\epsilon$ is the only **symbol** that has a **special meaning**

- We can proceed to denote **a set of all words** over a specific alphabet by $\sum^{*}$ 
	- It can either be a **finite or infinite** set
- Inductively, $\sum^{*}$ can be defined inductively as follows:
	- $\epsilon \in \sum^{*}$ 
	- if $x \in \sum^{*}$ and $w \in \sum^{*}$ then $(x,w) \in \sum^{*}$
		- which includes $\sum = \emptyset$

> The above shows, for any $\sum^{*}$, the empty word $\epsilon$ exists
> An inductive definition of a set S consists of first specifying one or more elements of the set S and then specifying one or more construction rules to obtain other elements of S based on existing elements of S

### Alternative Notation
- Logically, we could take that a **set of all words of length `n`** is denoted by $\sum^{n}$ where ($n \in \mathbb{N}$)
	- As an example, given $\sum = \{a,b\}$ , $\sum^{2} = \{aa, ab, bb, ba\}$ 

### Epsilon
- $\epsilon$ is used to the denote **an empty word**, or **a sequence of zero symbols**
	- Note that it's an empty *word* hence it is a **word** and not merely a **symbol**
	- It should also be taken that it does **not denote** an **empty set** ( $\emptyset \enspace \{\}$ )
- Hence, $\{\epsilon\} \neq \{\}$ 

#semester4 #languages-computation 