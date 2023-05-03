### RegEx
- Suppose you need to locate a piece of text in a file directory, or simply just searching for an expressive string, and you remember bits of the string, such as it having a 19-,, hence we can create a *regular expression* for the string to be:
	- `19[0-9][0-9]*`
	
> The above is an implementation of the literal regular expression in languages, the below section is on Regular Expression in languages

---
## Regular Expressions
- A regular expression is a *string* made up of alphabet symbols and six additional RE symbol: `+ * ( ) `$\emptyset$, $\epsilon$ 
- Below are some syntax example to help understand how we can identify regular expressions
	- $\emptyset$ is *by itself* an RE
	- Similarly, $\epsilon$ is an RE
	- If $x \in \sum$, then $x$ by itself is an RE
	- If $E$ and $F$ are REs (individually), then $E + F$ is an RE
	- If $E$ and $F$ are REs, then $EF$ is an RE
	- If $E$ is an RE, then $E^{*}$ is an RE
	- If $E$ is an RE, then $(E)$ is an RE

- Semantics of a regular expression is a *set* of words, that is a language.
	- Hence we can say $L(E) = A$ which means that the language of the regular expression $E$ is the *set of words* $A$
- This means that the basics of language concatenations hold up here as well.

> It should just be remembered when we want to read regular expressions, arithmetic conventions apply following **relative priority**
> - Basically, $*$ binds stronger than *sequence and $+$* 
> - Whilst *sequencing* binds stronger than $+$

## RE -> NFA

- As we know that an RE *describes* a language, hence we can come up with an NFA that could *accept* the language that the RE *describes*
	- Something like $L (R) \equiv L(N)$
- To make it simpler, what we want is simply an NFA that expresses *precisely* the same language as the RE $R$, hence $L(N(A)) \equiv L(R)$

> It's better to try and understand the proper working of converting an RE to an NFA through practice, but simply an RE is already given as a transition diagram, so creating that NFA is a simple conversion.

- One of the more problematic ones, is creating the NFA $N(R_{1}R_{2})$ because it *composes* the two RE (NFA), or known as the [[Nondeterministic Finite Automata#Sequential Composition of NFAs]]



#semester4 #languages-computation