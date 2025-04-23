# Linear modelling 

For all models, input data was excel sheets which contained rows corresponding to each sample (ie sample 1, sample 2, etc)
and columns corresponding to metadata (age, sex, pre-processing conditions like time, temperature, collection method) and
columns for each of the 7596 detected proteins. Cells were filled with either metadata (in the metadata colums) for the corresponding sample, or detection of proteins in relative fluoresence units. Models specified to only use protein RFU data, metadata was only included for organizational/informational purpose. Data was pre-sorted into new excel sheets before analysis to only include necessary samples (ie. if looking at participant A's data, participants B, C, and D were not included in the input data table). Design matrices were made as csv files, with the number of rows corresponding to the number of samples in the particular analysis (+1 for the header) and columns corresponding to the test variables (sample number (arbitrary, based on number of samples in analysis), sample ID, group (to group baseline samples together), participant, time, temperature). 

## Model A - Univariate models for individual samples vs baselines
Model A compared individual samples to the three immediately-processed Tasso-collected samples (from the same participant) to assess variation in the samples from the baseline. 20 models were created (there were five non-baseline samples for each of the four participants) with the structure RFU ~ B + group, where B is the intercept and group is a dummy variable, used to group the three baselines (with value 0) to the non-baseline sample of interest (value 1). Input data was structured as mentioned above in an excel sheet, and included all data from each participant individually - the specific sample of interest was specified in the code. Design matrices were the same, including all 8 samples from each individual and specific samples were specified in the code.

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