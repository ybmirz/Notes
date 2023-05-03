### DFA -> NFA
- First thing to note is that **DFAs are a special case of an NFA**, with its specialty being a DFA having: (as defined in [[Deterministic Finite Automata]])
	- exactly **one initial state**
	- and exactly **one transition from each state** per symbol

> thus all **DFA transition diagrams** also *define* an NFA that accepts the *same language*

- Let's look into how it defines this NFA; Given a DFA
	$$
A = ( Q,\sum, \delta_{A}, q_{0}, F)
$$
- an **equivalent NFA** $N(A)$ can be constructed as follows:
$$
\begin{align}
N (A) &= \left( Q, \sum, \delta_{N(A)}, \{ q_{0} \}, F\right) \\
where \\
&\delta_{N(A)}(q,x) = \{ \delta_{A}(q,x) \}
\end{align}
$$

> Notice that the intial state $q_{0}$ in the DFA, is added into the *set of initial states* in the NFA ($\{ q_{0} \}$) and the transition function $\delta_{N(A)}$ is simply the *set of transition function* with the DFA's transition function being an element.

### NFA -> DFA
Given the observations in [[Nondeterministic Finite Automata#Observations]] , we could convert an NFA to a DFA by simply **taking each set of NFA** to be a **single DFA state**

- Let's say given an NFA;
$$
\begin{align}
A &= \left( Q, \sum, \delta_{A}, S, F_{D(A)} \right) \\
\end{align}
$$
- an equivalent DFA $D(A)$ can be constructed as follows:
$$
\begin{align}
D (A) &= \left(P(Q), \sum, \delta_{D(A)},S, F_{D(A)}\right) \\
where \\
&\delta_{D(A)}(P,x) = U\{ \delta_{A}(q,x) | q\in P \} \\
&F_{D(A)} = \{ P | P\in P(Q) \wedge (P \cap F_{A}) \neq \emptyset \}
\end{align}
$$
> $P$ in the above definition can be seen to be the *interchangeable constant* where it is a **single DFA state** and as well, a **set of NFA states**

- Examples are given in the slide; too lazy to write them all out

> A DFA computes by going from **one state to another.** An NFA computes by going from **one configuration of states to another.**

### Lazy Subset Construction
- The above example of converting an NFA to a DFA is known as the **subset construction method** but given an example, often times many of the DFA states are unreachable from the initial state. (we can simply avoid this work) and comes down on a *lazy method*

- All that needs to be done is simply, continuing with the transition table from an NFA, and construct a DFA that includes the unreachable state as *an actual state*

- Given the below NFA transition diagram
![[Pasted image 20230312150505.png]]
- A **transition table** can be created that follows the above diagram, such as;

| | a | b | c |
|-|--|---|---|
|$*\{ 1,3 \}$ | $\{ 1,2 \}$ | $\{ 3 \}$ | $\emptyset$ |
|$*\{ 1,2 \}$ | $\{ 1,2 \}$ | $\{ 3, 2, 1 \}$ | $\{ 3 \}$ |
|$*\{ 3 \}$ | $\emptyset$ | $\emptyset$ | $\emptyset$ 
|$\emptyset$ | $\emptyset$ | $\emptyset$ | $\emptyset$ |
|$*\{ 3, 2, 1 \}$ | $\{ 1,2 \}$ | $\{ 1,2,3 \}$ | $\{ 3 \}$ |

> It should be remembered that above is an NFA hence the inital set of states, rather than a single initial state

- Lazily, this table can then be translated into a *literal diagram* as follows:
![[Pasted image 20230312151747.png]]

### Proof of Subset Construction
- An **inductive** proof could be given to describe the subset construction of a DFA from an NFA; a proof that they can be converted which then shows $L(A) = L(D(A))$ where $A$ is an NFA


### DFA Minimization
Before we minimise a DFA, we need to figure out the equivalence of states within the DFA; the main definition of which is:
$$
\begin{align}
DFA&( Q,\sum, \delta, q_{0}, F) \\
&p,q \in Q \\
&\forall w \in \sum*  \\ \\
\hat{\delta}(p,w) &\in F \iff \hat{\delta}(q,w) \in F
\end{align}
$$

> $p$ and $q$ are equivalent states of the transformation of the word at state $p$ is equivalent to the transformation of the word at state $q$

> It should be noted that $p$ and $q$ does not have to be the **same** state. The opposite of equivalent is **distinguishable**



#semester4 #languages-computation 