
# Texas Housing Market Analysis

## Purpose

Over the last couple of years, we have seen home prices rise in Texas. The main objective of this project is to analyze the current housing prices in Texas and determine what are some of the causes of the changes in prices.

## Methodology

##### Extraction:

It was determined that the data needed to perform this analysis would be:

- Housing prices - Zillow Research Data (https://www.zillow.com/research/data/). Zillow Home Value Index downloaded by zip code. This data was downloaded directly from the Zillow website into the Resources folder.
- Consumer Price Index (CPI) of the principal materials used in construction of residential homes (lumber, cement, steel, stone, brick). To obtain this, we used an API from The Federal Reserve of St. Louis.

##### Transformation:

As we extracted the data for the materials, we cycled through each one and appended to a dataframe composed of the columns: Commodity, date and values. The commodity was represented by its code and the date was the first day of the month.

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/commodity.PNG?raw=true" style="zoom:50%;" />

The housing data involved several transformation steps. First, we created a dataframe with the information from the CSV file and filtered it only for data points in Texas. 

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/housing1.PNG?raw=true" />

We then removed several columns. In the original file, each measurement date is a column and the rows identify the zip codes. In order to change this, pd.melt was used. The date recorded was also for the last day of the month. To change this to the first day of the month, we converted the date column to "DateTime" format and added a day.

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/housing2.PNG?raw=true"/>

Both these dataframes were then converted to CSVs and downloaded into the "Resources" folder.

##### Loading

After the both dataframes were created and transformed to the appropriate format, they were loaded into Tableau. Once they were loaded, an inner join was performed on dates to allow for a comparison of housing price vs commodity price on a given day

## Results

##### Housing Prices

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/MedianPriceLine.PNG?raw=true"/>

This chart shows how the average median price of homes in Texas has changed between 2000 and 2021. As can be seen, prices drop after the housing crisis of 2008 and start rising after 2012. In 2020, the rate at which these prices rise is significantly higher than in previous years as can be shown by the following chart.

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/DPrice.PNG?raw=true"/>

##### Commodities

After the evolution of the prices of the main four materials was graphed, it was seen that while the prices of  stone, brick and cement rise steadily, lumber and steel display a lot more volatility. The volatility of these can be seen specifically after 2020.

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/CommodityLegend.PNG?raw=true"/><img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/CommodityLine.PNG?raw=true"/>

##### Commodities vs Price

After comparing the CPI for each commodity vs the Housing Price, it was seen that the prices of these commodities do affect the housing prices as a positive correlation can be seen for all four materials.

<img src="https://github.com/simoncastellanos9/TexasHousingAnalysis/blob/main/Resources/HousingVsCommodity.PNG?raw=true"/>

To view these in an interactive manner, please visit the Tableau dashboard.(https://public.tableau.com/app/profile/simon5203/viz/TexasHousingAnalysis/TexasRealEstateCommodities)
