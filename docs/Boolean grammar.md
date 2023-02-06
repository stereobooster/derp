# Boolean grammar

Idea of boolean grammar was proposed by Okhotin in 2004 as extension of CFG and conjunctive grammar. See [boolean grammar](https://www.sciencedirect.com/science/article/pii/S0890540104001075).

## Brzozowski derivatives of boolean grammar

It tempting to define derivative the same way as for [Context free grammar](./Context%20free%20grammar.md), except we need to add rules for intersection (R6) and complement (R7) from [Regular expressions](./Regular%20expressions.md). **But this won't work in general case**, because language equations with complement doesn't have least solution. See: **Lemma 6.7 (Complement operation is not Scott continuous)** in  [Extending context-free grammars with conjunction and negation, Astrid van der Jagt, 2021](https://www.cs.ru.nl/bachelors-theses/2021/Astrid_van_der_Jagt___4571037___Extending_context-free_grammars_with_conjunction_and_negation.pdf)

Okhotin also proposes "well-founded boolean grammar", which suppose to have unique solution. But this variation also has issues see Vassilis Kountouriotis, Christos Nomikos, and Panos Rondogiannis, "Well-founded semantics for Boolean grammars", 2009.

## Notation

- concatenation $L_1 \cdot L_2$. Okhotin uses $L_1L_2$
- union (aka unordered choice) $\cup$. Okhotin uses $|$
- intersection $\cap$. Okhotin uses `&`
- complement $^c$. Okhotin uses $\lnot$

## Related

- [sbp: A Scannerless Boolean Parser](http://www.megacz.com/berkeley/research/papers/megacz,adam-sbp.a.scannerless.boolean.parser.pdf)
- [Partial Derivatives of an Extended Regular Expression](https://www.researchgate.net/publication/220836274_Partial_Derivatives_of_an_Extended_Regular_Expression)
- [Efficient Parsing with Derivatives and Zippers](https://infoscience.epfl.ch/record/287059?ln=en)