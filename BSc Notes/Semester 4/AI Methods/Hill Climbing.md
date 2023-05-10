Heuristics usually has a possibility in reaching a local optima, hence a mechanishm should be done to ensure that a solution is not at the local optima, one example is Hill Climbing.

>Hill climbing itself is a *local search algorithm* that constantly moves in the direction of increasing or decreasing level/objective value to find the peak or nadir of the landscape (best/near optimal solution to the problem) *climbs the hill!*

#### The Hill Climbing heuristic/operator
- Processes a given candidate solution and generates *a better or equal quality solution*
![[Pasted image 20230510120302.png]]
> The image shows how the hill climbing operator can probably reach a better optimum. By minimising or maximising (more on the algo in [[#Hill Climbing Algorithm]])

---
### Mutational Heuristic/operator
- Another method to escape a local optima could be through a mutational operator that realizes on diversification and exploration. 
- Processes a given candidate solution and generates a solution which is *not guaranteed to be better than the input*. 
	- An explorative method of escaping the local optima.

![[Pasted image 20230510205207.png]]

---

### Hill Climbing Algorithm
- There's two exact algorithms for hill climbing that depends on what type of optimisation problem is presented:

**Minimisation Problem**
- the algorithm constantly *moves* in the direction of *decreasing* level or objective value (hence a *minimsation problem*) to find the **nadir/lowest point** of the landscape or best/near optimal solution to the problem
- This hill climbing algorithm halts when it detects a *nadir value where no neighbour has a lower value*

**Maximisation Problem**
- contradictingly, the algorithm *moves* in the direction of *increasing* level or objective value (hence a *maximisation problem*) to find the **peak/highest point** of the landscape or best/near optimal solution to the problem
- The hill climbing algorithm halts when it detects a *peak value where no neighbour has a higher value*

##### Additionals
Variations of hill-climbing algorithms differ in the way a new solution/state/string is selected for comparisons with the current solution/state/string. This can range from:
- Randomly choosing the initial starting point
- Using a more constructive heuristic/operator(s)
- Based on other information (e.g. results of a prior search)

**Simple Hill Climbing Heuristic**
A simple hill climbing consists of *examining the neighbours*
- for the *best improvement* (steeper descent/ascent)
- or for the *first improvement* (next descent/ascent)
It could also be *stochastic* by simply *randomly chooosing neighbours* (aka random mutation hill climbing)

**Random-Restart Hill Climbing**
Another hill-climbing method known as the *shotgun method* where it is built on top of hill climbing and operates by *changing the start solution for the hill climibing randomly* and returning the *best*.

Example Pseudocode for a **best improvement hill climbing method**:
```
bestEval = evaluate(currentSolution);
improved = false;
for (j to length[currentSolution])
	bitFlip(currentSolution, j); // flips the jth bit of the current solution
	tmpEval = evaluate(currentSolution);
	if (tmpEval < bestEval){
		bestIndex = j;
		bestEval = tmpEval;
		improved = true;
	}
	bitFlip(currentSolution, j);

if (improved)
	bitFlip(currentSolution, bestIndex);
```

Now the question comes, how do we know that we are possibly out of the local optima and [[#When to Stop]]; 

#### When to Stop
Intuitively, we stop hill climbing when a *target* or *threshold* criterion is met; and it can either be *known* or *applied.*
- If the target *objective* is  *known*, then the search can be stopped when that target objective value is achieved
	- I.e. the minimum value for $f_{2}$ is known to be 0 (we stop when we reach 0)
- If a *termination criterion* is *applied*, then the search can be stopped when the criterion is satisfied
	- i.e. the maximum number of evaluations is exceeded which is a factor of the string length

> There are some caveats but the above generalises when to stop hill climbing within the local search space

### Weaknesses of Hill Climbing
- *woopsie* the **Local Optimum**; If all neighbouring states are worse or the same, the algorithm will halt even though the solution may be far from satisfactory :(
- **Plateau (neutral space/shoulder)**: All neighbouring states are the same as the current state; which means the evaluation function is essentially flat or plateaued. (we can solve using random walk!)
-  **Ridges/Valleys**: the search may oscillate from side to side, making little progress. Such happens when in each case, the algorithm reaches a point at which no progress is being made. 

![[Pasted image 20230510223330.png]]
> Visualisation of the weakness of hill climbing in a graph
> hence, hill climbing may not find the *optimal solution* and may get *stuck at the local optimum*

- No information as to how the discovered local optimum deviates from the global (or possibly even other local optimum)

### Strength of Hill Climbing
- Very *easy* and simple to implement because it simply requires a few components:
	- **Representation**
	- **An evaluation function**
		- a measure that defines the *neighbourhood* around a point in the search space


---
### Hill Climbing vs Random Walk
- Random walk? Simply, random walk performs a search in the search space by *sampling new points with equal probability* (such as random bit flips or random swaps); think of it like randomly walking around the search space for the global optima.
- The **main difference** between the two is that **hill climbing** *exploits* the best available solutions for possible improvements but neglect exploring a large portion of the search space
	- Whilst **randm walk** *explores* a large portion of the search space thoroughly but misses exploiting promising regions within the search space.

---

#ai-methods #semester4 