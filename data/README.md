# Data

`reading-derivation.json` is the record the derivation wrote: the instructions induced, the five taught
sentences, the procedure synthesized, and each held-out sentence with the meaning the procedure emitted.

| Field | What it carries |
|---|---|
| `instruction_set` | each read-instruction induced from before/after demonstrations, and what it explains |
| `derivation` | the synthesis status, the size of the procedure, the candidates searched, and the steps |
| `held_out` | each held-out sentence and the meaning emitted for it |
| `held_out_correct` | how many were read correctly |
| `model` | the model condition of the run |

The `model.entry_points_checked` list names four modules through which a language model could once have
been called. All four have been removed from the system; the run looks for each one and records which, if
any, can still be imported. `entry_points_present: []` is the result: there is nothing to consult. The
names are recorded because a check is only meaningful if it says what was checked.
