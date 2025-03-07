# Project1_Group4
Project_1
Group Questions:

Which Country has the highest level of energy consumption and Greenhouse Emissions?
Do Forms of energy consumption have a direct effect on greenhouse gas emissions in countries?
Does the size of population influence the output of greenhouse gas emissions and energy consumption in general?
From data sets provided by the U.S Energy Information Administration: Opendata - U.S. Energy Information Administration (EIA). We will look for any trends in greenhouse emissions that coincide with yearly values of energy consumption.

Project Data Collection:

We will be utilizing Jupyter and VS code along with mods to isolate particular countries of interest which are relevant to our questions posted. We will be importing data from Pandas library in order to isolate and organize particular data that we intend to find. Such as; Country, Greenhouse Emissions, Fossil fuel Consumption, and Electricity Generation.




Analysis Group 4/Key points:

   -From the data provided,  China produces the largest amount of greenhouse gas emissions into the atmosphere.The data also shows us that China has the largest energy consumption out of any other country. 

-We can conclude from the data provided  that  energy consumption also results C02 emissions in the atmosphere.


-Despite its increase in consumption of all forms of energy, data provided shows a gradual decrease in overall greenhouse gas emissions in the United States. Records for other Countries such as China have shown a gradual increase in all categories of energy and greenhouse gas emissions. 

-Brazil has a similar yearly out put like the US. Greenhouse gas emissions are on a gradual decrease despite the increasing consumption of fossil fuel energy.

-Data provided would suggest that any form of energy consumption, especially fossil fuel consumption, influences greenhouse gas emissions in any country.
-Smaller countries or territories that have an overall smaller energy consumption output, such as the Bahamas, have a significantly smaller, or completely unrecorded number of emissions recorded.

-The United States hit an all-time low in all forms of energy consumption in 2020. COVID 19 epidemic.


Analyzing the Data in Python:

Before loading the dataset into Python, the following packages were installed/loaded:

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
from scipy import stats
from pprint import pprint
import seaborn as sns
from scipy.stats import linregress
from Adrian_config import eia_key
from pathlib import Path
import csv
import os

Inspecting the Data  

To find the energy consumption and CO2 emissions in China over the last 5 years the following data cleaning occurred:
All missing values were dropped from data set
Data was filtered by "primary_energy_consumption & greenhouse_gas_emissions, country & year
Non-country columns were dropped from the dataset
Data was filtered out by the last 5 years
The country with the highest CO2 and greenhouse gas emissions was pulled
Line-graph was created for C02 and greenhouse gas emissions

To compare the greenhouse gas emission China produces compared to other countries, a quick search was performed to see which countries have the highest population

Countries we wanted to analyze were pulled from the data set
An average was pulled for the average amount of greenhouse gas emissions in 2023 for each country
Bar-graph created to visualize this comparison




We filtered and selected data from the existing data frame; we filtered values and created a list of data/columns that will remain in the newly created DataFrame. We did this, so we can see the effect of size of population on the greenhouse gas emissions, energy consumption, as well as fossil fuel consumption. We chose 5 largest countries that weren't previously used, as well as five countries with a much smaller population so we can show the correlation. From this, we defined a list of countries we want to focus on for the analysis by creating a list of small/large countries

-Greenhouse gas emissions:
	-Extracting and Filtering Data:
		-We found the most recent year in both large and small countries datasets.
		-Filtered data to include only the most recent year.
		-Further filtered data to keep only the selected countries.
		-Extracted only the necessary columns (country, year, greenhouse_gas_emissions).
		-Displayed a Preview of the Data:
			-Created and Customizes a Dual Bar Chart:
				-Used matplotlib to create two side-by-side bar charts.

-Using a similar process, we did the same analysis for Fossil Fuel consumptions, as well as electricity generation. 

-Finally, we cleaned up data even further to remove any rows from the dataset where either the population or greenhouse gas emissions (greenhouse_gas_emissions) values are missing (NaN). We did this to ensure that only complete data is used for the regression analysis to prevent errors or misleading results.
	-Used SciPy's linregress function to perform linear regression.
	 - we got:
		slope: How much greenhouse gas emissions increase per unit increase in population.
		intercept: The expected greenhouse gas emissions when the population is zero.
		r_value: The correlation coefficient, indicating how strongly population and emissions are related.
		p_value: Significance level of the correlation.
		std_err: The standard error of the regression slope.

