# Compiler-Design-Notes
## Basics
#### Definition 
A compiler translates (or compiles) a program written in a high-level programming language that is suitable for human programmers into the low-level machine language that is required by computers.
#### The phases of a compiler
##### Lexical analysis 
This is the initial part of reading and analysing the program text:
The text is read and divided into tokens, each of which corresponds to a symbol in the programming language, e.g., a variable name, keyword or number.
##### Syntax analysis 
This phase takes the list of tokens produced by the lexical analysis
and arranges these in a tree-structure (called the syntax tree) that reflects the structure of the program. This phase is often called parsing.
##### Type checking 
This phase analyses the syntax tree to determine if the program violates certain consistency requirements, e.g., if a variable is used but not
declared or if it is used in a context that does not make sense given the type of the variable, such as trying to use a boolean value as a function pointer.
##### Intermediate code generation 
The program is translated to a simple machine independent intermediate language.
##### Register allocation 
The symbolic variable names used in the intermediate code are translated to numbers, each of which corresponds to a register in the
target machine code.
##### Machine code generation 
The intermediate language is translated to assembly language (a textual representation of machine code) for a specific machine architecture.
##### Assembly and linking 
The assembly-language code is translated into binary representation and addresses of variables, functions, etc., are determined.


*The first three phases are collectively called the front-end of the compiler and the last three phases are collectively called the back-end. The middle part of the compiler is in this context only the intermediate code generation, but this often includes various optimisations and transformations on the intermediate code.*

## Lexical Analysis
#### Definition
A *lexical analyser*, or *lexer* for short, will as its input take a string of individual letters and divide this string into tokens. Additionally, it will filter out whatever separates the tokens (the so-called *white-space*), i.e., lay-out characters (spaces, newlines etc.) and comments.
