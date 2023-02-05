# Conjunctive grammar

Idea of Conjunctive grammar was proposed by Okhotin in 2001 as extension of CFG. See [conjunctive grammars](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=b1b58648d9b644352116197be20b58f84e769c04).

Conjunctive grammar can define non-context-free languages. For example, $\set{a^nb^nc^n \mid  n \geq 0}$. The same example that [Ford uses for PEG](https://bford.info/pub/lang/peg.pdf) (see 3.4 Language Properties).

$$
\begin{align}
S &\rightarrow A\cdot B \cap D\cdot C \\
A &\rightarrow a\cdot A \cup \epsilon \\
B &\rightarrow b\cdot B\cdot c \cup \epsilon \\
C &\rightarrow c\cdot C \cup \epsilon \\
D &\rightarrow a\cdot D\cdot b \cup \epsilon \\
\end{align}
$$

## Brzozowski derivatives of conjunctive grammar

Derivative can be defined the same way as for [Context free grammar](./Context%20free%20grammar.md), except we need to add rule for intersection (R6) from [Regular expressions](./Regular%20expressions.md).

It is possible to use the same definition because language equations with intersection also have the least solution (fixed point). See **Corollary 5.19 (CG - Least solution)** in [Extending context-free grammars with conjunction and negation, Astrid van der Jagt, 2021](https://www.cs.ru.nl/bachelors-theses/2021/Astrid_van_der_Jagt___4571037___Extending_context-free_grammars_with_conjunction_and_negation.pdf)

## Notation

- concatenation $L_1 \cdot L_2$. Okhotin uses $L_1L_2$
- union (aka unordered choice) $\cup$. Okhotin uses $|$
- intersection $\cap$. Okhotin uses `&`
