# Multi-Ordered Grammars

- [Parsing Multi-Ordered Grammars with the Gray Algorithm](https://npapoylias.gitlab.io/lands-project/Multi-Ordered-Grammars-Gray-Algorithm-Papoulias-PeerJ-PrePrint.pdf)
  - `MOG = PEG + Unordered + RecScopedOrdered`
  - `MOG = CFG + LAhead + Ordered + RecScopedOrdered`
- [For and Against PEGs: Why we need Multi-Ordered Grammars](https://peerj.com/preprints/27358.pdf)

## Notation

| Operator | Appears in         | Description                                      |
| -------- | ------------------ | ------------------------------------------------ |
| `AB`     | MOG, EBNF, PEG, RE | Composition operator aka concatenation, sequence |
| `?`      | MOG, EBNF, PEG, RE | Optional operator                                |
| `*`      | MOG, EBNF, PEG, RE | Zero-or-more operator aka Kleene star            |
| `+`      | MOG, EBNF, PEG, RE | One-or-more operator aka Kleene plus             |
| `()`     | MOG, EBNF, PEG, RE | Grouping operator                                |
| \|       | MOG, EBNF, PEG, RE | Non-deterministic (unordered) choice operator    |
| `&`      | MOG, PEG           | Syntactic positive predicate                     |
| `!`      | MOG, PEG           | Syntactic negative predicate                     |
| \|\|     | MOG (scoped), PEG  | Deterministic (ordered) choice operator          |
| `/`      | MOG                | Self-recursive (ordered) choice operator         |
| `\`      | MOG                | Recursive (ordered) choice operator              |
