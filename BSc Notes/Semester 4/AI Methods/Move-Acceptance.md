> As it could be intuitively deduced, this topic dives into the decision of which to accept or reject a *move* or the new solution considering its evaluation; aka $f(s')$

> It can be debated that accepting non-improving moves could be used as a mechanism to escape from the local optimum

Move-Acceptance of a specific algorithm results in a description of the nature of said algorithm. It follows the following taxonomy:
![[Pasted image 20230511191115.png]]

> The taxonomy describes the methods in which move-acceptance can be determined; either based on how the algorithmic parameters are set or the nature of accept/reject decision.

---

## Parameter Setting Mechanisms in Move Acceptance
**Static**: *no parameter* to set or parameters are set to a *fixed value*

**Dynamic**: the values *vary with respect to time/iteration count*. Given the same candidate and current solutions at the same current elapsed time or iteration count, the *acceptance threshold or probability* would be the *same* (irrespective of search history)

**Adaptive**: Given the same candidate and current solutions at the same current elapsed time or iteration count, the acceptance threshold or probability is *not guaranteed* to be the same as *one ore more components* *depending* on the search history.

> the above relation to move-acceptance is seen in the acceptance threshold or probabilty being *the same* or *not guaranteed* and its relation with the search history.

## Stochastic Move Acceptance
**Static**: simple *naive acceptance* such as $P$ being fixed 

**Dynamic**: An example of a dynamic stochastic move acceptance is *Simulated Annealing* where $P$ changes in time with respect to the difference in the quality of current and previous solutions

**Adaptive**: An example of this is *Simulated annealing with reheating* where $P$ is modified via *increasing temperature* time to time causing partial restart - increasing the probability of acceptance of non-improving solutions.

## Non-Stochastic Move Acceptance
- What about the non-stochastic move acceptance approach?

##### Threshold Move Acceptance method
**Static**: *accept* a *worsening solution* if the worsening of the objective value is no worse than a fixed value.

**Dynamic**: [[#Great Deluge]] and the [[#Flex Deluge]]

**Adaptive**: Using *record-to-record* travel (RRT) with an *extended or modified* [[#Great Deluge]]

##### Basic Move Acceptance method
- Reuse the *objective values* of *previously encountered solutions* for the accept/reject decisions.

**Static**: for *all moves*: return true regardless of evaluation
for *improving moves only*: $f(s') < f(s)$
for *improving and equal moves*: $f(s') \leq f(s)$

**Dynamic**: *No such thing* as a dynamic non-stochastic basic move acceptance method

**Adaptive**: In an adaptive manner of move-acceptance for a non-stochastic basic approach is using [[#Late Acceptance]]. Where you compare the *quality of the solution* with that of the solution *accepted /visited* $L$ iterations previous. (aka $S_{t-L}$) and *accepts moves* if and only if $f(s') \leq f(s_{t-L})$

----

#### Late Acceptance

> We can implement late acceptance by assigning all element of the list to be equal to the initial cost (objective value); and the list for the history of the objective values of the recent solutions is implemented as a *circular queue*

Pseudocode:
![[Pasted image 20230511193022.png]]

### Great Deluge
The great deluge is done with the intention of *minimising* $f(s')$. It determines a threshold which is in the vicinity of a chosen solution quality (ie the quality of the best solution found so far or current solution) and accepts all solutions *below the threshold*. 

This threshold is updated dynamically during the search process. Feedback is received during the search and the decay-rate is updated/reset accordingly whenever there is no improvement for a long time. 

![[Pasted image 20230511193425.png]]



#semester4 #ai-methods 