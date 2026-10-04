# CODAP grouping, Exercise 2: media and alt text

Recorded in CODAP v3.1.0 with compas_classroom.csv, grouped by c_charge_degree. The table already has the columns n, positives and base rate from Exercise 1. Base rate is shown with 4 decimal places (0.5044 and 0.3635). The part of the recording that set the precision was cut.

| File | Use |
|---|---|
| CODAP_grouping_steps_labeled.mp4 | Silent recording (3 min 26 s) with step labels burned in; the last frame holds for 4 seconds. Post it where students can pause and replay. |
| grouping_step1.png … grouping_step9.png | One still per step. |

## Text version of the video (the accessible alternative)

1. Scroll the people's part of the table (blue title bar "cases (3000 cases)") all the way to the right. Click the + at the right end of that blue bar. A new column called newAttr appears.
2. Type cell as the new column's name and press Enter. You choose this name.
3. Click the cell heading → Edit Formula… → type split + label + predicted → Apply.
4. Each row now shows a code built from its split, label and predicted values, such as test11, test01, train00 or train11. For example, test11 means a test row where the actual label is 1 and the prediction is 1.
5. Scroll back to the left. Click the + on the yellow group title bar ("c_charge_degrees (2 cases)"), then type TP as the name and press Enter.
6. Click the TP heading → Edit Formula… → type count(cell, cell="test11") → Apply. You should see F 190 and M 42.
7. Add a column FN with count(cell, cell="test10"). You should see F 102 and M 75.
8. Add a column FP with count(cell, cell="test01"). You should see F 112 and M 23.
9. Add a column TN with count(cell, cell="test00"). You should see F 181 and M 175.

Check: TP + FN + FP + TN = 585 for F and 315 for M, the number of test rows in each group.

## Alt text for each image

- **grouping_step1.png:** The people's part of the CODAP table, scrolled to the right, with a new column named newAttr at the right end next to predicted_threshold.
- **grouping_step2.png:** The same table with the new column renamed cell; the column is still empty.
- **grouping_step3.png:** The Edit Formula window for the attribute cell, with the formula split + label + predicted typed in and the pointer on Apply.
- **grouping_step4.png:** The cell column now filled with codes such as test00, train01, train00, train11 and test01, one per row.
- **grouping_step5.png:** The grouped table with rows F and M showing n, positives and base rate (1949, 983, 0.5044 and 1051, 382, 0.3635) and a new empty column named TP.
- **grouping_step6.png:** The TP column shows 190 for F and 42 for M.
- **grouping_step7.png:** The FN column, next to TP, shows 102 for F and 75 for M.
- **grouping_step8.png:** The FP column shows 112 for F and 23 for M.
- **grouping_step9.png:** The finished group table: for F, TP 190, FN 102, FP 112, TN 181; for M, TP 42, FN 75, FP 23, TN 175.
