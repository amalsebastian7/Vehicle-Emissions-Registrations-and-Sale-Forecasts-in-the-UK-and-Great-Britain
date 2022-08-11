# **Vehicle Emissions, Registrations and Sale Forecasts in the UK and Great Britain. (Comparing Electric Vehicles Against Petrol and Diesel Vehicles)**

# **Abstract**
This report considers data from the onset of the production of battery electric vehicles (BEVs) as well as the data on petrol and diesel vehicle registrations up till the present day. The analysis of this data brings to light the financial implications of the electric vehicle production, sales, as well as the future projections of those sales, thus making a recommendation on the viability of the electric vehicle manufacturing industries. This study examined data from different reliable sources to look at market developments and how that is affecting the sales and demand of battery electric vehicles in contrast to electric combustion engine vehicles (ICE) in the UK and Great Britain, the factors that led to those changes, and the likelihood of probable changes in the coming years. Additionally, comparison of CO2 emissions between electric and diesel/petrol cars was done.

Below are the stages of this analysis:

1. Data Collection and Importation: data of different vehicles produced as well as the cost and number of sales in the United Kingdom (UK) was explored and imported into the local Mathematica Notebook.
1. Data Pre-procession and Cleaning: this revolved around putting the imported data into a more suitable form for the analysis, especially the registrations of the electric vehicles in the UK as well as the petrol and diesel cars, and the emissions data. We transformed the unstructured and unclean data into structured and easy to use xlsx files that can be imported into Mathematica. 
1. Data Analysis Process: the analysis stage explored Mathematica functions that sought to train, visualize as well as check the accuracy of proposed models of interpretation. We used various functions and commands to clean and make the data more readable and comprehensible, as well as to remove parts of the data that would obstruct plotting. To visualize our findings, plotting was done using *DateListPlot*. Again, to compare our findings, a time series model was run with its accompanying time series forecasts.
1. The results: this demonstrates the outcome of the analysis performed on the datasets. This consisted of visualization graphs, comparative graphs as well as predictive and forecast model diagrams. The data acquired gave us an insight on future projections in the vehicle markets upon which we made our conclusions.
1. Conclusion: this is where we came to a suitable recommendation based on the results of our analysis. We concluded that battery electric vehicle production and sales are going to increase as opposed to that of diesel and petrol vehicles, due to various reasons, some of which are financial costs, environmental implications, as well as the eco-friendly nature of EVs.

# **Introduction**
As the world shifts towards more sustainable and renewable energies, there’s a global pressure on governments and countries to help aid in the battle against climate change. Populations endeavour to have as little of a carbon footprint as possible. A larger scale to achieve this goal has been to reduce Carbon Dioxide (CO2) emissions.

It is widely known that internal combustion engine vehicles, including petrol and diesel vehicles emit CO2 into the atmosphere as the fuel within is burned. This leads to various health complications, it causes the Earth’s temperature to rise, and increases its natural greenhouse effect. CO2 levels are higher today than ever, and with climate change and global warming, governments and companies are compelled to find solutions to these problems before it’s too late. [5]

Due to these reasons, vehicle manufacturing companies are responding to this call and doing their part by producing electric versions of their cars. New electric vehicle companies are growing (Lucid Motors, Rivian), and there’s a great competition between those companies to produce the most battery and software efficient cars with a user-friendly interface.

Electric vehicles are now being purchased in greater numbers than at any other time in history. They may initially cost more than traditional vehicles, but their maintenance cost, and the fact that they don’t require fuel to work, makes them cheaper which is a good return on investment in the long term. 

There are arguments that electric vehicles are not the answer, due to the non-renewable state of electricity, and the emission release in their line of production. While that may hold some truth, they are still a better trade off than diesel and petrol vehicles. This report aims to demonstrate the actual extent of those statements.

# **The Data Model, Source, And Explanation**
The data used in this report was collected from different sources. 

- Data on electric vehicles registered [1], and data on licensed ultra-low emission vehicles [2] was obtained from the United Kingdom Government website which contains information about vehicles registered or licensed in the UK or Great Britain through the years. This data helps track the amount of vehicles sold each year, whether by fuel type, model of the vehicle, tax class, etc.
- Data on the car registration by fuel type was obtained from the SMMT website (Society of Motor Manufacturers and Traders) which contains a wide range of vehicle information and reports about sales, forecasts, registrations, production, and manufacturer data among other things. [3]
- Per the knowledge garnered throughout the course, data prepossession that included selection of relevant data, data reduction as well as some wrangling were done using Wolfram Mathematica with immense help from our Data Science course text “A Hands-on Introduction to Data Science”. [4]

