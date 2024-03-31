Moved to https://parsing.stereobooster.com/

# Parsing with derivatives

[![](docs/Operations%20concept%20map.svg)](docs/Operations%20concept%20map.md)

## Innovation

- Parsing with derivatives can easily support [Conjunctive grammar](docs/Conjunctive%20grammar.md), which can parse not context-free grammar, for example $\set{a^nb^nc^n \mid  n \geq 0}$. This is not something innovative per se, but I haven't seen it mentioned anywhere in reviewed publications.
- Parsing with derivatives can support [Conjunctive grammar with right context](docs/Conjunctive%20grammar%20with%20right%20context.md), if we add recursion to [REwLA](docs/Regular%20expressions%20with%20lookahead.md)
- I showed how to express [PEG](docs/PEG.md) in terms of REwLA with recursion. Which allows to define derivative formula for PEG.
  - This allows to create variation of PEG with unordered choice. Related work:
    - [Parsing Expression Grammars with Unordered Choices](https://www.jstage.jst.go.jp/article/ipsjjip/25/0/25_975/_pdf)
  - By the nature of parsing with derivatives it doesn't have issues with left recursion. Related works:
    - [Left recursion in Parsing Expression Grammars](https://www.sciencedirect.com/science/article/pii/S0167642314000288)
    - [Packrat Parsers Can Support Left Recursion](https://web.cs.ucla.edu/~todd/research/pepm08.pdf)
    - [Direct Left-Recursive Parsing Expression Grammars](https://tratt.net/laurie/research/pubs/html/tratt__direct_left_recursive_parsing_expression_grammars/)
    - [More about left recursion in PEG](https://ceur-ws.org/Vol-2240/paper9.pdf)
  - It can open door to understand expressive power of PEG (it is not contained within context-free, but also can express some context-sensitive languages)
