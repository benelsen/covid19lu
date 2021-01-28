# Changelog

## 2021-01-28

- `timeline.csv`, `daily_sante.csv`, `weekly/weekly_sante.csv`:
  Sorry about all the changes to the vaccination data, I think we're now stable but I might add some additional columns.

  We now have:
  - `vaccination_doses_received`: 
        Doses received from the manufacturers, not much data available for this
  - `vaccination_doses_administered`
        Total doses administered independent of whether it's a single or multi-dose vaccine.
  - `vaccination_dose_1_administered` & `vaccination_dose_2_administered`
        How many 1st/2nd doses have been administered. Not yet sure what data will be available once single-dose vaccines are approved and used. Might be best to only count them in total doses, but leave them out of `dose_1`/`dose_2` in order to keep track of dropouts from multi-dose schedules.
  - `vaccination_persons_complete`
        How many persons have completed either received a single dose vaccine or all doses of a multi-dose vaccine.

  Every column has `_new` variants with the daily increases.

## 2021-01-26

- `timeline.csv`, `daily_sante.csv`:
    Going to add and rename some columns for vaccinations this later week to make things a little clearer.

## 2021-01-24

- `vaccination/schedule.csv`: 
    renamed `received` to `reception_confirmed`

## 2021-01-23

- `of_date/*/*_age.csv`: 
    All files having breakdowns by age will be removed from the `of_date` folders (i.e. `active_age.csv`, `deaths_age.csv`, `hospital_intensive_age.csv`, `hospital_normal_age.csv`) shortly.
    They don't have any use as the main files contain the same data and there no source for past values.

