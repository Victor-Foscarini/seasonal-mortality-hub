# Seasonal Mortality Hub

This is the repository of the most critical code that I, Victor Foscarini Almeida, wrote during my master's degree, supervised by Fabio Kon and co-supervised by Raphael Carmago. The project was part of [InterSCity](https://interscity.org/) and [IME-USP's Systems group](https://www.ime.usp.br/en/computer-science-department/research/).

The project's primary goal was to analyze the seasonal variation in mortality in Brazil. Yet, we also expanded the area of the research to encompass the development of a new methodology for measuring seasonality and an analysis of the climate factors influencing mortality. We used healthcare data from [SIM-DATASUS](https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao), IBGE demographic data from [population estimation](https://www.ibge.gov.br/estatisticas/sociais/populacao/9103-estimativas-de-populacao) and [census](https://sidra.ibge.gov.br/pesquisa/censo-demografico/demografico-2022/universo-alfabetizacao), and historical climate data from [INMET's automatic stations](https://portal.inmet.gov.br/dadoshistoricos). Additionally, we extracted the ICD-10 codes from the [WHO website](https://icd.who.int/browse10/2019/en). 

The code is divided into jupyter notebooks containing different research steps. We start with [extracting_datasus_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/extracting_datasus_data.ipynb), using an R API to get the mortality data for our study. Then, in [preprocessing_datasus_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/preprocessing_datasus_data.ipynb), we perform the necessary aggregations and transformations on the mortality data needed for the analysis, enriching it with demographic data. In [preprocessing_inmet_data.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/preprocessing_inmet_data.ipynb), we do similar preprocessing for climate data, aggregating it, and dealing with missing data. After that, the notebooks [seasonal_variation_in_mortality_in_brazil.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/seasonal_variation_in_mortality_in_brazil.ipynb) and [climate_and_mortality_data_in_brazil.ipynb](https://github.com/Victor-Foscarini/seasonal-mortality-hub/blob/main/climate_and_mortality_in_brazil.ipynb) contains the analyses themselves, respectively, of the various metrics used and their values across the country and the study of the climate factors influencing mortality in three strategic cities chosen from the results of the seasonality analysis.

The procedures of the research are also available on my medium:

- [Extracting mortality data](https://medium.com/@victorfoscarini/unlocking-brazils-mortality-data-a-guide-to-extracting-sim-datasus-data-with-the-microdatasus-d7ea7bb1cc61)

- [Transforming mortality data](https://medium.com/@victorfoscarini/refining-brazils-mortality-data-a-guide-to-transforming-sim-datasus-data-with-standardization-to-13ed10d6f808)

- [Preprocessing climate data](https://medium.com/@victorfoscarini/processing-brazils-climate-data-aggregating-inmet-data-from-brazilian-state-capitals-912de4d55e32)
