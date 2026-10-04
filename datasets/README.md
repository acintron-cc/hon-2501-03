# Classroom files: three models to compare

Prepared by the instructor from public versions of each dataset, with the models fitted using seed `42`. Each `<name>_classroom.csv` keeps every original column unchanged and adds the columns below at the end.

**Compute every metric on the test rows only: filter to `split == "test"`.** The models were fitted on the train rows, so train rows flatter them.

## New columns

| column | meaning |
|---|---|
| `label` | the target as 0/1 (see each dataset below for what 1 means) |
| group column | the sensitive attribute for this lesson: `race_group` in COMPAS and `age_group` in Bank are new; Adult and German Credit use their existing `sex` column |
| `split` | `train` (70%) or `test` (30%), stratified on label × group, `random_state=42` |
| `score` | original model's probability that `label = 1` (3 decimals) |
| `predicted` | original model's prediction: 1 when `score` ≥ 0.5 |
| `predicted_reweighed` | the same model retrained with Reweighing weights (Kamiran & Calders, 2012) |
| `predicted_threshold` | Fairlearn `ThresholdOptimizer` applied to the original model, with group-specific thresholds |

All models are logistic regressions that **do not see** the sensitive attributes (they are removed from the model inputs but kept in the file). Other columns can still act as proxies for them.

Threshold constraint for every dataset: true-positive-rate parity (equal opportunity): equal TPR across groups.

The Reweighing weights are not in these files: computing them from the group × label table of the train rows is the class exercise.

## `adult_classroom.csv`

2,000 rows, 600 of them test rows. Group sizes: Female 666, Male 1,334.

- Target `class`: `label = 1` means income `>50K`. **`label = 1` is the favorable outcome**, so a higher selection rate means more people are predicted to earn over $50K.
- Group column: `sex` (`Female`, `Male`), already in the file.
- Second attribute: `race`, already in the file. Try the same tables with `race`, or with `sex` and `race` together.

## `compas_classroom.csv`

3,000 rows, 900 of them test rows. Group sizes: African-American 1,543, Caucasian 1,022, Other 435.

- Target `two_year_recid`: `label = 1` means `Recidivated` (rearrested within two years). **Here `label = 1` is a harm, not a benefit.** A *higher* selection rate means more people are flagged as likely to be rearrested.
- Group column: `race_group` (new). `African-American` and `Caucasian` are kept from `race`; `Asian`, `Hispanic`, `Native American` and `Other` are pooled into `Other`. That pool mixes very different groups, so hand exercises can use just African-American and Caucasian, as in ProPublica's analysis.
- Second attribute: `sex`, already in the file.
- **Known limitation:** the rows come from ProPublica's two-year recidivism file, which keeps people screened after April 1, 2014 only if they were rearrested. That over-counts `label = 1`: Barenstein (2019, [arXiv:1906.04711](https://arxiv.org/abs/1906.04711)) estimates the true two-year rate at about 36% rather than 45%. Base rates are therefore inflated; false positive and false negative rates are barely affected. `label = 1` also records a new arrest, not necessarily a new crime.

## `german_credit_classroom.csv`

1,000 rows, 300 of them test rows. Group sizes: female 310, male 690.

- Target `credit-risk`: `label = 1` means `good` credit risk. **`label = 1` is the favorable outcome**.
- Group column: `sex` (`female`, `male`), already in the file.
- Second attribute: age group, `under 25` vs `25+`. It is **not** a column in this file: build it yourself from `age`, e.g. in a spreadsheet `=IF(age<25, "under 25", "25+")`.
- **Small data:** only 1,000 rows, so about 300 test rows. Group gaps are noisy; don't read much into a difference of a few points.
- `sex` and `marital_status` are perfectly linked in this data: every `female` row has `marital_status = div/dep/mar`, and no `male` row does. Dropping `sex` from the model therefore doesn't hide it if `marital_status` stays in. The model drops both, but other proxies remain.

## `bank_classroom.csv`

2,000 rows, 600 of them test rows. Group sizes: 25-59 1,881, under 25 or 60+ 119.

- Target `deposit`: `label = 1` means the client subscribed to a term deposit (`yes`). **`label = 1` is the favorable outcome**.
- Group column: `age_group` (new): `25-59` when 25 ≤ `age` ≤ 59, otherwise `under 25 or 60+`.
- No second attribute.
