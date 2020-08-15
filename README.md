# How do social indicators drive the spread of Covid-19 in Chile?


## Index

1. [About the project](#about)
2. [Related projects](#related-projects)
3. [Installation](#installation)
4. [Data](#data)
5. [About the Chilean socioeconomic indicators CASEN](#about-casen)
6. [Findings/Medium article](#findings)
7. [File descriptions](#file-description)
8. [How to interact](#interact)
9. [Acknowledgements](#thx)
10. [Author](#author)
11. [License](#license)

## <a class="anchor" id = "about">About the project</a>

In this notebook and the corresponding Medium blogpost, I analyzed the correlation between social indicators (such as poverty, distance from next pharmacy, income, etc.) and the number of confirmed Covid-19 cases and fatalities in Chile. 

Combining information from different data sources, I tried to find answers to the following questions: 
1. How is the situation in Chile compared to other countries worldwide?
2. How is the situation within Chile, comparing the different regions and districts?
3. Which correlation does exist between Covid-19 cases and fatalities in the most and less affected Chilean districts? 
4. How does a regression model trained on social indicators perform?


## <a class="anchor" id="related-projects">Related projects</a>

* [Covid-19 Chile Dashboard](http://covid-chile-dashboard.herokuapp.com/)([GitHub repository](https://github.com/muellermax/Covid-19-Chile-Dashboard))
* [Social Vulnerability and Covid-19 in the United States](https://medium.com/@muellermax1985/how-does-covid-19-affect-social-vulnerable-populations-in-the-us-11b1d9109876)([GitHub repository](https://github.com/muellermax/Covid-19-USA-social-vulnerability))


## <a class = "anchor" id="installation">Installation</a>

You simply fork or copy the code, the notebook includes links to all data sources *minus one*: The socioeconomic CASEN indicators for the Chilean districts (see below) have to be downloaded seperately. 

A part from this, the notebook runs on Python 3.7 and includes the libraries pandas, numpy, matplotlib, seaborn and sklearn.

## <a class="anchor" id = "data">Data</a>

This repository has been made with the help of many very important and helpful data sources: 

* The [Chilean Ministry of Social Development](http://www.desarrollosocialyfamilia.gob.cl/)provides a database with a wide range of socioeconomic indicators (Caracterización Socioeconómica Nacional, CASEN). You can download the [compressed file here](http://observatorio.ministeriodesarrollosocial.gob.cl/casen-multidimensional/casen/basedatos.php), I relied on the STATA data (unpacked, its about 630 MB); you will have to download it - I did not upload it to my repository. 
* For data about Covid-19 in Chile, the [Chilean Ministry of Science, Technology, Knowledge and Innovation](https://www.gob.cl/ministerios/ministerio-de-ciencia-tecnologia-conocimiento-e-innovacion/) and the [Chilean Data Observatory](http://dataobservatory.net/) provides [on GitHub more than 50 data products](https://github.com/MinCiencia/Datos-COVID19), including daily updated information about Covid-19 confirmed cases and fatalities in Chilean regions and districts. I included data about the Covid-19 cases per region ([data product 3](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto3)), Covid-19 fatalities per region ([data product 14](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto14)), Covid-19 cases per district ([data product 1](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto1)) and Covid-19 fatalities per district ([data product 38](https://github.com/MinCiencia/Datos-COVID19/tree/master/output/producto38))
* To compare the situation in Chile to other countries, I relied on the data of the [Center for Systems Science and Engineering (CSSE) at John Hopkins University and their Covid-19 GitHub repository](https://github.com/CSSEGISandData/COVID-19).
* Finally I used [WorldBank population data](https://data.worldbank.org/indicator/SP.POP.TOTL) to calculate the cases per 100,000 habitants.

Please not that all the data sources (WorldBank data not) are updated daily, which is way my findings and plots in the Medium blogpost may differ from when you are running the notebook. 


## <a class="anchor" id="about-casen">About the Chilean socioeconomic indicators CASEN</a>

The CASEN database includes answers from more than 216.000 individuals from all regions in Chile to questions from the following topics: education, work, income, health, identity, housing and poverty. Each category includes around 30 different questions, just like "How far is the next pharmacy?"

The CASEN study is realized every two years, e.g. to track the percentage of families that are still living in poverty.

## <a class="anchor" id="findings">Findings</a>

You can find my analysis and my findings in the [Medium blogpost](https://medium.com/@muellermax1985/how-do-social-indicators-drive-the-spread-of-covid-19-in-chile-86b0affb0442). 


## <a class="anchor" id="file-description">File description</a>
* Chile Capstone.ipynb: The jupyter notebook that includes all the code. 
* API_SP.POP.TOTL_DS2_en_csv_v2_1217749.csv: A csv with the World Bank population data
* Libro_de_Codigos_Casen_2017.pdf: A PDF that explains all indicators that appear in the CASEN database (Spanish)
* Media: A directory that includes the data (pictures and data) for the Medium blogpost

## <a class="anchor" id="interact">How to interact</a>

Every contribution is welcome. In the Medium blogpost, I have written some ideas and suggestions for further investigations. 


## <a class="anchor" id="thx">Acknowledgements</a>

Thanks to the [Chilean Ministry of Science, Technology, Knowledge and Innovation](https://www.gob.cl/ministerios/ministerio-de-ciencia-tecnologia-conocimiento-e-innovacion/) and the [Chilean Data Observatory](http://dataobservatory.net/) for providing daily updated data about Covid-19 on their [GitHub](https://github.com/MinCiencia/Datos-COVID19). Also thanks to the [Center for Systems Science and Engineering (CSSE) at John Hopkins University](https://github.com/CSSEGISandData/COVID-19).
Furthermore the socio-economic CASEN data, provided by the [Chilean Ministry of Social Development](http://www.desarrollosocialyfamilia.gob.cl/) was very useful and enabled me to make this investigation. I also relied on [WorldBank population data](https://data.worldbank.org/indicator/SP.POP.TOTL).
Also thanks to [Juan Manuel Núñez Méndez](https://unsplash.com/@juanmanunez?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) who provided the foto for my Medium blogpost and the project on GitHub. 
Finally, I would like to thank Udacity, Codecademy and Stackoverflow for allways providing answers to my questions.


## <a class="anchor" id="author">Author</a>
Maximilian Müller, Senior Business Development Manager for Smart Metering and Data Analytics in the Renewable Energy sector. Now diving into the field of Data Science.

## <a class="anchor" id="license">License</a>

Copyright 2020 Maximilian Müller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

From opensource.org
