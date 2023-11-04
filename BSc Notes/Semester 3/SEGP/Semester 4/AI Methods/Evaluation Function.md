- Generally known to be the **objective**, or cost, fitness, penalty, etc.
- It indicates the *quality* of a *given solution* and distinguishes between a **better or worse solution**
- It serves as a major link between the algorithm, and the problem being solves
	- Hence becoming a *feedback* for the *searching process* (given a heuristic search)

- Generally it could be **computationally expensive**

> Constructing a globally valid approximate model remains difficult, and so beneficial to selectively use the original evaluation function together *with the approximate model*

#### EF Example: TSP
- The travelling salesman problem (TSP) requires a *search for a permutation*
	- Which shows: $\pi: \{ 0, \dots, N-1 \} \to \{ 0,\dots,N-1 \}$
- The EF will use a *cost matrix* of $C=[c_{ij}]$ where $c_{ij}$ denotes the cost (assumed) of the travel, from city $i\to j$ that minimizes the *path length*

- General evaluation function is as follows:
	$$
f(\pi, C) = \sum^{N-1}_{i=0} c_{\pi(i), \pi((i+1)modN)}
$$
#### Delta (Incremental Evaluation)
- Calculating effects of differences between current search position *s* and a neighbor *s'* on the EF value.

> EF's often consists of *independent contributions of solution components; hence, $f(s')$* can be efficiently calculated from $f(s)$ by the **difference** in terms of solution components.

![[Pasted image 20230510112935.png]]

> The image shows the delta evaluation for TS

- This is crucial for efficient implementation of heuristics/meta/hyper

#semester4 #ai-methods 