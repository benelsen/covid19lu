# covid19lu

"Best effort" data of COVID-19 in Luxembourg.

## [luxembourg.csv](luxembourg.csv)

Data is sparse, missing data points are not imputed or backfilled.

- date

  the time the information was published (generally), or is applicable to.
  A delay in reporting is to be expected
  
- cases

  diagnosed cases of COVID-19 (positive tests + clinical diagnoses)
  
- deaths

  fatalities due to COVID-19
  
- recovered

  Successful recoveries from COVID-19
  
- tests

  Cumulative tests up to this point
  
- tests_new

  Tests performed over the last day
  
- hospitalized

  patients currently hospitalized
  
- critical

  patients in critical care
  
- state

  `import` before local transmission has been detected, `local` thereafter
  
- source

  information about the source of the data
  
