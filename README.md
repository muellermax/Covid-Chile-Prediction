# Covid-19 in Chile: Predict new cases and new fatalities per day with data about mobility and socioeconomic background


## Index

1. [About the project](#about)
2. [Related projects](#related-projects)
3. [Installation](#installation)
4. [Data](#data)
5. [About the Chilean socioeconomic indicators CASEN](#about-casen)
6. [About the Google mobility data](#about-mobility)


6. [Findings/Medium article](#findings)
7. [File descriptions](#file-description)
8. [How to interact](#interact)
9. [Acknowledgements](#thx)
10. [Author](#author)
11. [License](#license)

## <a class="anchor" id = "about">About the project</a>

In this notebook and the corresponding Medium blogpost, I analyzed the correlation between social indicators (such as poverty, distance from next pharmacy, income, etc.), Google mobility data and the number of confirmed Covid-19 cases and fatalities in Chile. 

After understanding the correlation, I built a Machine Learning model to predict the new cases per day for cases and fatalities caused by Covid-19 in Chile. 

Combining information from different data sources, I tried to find answers to the following questions: 
1. How is the situation within Chile and what differences are there in the different regions? 
2. How did mobility in the country change? 
3. Which correlation does exist between the socioeconomic indicators and the mobility data with the Covid-19 numbers? 
4. How does a Machine Learning model perform with socioeconomic and mobility data perform? 


## <a class="anchor" id="related-projects">Related projects</a>

* [Covid-19 Chile Dashboard](http://covid-chile-dashboard.herokuapp.com/)([GitHub repository](https://github.com/muellermax/Covid-19-Chile-Dashboard))
* [Medium article: How do social indicators drive the spread of Covid-19 in Chile?](https://medium.com/@muellermax1985/how-do-social-indicators-drive-the-spread-of-covid-19-in-chile-86b0affb0442) 
* [Medium article: Social Vulnerability and Covid-19 in the United States](https://medium.com/@muellermax1985/how-does-covid-19-affect-social-vulnerable-populations-in-the-us-11b1d9109876)([GitHub repository](https://github.com/muellermax/Covid-19-USA-social-vulnerability))


## <a class = "anchor" id="installation">Installation</a>

You simply fork or copy the code, the notebook includes directly reads in the Covid-19 data from its sources. The CASEN socioeconomic data has to be download separately (see below), as well as the Google mobility data (see below). 

Apart from this, the notebook runs on Python 3.7 and includes the libraries pandas, numpy, matplotlib, seaborn and sklearn.

## <a class="anchor" id = "data">Data</a>

This repository has been made with the help of many very important and helpful data sources: 

* The [Chilean Ministry of Social Development](http://www.desarrollosocialyfamilia.gob.cl/)provides a database with a wide range of socioeconomic indicators (Caracterización Socioeconómica Nacional, CASEN). You can download the [compressed file here](http://observatorio.ministeriodesarrollosocial.gob.cl/casen-multidimensional/casen/basedatos.php), I relied on the STATA data (unpacked, its about 630 MB); you will have to download it - I did not upload it to my repository. 
* For data about Covid-19 in Chile, the [Chilean Ministry of Science, Technology, Knowledge and Innovation](https://www.gob.cl/ministerios/ministerio-de-ciencia-tecnologia-conocimiento-e-innovacion/) and the [Chilean Data Observatory](http://dataobservatory.net/) provides [on GitHub more than 50 data products](https://github.com/MinCiencia/Datos-COVID19), including daily updated information about Covid-19 confirmed cases and fatalities in Chilean regions and districts. I included data about the Covid-19 cases per region ([data product 3](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto3)) and Covid-19 fatalities per region ([data product 14](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto14)).
* Finally, Google provides quite interesting mobility reports for a lot of countries. [On their website](https://www.google.com/covid19/mobility/) you can download the Global Mobility Report as CSV which includes the data for Chile and the Chilean regions. 

Please not that the data about cases and fatalities is updated daily.


## <a class="anchor" id="about-casen">About the Chilean socioeconomic indicators CASEN</a>

The CASEN database includes answers from more than 216.000 individuals from all regions in Chile to questions from the following topics: education, work, income, health, identity, housing and poverty. Each category includes around 30 different questions, just like "How far is the next pharmacy?"

The CASEN study is realized every two years, e.g. to track the percentage of families that are still living in poverty.


## <a class="anchor" id="about-mobility">About the Google mobility data</a>

As Google writes on the [mobility homepage](https://www.google.com/covid19/mobility/): 

> As global communities respond to COVID-19, we've heard from public health officials that the same type of aggregated, anonymized insights we use in products such as Google Maps could be helpful as they make critical decisions to combat COVID-19.

> These Community Mobility Reports aim to provide insights into what has changed in response to policies aimed at combating COVID-19. The reports chart movement trends over time by geography, across different categories of places such as retail and recreation, groceries and pharmacies, parks, transit stations, workplaces, and residential.

The Google mobility data show the change in percentage from a baseline (before Covid-19) in the amount of visitors in different categories, just like parks, retail, work etc. Only the "residential" category is different: It is measured in duration rather than visitors. 


## <a class="anchor" id="findings">Findings</a>

You can find my analysis and my findings in the [Medium blogpost](). 


## <a class="anchor" id="file-description">File description</a>
* Covid Chile Prediction.ipynb: The jupyter notebook that includes all the code. 
* Libro_de_Codigos_Casen_2017.pdf: A PDF that explains all indicators that appear in the CASEN database (Spanish)
* Media: A directory that includes the data (pictures and data) for the Medium blogpost

## <a class="anchor" id="interact">How to interact</a>

Every contribution is welcome. In the Medium blogpost, I have written some ideas and suggestions for further investigations. 


## <a class="anchor" id="thx">Acknowledgements</a>

Thanks to the [Chilean Ministry of Science, Technology, Knowledge and Innovation](https://www.gob.cl/ministerios/ministerio-de-ciencia-tecnologia-conocimiento-e-innovacion/) and the [Chilean Data Observatory](http://dataobservatory.net/) for providing daily updated data about Covid-19 on their [GitHub](https://github.com/MinCiencia/Datos-COVID19). 
Furthermore the socio-economic CASEN data, provided by the [Chilean Ministry of Social Development](http://www.desarrollosocialyfamilia.gob.cl/) was very useful and enabled me to make this investigation. I also relied on [WorldBank population data](https://data.worldbank.org/indicator/SP.POP.TOTL).
Thanks to Google for providing the [mobility reports](https://www.google.com/covid19/mobility/). 
I also read a lot of articles about time series prediction and would like to especially thank Varshita Sher, her article about ["Time Series Modeling using Scikit, Pandas, and Numpy"](https://towardsdatascience.com/time-series-modeling-using-scikit-pandas-and-numpy-682e3b8db8d1) was quite useful to get an understanding of time series prediction. Also a lot of my evaluation code (RMSE or the model selection etc.) was inspired by her code. 
Also very interesting was Mario Filhos description about ["How To Predict Multiple Time Series At Once With Scikit-Learn"](https://www.mariofilho.com/how-to-predict-multiple-time-series-with-scikit-learn-with-sales-forecasting-example/) which helped me to understand the concept of multiple time series prediction. 



## <a class="anchor" id="author">Author</a>
Maximilian Müller, Senior Business Development Manager for Smart Metering and Data Analytics in the Renewable Energy sector. Now diving into the field of Data Science.

## <a class="anchor" id="license">License</a>

Copyright 2020 Maximilian Müller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

From opensource.org
