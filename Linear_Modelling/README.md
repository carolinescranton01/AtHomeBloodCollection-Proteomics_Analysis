# Linear modelling 

## Model A - Univariate models for individual samples vs baselines

## Model B - Multivariate model to assess impact of collection type
Multivariate model B assess the impact of collection method (capillary, using Tasso+ kits, versus venous, collected via standard phlebotomy procedures) on the proteome, considering all
four participants at once. The model structure is RFU ~ B + Type + Participant, where B is the intercept, Type is the collection method, and Participant is the participant (A through D).

Protiens with significantly-impacted detection levels in the venous sample (compared to the three capillary baseline samples) were exported into an Excel sheet (as UniprotIDs with 
log2-fold change values and p values) for further analysis of the KEGG pathways of these proteins

## Model C - Multivariate model to assess impacts of time and temperature
Multivariate model C is a multivariate linear model which considers the participant, time-to-processing, and storage temperature. 
It was used to assess the impact of extended time-to-processing and storage temperature on the proteome for the four participants simultaneously

The design matrix will has sample number, sample name, time, temperature, group (dummy variable to establish baseline), and participant (dummy variable to distinguish participants from each other).

Linear models were fitted and proteins with significantly-different detection in samples with extended time-to-processing or when stored at 4˚C (compared
to 20˚C) were identified. Proteins and their log2-fold change values were exported into an Excel document to be matched with their function (see KEGG_mapping)