For the first part of the code; named “Electric vs Petrol & Diesel vehicle CO2 Emissions”, vehicle data was collected from unstructured data on the internet. We chose the top 10 best sellers for both diesel/ petrol , and electric vehicles in the UK [6], and we searched for each one of the cars’ CO2 emissions [7]-[24], then we turned that into an xlsx file by typing the data manually in Excel.

For the second part of the code; named “Battery Electric Vehicles (BEVs) Registered in the UK 2011-2021”, GOV.UK was used to download a dataset in the form of an xlsx file which shows the number of “licensed ultra-low emission vehicles” in the UK, and then from that dataset, the second sheet which shows only the Battery Electric Vehicles licensed in the UK from 2011 to 2021 was extracted into a different excel file in order to make it easier to import into Mathematica due to its large size. The file was renamed to “EVs Registered”.

After modifying the file, it was imported to Mathematica, then cleaned so that only the number of cars licensed and the respective years are visible. This was done so that it can be later used in a *DateListPlot.*

For the third part of the code; named “Petrol & Diesel Vehicles Registered in the UK 2011-2021”, the SMMT website was used to extract data about petrol and diesel vehicles registered in the UK between 2011 and 2021. 

Since the battery electric vehicle data was already downloaded from the GOV.UK website, only a part of the SMMT data (petrol and diesel vehicle registrations) was needed from this source. 

The graph found at the bottom of the webpage was used to determine the data mentioned above between September 2011 and September 2021. This graph can be manipulated to select the car registration type, and it can be filtered by month. The type selected was “Car Registrations By Fuel Type” and the month selected was “September” of each year as shown below.

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.001.png)

` `**Figure 1.** Car registrations by fuel type in the UK from September 2011 to September 2021

This data (excluding the AFV Car Registrations) was then manually typed in Excel so that it could be imported, since it can only be downloaded as a picture. The file name used was “Petrol and Diesel Registrations”.

For the fourth part of the code; named “Registered BEV, Petrol, and Diesel vehicles GB 1994-2020”, the GOV.UK website was used as well to download a dataset in the form of an xlsx file which shows the “Licensed cars by propulsion or fuel type” in Great Britain and the UK. 

Only Great Britain car registration data was chosen from this file because it dates back to 1994, as opposed to the UK data which only dates back to 2014, and since this data would be used later for a forecast, the more values that are used, the more accurate the result would be.

This file was then imported, cleaned, and it’s named “Registered V”.

# **Methodology** 
The data needed to be preprocessed, thus put into a simplified form to be used for analysis. The results from the data prepossessing gave us the data that was relevant to the purposes of our project. Firstly, a central location of our local computer was chosen to contain all acquired dataset upon which all pre-processing was done. 

All the data used in the Mathematica code was downloaded as, or transformed to an xlsx files so it can be structured and easier to deal with. All files were imported to Mathematica using the *Import* function.

**CASE 1: BEV, Petrol and Diesel Vehicle CO2 Emissions**

Extractions of the required data was done into separate excel files to facilitate a smooth cleaning process of the required data due to its large size. Since a chunk of the data had been extracted from the previous dataset, the second portion of the code was assessed to extract the petrol and diesel vehicle registrations from the SMMT data. 

After the xlsx file was imported, the function *TableForm* was used to make it readable. Then we eliminated the first row which contains text using the *Part* function.

For the petrol and diesel emission data, only the second column which contains their corresponding data was chosen and saved in a variable, and the same was done for the electric vehicle data where only column 4 was chosen.

The mean of CO2 emissions for both electric and petrol/ diesel vehicles was calculated using the *Mean* function, and only with the data of the 20 cars used in this case.

Using *ListLinePlot*, we plotted those two data and compared the results. Some plotting styles were used to make the graph easy to understand:

- *AxesLabel*, to label the y-axis
- *PlotLabel*, to title the plot
- *LabelStyle*, to make all the labels in the plot bold
- *ImageSize*, to change the plot size and make it bigger
- *PlotLegends*, to specify what each plot corresponds to
- The numbers on the x-axis were removed using the *Ticks* function since they were not necessary in this case.

**CASE 2: BEV, Petrol and Diesel Vehicle Registrations in the United Kingdom 2011 - 2021**

Registered Battery Electric Vehicles (BEVs) data from the first dataset file was imported. Afterwards, only the relevant columns of the year and number of vehicles registered were extracted. The original data had data for each quarter of the year to which only the last one was selected. This quarter represented the data of the entire year. 

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.002.png)

