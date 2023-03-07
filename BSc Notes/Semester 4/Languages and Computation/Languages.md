- Simply, a language $L$ over an alphabet $\sum$ is a **subset** of $\sum^{*}$ 
	- $L \subseteq  \sum^{*}$
	- or $L \in P(\sum^{*})$
- A Language can be either a **finite** or **infinite** set
	- However, $\epsilon$ is **not always** an element of $\sum^{*}$, but it **may or may not be** an element of a  language.

As an example:
$$
\sum = \{ a,b,c \}
$$
Some languages that could be defined under this alphabet goes as follows:
$$
\{ a, abba, ba, bb \}
$$
$$
\{  c \}
$$
$$
\{ a^{n} | n \in \mathbb{N} \}
$$
$$
\dots
$$

## Concatenation of Languages

- Similar to words, an operation that could be done onto Languages, is a **concatenation**
- It should be noted that *languages are sets*, unlike words which are *sequences*
- A definition that could be noted for a concatenation of languages could be taken as:
	$$
MN = \{ uv | u \in M \wedge v \in N \}
$$
As an example:
$$
\begin{align}
\sum &= \{ a,b,c \} \\
M &= \{ \epsilon, a, aa \} \\
N &= \{ b,c \} \\
MN &= \{ uv | u \in \{ \epsilon,a,aa \} \wedge v \in \{ b,c \} \} \\
&= \{ \epsilon b, \epsilon c, ab, ac, aab, aac \} \\
&= \{ b,c,ab,ac,aab,aac \}
\end{align}
$$

> $\sum, M, N$ denote languages

### Properties of Concatenation
- It is **associative**:
$$
L(MN) = (LM) N
$$
- A Concatenation of languages has **zero** $\emptyset$ (AKA the empty language):
$$
L\emptyset = \emptyset = \emptyset L
$$
- Hence, a concatenation shall have a **unit $\{ \epsilon \}$** (the language containing only the empty word):
$$
L \{ \epsilon \} = L = \{ \epsilon \} L
$$

- The concatenation of languages distributes through the set union:
$$
\begin{align}
L (M \cup N ) &= LM \cup LN \\
(L \cup M) N &= LM \cup MN \\
\end{align}
$$
	- but it **does not** distribute through the *set intersection* such:
	$$
L (M \cap N) \neq LM \cap LN
$$
## Kleene Star
- Given L $\subseteq \sum^{*}$, $L^{*}$ is **zero or more concatenations of $L$
- Multiple definitions could be given for a Kleene star, from using the Big U or Propositional Logic or Set Theory

Using set theory:
$$
L^{*} = \{ w_{0}w_{1} \dots w_{n-1} | n,i \in \mathbb{N}, \forall i \lt n, w_{i} \in L \}
$$
> A Kleene star of L is a set of words of L concatenated. In other words, zero or more concatenations of L


#semester4 #languages-computation 