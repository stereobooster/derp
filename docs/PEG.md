# Parsing Expression Grammar

PEG was proposed by Ford in 2004. See [Parsing Expression Grammars: A Recognition-Based Syntactic Foundation](https://bford.info/pub/lang/peg.pdf).

## Brzozowski derivatives of PEG

There were previous attempts to define derivative for PEG:

- [Derivatives of Parsing Expression Grammars](https://arxiv.org/pdf/1405.4841.pdf), Aaron Moss, 2014
- [Simplified Parsing Expression Derivatives](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7206630/), Aaron Moss, 2020
- [Recognising and Generating Terms using Derivatives of Parsing Expression Grammars](https://www.semanticscholar.org/paper/Recognising-and-Generating-Terms-using-Derivatives-Garnock-Jones-Eslamimehr/b415bd943c4fd3458c60672dd9b277e4755cc6bc), Tony Garnock-Jones, Mahdi Eslamimehr, Alessandro Warth, 2018

But the problem is that those definitions are incompatible with original Brzozowski definition. So I want to give definition of PEG in terms of extensions of context free grammars.

- negative syntactic predicate: $!(L_1) \cdot L_2 = \not{\triangleright}' (L_1 \cdot \Sigma^*) \cdot L_2$
- positive syntactic predicate: $\&(L_1) \cdot L_2 = \triangleright' (L_1 \cdot \Sigma^*) \cdot L_2$
- prioritized choice: $L_1 / L_2 = L_1 \cup !(L_1) \cdot L_2 = L_1 \cup \not{\triangleright}' (L_1 \cdot \Sigma^*) \cdot L_2$

Which means that PEG $\subseteq$ conjuctive grammar with "negative" right context.

**Note**: this was not previously proposed in any reviewed publication. I also didn't try to prove it myself, this is rather educated guess.

## Notation

- Any character: $\Sigma$. Ford uses `.`
- Optional: $L \cup \epsilon$. Ford uses $L?$
- Concatenation (sequence): $L_1 \cdot L_2$. Ford uses $L_1L_2$
