# Quality-of-Life-and-Internet-Access

# Introduction
As data science students, we place much of our faith in the ability of technology to shape a more knowledgeable, ethical, and prosperous world. However, many communities around the world lack access to computers and the internet. The San Diego Foundation of September 19, 2020 defines the digital divide as threefold: an economic divide, a usability divide, and an empowerment divide. The digital divide doesn’t just describe an inequity in basic access to technology; in our rapidly developing world, it also encompasses the technical and financial ability to make full use of available technology, taking into consideration access (or lack of access) to the internet.

According to the Office of Policy Development & Research of 2016, lack of high-speed internet access can negatively impact economic growth, household income, educational performance, healthcare access, and employment searches. It is clear that internet access plays a big role in one’s well being. So, we decided to analyze data about internet access and various wellness aspects in a number of countries to answer the following question: How does access to the internet affect a country’s overall quality of life?

Although many studies have been conducted regarding the rural-urban digital divide in the United States, we are interested in the global impact of internet access. This analysis could help us identify whether it is worth investing in infrastructure that will provide high-speed internet access across the world, or if the presence of the internet is more detrimental than helpful.

# Data Organization
In order to obtain insight on our question of how access to the internet affects a country’s quality of life, we used two main datasets. The first dataset, World Happiness Report, is a survey of the state of global happiness. This particular dataset compiles data from 2005 to 2020, although not every country has values for every year. Each country’s happiness score is based on answers to the Gallup World Poll. The dataset also calculates the extent to which six factors (GDP, social support, life expectancy, freedom to make life choices, generosity, and perception of corruption) contribute to a country’s happiness score.

The latter dataset, which is from the International Telecommunication Union (ITU), describes the percentage of population in a given country who are using the internet. This dataset spans from 2000 to 2019, but, as with the former dataset, some countries do not have values for certain years. ITU is a UN specialized agency for global ICT (Information Communication Technology) statistics. These percentages were provided by internet providers in the specific countries. We will use these two datasets to investigate the impact that internet access has on various metrics of well-being.

After filtering the data by removing the irrelevant attributes to our analysis, we ended up with the following attributes:

# World Happiness Project Data

| Attribute | Data Type | Description | Nullable |
| --- | --- | --- | --- |
| Country name | Categorical | Indicates country this data is collected from | No |
| Year | Ordinal | Indicates year this data is collected from | No |
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






