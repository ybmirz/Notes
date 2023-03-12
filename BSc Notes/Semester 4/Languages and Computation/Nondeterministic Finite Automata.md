## Definition
- Informally, they are mostly the same as DFAs, but:
	- an NFA can *make choices*
	- a word is accepted if choices can be made such that the machine ends in a final state.
- Another way to look at it, is that:
	- an NFA can be in **multiple states** at the same time
	- a word is accepted if **any** of the ending states are finals

- Formally, a NFA $N$ is a **5-tuple** (similar to a DFA), $N = (Q, \sum, \delta, S, F)$
	- $Q$ is a **finite set of states**
	- $\sum$ is **an alphabet**
	- $\delta \in (Q * \sum \rightarrow P(Q))$ is a **transition function**
	- $S \subseteq Q$ is a **set of initial states**
	- $S \subseteq Q$ is a **set of accepting (or final) states**

### Example
- We can create an NFA $A$ that *accepts **all words*** over $\sum = \{ 0,1 \}$ 
![[Pasted image 20230307225304.png]]
The above NFA can be represented by a **transition table** and a **formal definition** as:
$$
A = (\{ q_{0}, q_{1}, q_{2} \}, \{ 0,1 \}, \delta_{A}, \{ q_{0} \}, \{ q_{2} \})
$$
| | 0 | 1 |
| - | - | - |
| $\rightarrow q_{0}$ | $\{q_{0}\}$ | $\{ q_{0}, q_{1} \}$ |
| $q_{1}$ | $\{ q_{2} \}$ | $\{ q_{2} \}$ |
| $*q_{2}$ | $\emptyset$ | $\emptyset$ |

- To check if a word is accepted by an NFA, it requires you to check with all the possible states. **If at the end of the word, any of the final states are marked, the word is then accepted** (more formal definition underneath)

- Another way that could determine languages that are accepted by an NFA, is by a **generalisation** of the *union operation* on a finite set of sets; such as
$$
U\{ A_{1}, A_{2}, \dots A_{n} \} = A_{1} \cup A_{2} \cup \dots \cup A_{n}
$$

- Hence when we define $\delta \in P(Q) x \sum^{*} \rightarrow P(Q)$ with the intention that $\delta(S,w)$ is the *set of states* that is **marked** after having read $w$ starting with the initial markers given by $S$; it can be shown as:
$$
\begin{align}
\delta(P, \epsilon) &= P \\
\delta(P, xw) &= \delta(U\{ \delta(q,x) | q \in P \})
\end{align}
$$
> the transition function given an initial state set P, $x$ (a symbol in the word $w$) is to be recursively transited in the states in P

![[Pasted image 20230312142014.png]]
> The above image is an example to how we can use the *union definition* to define a language accepted by an NFA.

### Observations
- An NFA is always in a **set of states**
	- Hence *when reading an input*, the automata *enters a new set of states*
- The total possible sets of states is $2^{|Q|}$ *possibilities*, because for *each state, the automata is either in that state or not* (hence 2 possibilities). 
	- $Q$ is the finite set of states given into the automata


#semester4 #languages-computation 