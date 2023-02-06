### Basics of Python
- Recapping the basics of python, where Python is a *dynamically* and *strongly typed*, so the compiler would not convert/change the typing of the variables.
- **whitespace is significant** in python, as the code blocks are determined based on indentation.
> Python supports object-oriented programming, with the concepts of classes, objects and attributes with methods!
- Python has **nullable types** as well, but it is denoted by `none`, signifying an absence of value, and an equivalence check using `is` 
	- ie. `var is none`

**Lists and Tuples**
- Lists are declared using **square brackets** whilst Tuples are declared using **circle brackets**, lists are mutable whilst Tuples are immutable.
- Lists can be easily *indexed and sliced* meaning values in a list can be accessed through it's index, (Python is 0-indexed), and slicing refers to something like below:
```python
test_list = ['a', 'b', 'c']
test_list[1:3] # Slicing 
```
- Methods when using a list data structure:
- ![[Pasted image 20220314195102.png]]

**Dictionaries**
- Declared with `key:value` within **curly brackets** where keys have to be unique and immutable, whilst the getting and setting of the values can be done thru square brackets `[]`.
- Dictionary methods:
- ![[Pasted image 20220314195241.png]]

### How to Proceed.
1. What problems do you **want** to solve?
	- In the code questions, there are mainly three parts of the problem, the data, the method and where to store the data, so essentially this question is crucial to solve problems. **Identifying what you wanna go towards**
2. What are the **net costs** for learning a language?
	- It will always cost time to learn a new system that is better aligned for the problem you'd like to solve, but staying with the system you know may not be made for the kind of problem. Identifying the commonly used tools as well for the type of the problem you'd like to solve.
3. Relating to the previous point, what are the **commonly used tools** in your field?
4. What are the **valuable things** needed;

> Almost all problems would have a date element in the question

### Algorithms in Python
- There are **no arrays** in Python, but they can be imported using *numpy* and only Lists are built into Python, linked lists might be needed.
![[Pasted image 20220314202556.png]]

<img src="Pasted image 20220314202556.png"/>