# Operations concept map

Properly this diagram is called concept lattice (it comes from Formal Concept Analysis). It is very similar to Hasse diagram.

![](Operations%20concept%20map.svg)

## As table

|          | ·   | ∪   | \*    | ∩     | '     | ⟲   | &   | !   | /     |
| -------- | --- | --- | ----- | ----- | ----- | --- | --- | --- | ----- |
| RE       | x   | x   | x     |       |       |     |     |     |       |
| REE      | x   | x   | x     | x     | x     |     |     |     |       |
| REwLA    | x   | x   | x     | x (4) | x (5) |     | x   | x   | x (2) |
| PEG      | x   |     | x (1) | ? (4) | ? (5) | x   | ?   | ?   | x     |
| CFG      | x   | x   | x (1) |       |       | x   |     |     |       |
| Conj     | x   | x   | x (1) | x     |       | x   |     |     |       |
| Bool     | x   | x   | x (1) | x     | x     | x   |     |     |       |
| ConjCont | x   | x   | x (1) | x     |       | x   | x   |     |       |
| ~MOG (3) | x   | x   | x (1) | ? (4) | ? (5) | x   | ?   | ?   | x     |

- (1) Kleene star (`A*`) can be simulated with `S -> "" | S · A`
- (2) Prioritised choice (`A / B`) can be simulated with `A ∪ !(A) · B`
- (3) MOG has concept of "tainted" operators, this diagram doesn't take it into account

**Note**: not taken in account in diagram:

- (4) Intersection (`A ∩ B`) can be simulated with `&(A) · &(B) · Σ* · &(ϵ)`
- (5) Complement (`A'`) can be simulated with `!(A) · Σ* · &(ϵ)`
- Negative lookahead (`!A`) can be simulated with positivie lookahead and complement `&A'`
- Positivie lookahead (`&A`) can be simulated with negative lookahead `!!A`

## Abbreviations

- [RE](Regular%20expressions.md) - Regular Expressions
- [REE](Regular%20expressions.md) - Regular Expressions Extended
- [REwLA](Regular%20expressions%20with%20lookahead.md) - Regular Expressions with Look Ahead
- [PEG](PEG.md) - Parsing Expressions Grammar
- [CFG](CFG.md) - Context-Free Grammar
- [Conj](Conjunctive%20grammar.md) - Conjuctive grammar
- [Bool](Boolean%20grammar.md) - Boolean grammar
- [ConjCont](Conjunctive%20grammar%20with%20right%20context.md) - Conjuctive grammar with Context (right)
- [MOG](MOG.md) - Multi Ordered Grammar

### Not in diagram

- [Regex](Regex.md) - Regular Expressions with backreferences
- TAG - Tree Adjoining Grammar
- MG - Minimalist Grammar

## Operators

- `·` - concatenation or sequence. Often ommited in noatation e.g. `AB` instead of `A · B`
- `∪` - unordered or non-determenistic choice or union. Chomsky uses `|`. Brzozowski uses `+`
- `*` - Kleene star or iteration
- `∩` - intersection. Okhotin and Brzozowski use `&`
- `'` - complement. Okhotin uses $\lnot$
- `⟲` - recursion. It is not an explicit operator, but rather "permision" to form recursion a la `S -> S`
- `&` - positive lookahead or right context or positive syntatic predicate. Barash and Okhotin use $\triangleright$
- `!` - negative lookahead or negative syntatic predicate
- `/` - ordered or determenistic or prioritized choice. In MOG they use `||`

### Not in diagram

- `↑` - cut operator (from extension of [PEG](PEG.md))
- `||` - interleave operator (from [POMS](POMS.md))
- $\triangleleft$ - left context (from Conjuctive grammar with Context)
- `\x` - backreference (from Regex)

## Related

![Post's lattice for language equations](Posts%20lattice%20for%20language%20equations.png)

From [On language equations with concatenation and various sets of boolean operations](http://www.numdam.org/item/10.1051/ita/2015006.pdf)

**TODO**: diagram of expressive power of grammars
