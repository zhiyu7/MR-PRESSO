# MR-PRESSO
MR-PRESSO (**Mendelian Randomization Pleiotropy RESidual Sum and Outlier**) is a R package to use a unified framework that allows for the evaluation of pleiotropy in a standard Mendelian Randomization model.

The method extends on previous approaches that utilize the general model of multi-instrument MR on summary statistics. MR-PRESSO has three components, including:
1. detection of pleiotropy (*MR-PRESSO global test*)
2. correction of pleiotropy via outlier removal (*MR-PRESSO outlier test*)
3. testing of significant distortion in the causal estimates before and after MR-PRESSO correction (*MR-PRESSO distortion test*).

### 1. Install and load MR-PRESSO
To install the latest development builds directly from GitHub, run this instead:
```r
if (!require("devtools")) { install.packages("devtools") } else {}
devtools::install_github("rondolab/MR-PRESSO")
```
Load MR-PRESSO 
```r
library(MRPRESSO)
```

### 2. Example
```r
# Load a simulated toy dataset
data(SummaryStats)

# Run MR-PRESSO global framework
mr_presso(BetaOutcome = "Y_effect", BetaExposure = "E1_effect", SdOutcome = "Y_se", SdExposure = "E1_se", OUTLIERtest = TRUE, BIAStest = TRUE, data = SummaryStats, NbDistribution = 100,  SignifThreshold = 0.05)
```
