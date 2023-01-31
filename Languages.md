# Languages

"Hardest" languages to test parsers. Most examples taken from
[Expressive power of LL(k) Boolean grammars](https://www.sciencedirect.com/science/article/pii/S0304397511003951)

## Linear context-free language

"Balanced brackets":

$$
\set{a^n b^n | n \geq 0}
$$

And variations of the above:

$$
\set{a^n b^n c^l | n, l \geq 0}
$$

$$
\set{a^m b^m a^n b^n | m, n \geq 0}
$$

## Classical context sensitive (LinConjLL)

Classical context sensitive example:

$$
\set{a^nb^nc^n | n \geq 0}
$$

```
S → A&C
A → aA | D
D → bDc | ε
C → aCc | B
B → bB | ε
```

### PEG

[Same example used by Ford](https://bford.info/pub/lang/peg.pdf) to show that PEG can handle context sensitive grammar.

```
A ← aAb/ε
B ← bBc/ε
S ← &(A!b)a∗ B!.
```

Actually it can't handle exactly this language, but it still can handle other context sensitive language. See https://github.com/SRI-CSL/PVSPackrat/issues/3


## Other context sensitive

$$
\set{a^{n^2} | n \geq 0}
$$

$$
\set{a^{n} | n \text{ is prime}}
$$

"copy langauge":

$$
\set{ww | w \in \Sigma^*}
$$

## TAG (Tree Adjoining Grammar)

$$
\set{ a^n b^m c^n d^m | n, m \geq 0 }
$$

## MG (Minimalist Grammar)

$$
\set{ a^n b^n c^n e^n f^n | n \geq 0 }
$$

## CFLL, but not in LinCFLL

$$
\set{a^n b^n cs | n \geq 0, s \in \set{a, b}}
$$

```
S → X &¬T
T → X &¬Aca&¬Acb
A → aAb | ε
X → aX | bX | cX | ε.
```

## Strongly non-left-recursive Boolean P-complete language

$$
a^{n−1−j_n} b a^{n−2−j_{n−1}} b \ldots a^{2−j_3} b a^{1−j_2} b
$$

```
S → E&¬AbS&¬CS
A → aA | ε
C → aCAb | b
E → aE | bE | ε.
```

## Strongly non-left-recursive conjunctive language

$$
\set{wcw |  w \in \set{a, b}^*}
$$

```
S → C &D
C → XCX | c
X → a | b
D → aA&aD | bB&bD | cE
A → XAX | cEa
B → XBX | cEb
E → aE | bE | ε.
```

## Jeż language

$$
\set{a^{4n} | n \geq 0}
$$

```
A1 → A1 A3 & A2 A2 | a
A2 → A1 A1 & A2 A6 | aa
A3 → A1 A2 & A6 A6 | aaa
A6 → A1 A2 & A3 A3.
```

## LL(1) linear Boolean language

$$
\set{a^m b^n | 0 \leq m \leq n}
$$

```
S → aS&¬A | bB
A → aAb | ε
B → bB | ε
```

## Boolean

$$
\set{ a^n b^{2^n} | n \geq 1}
$$
