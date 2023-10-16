# abcd-prepost-cbcl-rsi

This repository contains scripts used to preprocess and analyze data used in the manuscript "Disrupted maturation of white matter microstructure after concussion is associated with internalizing behavior scores in female children". Below is the order in which the scripts were run.

**1. create_groups.Rmd**

This script was used to extract the concussion and comparison groups with baseline and follow-up behaviour and MRI information. To continue script from line 714, the output from _mri_qc.Rmd_ is needed.

**2. mri_qc_Rmd**

This script is the imaging data quality control (QC). It checks if participants have completed QC, received a passing score, have restriction spectrum image (RSI) data available, and are not diagnosed with any neurological conditions. The output from this script is used to complete group extraction in _create_groups.Rmd_.

**3. ses_imputation.Rmd**

For the participants extracted from the scripts above, this script checks for missing data in the following variables: sex, pubertal status, total combined family income, highest parental education, ethnicity, scanner, and medications including anticonvulsants, antipsychotics, stimulants, and antidepressants.

**4. behaviour_analyses.Rmd**

This script contains the analyses comparing change in child behaviour checklist (CBCL) scores between concussion and comparison groups.

**5. check_scanner.Rmd**

Some participants were scanned on different scanners at follow-up than at baseline. This script checks which participants have different scanners. Only those that were scanned on the same scanners at both timepoints were used for the MRI analyses. 

**6. combat_harmonization.Rmd**

First, this script calculates change scores (change in neurite density between baseline and follow-up) in participants with MRI data available and that were scanned on the same scanner (output of script above). Second, this script performs comBat harmonization using `neuroCombat`.

**7. brain_behaviour_analyses.Rmd**

This script contains the analyses comparing chane in neurite density between concussion and comparison groups.
