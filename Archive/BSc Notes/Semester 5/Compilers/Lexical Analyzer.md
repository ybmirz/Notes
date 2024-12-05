The first component under *lexical analysis* where we identify the *tokens* given an *input string* not based in *any grammar.*

### Describing Tokens?
- Regular Expressions is defined inductively (through references to parts of itself) hence the regular expressions can then result in a *lexical specification*

> Essentially, the lexer can taken as an NFA $L$ for a Regular Expression $RE$, hence the set of tokens is defined to be the set of words **accepted** by the NFA $L$

The exact method of lexical analysis is hard to describe on typed notes. Hence, we'll skip through the part since a lexer is simply *an implementation of NFA or DFA on a regular expression* 

### The Lex and Flex Scanner Generators
- Ideally, we can create a *lexer* through the use of **scanner generators**, where we simply input a *language* that specifies scanners, and output a *scanner*.

![[Pasted image 20231104180004.png]]