Lexical Analysis *focuses* on *recognising* the vocabulary of the programming language and transforms a string of characters into a string of words or *tokens*.

> Some would say it's *tokenising*; 
> Another term for a *lexical analyzer* is a *scanner* or *lexer*

By default, a lexical analyzer should discard **white spaces** and **comments**.

Lexical Analysis can be further divided into several processes and components. The *[[Lexical Analyzer]], or Scanner*, a *[[{Parser]] and a *symbol table*.

## Definitions
- **[[#Tokens]]** as a classification of *lexical units*
	- *atomic units* of a language and there can be various **categories** of tokens:
		- ie. identifiers, and reserved keywords
- **Lexemes** are *specific character strings* that make up a *token*
	- *lowest* level of syntatic units
- **Patterns** are the *rules set in describing lexemes* belonging to a token.

> Understanding how to cut a string is crucial in understanding lexical analysis, so more on this in [[Parts of a String]]

### Tokens 
**Tokens** as a classification, of the sequence of *lexemes* can be treated as a *unit* in the **grammar of a programming language**. 
> A programming language should classify tokens into a finite set of *token types or categories*

- *Token types* affect [[Syntax Analysis]] and *Semantic values* affect [[Semantic Analysis]]

> Inherently, each token can be given a *semantic value* where it is used to distinguish different tokens in a token type. 

**Attributes** can be associated with tokens as well, where it *points to the symbol table entry that keeps information*

> You can use *regular expressions* as a tokeniser to define the *token  types* of a programming language


#semester5  #compilers