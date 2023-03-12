## Definition
- Informally, a *finite automata* is a machine that has *finite number of states*
	- This machine is also in *exactly one state* at a time.
	- The input is also read in one symbol at a time.
- State changes happen according to the current state and the current symbol.

- Formally, a **DFA** (D) is a **5-tuple**, $D = \left( Q,\sum, \delta, q_{0}, F  \right)$
	- $Q$ is the **finite set of states**
	- $\sum$ is an **alphabet** (that the DFA interacts with)
	- $\delta \in \left( Q *\sum \rightarrow Q \right)$ is a **transition function** that the DFA follows
	- $q_{0} \in Q$ is the **initial state**
	- $F \subseteq Q$ is a **set of accepting (or final) states**

### Example

An example the following *automaton*:
$$
D = (\{ q_{0}, q_{1}, q_{2} \}, \{ 0,1 \}, \delta_{D}, q_{0}, \{ q_{2} \})
$$
> $\{ 0, 1 \}$ is the alphabet
> $\{ q_{0}, q_{1}, q_{2} \}$ is the set of states for the automaton

the $\delta_{D}$ function could be represented using a **transition table** and it's represented as below from:
$$
\delta_{D} = \{ ((q_{0},0),q_{1}), ((q_{0}, 1),q_{0}) \dots ((q_{2}, 1), q_{2}) \}
$$
resulting in a **transition table** of 
| | 0 | 1 |
| - | - | - |
| $\rightarrow q_{0}$ | $q_{1}$ | $q_{0}$ |
| $q_{1}$ | $q_{1}$ | $q_{2}$ |
| $*q_{2}$ | $q_{2}$ | $q_{2}$ |

>$q_{2}$ is the final state of the automaton
>The transition table could be further explained using a **transition diagram**

![[Pasted image 20230307215800.png]]

- As an example below are *sample words* being tested if they are part of the automaton:
$$
\begin{align}
1110 &\rightarrow False \\
000 &\rightarrow False  \\
101 &\rightarrow True  \\
1101 &\rightarrow True  \\
1000 &\rightarrow False 
\end{align}
$$

- Using a DFA $A$, we can associate a *language* $L(A) \subseteq \sum^{*}$. To determine if a *word* $w \in L(A)$, we follow through its *transition function* (and its edges) corresponding to that *word* $w$, and if we *end up in an accepting state* (part of the final states), it can be **easily said that** $w \in L(A)$, **else** $w \notin L(A)$.
> This basically means we can **finitely describe** an **infinite language** and even an easy method for checking up *language membership*

Given a DFA $D = (Q, \sum, \delta, q_{0}, F)$, the *language of D* is defined as:
$$
L (D) = \{ w | \delta(q_{0}, w) \in F \}
$$
#semester4 #languages-computation 