> A heuristic is a *rule of thumb method derived from human intuition*. It is a search method which seeks good *near optimal solutions* at a reasonable cost **without being able to guarantee optimality**

- Heurisitic search are searches that have *heuristic* characteristics in finding the solution.
- It is a *search algorithm*
	- Figuring out how to get into a search function

## Main Components
- [[Representation]] of  a *candidate solution*
	- Finding someway to *represent* a *mock* solution
	- Also representing the operators or objects within the algorithm
- [[Evaluation Function]] otherwise known as *Objective Function*
- An Initialisation
- The [[Neighbourhoods]] relation (moving operators)
- The [[#Search Process]] itself 
- Mechanism for *escaping* from the **local optima** (as a failsafe)
	- An example could be taken from [[Hill Climbing]]

	Initialisation could influence the performance of an optimisation algorithm. The evaluation function then guides the search process and fast evaluation is important.

---

#### Max-Sat Problem
- Maximum-Satisfiability Problem refers to the *maximum* possible *satisfied clauses* given a problem instance.
	- More research necessary here 

#### Travelling Salesman Problem
- One of the most common problems to solve:
	- Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city and returns to the origin city? *NP-Hard
- Some example **Heuristics Searches** that can be done here is 
	- the Nearest Neighbour Algorithm (*deterministics and systematics*)
		- Simplifying this algorithm, an initial location is chosen at random, and then the algorithm chooses the nearest unvisited city as the next move, and so forth until the last city is reached (back to the initial city). 
	- Pairwise Exchange (2-opt) aka Lin-Kernighan heuristics (*perturbative, stochastic and local search*)
		- Simplifying this algorithm, routes between all the city has been defined, applying 2-opt results by removing two edges and replacing them with two different edges (within the route), reconnects the fragments into a new shorter route.

Let's look into how heuristics search can optimise the two algorithsm stated above:
- a **constructive stochastic local search** is done using the first algorithm, where we apply NN to construct a complete solution. A comparison between the new solution to the best found so far and update the best solution as appropriate. This works as NN has random initial location chosen, hence different comparable routes created. This is repeated while the *maximum number of iterations is not exceeded* (as a parameter to the local search)
- a **perturbative stochastic local search** is done for the second algorithm, where we apply 2-opt on a random current solution. This new solution is compared to the previous solution, and if there is improvement, make the new solution the current solution (similar to constructive stochastic). This is repeated while the *maximum number of iterations is not exceeded* (parameter)

> It should be noted that the example heuristics above are *stochastic* meaning they move from solution to solution in the space of candidate solutions by applying *local changes* (such as neighbours or edges/operators). The stochastic is due to an element of randomisation in the search.


### Deterministic vs Stochastic
- Deterministic Heuristic searches provide the *same solution* when run on the given *problem instance* regardless of *how many times*
- Stochastic heuristic searches contain a *random component* and may return a different solution at each time they are run on the *same instance*
	- This enables *an average performance* that can be computed for comparison of different stochastic heuristic applying **statistical tests**



#semester4 #ai-methods 