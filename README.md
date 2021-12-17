# Quality of Life and Internet Access
* [Introduction](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Introduction)
* [Data Organization](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Data-Organization)
  * [World-Happiness-Project-Data](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#World-Happiness-Project-Data)
  * [ITU-Internet-Access-Data](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#ITU-Internet_Access-Data)
  * [Data-Preparation](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Data-Preparation)
* [Exploratory Data Analysis](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Exploratory-Data-Analysis)
  * Different Kinds of Charts
* [Conclusions](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Conclusions)
  * [Main Observations](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Main-Observations)
  * [Future Directions](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Future-Directions)
* [Youtube Video Links](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Youtube-Video-Links)
* [Run Notebook on Google Colab](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Run-Notebook-on-Google-Colab)
* [Inquiries](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Inquiries)
* [Data Sources](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Data-Sources)
* [Acknowledgements](https://github.com/NatSchmit/Quality-of-Life-and-Internet-Access/blob/main/README.md#Acknowledgements)


## Introduction
As data science students, we place much of our faith in the ability of technology to shape a more knowledgeable, ethical, and prosperous world. In the past decade, most countries were faced with an increasing number of Internet users. With easier access, the Internet has become an integral part of our lives. However, many communities around the world lack access to computers and the internet. The San Diego Foundation of September 19, 2020 defines the digital divide as threefold: an economic divide, a usability divide, and an empowerment divide. The digital divide doesn’t just describe an inequity in basic access to technology; in our rapidly developing world, it also encompasses the technical and financial ability to make full use of available technology, taking into consideration access (or lack of access) to the internet.



According to the Office of Policy Development & Research of 2016, lack of high-speed internet access can negatively impact economic growth, household income, educational performance, healthcare access, and employment searches. It is clear that internet access plays a big role in one’s well being. However, there are opposite voices with the growing number of researches on Internet addiction saying that Internet usage caused psychosocial disorder. They claim that internet usage creates  a heightened level of psychological arousal, resulting in little sleep, failure to eat for long periods, and limited physical activity, possibly leading to the user experiencing physical and mental health problems such as depression, OCD, low family relationships and anxiety.


So, we decided to analyze data about internet access and various wellness aspects in a number of countries to answer the following question: **How does access to the internet affect a country’s overall quality of life/ happiness?** We want to see whether internet plays a positive impact more to people's life or negative impact is more dominant.

Although many studies have been conducted regarding the rural-urban digital divide in the United States, we are interested in the global impact of internet access. This analysis could help us identify whether it is worth investing in infrastructure that will provide high-speed internet access across the world, or if the presence of the internet is more detrimental than helpful.

## Data Organization
In order to obtain insight on our question of how access to the internet affects a country’s quality of life, we used two main datasets. The first dataset, World Happiness Report, is a survey of the state of global happiness publiced by the Sustainable Development Solutions Network. The Report is written by a group of independent experts acting in their personal capacities. Any views expressed in this report do not necessarily reflect the views of any organization, agency or program of the United Nations. This particular dataset compiles data from 2005 to 2020, although not every country has values for every year. Each country’s happiness score is based on answers to the Gallup World Poll. The dataset also calculates the extent to which six factors (GDP, social support, life expectancy, freedom to make life choices, generosity, and perception of corruption) contribute to a country’s happiness score.

The latter dataset, which is from the International Telecommunication Union (ITU), describes the percentage of population in a given country who are using the internet. This dataset spans from 2000 to 2019, but, as with the former dataset, some countries do not have values for certain years. ITU is a UN specialized agency for global ICT (Information Communication Technology) statistics. These percentages were provided by internet providers in the specific countries. We will use these two datasets to investigate the impact that internet access has on various metrics of well-being.

After filtering the data by removing the irrelevant attributes to our analysis, we ended up with the following attributes:


### World Happiness Project Data

| Attribute | Data Type | Description | Nullable |
| --- | --- | --- | --- |
| Country name | Nominal | Indicates country this data is collected from | No |
| Year | Interval | Indicates year this data is collected from | No |
| Life Ladder | Ordinal | Overall Happiness Score (Variable name Life Ladder). National average response to life evaluation question: Please imagine a ladder with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time? | No |
| Log GDP per capita | Ratio | Measures the total monetary value of all final goods and services produced throughout a year per person per country. Logarithmic GDP per capita means every step up the y-axis is an identical percent change in real GDP per capita. Log GDP per capita is an indicator of economic growth. | Yes |
| Social Support | Ordinal | Having someone to count on in times of trouble (Social Support) is the national average of binary (0-1) responses to the question: If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not? | Yes |
| Healthy life expectancy at birth | Ratio | Indicates life expectancy. This number is extracted from WHO data. | Yes |
| Freedom to make life choices | Ordinal | National average of binary responses to the question: Are you satisfied or dissatisfied with your freedom to choose what to do with your life? | Yes |
| Generosity | Ordinal | Residual regression of national average in response to the following question on GDP per capita: Have you donated money to a charity in the past month? | Yes |
| Perceptions of Corruption | Ordinal | National average of survey responses to two binary questions: Is corruption widespread throughout the government or not? Is corruption widespread throughout businesses or not. | Yes |
| Positive Affect | Ordinal | National average of three positive affect measures: happiness, laugh, and enjoyment. Based on the following questions: Did you experience the following feelings during a lot of the day yesterday? How about happiness? Did you smile or laugh? How about enjoyment? | Yes |
| Negative Affect | Ordinal | National average of three negative affect measures: worry, sadness, anger. Questions: Did you experience the following feelings during a lot of the day yesterday? How about sadness? How about worry? How about anger? | Yes |

Definitions acquired from the Statistical Appendix from the World Happiness Report. 

### ITU Internet Access Data
| Attribute | Data Type | Description | Nullable |
| --- | --- | --- | --- |
| Country | Nominal | Indicates country this data is collected from | No |
| Years (2000-2019) | Interval | Indicators year this data is collected from | No |
| Values under years | Ratio | Percent of individuals using the internet in a given country in a given year | Yes |

## Data Preparation
Both data sets were downloaded from Kaggle.com. Unnecessary columns were removed from the ITU data set such as “notes” and “source” columns which had limited applicable data. Then, we used R to merge the World Happiness Project data with the ITU data on country and year. 

## Exploratory Data Analysis
Here we explore some of the most interesting trends in our data. Please refer to our notebook to explore the findings in greater depth. 

The following plots show the general distribution of Internet Access, Overall Happiness, and Logarithmic GDP per Capita. These general distributions allow us to gain greater insight into the data set.

![download](https://user-images.githubusercontent.com/70483666/146561171-17fa1d9d-e9de-4b1e-a6c8-84b9aea4f0d4.png)
![download-1](https://user-images.githubusercontent.com/70483666/146561179-a9e87ab3-6c0d-40f4-8d79-b7b22170584b.png)
![download-2](https://user-images.githubusercontent.com/70483666/146561187-0b20bc4a-f6a4-449f-9b4d-c85e05dcfec7.png)


## Conclusions
The goal of our analysis was to analyze how internet access affects a country’s overall well-being. We explored data on various aspects relating to the happiness of different countries, as well as the percentage of the population who has internet access in these countries. Based on our analysis we make the following conclusions:


## Main Observations


## Future Directions


## YouTube Video Links


## Run Notebook on Google Colab


## Inquiries
For inquiries about this project, please contact Biddy Bi (bix@lafayette.edu), Sam Iacavazzi (iacavazs@lafayette.edu), Shirley Liu (liushi@lafayette.edu), or Natalie Schmit (schmitn@lafayette.edu).  


## Data Sources
- [World Happiness Report dataset](https://worldhappiness.report/ed/2021/#appendices-and-data)
- [ITU internet access dataset](https://www.itu.int/en/ITU-D/Statistics/Pages/stat/default.aspx)


## Acknowledgements
- Office of Policy Development & Research, *[Community Development and the Digital Divide](https://www.huduser.gov/portal/periodicals/em/fall16/highlight1.html)*, Fall 2016
- The San Diego Foundation, *[What is the Digital Divide?](https://www.sdfoundation.org/news-events/sdf-news/what-is-the-digital-divide/)*, September 2020
