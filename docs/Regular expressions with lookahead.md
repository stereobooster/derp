# Regular Expressions with Lookahead

- [Regular Expressions with Lookahead](https://www.researchgate.net/publication/351177928_Regular_Expressions_with_Lookahead)

## Brzozowski derivative

[Derivatives of Regular Expressions with Lookahead](https://www.jstage.jst.go.jp/article/ipsjjip/27/0/27_422/_pdf)

1. $D_{a}(\emptyset) = \emptyset$
2. $D_{a}(\epsilon) = \emptyset$
3. $D_{a}(a) = \epsilon, D_{a}(b) = \emptyset$
4. $D_{a}(L_{1} \cup L_{2}) = D_{a}(L_{1}) \cup D_{a}(L_{2})$
5. $D_{a}(L_{1} \cdot L_{2}) = D_{a}(L_{1}) \cdot L_{2} \cup D_{a}^\sim(L_{1})D_{a}(L_{2})$
6. $D_a(L^*) = D_a(L) \cdot L^*$
7. $D_{a}(!L) = \emptyset$
8. $D_{a}({\&}L) = \emptyset$

They don't use nullabilty function ($\delta$), instead they use $D^\sim$:

| REwLA                                                                       | delta                                                   |
| --------------------------------------------------------------------------- | ------------------------------------------------------- |
| $D_{a}^\sim(\emptyset) = \emptyset$                                         | $\delta(\emptyset) = \emptyset$                         |
| $D_{a}^\sim(\epsilon) = \epsilon$                                           | $\delta(\epsilon) = \epsilon$                           |
| $D_{a}^\sim(a) = \emptyset$                                                 | $\delta(a) = \emptyset$                                 |
| $D_{a}^\sim(L_{1} \cup L_{2}) = D_{a}^\sim(L_{1}) \cup D_{a}^\sim(L_{2})$   | $\delta(L_1 \cup L_2) = \delta(L_1) \cup \delta(L_2)$   |
| $D_{a}^\sim(L^*) = \epsilon$                                                | $\delta(L^*) = \epsilon$                                |
| $D_{a}^\sim(L_{1} \cdot L_{2}) = D_{a}^\sim(L_{1}) \cdot D_{a}^\sim(L_{2})$ | $\delta(L_1 \cdot L_2) = \delta(L_1) \cdot \delta(L_2)$ |
| $D_{a}^\sim(!L) = !(D_{a}(L) \cup D_{a}^\sim(L))$                           |                                                         |
| $D_{a}^\sim({\&}L) = {\&}(D_{a}(L) \cup D_{a}^\sim(L))$                     |                                                         |
| $D_{a}^\sim(L_{1} \cap L_{2}) = D_{a}^\sim(L_{1}) \cap D_{a}^\sim(L_{2})$   | $\delta(L_1 \cap L_2) = \delta(L_1) \cap \delta(L_2)$   |
| $D_{a}^\sim(L') =$?                                                         | $\delta(L') =$?                                         |
