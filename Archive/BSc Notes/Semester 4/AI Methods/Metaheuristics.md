- A *high-level* **problem independent** algorithmic framework that provides a *set of guidelines or strategies* to **develop heuristic optimisation algorithms**

### General Types
- There are some types of metaheuristic algorithms, and they come under the following:
	- [[Local Search]]
	- [[Population-based Search]]
	- Constructive

### Main Components of a MH Search
- [[Representation]] of candidate solution
- [[Evaluation Function]]
- [[The Initialisation]] where an initial candidate solution may be chosen.
	- *randomly*
	- using a *constructive heuristic*
	- according to *some regular pattern*
- [[Neighbourhoods]] relations (the move operators)
	- the *search process* (guideline)
	- [[#Stopping conditions]]
	- a *mechanism* for [[#Escaping from the Local Optima]]

> It looks very familar and similar to [[Heuristics]] components, except the function results in a heuristic optimisation

### Escaping from the Local Optima
There are a few methods that can help us escape from the local optima:
- **Iterate with different solutions** or re-initialise search whenever a local optimum is encountered.
	- [[Local Search#Iterated Local Search]] does this! 
- **Changing the search landscape** by
	- changing the *objective function* (i.e. Guided Local Search)
	- or using *different neighbourhoods* ultimately (i.e. Variable neighbourhood search and hyper-heuristics..)
- **Using memory** ([[Local Search#Tabu Search]] does this!)
- **Accepting non-improving moves**; simply allow search using candidate solutions with *equal or worse evaluation function values than one in hand*
	- This could lead to *long walks* on *plateaus* during the search process and potentially causing cycles - visiting the same states of solution (tread with caution!)

> Note that **none** of the mechanisms is guaranteed to always escape effectively from local optima

### Stopping conditions
AKA *termination criteria*
- If a **fixed max number of iterations** or moves/objective function evaluations, or a fixed amount of CPU time is *exceeded*
- If the **consecutive number of iterations** since the *last* improvement in the best *objective function value* is *larger* than a **specified number (threshold)**
- If **evidence** can be given that an *optimum solution* has been obtained (this means that an optimum objective value is known)
- If **no feasible solutions** can be *obtained* for a *fixed number of steps* 
	- a *solution is feasible* if it *satisfies **all constraints*** in the optimisation problem
> we can deal with infeasible solutions by using a problem domain *specific repair operator* or penalise *each constraint violation* for the infeasible solution such that they can't be better than the *worst feasible solution for a given instance*

> the last part of the move operator is the search process; this varies from one metaheuristic algorithm to the next; but a common denominator being the move acceptance.

---

#ai-methods #semester4 