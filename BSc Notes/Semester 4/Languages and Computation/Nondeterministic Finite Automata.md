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

---
Below are topics in relation with Regular Expressions;  NFA that expresses regular expressions

#### Sequential Composition of NFAs
An example of this composition is $N(R_{1}R_{2})$

- Let's get through it step by step; 
	- Placing $N(R_{1})$ and $N(R_{2})$ side by side
	- Remove the *initial* arrows in $N(R_{2})$
	- Any arrows that points to an *accepting state* in $N(R_{1})$ need to be *duplicated* to point to **all** states that were *the initial arrows* in $N(R_{2})$. (including transition and initial arrows)
	- All *accepting states* in $N(R_{1})$ should be changed to **not accepting**

- Another difficult one would be figuring out $N(R^{*})$; We simply;
	- Start with drawing out $N(R)$
	- Take all transitions that point to an *accepting state* is to be *duplicated* to point to **all** the initial states
	- An additional initial (and accepting state should be added)

#### Repetition of NFAs
Following the format of $N(R*)$

- Simple two steps of transformation:
	- Starting with the one $N(R)$
	- All transitions that point to an accepting state need to be duplicated to point to **all** initial states
	- An additional state (and accepting state) should be added

> last note; the NFA of an NFA of R is the same as  the NFA of R;
> 	$N((R)) = N(R)$

#semester4 #languages-computation 