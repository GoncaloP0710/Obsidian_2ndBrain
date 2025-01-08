2025-01-08 14:54

Status: #done 

Tags: [[Software Security]] [[Code Analysis]] 

# Semantic Analysis

### Syntax Tree (or Parse Tree)
The parser uses a context-free grammar (CFG) to match the token stream and then derive a parse tree.

![[Semantic Analysis 1.png]]

### Abstract Syntax Tree (AST)
Build a model of the program
- do lexical analysis and parsing
- build an abstract syntax tree (AST)
	- similar to the syntax tree but abstracting away details specific to compilation
- generate simultaneously a symbol table, which associates to each identifier the type and a pointer to its definition/declaration

![[Semantic Analysis 2.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554479/mod_resource/content/7/T_StaticA.pdf