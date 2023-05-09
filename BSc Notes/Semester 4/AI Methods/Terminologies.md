## Decision
- Generally defined, a **decision** is known as the *choice* of one among a *number* of alternatives (Quoted from Wikipedia, defined under Knowledge)
#### Decision Making
- The process of choosing among alternative course of action for the purpose of attaining a goal, and goals. (Turban and Aronson)
- It could also be noted that every decision-making *process* produces a *final choice*, or a *decision*. This output can be an *action* or *opinion of choice* (Definition under General Knowledge)

> Decisions can be supported through a **decision support**, where some sort of system is applied durign the decision making process as a support and create a more reformed output, hence increasing decision making capabilites.

## System
- A set of interacting or interdependent component parts forming a complex or intricate whole. There comes a degree of independence to a system;
	- A Closed System is totally independent
	- an Open System is dependent on the environment around a system
- Systems can also be evaluated;
	- by means of **effectiveness**; where the degree to which goals are achieved 
	- by means of **effeciency**: where a measure of input use to the achieve the outputs, usually space or time

### Model 
- A simplified representation or abstraction of reality; because reality is often too complex and much of this complexity is irrelevant to solving the problem
- A major characteristic of decision support system is that it has to include at least one model

##### Types of Models
- **Iconic Models**: the least abstract type of models; where it is a *physical replica* of a system; a 3D car
- **Analog Models**: a more abstract model; a *symbolic representation of reality*.
	- It behaves like a real system but does not look like it; such as 2D charts or cardboard models
- **Mathematical Models**:  Most abstract model; the *mathematical relationships in the problem*
	- The main idea here is that it is easier to model than to manipulate the real system; hence a lower-cost of analysis.
	- With this type of modelling, the cost of making mistakes is less than mistakes on the real system
	- a very large number of solutions can be analysed and with this type, it can then lead to a risk and uncertainty model of the system

> Stated above that there are numbers of solutions that can be further analysed, how can we reach these solutions with the mathematical model; Searching!

---
### Solving Problems by Searching

- Given an initial state; efficiently finding a *set of action* that will move from the initial state to a given goal
	- This is central to many AI problems such as Game Playing and Path Finding
- Typical algorithms are DFS, BFS, branch and bound, and A*. 

- The above describes the search for *path to goal* but what if we want to search *for solutions*; this is known as **Optimization**. 
	-  A more general class than searching for the path
	- It is efficiently finding *the solution* to a problem in a large space of *candidate solutions*
	- It expands further the previous searching type as any path in the search tree can be taken as a *candidate solution*

#### Global Optimisation
- It is the task of finding absolutely the **best set** of admissible conditions to achieve the objective, formulated in mathematical terms; (making it a mathematical model)
- The fundamental problem of optimisation is to arrive at the **best possible or optimal** decision/solution in any given set of circumstances
	- In most cases, it's **unattainable** 

**Global vs Local**
- the local optimum refers to a **better** than all solutions in a certain *neighbourhood* $N$ ; whilst the global is the **best** solution
![[Pasted image 20230509143939.png]]

> The above graph visualises a comparison between the local and global optimum (minimisation!)

--- 
### Solving an Optimisation Problem
> With the main idea of considering everything; we keep the good and avoid the evil when noticed

- First choosing a quantity (typically a function of several variables known as the *objective function*) to be maximised or minimised, which might be subject to one or more constraints (*constraint optimisation*)
	- An example of this is either maximising or minimsing $z  = f(X)$ with a one or more equality constraint $g_{i}(X) = ci$
- Next, simply choose a *mathematical method* to solve the optimisation problem (done by searching the space of solutions and finding the absolute best solution)

#semester4 #ai-methods 