By formal definition: 
- A CFG is a **4-tuple** $(N, \sum, P, S)$ where
	- $N$ is a finite set of non-terminal symbols
	- $\sum$ is a finite set of terminal symbols
	- $N \cap \sum \neq  \emptyset$  // the above sets are not to intersect
	- $P$ is a finite set of productions; Each production has the form $A \to a$  where $(A \in N),  (a \in (N \cup \sum)^{*})$
	- $S \in N$ is the start symbol
	
> The grammar can further define a context free language, as it can be see later down the line; The grammar here is consisting of a starting symbol (a part of the non-terminal symbol) and various other symbols, a set of terminal symbols; and a finite set of production where each production transforms a non-terminal symbol into a symbol within the language (shown by $A \to a$)

In other words, a grammar is a set of **production rules** that describe all possible strings in the formal language. This grammar can further generate Context free languages;

How these productions are applied can affect how this grammar *derives*
>  a CFG can be used as the context of a derivation; A Derivation is a type of relation between a set of symbols to another;

For any context free grammar $G = (N, \sum, P, S)$, there are **three** derivation relations that can happen:
- [[#Directly Derives]]
- [[#Derives]]
- [[#Derives in 1 or more]]

### Directly Derives
$$
\Rightarrow_{G}{} \subseteq \left( N \cup \sum \right)^{*} \times (N \cup \sum)^{*}
$$
- If $(A \to \beta) \in P$ and $\alpha, \gamma \in (N \cup \sum)^{*}$
	- then $\alpha A \gamma \Rightarrow_{G}{} \alpha \beta \gamma$
> If the grammar has a production for A, then regardless of context it can be applied

### Derives
$$
\Rightarrow^{*}_{G}{} \subseteq (N \cup \sum) ^{*} \times (N \cup \sum)^{*}
$$
- This is simply a *transitive reflexive closure* of the directly derives; which means that it is, **zero or more applications of $\Rightarrow_{{G}}$** thus
$$
a_{0} \Rightarrow_{G}^{*} a_{n} \iff a_{0} \Rightarrow_{G} a_{1} \Rightarrow_{G} \dots \Rightarrow_{G} a_{n}
$$

### Derives in 1 or more
$$
\Rightarrow_{G}^{+} {} \subseteq (N \cup \sum) ^{*} \times (N \cup \sum) ^{*}
$$
- This is a *transitive closure* of $\Rightarrow_{G}$
- That is; **one or more applications of $\Rightarrow_{G}$**


> as a summary;
> - $\Rightarrow$ applies **one production**
> - $\Rightarrow^{*}$ applies **zero or more productions**
> - $\Rightarrow^{+}$ applies **one or more productions**

---
### Examples

Some examples of a constructed CFG
- Any number of **a's** : $S \Rightarrow aS | \epsilon$ 
- Any number of a's and b's : $S \Rightarrow aS | bS | \epsilon$
- One `a` followed by one or two b's, followed by any number of a's: $$
\begin{align}
A &\Rightarrow aBC \\
B &\Rightarrow bB | bb  \\
C &\Rightarrow aC | \epsilon
\end{align}
$$
> The above productions create a grammar that fulfils the condition of string production

#languages-computation #semester4 