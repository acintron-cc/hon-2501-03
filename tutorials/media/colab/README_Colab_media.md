# Colab first run: media and alt text

Recorded in Google Colab with the class notebook `fairness_lesson.ipynb` (dropdown `compas`, protected attribute `race_group`; Partner A). The recording opens the notebook from its GitHub link, signs in, saves a copy, and runs Sections 1, 2 and 3, then shows Gemini and a deliberate error.

**Privacy:** the Google sign-in screens (3 to 25 seconds into the recording) are blurred in every frame. The account's profile picture (top right and in the Gemini panel), the name greeting in the Gemini panel and every "executed by" hover tooltip are also blurred; a text-recognition scan of the finished video every 0.25 seconds found no name. The stills are cropped so that none of these appear.

| File | Use |
|---|---|
| Colab_walkthrough_labeled.mp4 | Silent recording (5 min 13 s) with step labels burned in. The Section 1 install wait is sped up 4 times (labeled "sped up here"); the last frame holds for 4 seconds. |
| colab_step1.png … colab_step12.png | One still per step, cropped to the part of the screen the step is about (so the numbers are readable on a slide). |

## Text version of the video (the accessible alternative)

1. Open the class notebook from its Colab link. The page shows "Algorithmic Fairness: class notebook" and a blue **Sign in** button at the top right.
2. Click **Sign in** and sign in with your Google account. (The recording blurs this screen for privacy.) You return to the notebook, now with your picture at the top right.
3. Click **File → Save a copy in Drive**. A new tab, "Copy of fairness_lesson.ipynb", opens. Work in the copy.
4. Section 1: click the ▶ at the left of "Install and load the tools (just run this)". Wait 1 to 2 minutes the first time (sped up in the video). If Colab warns that the notebook was not authored by Google, click **Run anyway**. It is finished when it prints `Ready. Fairlearn version: 0.13.0`.
5. Section 2: in the DATASET dropdown on the right of the cell choose `compas` (Partner A) or `adult` (Partner B), then click ▶. For COMPAS it prints `Dataset: compas   rows: 3,000   train: 2,100   test: 900`, what label 1 means, the protected attribute `race_group`, the groups compared (African-American and Caucasian), and the first rows of the table.
6. Section 3.1: click ▶ on "Exercise 1: base rates (all rows)". A table shows, for each group, label = 0, label = 1, n and base rate. For COMPAS: African-American 735, 808, 1543, 0.524; Caucasian 622, 400, 1022, 0.391; Other 278, 157, 435, 0.361; Total 1635, 1365, 3000, 0.455.
7. Section 3.2: click ▶ on "Exercise 2: confusion matrices (test rows, original model)". For COMPAS it prints, for example, `African-American (463 test rows) TP=158 FN=84 FP=75 TN=146` with a 2 × 2 table, and the same for Caucasian (307 test rows: TP=55 FN=65 FP=44 TN=143).
8. Section 3.3: click ▶ on "Exercise 3: MetricFrame". It shows selection rate, TPR, FPR, accuracy and n for each group, then the gap row (0.181, 0.195, 0.104, 0.012) and `Selection-rate ratio (smaller / larger): 0.641 -> fails the 80% rule`. (The "Chart: rates by group" cell comes next in the notebook; the recording does not run it.)
9. Meet Gemini: point at the blue button at the bottom centre of the page (its tooltip says "Toggle Gemini") and click it. A Gemini panel opens on the right. Type "Explain what the table in Section 3.1 shows, in plain words." and press Enter. Gemini explains the rows, label = 0 and label = 1, n and base rate.
10. Make an error on purpose: click **Runtime → Restart session**, confirm, scroll to "Exercise 3: MetricFrame" and click ▶ without running Section 1 first. A red error appears: `NameError: name 'MetricFrame' is not defined`. Colab forgot what the earlier cells loaded.
11. Click **Explain error** under the red message. Gemini says the setup cell (Section 1) has not run since the restart, and says to scroll up to Section 1, click ▶, wait for Ready, then run Section 2, then Section 3. Read it; do not accept code changes.
12. The fix: run the cells again in order. Section 1 (now quick: "Fairlearn is already installed. Ready."), then Section 2, then the Section 3 cells.

## Alt text for each image

- **colab_step1.png:** The top of the class notebook in Colab, titled "Algorithmic Fairness: class notebook", with the "How to use this notebook" list and a blue Sign in button at the top right.
- **colab_step2.png:** The top right of the notebook page, with the pointer on the blue Sign in button, circled in yellow, next to Share.
- **colab_step3.png:** The File menu open on the left, listing New notebook in Drive, Open notebook, Upload notebook, Save a copy in Drive, Save a copy as a GitHub Gist, Save and Download.
- **colab_step4.png:** The copied notebook ("Copy of fairness_lesson.ipynb") with the line "Ready. Fairlearn version: 0.13.0" at the top, followed by the Section 2 heading "Choose your dataset" and a table of the two partners' datasets.
- **colab_step5.png:** The output of Section 2: "Dataset: compas rows: 3,000 train: 2,100 test: 900", the meaning of label 1, the protected attribute race_group, the groups compared, and a table of the first five rows.
- **colab_step6.png:** Section 3.1 output, a table by race_group with columns label = 0, label = 1, n and base rate: African-American 735, 808, 1543, 0.524; Caucasian 622, 400, 1022, 0.391; Other 278, 157, 435, 0.361; Total 1635, 1365, 3000, 0.455.
- **colab_step7.png:** Section 3.2 with the code cell and its output: "African-American (463 test rows) TP=158 FN=84 FP=75 TN=146" and a small 2 × 2 table of label by predicted.
- **colab_step8.png:** Section 3.3 output: a table of selection rate, TPR, FPR, accuracy and n for African-American, Caucasian and Other, a gap row (0.181, 0.195, 0.104, 0.012), and the line "Selection-rate ratio (smaller / larger): 0.641 -> fails the 80% rule".
- **colab_step9.png:** The notebook with the Gemini panel open on the right, showing Gemini's plain-words explanation of the Section 3.1 table and a text box below it.
- **colab_step10.png:** A cell with a red error: a traceback pointing at "mf = MetricFrame(" and the message "NameError: name 'MetricFrame' is not defined", with an **Explain error** button under it.
- **colab_step11.png:** The Gemini panel showing "Please explain this error: NameError: name 'MetricFrame' is not defined" and Gemini's explanation, which tells the reader to scroll up to Section 1 - Setup, run it, wait for Ready, then run Section 2 and Section 3. The red error cell is on the left.
- **colab_step12.png:** Section 1 and Section 2 rerun in order: the text "Fairlearn is already installed. Ready. Fairlearn version: 0.13.0", the Section 2 cell with the DATASET dropdown set to compas.