-We used r/r square-value to analyze how population affects greenhouse gas emissions in small countries.
	-Our results told us that even though larger population size does have a bog impact on greenhouse emissions, r squared value of0.35 tells us that there are other variables (like GDP, industrialization level, or renewable energy use) have an effect on its well.

-By doing this, we were able to see fossil fuel consumption, electricity consumption, and greenhouse gas emissions for large and small countries, from data extracted. This data was used for visualizing the results in side-by-side bar charts, line charts, as well.



[- BACK TO TOP -](#correlation-between-energy-consumption-and-gas-emissions)

---

## Analyzing Data

-China's Energy Consumption and Emissions
	-Leading Global Producer: China ranks as both the largest energy consumer and the largest emitter of greenhouse gases globally. With a rapidly expanding industrial sector, increasing energy demands, and rising urbanization, China's energy consumption has increased year-over-year.

-Direct Correlation: The data shows a direct correlation between rising energy consumption and escalating greenhouse gas emissions in China. As energy consumption increases (primarily through coal and natural gas), CO? emissions are directly impacted. The industrial sector's reliance on fossil fuels is a major contributing factor.

-Five-Year Growth: From 2018 to 2023, both energy consumption and CO? emissions in China saw a significant rise, following an upward trajectory linked to economic and industrial growth. This suggests that without a shift to greener technologies, China's emissions will likely continue to grow.


-United States' Emission Trends
	-Declining Emissions Despite Increased Fossil Fuel Use: Interestingly, while fossil fuel consumption in the United States increased during the last five years, greenhouse gas emissions have declined. This could be attributed to a shift towards cleaner energy sources like natural gas, along with improvements in energy efficiency and renewable energy capacity.

-2020 Anomaly: In 2020, the United States experienced a dramatic drop in both fossil fuel consumption and emissions. This decline coincides with the COVID-19 pandemic, which led to a reduction in industrial activity, transportation, and overall energy demand. This anomaly suggests that external factors (like pandemics) can significantly influence energy use and emissions.


-Brazil's Emission Patterns

-Trends Similar to the US: Brazil’s emissions trend over the last five years mirrors that of the U.S. with a gradual decrease in emissions, despite an increase in fossil fuel consumption. A closer look at Brazil’s energy mix shows increasing use of renewable energy sources like hydropower, wind, and solar, which could be contributing to reduced emissions even as fossil fuel consumption rises.

-Impact of 2020: Like the United States, Brazil saw a temporary dip in fossil fuel consumption in 2020, likely due to the global pandemic. However, the long-term trend points toward a gradual increase in energy consumption, particularly electricity generation, despite fluctuations in fossil fuel use.
Fossil Fuel Consumption

-Impact of 2020 on Fossil Fuel Use: 

-Both the United States and Brazil experienced sharp declines in fossil fuel consumption in 2020. This was largely due to the economic slowdown during the COVID-19 pandemic, which temporarily reduced industrial activity and transportation.

China's Steady Increase: In contrast to the U.S. and Brazil, China saw a steady increase in fossil fuel consumption year-over-year, even in 2020, signaling its continued industrial growth and energy demands despite global trends.


-Large vs. Small Energy Trend Analysis

-Larger Populations and Higher Energy Demand: Larger countries with bigger populations, such as the United States, China, and Russia, naturally demand more energy. However, their energy intensity (energy consumed per unit of GDP) and reliance on fossil fuels also play a critical role. While population size does have an effect, industrial activity and energy efficiency are also significant factors in determining a country’s total energy consumption and emissions.

-Per Capita Consumption and Emissions: Smaller countries, like Slovenia and Croatia, tend to have lower energy consumption per capita and emissions, especially if they prioritize energy efficiency and renewable energy sources. However, countries with large industrial sectors or growing energy demands, like Nigeria and Indonesia, may show rising consumption and emissions despite their relatively lower population size.

-Industrialization vs. Population Size: Industrialized countries like the U.S. and Japan have high energy consumption and emissions per capita, regardless of population size. Meanwhile, countries with developing economies, like Nigeria and Indonesia, may have lower per capita consumption but are rapidly increasing their emissions due to industrialization and urbanization.

Visualizations

-Bar Chart: Greenhouse Gas Emissions (Small vs. Large Countries)
This bar chart should visually demonstrate the difference in greenhouse gas emissions between a selection of small and large countries, focusing on the most recent year (2023). It will allow you to compare countries like China, the U.S., Brazil, Serbia, and Greece. This visual comparison can help reinforce the point about the scale of emissions and energy consumption in larger countries versus smaller ones.

-Electricity Generation Comparison (2018-2023)
This graph compares electricity generation across the years in both large and small countries. It will show whether energy consumption increases correlate with higher electricity generation. You can highlight any countries that may have diversified their energy sources (e.g., an increase in renewables in Brazil or a steady increase in China).

-Fossil Fuel Consumption Trends (2018-2023)
A line graph or bar chart showing fossil fuel consumption trends for both large and small countries. The graph will showcase the rise or fall in fossil fuel consumption in countries like the U.S., Brazil, China, and others, particularly during the COVID-19 year (2020).
 


## SUMMARY 

-The Impact of Population Size on Energy Consumption, Fossil Fuel Consumption, and Greenhouse Gas Emissions
The size of a country's population plays a significant role in its overall energy consumption, fossil fuel usage, and greenhouse gas emissions, though it is not the sole determining factor. Larger populations tend to have higher total energy demands due to increased residential, industrial, and transportation needs. However, the relationship between population size and these factors is influenced by other variables, such as the level of industrialization, the energy mix, and technological advancements.

-In countries with large populations, such as the United States, China, and Russia, energy consumption and emissions are typically higher due to the sheer scale of industrial activity and transportation needs. These countries also tend to have higher per capita emissions, as their energy-intensive industries and fossil fuel-based energy mix contribute significantly to greenhouse gas output. For example, the U.S. and China, despite having large populations, also show higher energy consumption due to their industrial sectors and reliance on fossil fuels, which correlate directly with rising greenhouse gas emissions.

-On the other hand, smaller countries with more energy-efficient industries and a greater reliance on renewable energy sources, like Slovenia and Croatia, tend to exhibit lower emissions per capita. Although these countries consume less energy overall, their transition to cleaner energy sources and smaller industrial footprints result in reduced emissions. This trend is particularly evident in countries that have made significant investments in renewable energy and energy efficiency technologies.

-However, even within smaller countries, the size of the population still affects energy consumption. While industrialized nations with smaller populations, like Japan, have high per capita consumption, the key factor remains the extent of industrialization and technological sophistication. Smaller, developing countries, such as Nigeria and Indonesia, are experiencing rapid urbanization and industrial growth, leading to increases in both energy consumption and emissions despite their relatively smaller populations. These countries' growing demand for energy, particularly fossil fuels, indicates that population size alone cannot fully explain energy and emissions patterns.

-Moreover, the global trend in 2020, where countries like the United States and Brazil saw significant reductions in fossil fuel consumption and emissions due to the COVID-19 pandemic, highlights the influence of external factors. Despite similar population sizes, the energy and emissions trends in these countries diverged, suggesting that factors such as economic activity, energy policy, and external shocks (like a global pandemic) play crucial roles in shaping energy consumption and emissions profiles.

-Overall, while population size does have a clear impact on a country's total energy consumption and emissions, it is the combination of industrial activity, energy mix, technological advancements, and external influences that ultimately determine the environmental footprint of a nation. The interaction between these factors underscores the need for tailored policies that address not only population growth but also the underlying drivers of energy consumption and emissions.



### Results and Key Findings:

-Global Energy Consumption: Some countries exhibit significantly higher energy usage than others.

-CO? Emissions and Energy Use: A strong correlation exists between high energy consumption and greenhouse gas emissions.

-Top Emission Contributors: China and other industrialized nations lead in both energy consumption and emissions.

-We can conclude from the data provided that energy consumption also results in C02 emissions in the atmosphere.



 Opportunities for future analysis:

-Our findings can be used for the purposes of:

-Policy Making: Helps governments and organizations create policies for sustainable energy use.

-Climate Change Mitigation: Identifies opportunities to reduce emissions through renewable energy adoption.

-Economic Analysis: Assesses how energy consumption trends impact economic development.

-Corporate Strategy: Provides insights for businesses looking to optimize energy use and reduce carbon footprints.

-Energy Efficiency Programs: Helps design programs to promote energy-saving initiatives.









