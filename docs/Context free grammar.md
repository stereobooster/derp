# Context free grammar

Idea of extending Kleene algebra with general recursion (Kleene star is iteration) was investigated by Dexter Kozen and Hans Leiß in 1990-s. See [Towards Kleene Algebra with Recursion](https://www.cis.uni-muenchen.de/download/publikationen/kar_csl-91.pdf).

They also ntocied that regular expressions with general recursion correspond to context free languages.

## Brzozowski derivatives of CFG

Matthew Might et al. in 2011 showed how to implement algorithm to parse CFG with Brzozowski derivative. See [Parsing with Derivatives](https://matt.might.net/papers/might2011derivatives.pdf).

It uses the same definition of Brzozowski derivative as in [Regula expressions](./Regular%20expressions.md), except they don't use intersection (REE6) and complement (REE7).

## Notation

- concatenation $L_1 \cdot L_2$. Might uses $L_1 \circ L_2$
- Kleene star $^*$.  Might uses $^\star$
