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

#semester4 #languages-computation 