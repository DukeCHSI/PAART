# PAART

# Overview
This repository contains the necessary files to start and execute the first version of Polyclonal Antibodies Avidity Resolution tool (PAART v1.0).

# Description
Polyclonal antibodies avidity resolution tool (PAART) is intended to probe the diversity in the avidity of polyclonal antibody (pAb) responses by analyzing the dissociation kinetics time courses of pAb-antigen interactions and resolve multiple dissociation rates contributing to the overall dissociation by fitting the dissociation time courses to a sum of exponentials decay model.
The PAART tool is currently built as an R markdown notebook, suited to run in R Studio environment. It has been tested under R version 4.1.2. The markdown notebook contains 3 main parts: importing data and data fitting preferences, data fitting for resolving multiple dissociation rates, and exporting fitted sensorgrams and statistics.
The resulting Excel and PDF report provide information on fitting quality, fitting residuals, response contribution from individual dissociation rate components, and details of parameter estimations. The user can select the model that best describes the dissociation curve with the minimal number of dissociation rate components.

# Getting Started
## Project files
* polyclonal simulated 6 choices sd.Rmd: main R markdown script for PAART analysis
* polyclonal simulated 6 choices sd.nb.html: webpage view of the R markdown script
* Simulated PAART Data.xlsx: example data set
* Simulated PAART Data windows.xlsx: example fitting preference table for the example data set
* PAART fit - stats.xlsx: statistical summary output after fitting the example data
* PAART fit - plots.pdf: PDF report output after fitting the example data
## Dependencies
Running this R markdown script requires following R packages: readxl, xlsx, plyr, grid, gridBase, gridExtra, gnm, and msm.
## Execution
“Simulated PAART Data windows.xlsx” and “Simulated PAART Data.xlsx” are provided as examples of a data set and fitting preferences, respectively, to accompany “polyclonal simulated 6 choices sd.Rmd”, the main R notebook for PAART analysis. As the file name indicates, PAART currently provides 6 different choices for parameter initialization of binding responses and dissociation rates, as well as the ability to calculate standard errors of parameter estimations. Appropriate explanations have been provided as annotations in the R notebook file.
The user can customize the fitting window for each dissociation curve as well as select a subset of the sensorgrams to analyze. During automatic fitting, PAART automatically generates 3 types of fits: 1, 2, or 3 dissociation rate components. Two or three components fit is typically adequate to describe the curvature in a sensorgram without over-parameterizing. For each sensorgram, 1, 2, and 3 component exponentials will each be independently fitted 100 times, then the fit with the lowest Akaike Information Criterion (AIC) score for each type will be selected for reporting. To increase efficiency, the code will first attempt to fit 20 times. If a minimum cannot be reached during any of the 20 attempts, the remaining 80 fits will be skipped. The maximum time (in seconds) allowed for each fit can be defined by the user (maximum time spent on each sensorgram is 3 × 100 × maximum time for a single fit).
“PAART fit - plots.pdf” and “PAART fit - stats.xlsx” are example output files generated using the aforementioned data set and fitting preferences.

# Version history
Version 1.0: initial release

# Help
If you need help or have suggestions, feel free to contact Kan Li via email at kl122@duke.edu. You may also communicate through GitHub Discussions.

# Author
Code was initially developed by Mike Dodds and subsequently optimized by Kan Li (kl122@duke.edu).
Other contributors to code development include Georgia D. Tomaras, S. Moses Dennison (moses.sekaran@duke.edu), Richard H.C. Huntwork and Rachel L. Spreng (rachel.spreng@duke.edu).

# License
This project is licensed under the GNU GPLv3 license. Please see LICENSE.md file for details.