**Figure 2.** A sample of the number of BEVs registered at the end of each quarter of the year.

The main functions used in this case were:

- *Part* (the double brackets [[ ]]), to choose specific columns and eliminate others so that only the numeric values remain. Example: the command data[[All,3;;]] chooses the 3rd till the last column of the data; i.e. it eliminates the first two columns which contain text above the year values.
- *Transpose*, to assign each value to its respective year, and group them together in one list. Example: data//Transpose
- *StringSplit*, which was used to split the “Q4”, “Q3”, “Q2”, or “Q1” part of the year value from the actual year. 
- *Cases*, used to assign the *StringSplit* function to every value that has two attributes. 
- *Flatten*, to remove the extra set of parentheses from the list. (Added before *StringSplit*)
- *MapAt*, and *DateObject* to transform all the date strings into date objects that can be used in a *DateListPlot*.

**CASE 3:  A Comparison of BEV, Petrol and Diesel Car Registration in the UK 2011 -2021**

The data corresponding to the BEV, petrol, and diesel car registrations was cleaned and ready to plot, so *DateListPlot* was used again to plot those three sets of data together for comparison. 

Only the values from 2011 were used for the BEV registration *DateListPlot* instead of those from 1994. This is due to electric vehicles gaining popularity after 2011.

The functions: *PlotLabel*, *FrameLabel*, *LabelStyle*, *PlotLegends*, and *ImageSize* were used inside the *DateListPlot* function. The plot was clearly labelled to enhance visibility as well as communicate its purpose and structure. 

**CASE 4: The Forecast Models**

In this part, and after each set of data was plotted on its own and then in the same graph for comparison, a forecast of each vehicle type was done.

To determine whether the BEV, petrol, and diesel sales are going to increase or decrease in the future, the previous data was used to construct a time series forecast.

First, the *TimeSeries*, and *TimeSeriesModel* functions were used to make a series and a model of the data from 1994 to 2020 for petrol and diesel vehicles. There was an attempt to use the data from 1994 to do a time series forecast on BEV registration values, since a larger training data set gives a more accurate representation of the data behaviour and hence the more accurate the forecast would be, but since the values before 2011 were very small in comparison to now, the time series was not shown in the *DateListPlot*, and only the forecast could be seen. So the data from 2011 to 2021 was used for the BEV forecast. 

After that, the *TimeSeriesForecast* function was used to make forecasts up to 12 years for BEVs and petrol vehicles, and up to 7 years for the diesel vehicles (diesel vehicle values after 7 years become negative, and thus are inaccurate and could not be used).

The *Path* function was used in conjunction with the *TimeSeriesForecast* to show each value in a list.

The time series and time series forecasts of each vehicle type were plotted together in 3 separate graphs to show the available data of the vehicles and the forecasted data on the same plot.
# **Results**
**Case 1: BEV, Petrol and Diesel Vehicle CO2 Emissions**

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.003.png)

**Figure 3.** ListLinePlot of** CO2  emissions in petrol and diesel vehicles vs electric vehicles

There’s a clear difference between the emissions released by petrol and diesel vehicles, in comparison to that of electric vehicles. BEVs release 0 emissions, and PHEVs (hybrid-electric vehicles) release emissions but in low levels. 

According to our data, the average emissions of EVs is 15g/km, while petrol and diesel vehicles release on average 118.9 g/km of CO2

**Case 2A: BEV registrations in the UK 2011-2021** 

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.004.png)

**Figure 4.** DateListPlot of BEVs registered in the UK 2011-2021

The battery electric vehicle registrations in the UK are increasing drastically especially after 2019, which concludes that sales for these vehicles are growing.











**Case2B: Petrol and Diesel Vehicle Registrations in GB 1994-2020**

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.005.png)

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.006.png)

**Figure 5.** DateListPlots of petrol and diesel vehicle registrations in Great Britain 1994 – 2020

As opposed to the BEV plot, the plots in figure 5 show an apparent decrease in registrations for these vehicle types. The peak for the petrol vehicles was in the mid-2000s, then it saw an almost continuous drop to date, while the diesel vehicles kept rising until about 2015, then it started dropping as well.



**Case 3: A Comparison of BEV, Petrol and Diesel Car Registration in the UK 2011-2021**

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.007.png)

**Figure 6.** DateListPlot of BEV, Petrol and Diesel Car Registrations in the UK 2011 – 2021

