# covid19lu

"Best effort" data of COVID-19 in Luxembourg.

The dataset is compiled from official and media reports. The government now publishes [daily update](https://coronavirus.gouvernement.lu/en.html).

Columns can and will be added, changed and reordered as data becomes available or changes.


## [luxembourg.csv](luxembourg.csv)

This file contains sparse data. Multiple entries per days can be present if information is made public at different times or via different sources. Only data points published by that source are included — missing data are not imputed or back-filled from other entries. **For a condensed datset see [timeline.csv below](#timelinecsv).**

- `date_published`

  the time the information was published
  
- `date`

  the day the information applies to (generally). The government never explicitly specified what period the data refers to, but indications are that they now refer to the previous day.

- `cases`

  diagnosed cases of COVID-19 (positive tests + clinical diagnoses)

- `deaths`

  fatalities due to COVID-19

- `recovered`

  Successful recoveries from COVID-19. Before April 3 only the number of patients discharged from hospitals was know. For persons diagnosed with COVID-19 that do not need to be hospitalised the criteria for recovery is two weeks elapsed since the initial diagnosis and 48h after no symptoms are preset, whichever is longer.

- 'active'

  Still active cases of COVID-19 (cf `recovered`)

- `tests`

  cumulative tests up to this point

- `tests_new`

  tests performed over the last day

- `hospitalized`

  patients currently hospitalised

- `critical`

  patients in intensive care

- `discharged`

  cumulative number of patients discharged from hospital

- `cases_mean_age`

  mean age of diagnosed cases

- `cases_ratio_female`

  proportion of female persons of all diagnosed cases

- `deaths_median_age`,  `deaths_mean_age`, `deaths_min_age`, `deaths_max_age`

  median/mean/minimum/maximum age of patients succumbed to COVID-19

- `deaths_ratio_female`

  proportion of female persons of all deaths

- `deaths_ratio_hospital`

  proportion of deaths that occured in hospitals

- `deaths_transfer`

  patients transferred to Luxembourg that died. (Not included in the `deaths` column of this data set.)

- `critical_transfer`

  patients transferred to Luxembourg that are in intensive care. (Not included in the `critical` column of this data set.)

- `hospitalized_transfer`

  patients transferred to Luxembourg that are hospitalized. (Not included in the `hospitalized` column of this data set.)

- `state`

  `import` before local transmission has been detected, `local` thereafter

- `source`

  information about the source of the data

## [timeline.csv](timeline.csv)

This file has been condensed to a single entry per day and contains additional columns.

- `hospitalized`, `critical`

  includes patients transferred to Luxembourg (`critical_transfer`) from neighbouring regions to accurately reflect hospital bed occupation

- `cases_new`, `deaths_new`, `recovered_new`, `active_change`, `hospitalized_change`, `critical_change`, `discharged_new`, `hospitalized_transfer_change`, `critical_transfer_change`, `deaths_transfer_new`

  change in cases/deaths/hospitalisations from the previous day. If the previous day's numbers were unknown the change is undetermined and considered a missing value.

- `cases_dT`, `deaths_dT`

  days since the previous change in cases/deaths

- `cases_growth`, `deaths_growth`

  daily increase in cases/deaths `g` (`N[t] = (1 + g)^k * N[t-k]`)

- `cases_doubling_d`, `deaths_doubling_d`

  days for cases/deaths to double assuming a daily growth of `cases_growth`/`deaths_growth`

- `tests_new_ratio_positive`

  proportion of positive tests among new tests. Assumptions: the number of tests conducted and the number of new cases refer to the same time span, all new cases stem from positive tests

- `days_1c`, `days_10c`, `days_100c`, `days_10d`

  Days since first, 10th, 100th case, 10th death

## [deaths_age_distribution.csv](deaths_age_distribution.csv)

Age distribution of persons that died from COVID-19.

The data includes one line for every age group per day. These are proportions of all deaths not new ones.

- `data`

  date on which the information was published

- `age_group`

  name for the age group

- `min_age`, `max_age`

  lower and upper bound of the age group. (Lower bound inclusive, upper bound exclusive)

- `proportion`

  proportion of total deaths occuring in this age group
