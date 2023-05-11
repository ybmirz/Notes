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
- In a stochastic local search, the *move acceptance* (code seen above) whether to *reject or accept* the new solution considering its **evaluation, $f(s')$ and memory**
	- More on [[Move-Acceptance]]
- Accepting *non-improving* moves could be used as a mechanism to escape from the *local optima*

---

## Iterated Local Search
General pseudocode:
```
m0 = GenerateInitialSolution()
s* = LocalSearch(s0)
Repeat
	s' = Perturbation(s*, memory) // random move
	s' = LocalSearch(s') // the "hill climbing"
	// the conditions that the new local optimum must satisfy
	// to replace the current solution
	s* = AcceptanceCriteria(s*, s', memory) // has to be S best!
until (termination condition satisfied)
return s*
```
It may result in the below search:
![[Pasted image 20230510232248.png]]

- Iterated Local Search works based on *visiting a sequence* of *locally optimal solutions* by 
	- **perturbing** the current *local optima* (fulfils exploration!) and **applying local search** (exploitation!) after starting from the *modified solution*
> The perturbation phase might consist of more than one step
- The **perturbation strength** is *crucial* in this search as:
	- *too weak* may generate cycles within the search space
	- *too big* may result in the *loss of good properties* from the local optima.

- This algorithm can be analysed in the two main focus of:
**Acceptance Criteria**
	- where it could be extreme in *exploitation*: accepting only *improving solutions*
	- where it could be extreme in *exploration*: accepting *any solutions*
	- or it could be *deterministic* (using a threshold), *probabilistic* (like Simulated Annealing!)

#### Guidelines for ILS
- The **initial solution** should be to a large extent *irrelevant* for longer runs
- The **interactions among perturbation strenghts and acceptance criterion** can be important as it *determins the relative balance* of exploitation and exploration
- **Advanced acceptance criteria** take into account *search history*, by occasionally reverting to incumbent solutions
- Advanced ILS algorithms may *change nature or perturbation strength* **adaptively** during the search
- Local Search should be effective and as fast as possible. Better local search generally leads to better ILS performance.
- **Choosing a perturbation operator whose steps cannot be undone** easily by the local search.

> These guidelines allow for the most effective and efficient iterated local search

---

## Tabu Search
Initially proposed by Fred W Glover in 1986 and formalised in 1989; Uses **history** (memory structures) to escape from the *local minima* inspired by ideas from AI in the late 1970s.
- This search applies hill climbing/local search
	- Some solution moves are regarded as *tabu*
	- It revolves around the idea of that there is no point in accepting a new (poor) solution unless it is to avoid a path already investigated
- Determine the *initial candidate solution* $s$; While *termination criterion* is not satisfied, determine the *set $N'$* of *non-tabu neighbours* of $s$ and choose the *best improving candidate solution* $s'$ in $N'$
	- **Update** the *tabu attributes* based on $s'$
$$
 s := s'
$$

> a metaheuristic that guides a local heuristic search procedure to explore the solution space beyond the local optimum by use of a Tabu list!
> Using flexible memory structure in conjunction with strategic restrictions and aspiration levels as a means for exploiting search spaces!
> Examples of where Tabu Search can be used is in [[Scheduling]] optimisation problems.

##### How it Works
- It is a **stochastic local search algorithm** which heavily relies on the use of *explicit memory* for the search process
	- Systematic use of memory to *guide* the search process
	- Typically, *memory contains specific attributes* of previously seen solutions
	- Simple search strategies exploit only short term memory whereas more complex tabu strategies exploit longer term memories.

- In each step, **move** to *non-tabu* best neighbouring solution (taken as admissible neighbours) although it might be worse than the current one
	- To avoid cycles, tabu search tries to *avoid revisiting previously seen solutions*
	- also avoid *storing complete solutions* by basing the memory on *attributes of recently seen solutions*

> Tabu solution attributes are defined via local search moves!

- The tabu-list contains moves which have been made in the recent past. Solutions which contain tabu attributes are *forbidden* for a *certain number of iterations*
- Often, an *additional aspiration criterion* is used which specifies *conditions under which the tabu status can be override*
	- such as if the considered step leads to improvement in incumbent solutions

### Improvement on Tabu Search
- Further improvements can be achieved by using *intermediate-term* or *long-term memory* to achieve additional exploitation or exploration:
	- this can be used to *backtrack to elite candidate solutions* which then can reset the tabu list
	- *freezing certain solution components* for a number of steps
	- *occasionally force rarely used solutions*
	- even *extend the evaluation function* to capture frequency of use of candidate solutions (or components)

---
## Simulated Annealing
a stochastic local search algorithm inspired by the physical process of annealing. Simple to implement and achieves good performance setting for improved performance.
- It has an interesting theoretical property (convergence) but these are of very limited practical relevance.

> Real world annealing: a liquid material cools and anneals too quickly, this material will solidify into a *sub-optimal* solid configuration. But if it cools slowly, the crystals within the material will solidify *optimally into a state of minimum energy* - we  take the ground state of our algorithm to be the minimum of the cost function in an optimisation problem.




#semester4 #ai-methods 