Using the data from 2011 to 2021 for BEVs, petrol, and diesel vehicles, figure 6 shows the comparison done between each vehicle type when plotted together. This graph makes it easier to understand how the values perform with respect to each dataset. As previously explained, petrol and diesel vehicles seem to be underperforming as time passes while BEVs are still increasing. The plot showed the rise of the petrol and diesel vehicles up until the year 2015-2016, after which their decline is seen whereas the BEVs climb quite exponentially from the year 2018. In the year 2020 of the pandemic, where a general decline is seen, the BEV registrations still steadily climb.

**Case 4: The Forecast Models**	

1. BEV Time Series and Time Series Forecast

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.008.png)

**Figure 7.** DateListPlot of a time series and 12-year time series forecast of BEVs registered in the UK

According to figure 7, the forecast showed a very significant increase in BEV registrations, and it can be deduced that BEV sales would in fact increase in the upcoming 12 years.

1. Petrol and Diesel Vehicle Time Series and Time Series Forecast

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.009.png)

![](Images/Aspose.Words.f0e3fba0-89a0-4079-a870-9881559861b4.010.png)

**Figure 8.** DateListPlot of the time series and time series forecast of petrol vehicles up to 12 years and diesel 

vehicles up to 7 years.

For both plots, it can be noticed that according to the forecast data, the values of petrol and diesel vehicle registrations are likely to decrease dramatically in the upcoming 12 and 7 years respectively, in contrast to the BEV registrations.


# **Conclusion**
The purpose of this report was to study the environmental consequences of driving petrol and diesel vehicles versus that of the electric vehicles, as well as the financial and economic implications of the production and sales of battery electric vehicles using data science approaches. 

With several regions of the world making policies to move towards a greener world, shift to renewable energies, and reduce emissions, as well as the pressure on authorities to help reduce the rate of global warming and implement strategies to control this crisis, electric vehicles are expected to become much more of a common sight than they are now, as they are more eco-friendly than ICE vehicles, and are a better long-term investment.

Also, with increased taxes on petrol and diesel-based vehicles for their impacts on the environment and the health of individuals, as well as great incentives of owning electric vehicles, the future is pretty much guaranteed to move in the direction of electric vehicles ownership.

Analysis of this trajectory implies that it is worth the concentration of companies into the production of electric vehicles on a much larger scale, it is worth buying today, and it is the better choice for the environment.

# **Bibliography** 

*[1]	GOV.UK, “Licensed cars by propulsion or fuel type: Great Britain and United Kingdom.” https://www.gov.uk/government/statistical-data-sets/veh02-licensed-cars#registered-for-the-first-time (accessed Nov. 02, 2021).*

*[2]	GOV.UK, “Licensed ultra-low emissions vehicles (ULEVs) by local authority: United Kingdom.” https://www.gov.uk/government/statistical-data-sets/all-vehicles-veh01#ultra-low-emissions-vehicles-ulevs (accessed Nov. 09, 2021).*

*[3]	SMMT VEHICLE DATA, “CAR REGISTRATION BY FUEL TYPE.” https://www.smmt.co.uk/vehicle-data/car-registrations/ (accessed Nov. 09, 2021).*

*[4]	CHIRAG SHAH, A Hands-On Introduction to Data Science, 1st ed. CAMBRIDGE: CAMBRIDGE UNIVERSITY PRESS, 2020.*

