- A *high-level* **problem independent** algorithmic framework that provides a *set of guideliens or strategies* to **develop heuristic opitimisation algorithms**

### General Types
- There are some types of metaheuristic algorithms, and they come under the following:
	- [[#Local Search]]
	- Population-based
	- Constructive

### Main Components of a MH Search

- [[Representation]] of candidate solution
- [[Evaluation Function]]
- The Initialisation; where an initial candidate solution may be chosen.
	- *randomly*
	- using a *constructive heuristic*
	- according to *some regular pattern*
- [[Neighbourhoods]] relations (the move operators)
	- the *search process* (guideline)
	- [[#Stopping conditions]]
	- a *mechanism* for [[#Escaping from the Local Optima]]

> It looks very familar and similar to [[Heuristics]] components, except the function results in a heuristic optimisation

### Escaping from the Local Optima


### Stopping conditions


## Local Search

> A Local search is an *optimising algorithm* to find the **optimal solution more quickly**. It cares only about *getting the solution* rather than the path of the solution

- As an example: a **Stochastic Local Search**
```
s0 ; // starting solution 
s* = initialise(s0); // e.g., improve s0 or use the same repeat 
	// generate a new solution 
	s' = makeMove(s*, memory); 
	// choose a neighbour of s* 
	accept = moveAcceptance(s*, s', memory); 
// remember sbest 
if (accept) s* = s'; 
// else reject new solution s' until (termination conditions are satisfied);
```
- In a stochastic local search, the *move acceptance* (code seen above) whether to *reject or accept* the new solution consdering its **evaluation, $f(s')$ and memory**
	- More on [[Move-Acceptance]]
- Accepting *non-improving* moves could be used as a mechanism to escape from the *local optima*

### Iterated Local Search


#ai-methods #semester4 