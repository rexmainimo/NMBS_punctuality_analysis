🚆 NMBS Train Punctuality Analysis (2024–2025)
This repository contains analyses of NMBS train punctuality based on open data. The goal is to compute a more realistic picture of train delays and identify stations where trains typically gain or lose time.

✅ Question 1 – Realistic Monthly Punctuality vs. NMBS Metrics
Objective:
Compute a realistic representation of train delays using actual vs. scheduled departure times, and compare it to NMBS’s official punctuality rate.

Approach:

Merged departure date and time into full timestamps.

Calculated delay in minutes:
delay = actual_departure - scheduled_departure

A train is considered on time if the delay is under 6 minutes.

Compared this to NMBS’s official and "neutralized" punctuality data (from monthly archives).

Findings (May 2025):

Official NMBS Punctuality: 91.51%

Realistic Punctuality (based on actual departure times): 87.87%

Difference: −3.65 percentage points

Visualized delays per route and station (average delay, median, % on time)

📉 Question 2 – Where Is Time Gained or Lost?
Objective:
Identify the 5 stations where trains most often gain or lose time during stops.

Approach:

Used all 2024 train data from monthly archives.

Computed delay change:
DELAY_CHANGE = delay at departure - delay at arrival

Grouped by station to find average delay change.

Positive = time lost; Negative = time gained.

Filtered for valid rows (no missing values).

Results:

Top 5 Stations Where Most Time is Lost:

Station	Avg. Time Lost (min)
MERELBEKE-CENTRAAL	707.00
TURNHOUT	464.00
ANTWERPEN-NOORD-BUNDEL A1	444.07
RONET-P.E.	181.00
MONTZEN	175.00

Top 5 Stations Where Most Time is Gained:

Station	Avg. Time Gained (min)
VORST-RIJTUIGEN-DIENSTPERRON	-70.00
BOOM	-48.71
OUDENAARDE	-39.19
EINE	-31.25
WONDELGEM-BUNDEL	-31.17

Visualization:
A bar chart highlights stations with most time gained (green) vs. lost (red), including a custom legend.
