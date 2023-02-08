# Conjunctive grammar with context

Barash and Okhotin proposed idea of contexts in context free grammars in 2012. See [Defining Contexts in Context-Free Grammars](https://www.semanticscholar.org/paper/Defining-Contexts-in-Context-Free-Grammars-Barash-Okhotin/f914cf1b9b4c879cd7becd1f490176e2b4a1583e).

## Brzozowski derivatives of conjunctive grammar with right context

First of all, let's define "syntax sugar" for the right context $L_1 \cap \triangleright L_2$:

$$
\begin{align}
& L_1 \cap \triangleright L_2 = \\
& L_1 \cdot (\epsilon \cap \triangleright L_2) = \\
& L_1 \cdot \\& L_2
\end{align}
$$

$\\&$ - is positive lookahead from [REwLA](Regular%20expressions%20with%20lookahead.md).
