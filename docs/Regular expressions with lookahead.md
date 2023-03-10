# Regular Expressions with Lookahead

- [Regular Expressions with Lookahead](https://www.researchgate.net/publication/351177928_Regular_Expressions_with_Lookahead)

## Brzozowski derivative

[Derivatives of Regular Expressions with Lookahead](https://www.jstage.jst.go.jp/article/ipsjjip/27/0/27_422/_pdf)

- RE1 $D_a(a) = \epsilon$
- RE2 $D_a(b) = \emptyset, \text{ if } b = \emptyset, b = \epsilon, b \in \Sigma \text{ and } b \neq a$
- RE3 $D_a(L_1 \cup L_2) = D_a(L_1) \cup D_a(L_2)$
- REL4 $D_{a}(L_{1} \cdot L_{2}) = D_{a}(L_{1}) \cdot L_{2} \cup D_{a}^\sim(L_{1})D_{a}(L_{2})$
- RE5 $D_a(L^*) = D_a(L) \cdot L^*$
- REE6 $D_a(L_1 \cap L_2) = D_a(L_1) \cap D_a(L_2)$
- REE7 $D_a(L^c) = D_a(L)^c$
- REL8 $D_{a}(!L) = \emptyset$
- REL9 $D_{a}(\\&L) = \emptyset$

They don't use nullabilty function ($\delta$), instead they use $D^\sim$:

|      | REwLA                                                                       |      | delta                                                   |
| ---- | --------------------------------------------------------------------------- | ---- | ------------------------------------------------------- |
| REL1 | $D_{a}^\sim(\epsilon) = \epsilon$                                           | RE1  | $\delta(\epsilon) = \epsilon$                           |
| REL2 | $D_{a}^\sim(\emptyset) = \emptyset$                                         | RE2  | $\delta(\emptyset) = \emptyset$                         |
| REL2 | $D_{a}^\sim(a) = \emptyset$                                                 | RE2  | $\delta(a) = \emptyset$                                 |
| REL3 | $D_{a}^\sim(L_{1} \cup L_{2}) = D_{a}^\sim(L_{1}) \cup D_{a}^\sim(L_{2})$   | RE3  | $\delta(L_1 \cup L_2) = \delta(L_1) \cup \delta(L_2)$   |
| REL4 | $D_{a}^\sim(L_{1} \cdot L_{2}) = D_{a}^\sim(L_{1}) \cdot D_{a}^\sim(L_{2})$ | RE4  | $\delta(L_1 \cdot L_2) = \delta(L_1) \cdot \delta(L_2)$ |
| REL5 | $D_{a}^\sim(L^*) = \epsilon$                                                | RE5  | $\delta(L^*) = \epsilon$                                |
|      |                                                                             | REE6 | $\delta(L_1 \cap L_2) = \delta(L_1) \cap \delta(L_2)$   |
|      |                                                                             | REE7 | $\delta(L') =$ ...                                      |
| REL8 | $D_{a}^\sim(!L) = !(D_{a}(L) \cup D_{a}^\sim(L))$                           |      |                                                         |
| REL9 | $D_{a}^\sim(\\&L) = \\&(D_{a}(L) \cup D_{a}^\sim(L))$                       |      |                                                         |
