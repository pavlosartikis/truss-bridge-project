# Method of Joints — Full Hand Solution

Sign convention used throughout: **positive = tension, negative = compression** (consistent with the course convention of assuming every member is in tension and reading off the sign at the end).

The truss is a symmetric Pratt bridge truss, span 42 cm, height 7 cm, six 7 cm panels, all diagonals at 45°, with a single point load `W` applied at the centre joint (`G`) representing the test load.

Original scanned working: [`../images/method-of-joints-calcs-1.png`](../images/method-of-joints-calcs-1.png) (joints C, B, E, D) and [`../images/method-of-joints-calcs-2-sections.png`](../images/method-of-joints-calcs-2-sections.png) (joint D continued, plus the method-of-sections cut).

Joint labelling (left to right): `A, C, E, G, I, K, L` along the bottom chord; `B, D, F, H, J` along the top chord. `A` and `L` are the supports.

## Step 1 — Reactions

Taking moments about each support in turn (the load `W` acts at mid-span, 21 cm from each end on a 42 cm span):

```
Moments about L:   42·R_A = 21·W   →   R_A = W/2
Moments about A:   42·R_L = 21·W   →   R_L = W/2
```

Check: horizontal resultant = 0 (no horizontal external load), vertical resultant: `R_A + R_L = W` ✓.

By symmetry, the truss is solved on one half and the forces on the other half are the mirror image.

## Step 2 — Joint A

Three members meet at A: the support reaction `R_A` (vertical), the bottom chord `A–C` (horizontal), and the diagonal `A–B` (at 45°).

```
ΣFx:  F_AB·cos(45°) + F_AC = 0
ΣFy:  R_A + F_AB·sin(45°) = 0
```

Solving:
```
F_AB = -R_A / sin(45°) = -(W/2)·√2 = -W√2/2      (compression)
F_AC = -F_AB·cos(45°)  = +W/2                     (tension)
```

## Step 3 — Joint C

```
ΣFx:  F_CE - F_AC = W/2
ΣFy:  F_CB = 0
```
```
F_CB = 0
F_CE = W/2
```

## Step 4 — Joint B

```
ΣFx:  F_BD + F_BE·cos(45°) = F_BA·sin(45°)
ΣFy:  -F_BE·cos(45°) - F_BC - F_BA·cos(45°) = 0
```
```
F_BE = (-F_BC - F_BA·cos(45°)) / cos(45°) = W√2/2     (tension)
F_BD = F_BA·√2·cos(45°) - W/2 = -W                    (compression)
```

## Step 5 — Joint E

```
ΣFx:  F_EG - F_EC - F_EB·cos(45°) = 0
ΣFy:  F_ED + F_EB·sin(45°) = 0
```
```
F_ED = -(W√2/2)·sin(45°) = -W/2                       (compression)
F_EG = (W√2/2)·cos(45°) + W/2 = W                     (tension)
```

## Step 6 — Joint D

```
ΣFx:  F_FD + F_DG·cos(45°) = F_DB
ΣFy:  -F_DG·cos(45°) - F_DE = 0
```
```
F_DG = -F_DE / cos(45°) = (W/2)·√2 = W√2/2             (tension)
F_FD = -W - (W√2/2)·cos(45°) = -3W/2                   (compression)
```

## Step 7 — Continuing to mid-span (F, G)

Solved in conjunction with the method of sections cut at the central panel (see [`method-of-sections.md`](method-of-sections.md)), which directly gives:

```
F_FH = -3W/2     (compression)
F_FG = 0         (the central vertical, FG, is a "non-loading chord" — zero force at this load case, shown in yellow on the design sketch)
F_GE = W         (tension)
```

## Step 8 — Mirror for the right-hand half

By symmetry about the vertical through the loaded joint (G), the forces on joints `H, I, J, K, L` mirror those on `D, E, B, C, A` respectively.

The complete set of member forces is tabulated in [`force-table.md`](force-table.md).
