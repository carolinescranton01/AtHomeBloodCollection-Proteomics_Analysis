# KEGG protein function mapping to significantly-impacted proteins from models A, B, and C

After identification of significantly-impacted proteins across models A, B, and C, the protein IDs were exported into excel sheets (see code for the models). Within these sheets,
the data is originally structured with five columns (SampleID, log2FC, AveExpr, t, P.Value, adj.P.Val, B) and the number of rows is equal to the number of impacted proteins.

For KEGG analysis, the data was restructured to include 2 key rows - UniProt ID and Log2FC - and then any other rows necessary for grouping when plotting (ie for Supplemental figure
2, participant ID (A through D) was included as a third column. UniProt IDs were mapped to their function from the KEGG database using the enrichKEGG function (clusterprofiler). This
list of UniProt IDs and functions (KEGG category and subcategory/pathway) was exported into excel. Then, using the excel function VLOOKUP the two sets of data (UniProt IDs + L2FC
values and UniProt IDs + KEGG categories and subcategories) were matched to compile a data table with four columns - UniProt_ID, Category, Subcategory, and Log2FC.

This compiled data was reuploaded into R and plotted (see plots folder)
