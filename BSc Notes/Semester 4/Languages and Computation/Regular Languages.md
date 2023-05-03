Some facts to start off the note with:
- For any regular language, there is a **unique minimal DFA**
- Two regular languages can be **compared** for equality by converting them into minimal DFAs

---

As we go along understanding DFAs, and NFAs, these finite automatas' accepting languages can be formalised into what's known as a **Regular Language**.
- Such automatons have a finite number of states, hence can recognise *regularised* languages (somewhat like a pattern)
- however many languages are not regular.


## Definition
- Formally, Regular languages are languages that can be recognised by an automaton with a finite memory or space. However, there are many languages that cannot be recognised using only finite memory, such as the simple example of:
	$$
L = \{ 0^{n}1^{n} | n \in \mathbb{N} \}
$$
> Intuitively, think about it, this languages result in an **infinite** set, due to the *n* being a number within the set of natural numbers

A simple example like the above can be intuitively described, but how can we formalise and prove that a language is **not a regular one**

### Is that a regular language?

A lemme was introduced to identify if a non-finite language is regular or non-regular. It should be noted here that this lemma would only be considered for non-finite languages;
- intuitively thinking, a non-finite regular language must have a *pumping* property somewhere or a *loop* somewhere is its corresponding finite automaton; (because for a finite automaton to correspond with  a non-finite language, then there needs to be a pump or a loop for it to understand words in an non-finite set)

- Hence the Pumping Lemma is born.

##### Pumping Lemma
Given a regular language $L$, there is a number $n \in \mathbb{N}$ such that **all** words $w \in L$ that have length larger or equal to $n$ can be split into three words;
- $y \neq \epsilon$
- $|xy| \leq n$
- $\forall k \in \mathbb{N}, xy^{k}z \in L$

![[Pasted image 20230430175419.png]]
> there should exist a non-empty string Y not too far from the beginning of w, that can be pumped by repeating y any number of times

> all words that have a length greater or equal to n can be shown to atleast have one pumping part

-----
This section in particular requires practice sets in proving whether a specific language has a pumping lemme or not and often proofs are necessary

#languages-computation #semester4 
