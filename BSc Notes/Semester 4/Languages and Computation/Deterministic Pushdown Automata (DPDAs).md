> Informally, a Deterministic PDA is one that has at most one possible transition at any given point 

A PDA $P = (Q, \sum, \Gamma, \delta, q_{0}, Z_{0},F)$ or $\left( Q, \sum, \Gamma, \delta, q_{0}, Z_{0} \right)$ is **deterministic** iff:
$$
\begin{align}
&\forall q \in Q, \\
&\forall x \in \sum, \\
&z \in \Gamma, \\  \\
| \delta(q, x, z) | &+ |\delta(q, \epsilon, z) | \leq 1
\end{align}
$$
> Basically ensures that there is at most one possible transition at a time (a transition of a PDA holds a three tuple of state, word and stack symbol)

### Efficient but less Expressive
- DPDAs can be implemented more efficiently than non-deterministic PDAs
	- The set of languages described by DPDAs are a of a strict subset of the set of languages described by PDAs
	- most Context-Free languages of practical importance can be described by a DPDA


#languages-computation #semester4 