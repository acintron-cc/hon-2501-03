# CODAP grouping, Part A: optional video

| File | Use |
|---|---|
| CODAP_grouping_partA_labeled.mp4 | Silent recording (2 min 14 s) of Part A, with step labels burned in; the last frame holds for 4 seconds. Link it as the optional video at the end of Part A. |

Made from the same CODAP recordings as the Part A stills (CODAP v3.1.0, compas_classroom.csv). No personal information is visible.

## Text version of the video (the accessible alternative)

1. Drag the c_charge_degree heading to the left edge of the table. The table splits in two: a group part on the left with one row each for F and M, and the people on the right.
2. Click + on the yellow group title bar and name the new column n.
3. Click the n heading → Edit Formula… → type count() → Apply. n shows 1949 for F and 1051 for M.
4. Add a column positives with the formula count(label, label=1). It shows 983 for F and 382 for M.
5. Add a column base_rate with the formula positives / n. It shows 0.5 and 0.36.

Tip: click the base_rate heading → Edit Attribute Properties… → set Precision to 4 → Apply. base_rate now shows 0.5044 for F and 0.3635 for M. (In the recording, Precision starts at 0, so the column briefly shows 1 and 0 before it is set to 4.)
