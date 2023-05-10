- A **neighbourhood** of a solution *x* is the *set of solutions* that can be *reached from x* by a **simple operator move** (also known as the *move operator/heuristic*)
- There can be multiple neighbourhoods of multiple [[Representation]]s

> Every representation would have a neighbourhood of the same representation, hence below explains how it can be seen. This can easily be understood when you dive more in various algorithms; it comes intuitively. 

#### NH for Binary Representation
- a **bit-flip** operator; where *a bit* is *flipped* in a *given solution*
- Using the **hamming distance** between *two-bit strings* vectors of equal length in the number of positions at which the corresponding symbols differ

> if the binary string is of size *n*, then the neighbourhood size is *n* 

#### NH for Integer/Value Representation
- A random neighborhood/move/perturbation/assignment operator: a *discrete value* is replace by any other character of the alphabet.

> if the solution is of size $n$ and alphabet is of size $k$, then the neighborhood size is $(k-1)n$. Take each alphabet to be a solution.

#### NH for Permutation Representation
- **Adjacent Pairwise Interchange**: *swap adjacent entries* in the permutation
	- if the permutation size is $n$, then the NH size is $n-1$ (simple enough)
- **Insertion Operator**: take *an entry* in the permutation and insert *it in another position*
	- NH size: $n(n-1)$
- **Exchange Operator**: arbitrarily selected *two entries* are *swapped*
- **Inversion Operator**: select two arbitrary entries and *invert* the *sequence in between*

> Choosing an appropriate encoding to represent a candidate solution is crucial in heuristic optimisation



#semester4 #ai-methods 