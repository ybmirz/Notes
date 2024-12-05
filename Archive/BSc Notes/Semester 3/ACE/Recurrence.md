### Recurrence Relation
- It's simple to define that recurrence relation is an *equation* used to **represent** the **running time** of a recursive algorithm
	- It should define the *next value* in the sequence
	- As an example;
$$
T(n) = T(\frac{n}{2})+n
$$
> where `T(n)` is the **time required** to solve a problem of a size `n`
- Given the above equation, what should be the running time of the algorithm?
	- **Solving** the equation returns back a *formula* that bounds the recurrence by an expression that involves `n`


- It is a given that there are usually **two main parts** that determine a recursive algorithm, where there are *two separate calls*, known as:
	- a **recursive case**: a repeated call of the same method,, with a *different* input;
		- such as, $n-1$, $\frac{n}{2}$	
	- a **base case**: determines the method for when to stop the recursive call
	- $$f(x) = \begin{cases}
		1 & \text{if } x < 0 \\ aT(\frac{n}{b})+f(n) & \text{if } x \ge 0 \end{cases}$$
		- $a$ determines the **number of times** the function calls itself
		- $b$ the factor by which the input size is reduced (due to recursion)
		- $f(n)$ is the *execution time* of the **non recursion**

### Examples

- Solving recurrence relations, requires to find a **non recursive** formula to *calculate* $a_{n}$ , where what  is returned is known as a **closed formula**
- The following are some methods of *solving* the recurrence relation:
	- [[#Iteration Method]]
	- [[#Substitution Method]]
## Iteration Method

- The iteration method consists of *recursively* expanding the terms of the recurrence relation til we reach the base case.
	- It consists of constantly **expanding** the recurrence (relation) to make it only dependent on the *input* $n$ and the **initial condition**

**Example**:
Given $2T(\frac{n}{2})+n$ where $n > 1$ as the **recurrence relation**, find the **solution** by using the *iteration method.* Base case is known to be $n=1$
$$
\begin{align}
T\left( \frac{n}{2} \right) = 2T\left( \frac{n}{2^{2}} \right)+\frac{n}{2}  \\
T(n) = 2^{2} T\left( \frac{n}{2^{2}} \right)+2n \\
\dots
\end{align}
$$
> As you go along *consistently expanding and plugging in*, we get a general pattern of 
$$
T(n) = 2^{i}T\left( \frac{n}{2^{i}} \right)+i(n) \dots\dots\dots(1)
$$
> As we know that the base case of the recurrence is to be $n = 1$, $T(n) = 1$
$$
\begin{align}
hence \\
T\left( \frac{n}{2^{i}} \right) = 1 \\
\frac{n}{2^{i}} = 1 \\
n = 2^{i} \\
\log_{2} n = i
\end{align}
$$
> Substituting $i$ into equation (1), at T(1), we shall get
$$
\begin{align}
T(n) = 2^{\log n} * T(1)+ n \log n \\
T(n) = n + n\log n
\end{align}

$$
 
## Substitution Method

#semester4 #ace 