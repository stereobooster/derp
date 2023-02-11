# Parsing Expression Grammar

PEG was proposed by Ford in 2004. See [Parsing Expression Grammars: A Recognition-Based Syntactic Foundation](https://bford.info/pub/lang/peg.pdf).

## Brzozowski derivatives of PEG

There were previous attempts to define derivative for PEG:

- [Derivatives of Parsing Expression Grammars](https://arxiv.org/pdf/1405.4841.pdf), Aaron Moss, 2014
- [Simplified Parsing Expression Derivatives](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7206630/), Aaron Moss, 2020
- [Recognising and Generating Terms using Derivatives of Parsing Expression Grammars](https://www.semanticscholar.org/paper/Recognising-and-Generating-Terms-using-Derivatives-Garnock-Jones-Eslamimehr/b415bd943c4fd3458c60672dd9b277e4755cc6bc), Tony Garnock-Jones, Mahdi Eslamimehr, Alessandro Warth, 2018

But the problem is that those definitions are incompatible with original Brzozowski definition. So I want to give definition of PEG in terms of extensions of context free grammars.

- (PEG1) positive syntactic predicate: $\\&_{PEG}(L_1) \cdot L_2 = \\&(L_1 \cdot \Sigma^*) \cdot L_2$
  - $\\&(L) = \\&_{PEG}(L \cdot \\&_{PEG}(\epsilon))$
- (PEG2) negative syntactic predicate: $!_{PEG}(L_1) \cdot L_2 = !(L_1 \cdot \Sigma^*) \cdot L_2$
  - $!(L) = !{PEG}(L \cdot !_{PEG}(\Sigma))$
  - $!_{PEG}(!_{PEG}(L)) = \\&_{PEG}(L)$
- (PEG3) prioritized choice: $L_1 / L_2 = L_1 \cup !_{PEG}(L_1) \cdot L_2 = L_1 \cup !(L_1 \cdot \Sigma^*) \cdot L_2$

Where `!` and `&` are operators from [REwLA](Regular%20expressions%20with%20lookahead.md).

## Notation

- Any character: $\Sigma$. Ford uses `.`
- Optional: $L \cup \epsilon$. Ford uses $L?$
- Concatenation (sequence): $L_1 \cdot L_2$. Ford uses $L_1L_2$

## Related

- [Parsing expression grammars, constructing a linear-time parser](https://www.cs.ru.nl/bachelors-theses/2017/Jan_Martens___s348435___Parsing-expression-grammars-constructing-a-linear-time-parser.pdf)
- [The computational power of parsing expression grammars](https://arxiv.org/abs/1902.08272)
- [Packrat Parsers Can Handle Practical Grammars in Mostly Constant Space](https://kmizu.github.io/papers/paste513-mizushima.pdf)
