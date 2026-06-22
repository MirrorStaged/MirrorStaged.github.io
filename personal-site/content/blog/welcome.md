+++
title = "Colophon, and how the margin works"
date = 2026-06-22
+++

This first note exists to exercise the typographic machinery so you can see what the
site does before you fill it with real writing.

The defining feature is the **margin note**. A claim that needs a caveat gets one
without breaking the line of argument{{ sidenote(text="Numbered, auto-incrementing, and rendered in the right margin on wide screens. On a phone the superscript becomes tappable.") }} — the
reader's eye stays in the main column. Unnumbered margin notes work too{{ marginnote(text="Like this one — useful for a pointer or an image caption that shouldn't interrupt the count.") }}, for
asides that aren't really footnotes.

## Code and data render plainly

```python
def value_of_information(p_correct, payoff, cost):
    # crude EV-of-experiment sketch
    return p_correct * payoff - cost
```

Tables stay quiet — rules, not boxes:

| Method      | n    | effect (d) |
|-------------|------|------------|
| Replication | 1,021| 0.21       |
| Original    | 38   | 0.91       |

> A blockquote for the occasional borrowed sentence, set off without ornament.

That is the whole vocabulary: body column, margin, figure, code, table, quote.
Nothing else. Delete this file once you've seen it work.
