# Conjunctive grammar with "negative" right context

Extension of [conjunctive grammar with right context](./Conjunctive%20grammar%20with%20right%20context.md) with "negative" context or negative lookahead.

## Brzozowski derivatives of conjunctive grammar with "negative" right context

First of all, let's define "syntax sugar" for the "negative" right context $L_1 \cap \triangleright L_2^c$:

$$
\begin{align}
& L_1 \cap \triangleright L_2^c = \\
& L_1 \cdot (\epsilon \cap \triangleright L_2^c) = \\
& L_1 \cdot \not{\triangleright}' L_2
\end{align}
$$

Now we can define additional rules for delta:

- (R9) $\delta(\not{\triangleright}' L) = \delta(L^c)$

And derivative:

- (R9) $D_a(\not{\triangleright}' L) = \emptyset$ 

And "context" derivative:

- (R9) $D_{a}^\triangleright(\not{\triangleright}' L) = \not{\triangleright}' D_{a}(L)$

**Note**: it requires proof that language equations with "negative" context operation are Scott continuous.
