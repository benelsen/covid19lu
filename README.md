# covid19lu

"Best effort" data of COVID-19 in Luxembourg.

## [luxembourg.csv](luxembourg.csv)

Data is sparse, missing data points are not imputed or backfilled.

- `date`

  the time the information was published (generally), or is applicable to.
  A delay in reporting is to be expected

- `cases`

  diagnosed cases of COVID-19 (positive tests + clinical diagnoses)

- `deaths`

  fatalities due to COVID-19

- `recovered`

  Successful recoveries from COVID-19. (It is unclear if this refers to all recovered COVID-19 diagnosed cases or only those that have been hospitalized.)

- `tests`

  cumulative tests up to this point

- `tests_new`

  tests performed over the last day

- `hospitalized`

  patients currently hospitalized

- `critical`

  patients in intensive care

- `state`

  `import` before local transmission has been detected, `local` thereafter

- `source`

  information about the source of the data

## [timeline.csv](timeline.csv)

- `days_1c`, `days_10c`, `days_100c`, `days_10d`

  Days since first, 10th, 100th case, 10th death

- `cases_new`, `deaths_new`

  change in cases/deaths from the previous datapoint

- `cases_dT`, `deaths_dT`

  days since the previous change in cases/deaths

- `cases_new_s`

  three day equal weighted moving average of new cases. Scaled to sum to current total of cases.

- `cases_growth`

  daily increase in cases `a` (`N[t] = (1 + a)^k * N[t-k]`)

- `cases_growth_s`

  same as `cases_growth` but using the moved average of new cases

- `cases_doubling_d`, `cases_doubling_d_s`

  Days for cases to double assuming a daily growth of `cases_growth` and `cases_growth_s` respectivly
