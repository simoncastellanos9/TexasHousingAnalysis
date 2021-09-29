
# Texas Housing Market Analysis

### Purpose

Over the last couple of years, we have seen home prices rise in Texas. The main objective of this project is to analyze the current housing prices in Texas and determine what are some of the causes of the changes in prices.

### Methodology

##### Extraction:

It was determined that the data needed to perform this analysis would be:

- Housing prices - Zillow Research Data (https://www.zillow.com/research/data/). Zillow Home Value Index downloaded by zip code. This data was downloaded directly from the Zillow website into the Resources folder.
- Consumer Price Index (CPI) of the principal materials used in construction of residential homes (lumber, cement, steel, stone, brick). To obtain this, we used an API from The Federal Reserve of St. Louis.

##### Transformation:

As we extracted the data for the materials, we cycled through each one and appended to a dataframe composed of the columns: Commodity, date and values. The commodity was represented by its code and the date was the first day of the month.

The housing data involved several transformation steps. First, we created a dataframe with the information from the CSV file and filtered it only for data points in Texas. We then removed several columns. In the original file, each measurement date is a column and the rows identify the zip codes. In order to change this, pd.melt was used. The date recorded was also for the last day of the month. To change this to the first day of the month, we converted the date column to "DateTime" format and added a day.

Both these dataframes were then converted to CSVs and downloaded into the "Resources" folder.

##### Loading






