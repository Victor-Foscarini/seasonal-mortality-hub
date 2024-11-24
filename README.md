# Seasonal Mortality Hub

This is the repository of the most critical code of the seasonal mortality project that was part of  [InterSCity](https://interscity.org/) and [IME-USP's Systems group](https://www.ime.usp.br/en/computer-science-department/research/). The primary goal of this project was to analyze how to measure seasonal variation in mortality across diverse and heterogeneous contexts, using Brazil as a case study. The main part of the project is on the notebook [seasonal_variation_in_mortality_in_brazil.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/seasonal_variation_in_mortality_in_brazil.ipynb), where we compare seasonality across Brazilian states using several measures: the Excess Winter Death index (EWDi) and the Peak-to-Trough Ratio (PTR), both reproduced from scientific literature, as well as the Peak Season Excess Death index (PSEDi, referred to as EDi in our code) and the Excess Death with Variable Length index (PSEDVLi, referred to as EDVLi in our code), both of which we developed. The EWDi and the PSEDi are simple and we only rely on the counts of mortality, while for the PSEDVLi we rely on [Dynp’s algorithm](https://centre-borelli.github.io/ruptures-docs/code-reference/detection/dynp-reference/#ruptures.detection.dynp.Dynp) to detect the change points using dynamic programming before finding the period with more seasonality, and for the PTR we rely on [statmodel’s cyclic cubic spline algorithm](https://www.statsmodels.org/dev/generated/statsmodels.gam.smooth_basis.CyclicCubicSplines.html) to model the time series before obtaining the peaks and throughs.

We used healthcare data from [SIM-DATASUS](https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao), IBGE demographic data from [population estimation](https://www.ibge.gov.br/estatisticas/sociais/populacao/9103-estimativas-de-populacao) and [census](https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao), and historical climate data from [INMET's automatic stations](https://portal.inmet.gov.br/dadoshistoricos). Additionally, we extracted the ICD-10 codes from the [WHO website](https://icd.who.int/browse10/2019/en). The data processing code is divided into jupyter notebooks containing different research steps. We start with [extracting_datasus_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/extracting_datasus_data.ipynb), using an R API to get the mortality data for our study. Then, in [preprocessing_datasus_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/preprocessing_datasus_data.ipynb), we perform the necessary aggregations and transformations on the mortality data needed for the analysis, enriching it with demographic data. In [preprocessing_inmet_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/preprocessing_inmet_data.ipynb), we do similar preprocessing for climate data, aggregating it, and dealing with missing data. After that, the notebooks [seasonal_variation_in_mortality_in_brazil.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/seasonal_variation_in_mortality_in_brazil.ipynb) and [climate_and_mortality_data_in_brazil.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/climate_and_mortality_in_brazil.ipynb) contains the analyses themselves, respectively, of the various metrics used and their values across the country and the study of the climate factors influencing mortality in three strategic cities chosen from the results of the seasonality analysis.

The procedures of the data processing for the research are also available on my medium:

- [Extracting mortality data](https://medium.com/@victorfoscarini/unlocking-brazils-mortality-data-a-guide-to-extracting-sim-datasus-data-with-the-microdatasus-d7ea7bb1cc61)

- [Transforming mortality data](https://medium.com/@victorfoscarini/refining-brazils-mortality-data-a-guide-to-transforming-sim-datasus-data-with-standardization-to-13ed10d6f808)

- [Preprocessing climate data](https://medium.com/@victorfoscarini/processing-brazils-climate-data-aggregating-inmet-data-from-brazilian-state-capitals-912de4d55e32)

# How to run

The code was developed on Google Colab, making it the optimal platform for execution. However, it can also be run on a local machine using Jupyter Lab or Jupyter Notebook, or even on another cloud service. To do so, ensure you install the required libraries with the versions specified in the first code block of each notebook and update the path variables to suitable local paths.

# Contribution

Core Developer: Victor Foscarini Almeida

Supervisors: Profs. Fabio Kon, Raphael Carmago.

External advisor: Rudi Rocha
