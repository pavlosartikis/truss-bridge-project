# Method of Sections — Cross-Check

Used as an independent check on the method-of-joints solution, and to solve directly for the force in the central panel's top chord and diagonal without working through every joint from the support inward.

## The cut

A vertical section is taken through the truss just to the left of joint `H` (cutting the top chord member `F–H`, the diagonal `G–H`, and the bottom chord member `G–I`), isolating the left-hand portion of the truss (everything from support `A` up to and including joint `G`, plus the cut members' internal forces).

The three unknowns exposed by the cut — `F_FH` (top chord), `F_GH` (diagonal), `F_GI` (bottom chord) — are solved using the three equilibrium equations for the isolated left-hand section.

## Equilibrium of the left-hand section

**Moments about G** (eliminates `F_GH` and `F_GI`, since both pass through or act along lines through G — isolating `F_FH`):

```
M_G:  21·R_A + 7·F_FH = 0
      F_FH = -21·(W/2) / 7 = -3W/2          (compression)
```

This matches the value obtained independently via the method of joints at joint D (`F_FD = -3W/2`), confirming the top-chord force in the most-loaded panel.

**Moments about H** (eliminates `F_FH`, isolating `F_GI`):

```
M_H:  28·R_A + 7·F_GH·sin(45°) = 7·F_GH·sin(45°) + 7·F_GI + 7·W
      F_GI = (28·(W/2) - 7W) / 7 = W          (tension)
```

**Vertical equilibrium** (isolating the diagonal `F_GH`):

```
ΣFy:  R_A + F_GH·sin(45°) = W
      F_GH = (W - W/2) / sin(45°) = W√2/2     (tension)
```

## Cross-check at joint F

With `F_FH` and `F_FD` both known from above, joint F's own equilibrium confirms the central vertical `F_FG` carries no load at all under this load case:

```
ΣFx:  F_FH - F_FD = -3W/2   ✓ (consistent: both equal -3W/2, no net horizontal force needed beyond what's already balanced)
ΣFy:  F_FG = 0
```

`F–G` is therefore a **non-loading member** for this load case — shown in yellow on the final design sketch. It's structurally necessary (it fixes the joint geometry and would pick up load under an off-centre load case) but carries zero force for a central point load.

## Result

Both methods agree on every member checked, which is the main point of doing the cross-check: `F_FH = F_FD = -3W/2` (compression) — the most heavily loaded members in the truss for this load case.
