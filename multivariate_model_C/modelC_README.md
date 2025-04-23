# Code for Multivariate Model C

Multivariate model C is a multivariate linear model which considers the participant, time-to-processing, and storage temperature. 
It was used to assess the impact of extended time-to-processing and storage temperature on the proteome for the four participants simultaneously

The design matrix will has sample number, sample name, time, temperature, group (dummy variable to establish baseline), and participant (dummy variable to distinguish participants from each other).

Linear models were fitted and proteins with significantly-different detection in samples with extended time-to-processing or when stored at 4˚C (compared
to 20˚C) were identified. Proteins and their log2-fold change values were exported into an Excel document to be matched with their function (see KEGG_mapping)
