### Representation (Encoding)
- Representations must have the following main characteristics:
	1. **Completeness**: where *all solutions* associated with the problem *must be represented*
	2. **Connexity**: a *search path* *must exist* between any two solutions of the search space. 
		- Any solution of the search space *can be attained*
	3. **Efficiency**: the representation *must be easy* to be manipulated by the search operators

#### Binary Encoding
- Using *binary* as a medium of representation, *is the most common*
- ie. `100101001010`
> Given a **binary string of length N** (representing N items), the **search space** has a *size* of **2N**

- Problem example:
	- Fill the knapsack with as much value in goods as possible – which items to take? 
	= 10011 ($8), 11110 ($15)

#### Permutation Encoding
- Having a candidate solution for *a sequence*, where each *number string* represents the solution's *position* within the sequence.
- ie. `1 5 3 6 4 7 2`

> Given **N cities (objects)**, the **search space size** comes up to **N!**

#### Integer Encoding
- Representation using integers

- As an example, a *personnel rostering problem* or *timetabling problem*, or *layout/structure* optimisation
	- Such as: given an unlimited number of 5 different composite materials, whihc would you use for each of the 15 layer composit structure maximising the sound absorption? 
		- an integer encoding would be used to structure a candidate solution
	- Hence for a problem with **M composite materials** to form an **N-layer composite structure**, the **search space size** comes to be **MN**

#### Value Encoding
- Representation using a *sequence of values* of alphanumeric characters
	- which determines a candidate solution

#### Non-linear Encoding
- Representation using *abstract data types* such as trees and graphs

#### Special Encoding
-  A mix between *multiple* encoding methods
	- An example would be using the [[#Integer Encoding]] and [[#Permutation Encoding]] to create a *random key.*

> There are no exact rules that could be taken for this encoding

#semester4 #ai-methods 