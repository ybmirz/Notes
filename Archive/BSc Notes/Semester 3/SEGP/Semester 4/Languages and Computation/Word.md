- Definitively **words** are a **finite sequence** of symbols, based off a *finite or infinite* set of symbols, known as **alphabets**; [[Terminology]]

## Concatenation of Words
- A general operation on words is a **concatenation** of words.
- Concatenation is denoted by a **juxtaposition**, where the words are written side by side wtihout any operator symbol.

Example: **Juxtaposition**
$$
v \in \sum^{*}, w \in \sum^{*} \rightarrow vw \in \sum^{*}
$$

It could be further defined by promitive recursion:
$$
\begin{align}
\epsilon w = w \\ \\
(xv) w = x (vw)
\end{align}
$$

 where
 $$
\begin{align}
x \in \sum \\
v,w \in \sum^{*}
\end{align}
$$
>The above shows the general property/rule of concatenation
>me + miru = happy <3 

### Properties of Word Concatenation
Generally, there's **two properties** generally that could be said for word concatenation;
- Concatenation is **associative** and has **unit** $\epsilon$
$$
\begin{align}
u (vw) = (uv)w  \\
\epsilon u = u = u\epsilon \\ \\
w,v,u \in \sum^{*}
\end{align}
$$
> 	Above shows *associativity* of word concatenation. along with a consideration that $\epsilon$ is given as a *unit*

- Concatenation is **not commutative** (where order **matters**) as *words* are taken as *sequences*, shown as that 
	- the words $w,v$
	$$
vw \neq wv
$$
> Above shows the anti-commutative propery of word concatenation, as *sequences* of the alphabet within the word matters.

#semester4 #languages-computation 