# Catch_Inequality_Steelhead
Code for the manuscript: "Quantifying catch inequality in recreational fisheries: a case study with California steelhead (Oncorhynchus mykiss)". S.R. Sanchez, C. Schneider, N.A. Fangue, and R.L. Rypel. 

Corresponding author/code: Sophia R. Sanchez, sosanc@ucdavis.edu

CONTENT DESCRIPTION:

Steelhead_Script_Main.Rmd is the main code file, and requires the following data sets to run. 

SRRC_Dataset.csv is an aggregated dataset comprising California Department of Fish and Wildlife (CDFW) Steelhead Report and Restoration Card (SRRC) angler data from the following years: 2012 - 2022. Report cards failing to report critical data (e.g. any fish count, location code) are removed. The dataset has been summarized such that anglers are represented once per location code, per year; that is, fish counts and hours fished are summed. Columns detailing demographic data (e.g. "Date of Birth" and "Physical Zip Code") and repetitive information (e.g. "Complete Data?") removed for clarity. All other columns included. For full dataset inquires, contact the CDFW SRRC Program staff: SHcard@wildlife.ca.gov

breakpoints2000.csv is the output of the computationally-demanding power analysis for loop. Power analysis process: for each basin-year combination, all cards are subset into groups of 25; cumulative Gini calculated for each bin; estimated breakpoint (sample size where Gini plateaus) for simulation output. Loop excludes NAs (which occurs when there are too few cards to produce a breakpoint in that iteration) to avoid termination. Not all locations will have the same number of iterations, hence running 2000 simulations to ensure each basin-year combination has successful 500 iterations to randomly select. breakpoints2000_Hatchery_ALL.csv and breakpoints2000_Wild_ALL.csv are the analogous outputs for only hatchery catch and wild catch, respectively. 

USGS_Flow_Data.csv is an aggregated annual flow (cfs) data set via the lowermost United States Geological Survey flow gauge for 11 basins across California across the study period (2012-2022). Basins and associated gauge ID provided in Supplemental Table S1. USGS_Flow_Monthly.csv is an analogous dataset, on a monthly scale instead of annual averages.
