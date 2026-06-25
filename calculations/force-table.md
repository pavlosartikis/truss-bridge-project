# Complete Force Table

Full set of member forces, symbolic (in terms of the applied load `W`) and numeric (assuming `W = 60 N`, the brief's minimum design load). Right-hand-side joints (`H, I, J, K, L`) are obtained by mirror symmetry about the centre joint `G`, where the load is applied.

Original scanned working: [`../images/full-force-table-and-load-mass.png`](../images/full-force-table-and-load-mass.png).

**Sign convention:** positive = tension, negative = compression.

## Symbolic forces (in terms of W)

| Joint | Member | Force |
|---|---|---|
| A | R_A (reaction) | W/2 |
| A | A–B | −W√2/2 |
| A | A–C | W/2 |
| B | B–C | 0 |
| B | B–D | −W |
| B | B–E | W√2/2 |
| C | C–E | W/2 |
| C | C–B | 0 |
| C | C–A | W/2 |
| D | D–G | W√2/2 |
| D | D–F | −3W/2 |
| D | D–E | −W/2 |
| D | D–B | −W |
| E | E–G | W |
| E | E–D | −W/2 |
| E | E–C | W/2 |
| E | E–B | W√2/2 |
| F | F–D | −3W/2 |
| F | F–G | 0 |
| F | F–H | −3W/2 |
| G | G–D | W√2/2 |
| G | G–E | W |
| G | G–F | 0 |
| G | G–H | W√2/2 |
| G | G–I | W |
| *(mirror)* H, I, J, K, L | — | mirror of D, E, F/C, B, A respectively |

## Numeric forces at design load, W = 60 N

| Joint | Member | Force (N) |
|---|---|---|
| D | D–G | 42.4 |
| D | D–F | **−90** |
| D | D–E | −30 |
| D | D–B | −60 |
| E | E–G | 60 |
| E | E–D | −30 |
| E | E–C | 30 |
| E | E–B | 42.4 |
| F | F–D | **−90** |
| F | F–G | 0 |
| F | F–H | **−90** |
| G | G–D | 42.4 |
| G | G–E | 60 |
| G | G–F | 0 |
| G | G–H | 42.4 |
| G | G–I | 60 |
| H | H–G | 42.4 |
| H | H–F | **−90** |
| H | H–I | −30 |
| H | H–J | −60 |

## Most heavily loaded members

At the 60 N design load, the **top-chord members nearest mid-span (D–F and F–H) and the diagonal F–D / F–H carry the highest force: −90 N (i.e. 90 N compression)** — 1.5× the applied load. This concentration happens because these short top-chord members carry the full horizontal component of the force funnelling down through the diagonals from the load point, over a short member length, so the geometry amplifies the applied load rather than spreading it out.

This is the figure that should drive material/cross-section choice for those specific members if optimising the design further — they're the first members expected to fail as load increases, assuming the idealised pin-jointed model holds.

## Mass and predicted vs. measured performance

| | Mass used | Failure load | Load/mass ratio |
|---|---|---|---|
| **Predicted** (hand calc, design load assumption) | 0.08965 kg *(as written in the original calculation — see note below)* | 6 kg (=60N min target) | 181.3 |
| **Measured** (actual test) | 0.03965 kg (39.65 g, weighed) | 5 kg (≈49 N) | 126.1 |

**Note on the mass discrepancy:** the original hand-calculation page records the bridge mass as `0.08965 kg`, while the measured test-results table records `0.03965 kg` (39.65 g). These are very likely the same number with a transcription slip (`08` vs `03`) rather than two different bridges — the measured value (39.65 g, directly weighed) is the one used for the actual scored result. This is flagged here rather than silently corrected, since it's a real discrepancy in the original report and worth being transparent about.

The performance factor that actually counted for scoring was **126.1**, i.e. **71.4% of the 60 N minimum load requirement** — the bridge failed before reaching the design target.
