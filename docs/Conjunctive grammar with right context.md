# Conjunctive grammar with context

Barash and Okhotin proposed idea of contexts in context free grammars in 2012. See [Defining Contexts in Context-Free Grammars](https://www.semanticscholar.org/paper/Defining-Contexts-in-Context-Free-Grammars-Barash-Okhotin/f914cf1b9b4c879cd7becd1f490176e2b4a1583e).

## Brzozowski derivatives of conjunctive grammar with right context

First of all, let's define "syntax sugar" for the right context $L_1 \cap \triangleright L_2$:

$$
\begin{align}
& L_1 \cap \triangleright L_2 = \\
& L_1 \cdot (\epsilon \cap \triangleright L_2) = \\
& L_1 \cdot \triangleright' L_2
\end{align}
$$

Now we can define additional rules for delta:

- (R8) $\delta(\triangleright' L) = \delta(L)$

And derivative:

- (R4) $D_a(L_1 \cdot L_2) = D_a(L_1) \cdot L_2 \cup \delta(L_1) \cdot D_a(L_2) \cup D_{a}^\triangleright (L_1) \cdot D_{a}(L_2)$
- (R7) excluded
- (R8) $D_a(\triangleright' L) = \emptyset$ 

And "context" derivative:

1. $D_a^\triangleright(a) = \emptyset$
2. $D_a^\triangleright(b) = \emptyset, \text{ if } b = \emptyset, b = \epsilon, b \in \Sigma \text{ and } b \neq a$
3. $D_a^\triangleright(L_1 \cup L_2) = D_a^\triangleright(L_1) \cup D_a^\triangleright(L_2)$
4. $D_{a}^\triangleright(L_{1} \cdot L_{2}) = D_{a}^\triangleright(L_{1}) \cup \delta(L_{1}) \cdot  D_{a}^\triangleright (L_{2})$
5. $D_{a}^\triangleright(L^*) = D_{a}^\triangleright(L)$
6. $D_a^\triangleright(L_1 \cap L_2) = D_a^\triangleright(L_1) \cap D_a^\triangleright(L_2)$
7. excluded
8. $D_{a}^\triangleright(\triangleright' L) = \triangleright' D_{a}(L)$

**Note**: this was not previously proposed in any reviewed publication. I also didn't try to prove it myself, this is rather educated guess.

**TODO**: provide at least bare explanation
