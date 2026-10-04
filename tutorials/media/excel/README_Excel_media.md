# Excel warm-up: media and alt text

Recorded in Microsoft Excel for Mac with compas_classroom.csv (all rows). Windows differences are noted in the steps.

| File | Use |
|---|---|
| Excel_warmup_steps_labeled.mp4 | Silent 100-second recording with step labels burned in. Post it where students can pause and replay. |
| Excel_warmup_steps_labeled.gif | Same, as a looping animation. |
| excel_step1.png … excel_step9.png | One still per step, cropped to the part of the screen that matters. |

**Privacy:** in the Open and Save As windows, the personal folders and locations in the left sidebar are blurred, in the stills and in the video.

## Text version of the video (the accessible alternative)

1. File → Open, choose compas_classroom.csv (in your Downloads folder), and click Open.
2. Save the file as an Excel Workbook (.xlsx): File → Save As, File Format: Excel Workbook (.xlsx), Save. A plain .csv file cannot keep the table or the Answers sheet.
3. Click cell A1, press Cmd+T (Windows: Ctrl+T), keep "My table has headers" ticked, and click OK.
4. On the Table tab (Windows: Table Design tab), change Table Name from Table1 to data and press Enter.
5. Click + at the bottom to add a sheet; double-click its tab and name it Answers.
6. In cell A1 of Answers, paste =COUNTIFS(data[c_charge_degree],"F") and press Enter. You should see 1949.
7. In A2, paste =COUNTIFS(data[c_charge_degree],"F",data[label],1). You should see 983.
8. In A3, paste =AVERAGEIFS(data[label],data[c_charge_degree],"F"). You should see 0.50436121 (about 0.504).
9. Repeat in column B with "M" instead of "F". You should see 1051, 382 and 0.36346337 (about 0.363).

## Alt text for each image

- **excel_step1.png:** Excel's Open window showing the Downloads folder with compas_classroom.csv selected. The personal folders in the sidebar are blurred.
- **excel_step2.png:** Excel's Save As window with the name compas_classroom and File Format set to Excel Workbook (.xlsx). The personal folders in the sidebar are blurred.
- **excel_step3.png:** The Create Table window over the data, showing the range $A$1:$R$3001 and a ticked box 'My table has headers', with the OK button highlighted.
- **excel_step4.png:** The Table tab in Excel's ribbon with the Table Name box changed to 'data'; the data below now has coloured table rows and filter arrows in the header row.
- **excel_step5.png:** The sheet tabs at the bottom of Excel, with a new tab being named Answers next to the compas_classroom tab.
- **excel_step6.png:** The Answers sheet with 1949 in cell A1.
- **excel_step7.png:** Cell A2 shows 983; the formula bar shows =COUNTIFS(data[c_charge_degree],"F",data[label],1).
- **excel_step8.png:** Cells A1 to A3 show 1949, 983 and 0.50436121.
- **excel_step9.png:** Column A shows 1949, 983 and 0.50436121 (F); column B shows 1051, 382 and 0.36346337 (M).
