# Regex

Regex is [regular expressions](Regular%20expressions.md) with backreferences.

Backreferences are used to reference a captured value at matching time. Backreferences have the syntax `\n`, where `n` is the capture identifier. The backreference `\1` in pattern `([a-z])\1` is replaced with the substring matched by the capture `([a-z])`.

Backreferences extend regular expressions by allowing the recognition of more than regular languages. As an example, the expression `(a+)(b+)\1\2` defines the language $\set{a^ib^ja^ib^j \mid i, j > 0 }$ which is not context-free.

Backreferences can result in an exponential running time of the matching algorithm. This problem is unavoidable because the 3-SAT problem can be reduced to regexes with backreferences. Therefore, any matcher thus constructed is NP-Complete.

From: [Converting regexes to Parsing Expression Grammars](https://www.inf.puc-rio.br/~roberto/docs/ry10-01.pdf).

## Related

- https://github.com/goodmami/pe
- https://rosie-lang.org/about/
- [Converting Regex to Parsing Expression Grammar with Captures](https://repository.lib.ncsu.edu/bitstream/handle/1840.20/38685/etd.pdf?sequence=1)
- [Regular Expressions with Backreferences Re-examined](<https://www.cair.org.za/sites/default/files/2019-08/regex%20(003).pdf>)
  - TODO: rename Regex to REwB
