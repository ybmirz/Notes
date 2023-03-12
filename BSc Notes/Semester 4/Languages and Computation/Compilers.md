## Structure
![[Pasted image 20230312153854.png]]

### Lexical Analysis
- The first phase of a **compiler**, and is one of the most common applications of [[Automata Theory#Finite Automata]], and is also known as **scanning or lexing**.
- On its own, the *lexer* takes a **sequence of characters** and results a **sequence of tokens**; with definition as below:
	- Characters: the *alphabet* of the source program (often ASCII)
	- Token: a *name* and (optionally) an associated value
	- Lexeme: a *sequence of chars* that *corresponds* to a token
- The [[Automata Theory#Finite Automata]] is used to *recognize* lexemes where each *accepting state* can be annotated with a token to produce.


#semester4 #languages-computation 