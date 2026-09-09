# Step Count Analysis: Bootstrap Resampling and Historical Simulation

# Overview

I collected data showing how many steps hospitality workers (my colleagues) have done on a Saturday.
The data was collected via a Google form shared on the work group chat, where 19 people replied
anonymously. This is a small sample, making a good dataset to explore how much uncertainty a small 
sample carries using:
Bootstrap resampling - repeatedly resampling the data (with replacement) to estimate how much a
statistic might change if a different sample of colleagues was surveyed. 
Historical Simulation - Doesn't assume a distribution, rather it reads the risk threshold directly 
from empirical data. "What step-count level marks off the least active 10% of colleagues?"

# Structure

step_count_analysis.py     # main analysis: descriptive stats, bootstrap
                             # confidence interval, parametric CI comparison,
                             # Historical Simulation
outliers_iqr.py            # separate script: IQR 
                           # runs independently of step_count_analysis.py
Setup:
pip install matplotlib
python step_count.py
produces step_count_histogram.png 

# Key Findings: 
- Mean step count: 12,353 (95% bootstrap CI: [9,399, 15,239]
- The bootstrap and confidence intervals agree closely with each other, suggesting the normal
distribution holds, despite the small sample size. 
- Historical Simulation: the bottom 10% of colleagues recorded fewer than 1,573 steps,
with this estimate carring wider uncertainty than the mean since tail estimates from a small sample
are less reliable. The confidence interval on the 10th percentile is much wider than the one on the 
mean, as a small sample tells you more about its centre than its tails. 

# Limitations:
- The small sample size means conclusions should be taken as a suggestion rather than precise.
- It doesn't take into account any steps recorded that an inidividual may have done before or after
their shift. 
