# Regular expressions

Regular expressions correspond to regular languages in Chomsky hierarchy and DFA in automata theory.

Regular expressions are based on work Kleene, Stephen Cole - ["Representation of Events in Nerve Nets and Finite Automata", 1951](https://www.rand.org/content/dam/rand/pubs/research_memoranda/2008/RM704.pdf).

## Brzozowski derivatives of regular expressions

Janusz A. Brzozowski in 1964, proposed idea of derivative: ["Derivatives of Regular Expressions, doi:10.1145/321239.321249"](https://dl.acm.org/doi/pdf/10.1145/321239.321249).

Let's define "nullability" function as:

- $\delta(L) = \epsilon, \text{ if } \epsilon \in L$
- $\delta(L) = \emptyset, \text{ if } \epsilon \notin L$

Let's define it recursively:

1. $\delta(\epsilon) = \epsilon$
2. $\delta(\emptyset) = \emptyset, \delta(x) = \emptyset, x \in \Sigma$
3. $\delta(L_1 \cup L_2) = \delta(L_1) \cup \delta(L_2)$
4. $\delta(L_1 \cdot L_2) = \delta(L_1) \cdot \delta(L_2)$
5. $\delta(L^*) = \epsilon$
6. $\delta(L_1 \cap L_2) = \delta(L_1) \cap \delta(L_2)$
7. $\delta(L^c) = \epsilon, \text{ if } \delta(L) = \emptyset$ and $\delta(L^c) = \emptyset, \text{ if } \delta(L) = \epsilon$

Let's define derivative:

1. $D_a(a) = \epsilon$
2. $D_a(b) = \emptyset, \text{ if } b = \emptyset, b = \epsilon, b \in \Sigma \text{ and } b \neq a$
3. $D_a(L_1 \cup L_2) = D_a(L_1) \cup D_a(L_2)$
4. $D_a(L_1 \cdot L_2) = D_a(L_1) \cdot L_2 \cup \delta(L_1) \cdot D_a(L_2)$
5. $D_a(L^*) = D_a(L) \cdot L^*$
6. $D_a(L_1 \cap L_2) = D_a(L_1) \cap D_a(L_2)$
7. $D_a(L^c) = D_a(L)^c$

## Notation

- empty language: $\emptyset$. Brzozowski uses $\phi$
- null laguage:  $\epsilon$. Brzozowski uses $\lambda$. In other literature sometimes they use $\varepsilon$
- concatenation: $L_1 \cdot L_2$. Brzozowski uses $L_1L_2$
- union (aka unordered choice): $\cup$. Brzozowski uses $+$. In other literature sometimes they use $|$ and $\lor$
- intersection: $\cap$. Brzozowski uses $\\&$. In other literature sometimes they use $\land$
- complement: $^c$. Brzozowski uses $'$. In other literature sometimes they use $^\complement$ or $^C$ or $\lnot$
- Any character: $\Sigma$. In Regexp they use `.`
- Kleene star $^*$. In Regexp they use `*`
- "Kleene plus" $L^+ = L \cdot L^*$. In Regexp they use `+`

## Related

- https://github.com/awalterschulze/regex-reexamined-coq/
