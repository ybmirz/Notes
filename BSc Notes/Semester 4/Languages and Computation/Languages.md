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
- It should be remembered that *languages are sets* rather than sequences
- hence given *two languages* M and N over the alphabet $\sum$ their concatenation, known as ($MN$) is
$$
MN = \{ uv |u \in M \land v \in N\}
$$
As an example:
$$
\begin{align*}
\sum = \{ a,b,c \}\\
M = \{ \epsilon, a,aa \} \\
N = \{  b,c \} \\
MN = \{ uv | u \in \{ \epsilon, a,aa \} \land v \in \{ b,c \} \} \\
= \{ \epsilon b,\epsilon c,ab,ac,aab,aac \}\\
= \{ b,c,ab,ac,aab,aac \}
\end{align*}
$$
### Properties of Language Concatenation
1. It is known to be **associative**
   Given the example: $L(MN) = (LM)N$
2. Language concatenation *inherently* has **zero $\emptyset$**
   Hence $L\emptyset = \emptyset = \emptyset L$
3. The concatenation of languages has **unit $\{ \epsilon \}$** (a language where it only contains the *empty word*)
   Hence, $L \{  \epsilon \} = \{ \epsilon \} = \{ \epsilon \} L$
4. Generally, the concatenation of languages distributes through a **set union**
   $$
L (M \cup N) = LM \cup LN
$$
However it does **not distribute** through a **set intersection**
$$
L (M \cap N ) \neq LM \cap LN
$$

> A Lang can be concatenated with itself, and it is noted with an *exponent notation* 
> $L^{1} = L$, $L^{2} = L L$, $\dots$, etc.
> Reminder that $L^{0} = \{ \epsilon \}$, where $\epsilon$ is the unit of concatenation.

## Kleene Star
Given that $L \subset \sum^{*}, L^{*}$ is **zero or more** concatenations of $L$;
- There's a few definitions that could be written down to further explain a *kleene star* but think of this as a generalisation of language concatenation.

- Definition 1:
$$
\begin{align}
L^{*} = \{ w_{0}w_{1}\dots w_{n-1} | n, i \in \mathbb{N}, \forall i < n, w_{i} \in L \}
\end{align}
$$
> A kleene star by defnition of the above, has elements in which is *from L* yet concatenate of $n$ times

- Definition 2:
$$
L^{*} = \bigcup_{n=0}^{\infty} L^{n} = L^{0} \cup L^{1} \cup L ^{2} \cup \dots L^{n}
$$
> A kleene star is defined to be a big union of concatenations of L's up to *n*  times


#semester4 #languages-computation 