## Instantaneous Description (ID)
- An ID describes completely the **state of computation** for a PDA;
	- It is a triple where $(q, w, \gamma)\in Q \times \sum^{*} \times \Gamma ^{*}$
> a state, a word and a stack configuration; this three describes the current state of computation of a PDA by definition


## One Step Relation
The relation $i_{1} \vdash i_{2}$ means:
	"the PDA $P$ can move *one-step* from ID $i_{1}$ to $i_{2}$"
The formal definition of which:
$$
\begin{align}
\vdash{} &\subseteq ID \times ID \\
&(q', \alpha) \in \delta(q,x,z) \to (q,xw,z\gamma) \vdash (q', w, \alpha \gamma) \\
&(q', \alpha) \in \delta(q,\epsilon,z) \to (q,w,z\gamma) \vdash (q',w,\alpha \gamma) \\
where \\
q, q' &\in Q \\
x &\in \sum \\
w &\in \sum^{*} \\
z &\in \Gamma \\
\alpha, \gamma &\in \Gamma ^{*}
\end{align}
$$
> The above describes how we can use a one-step relation to easily describe  the transformation of one PDA state to another


## Many-Step Relation
With a one-step relation, there shall also be a simplified notation to describe a many-step relation and simply it is $i_{1} \vdash^{*} i_{2}$ which means:
	"the PDA $P$ can move zero or more steps from ID $i_{1}$ to $i_{2}$"
The formal definition goes on as follows:
$$
\vdash^{*}{} \subseteq ID \times ID
$$
- It is the reflexive transitive closure of $\vdash$
 ---
## Common Languages
As given by the definition of a PDA, there's two types of PDAs and hence two distinct languages that they can accept, as defined below:

- The Final state PDA $P = (Q, \sum,  \Gamma, \delta, q_{0}, Z_{0}, F)$ and its language can be defined as 
$$
L(P) = \{ w | ((q_{0}, w, Z_{0}) \vdash^{*} (q,\epsilon,\gamma)) \land (q\in F) \}
$$
> The language of the PDA $P$  is the set of words where the word associated with an initial state, and an initial set of stack symbols can be used to move zero or more steps to an association of a state, an $\epsilon$ and a set of stack symbols where the state is a part of final/accepting states

- The empty stack PDA $P = (Q, \sum, \Gamma,\delta, q_{0}, Z_{0},F)$ , the language of P  is defined as:
$$
L(P) = \{ w | (q_{0}, w, Z_{0}) \vdash^{*} (q, \epsilon, \epsilon) \}
$$

> The language of the PDA $P$ is the set of words where the word with its associated initial state, and the initial set of stack symbols can be used to move zero or more steps to an association of a state, empty words, and an empty stack.


#languages-computation #semester4 