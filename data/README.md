# Data Folder

This folder contains the datasets used in the **Bike Sharing Demand Prediction** project.

---

### 1. `hour_sample.csv`
- A small sample of the UCI Bike Sharing dataset for quick testing.
- Contains hourly bike rental data with the following columns:
  - `instant` : record index
  - `dteday` : date
  - `season` : 1 = spring, 2 = summer, 3 = fall, 4 = winter
  - `yr` : year (0 = 2011, 1 = 2012)
  - `mnth` : month (1–12)
  - `holiday` : whether the day is a holiday
  - `weekday` : day of the week (0 = Sunday, 6 = Saturday)
  - `workingday` : whether day is neither weekend nor holiday
  - `weathersit` : 1 = clear, 2 = mist/cloudy, 3 = light rain/snow, 4 = heavy rain/snow
  - `temp` : normalized temperature in Celsius
  - `atemp` : normalized “feels like” temperature
  - `hum` : normalized humidity
  - `windspeed` : normalized wind speed
  - `casual` : count of casual users
  - `registered` : count of registered users
  - `cnt` : total bike rentals (target variable)

---
