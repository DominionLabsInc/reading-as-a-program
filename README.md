# A Reading Is a Program over a Sequence

**Deriving a procedure for reading a sentence from examples, rather than writing a parser or training a
language model.**

Stefan Ragland, Dominion Labs Research & Development. Published 21 January 2025.

- Paper: <https://dmnlabs.org/research/reading-as-a-program/>
- Paper (offline copy): [`paper/reading-as-a-program.html`](paper/reading-as-a-program.html)
- Contact: research@dmnlabs.org

## The result

A reading is treated as a short program over a token sequence: a cursor advancing over words, writing a
subject, a predicate and a polarity into registers under branch conditions. The individual
read-instructions are induced from a handful of before/after demonstrations, and the branching procedure
that composes them is synthesized from sentence and meaning pairs alone.

From five taught sentences the substrate derived a six-step procedure and read seven held-out sentences
correctly, every content word of which was new to it. A corrupted-supervision control, with deliberately
wrong meanings, yielded no procedure within the search bound, so the capability is not an artifact of a
search that always finds something.

## Re-verification

| What was checked | Result | Data |
|---|---|---|
| The derivation, re-run against the live substrate on 18 September 2026 | the same six-step procedure, 7 of 7 held-out sentences read correctly, corrupted-supervision control still empty, no model entry point importable | [`data/reading-derivation.json`](data/reading-derivation.json) |

Two numbers in the manifest differ from the original run, and the difference is in the synthesizer rather
than the result: it enumerates policies (one operator per abstract state) and induces a decision list for
each, reaching its procedure after 1,464 candidates, and it identifies a procedure by its behaviour on
the evidence rather than by its syntax, so procedures that take the same route on every example count as
one. Section 5 of the paper states this.

## Citation

```bibtex
@techreport{ragland2025reading,
  title       = {A Reading Is a Program over a Sequence},
  author      = {Ragland, Stefan},
  institution = {Dominion Labs},
  year        = {2025},
  month       = {1},
  url         = {https://dmnlabs.org/research/reading-as-a-program/}
}
```

## License

The paper and the data are released under [Creative Commons Attribution 4.0](LICENSE). Please cite the
paper if you use them.