*[5]      Climate.gov, “Climate Change: Atmospheric Carbon Dioxide” [https://www.climate.gov/news-features/understanding-climate/climate-change-atmospheric-carbon-dioxide*](https://www.climate.gov/news-features/understanding-climate/climate-change-atmospheric-carbon-dioxide)*

*[6]	MoneyShake, “Petrol vs. Electric: Visualising Your Car’s Emissions in Real Life.” https://www.moneyshake.com/shaking-news/miscellaneous/petrol-vs-electric-emissions-visualised (accessed Nov. 17, 2021).*

*[7]     FleetNews, “VW Golf mk8: prices, specifications and CO2 emissions” https://www.fleetnews.co.uk/news/manufacturer-news/2020/02/05/vw-golf-mk8-prices-specifications-and-co2-emissions*

*[8]   Carbuyer, “BMW 3 Series saloon – MPG, running costs & CO2” https://www.carbuyer.co.uk/bmw/3-series/mpg#:~:text=BMW%203%20Series%20MPG%20%26%20CO2&text=The%20latest%20version%20is%20claimed,with%20xDrive%20four%2Dwheel%20drive.*

*[9]   FleetNews, “Vauxhall Astra facelift: prices, specifications and CO2 emissions” <https://www.fleetnews.co.uk/news/manufacturer-news/2019/07/30/vauxhall-astra-facelift-prices-specifications-and-co2-emissions#:~:text=It%20develops%20145PS%20and%20emits,from%2094%20%2D120g%2Fkm>.*

*[10]     T.C. Harrison Ford, “Ford Focus EcoBoost Emissions Guide” [https://www.tch.co.uk/advice-centre/ford-models/ford-focus/ford-focus-road-costs/ford-focus-ecoboost-emissions/*](https://www.tch.co.uk/advice-centre/ford-models/ford-focus/ford-focus-road-costs/ford-focus-ecoboost-emissions/)*

*[11]    FleetNews, “Vauxhall Corsa: prices, specs and CO2 emissions” <https://www.fleetnews.co.uk/news/manufacturer-news/2019/06/26/vauxhall-reveals-new-corsa-with-petrol-and-diesel-engines>*

*[12]    Auto Express, “Ford Fiesta review - MPG, CO2 and running costs” [https://www.autoexpress.co.uk/ford/fiesta/mpg*](https://www.autoexpress.co.uk/ford/fiesta/mpg)*

*[13]    FleetNews, “Nissan Qashqai: prices, specification and CO2 emissions” [https://www.fleetnews.co.uk/news/manufacturer-news/2021/02/18/nissan-unveils-new-petrol-only-qashqai*](https://www.fleetnews.co.uk/news/manufacturer-news/2021/02/18/nissan-unveils-new-petrol-only-qashqai)*

*[14]    Europe’s Energy Portal, “Toyota CO2 Emissions” [https://www.energy.eu/car-co2-emissions/toyota.php*](https://www.energy.eu/car-co2-emissions/toyota.php)*

 *[15]   Auto Express, “Volkswagen Polo review - MPG, CO2 and running costs” [https://www.autoexpress.co.uk/volkswagen/polo/mpg*](https://www.autoexpress.co.uk/volkswagen/polo/mpg)*
 
*[16]    FleetNews, “New Renault Clio: prices, specifications and CO2 emissions” <https://www.fleetnews.co.uk/news/manufacturer-news/2019/08/07/new-renault-clio-prices-specifications-and-co2-emissions>*

*[17]   Driving Electric, “BMW 530e hybrid range, MPG, CO2 & charging” [https://www.drivingelectric.com/bmw/5-series/range*](https://www.drivingelectric.com/bmw/5-series/range)*

*[18]    Driving Electric, “Volkswagen Golf GTE range, MPG, CO2 & charging” [https://www.drivingelectric.com/volkswagen/golf/range*](https://www.drivingelectric.com/volkswagen/golf/range)*

*[19]    Driving Electric, “Mitsubishi Outlander PHEV (2013-2021) range, MPG, CO2 & charging” [https://www.drivingelectric.com/mitsubishi/outlander/outlander-phev/range*](https://www.drivingelectric.com/mitsubishi/outlander/outlander-phev/range)*

*[20]    BMW.co.uk, “The BMW Guide” [https://www.bmw.co.uk/content/dam/bmw/marketGB/bmw_co_uk/buying/business-corporate/company-car-drivers/bmw-guide-to-company-car-tax-april-2021-v3.pdf.asset.1619084658986.pdf*](https://www.bmw.co.uk/content/dam/bmw/marketGB/bmw_co_uk/buying/business-corporate/company-car-drivers/bmw-guide-to-company-car-tax-april-2021-v3.pdf.asset.1619084658986.pdf)*

*[21]    Electric Vehicle Database, “Nissan Leaf” [https://ev-database.uk/car/1106/Nissan-Leaf*](https://ev-database.uk/car/1106/Nissan-Leaf)*

*[22]    BMW.bm, “The i3” [https://www.bmw.bm/en/all-models/bmw-i/i3/2020/bmw-i3-technical-data.html*](https://www.bmw.bm/en/all-models/bmw-i/i3/2020/bmw-i3-technical-data.html)*

*[23]    Electric Vehicle Database, “Renault Zoe ZE50 R135” [https://ev-database.uk/car/1205/Renault-Zoe-ZE50-R135*](https://ev-database.uk/car/1205/Renault-Zoe-ZE50-R135)*

*[24]   Tesla, “Vehicle Incentives” [https://www.tesla.com/en_IE/support/incentives*](https://www.tesla.com/en_IE/support/incentives)*

*Glossary of Terms*

*ICEV: Internal Combustion Engine Vehicle*

*EV: Electric Vehicle*

*BEV: Battery Electric Vehicle*

*PHEV: Plug-in Hybrid Electric Vehicle*
