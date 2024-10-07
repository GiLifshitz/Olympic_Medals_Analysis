# Olympic Games Medals Analysis Report
## Do host countries of the Olympic Games tend to win more medals?. Analysis Based on Residency Using Python

<img src="https://media.giphy.com/media/Ur7vrGqaUIXupMDMeV/giphy.gif" alt="Michael Phelps GOAT GIF" width="300">

### Introduction 
The Olympic Games represent the cherry of global athletic competition, bringing together athletes representing their nation from around the world to compete in a diverse array of sports. This project aims to analyze the Olympic Games dataset to uncover patterns, trends, and insights from the historical data of these events, with the focus on our research question, which is: does the fact that a country hosts the Olympics, contributes to the number of medals it won? Our null hypothesis is that there is no difference in the number of medals won when hosting versus not hosting. By leveraging various data analysis techniques, we will explore the evolution of the Games, and the performance of different countries. Our analysis will provide a comprehensive overview of how the Olympic Games have developed over time and highlight some insights and fascinating discoveries we learned during the process.

### Method
The process of the analysis was as follows:
* Searching for a reliable and comprehensive dataset.

* Cleaning and organizing the data.

* Performing exploratory data analysis.

* Attempting to answer the research question.
The data used in this research is “120 years of Olympic history: athletes and results” retrieved from Kaggle1. This dataset contains information about every individual athlete that participated in every Olympic. Each row in the dataset contains:

* ID – Unique number for each athlete

* Name - Athlete's name

* Sex - M or F

* Age - Integer

* Height - In centimeters

* Weight - In kilograms

* Team - Team name
  
* NOC - National Olympic Committee 3-letter code

* Games - Year and season

* Year - Integer

* Season - Summer or Winter

* City - Host city

* Sport - Sport

* Event - Event

* Medal - Gold, Silver, Bronze, or NA

*person who associated a work with this deed has dedicated the work to the public domain by waiving all of his or her rights to the work worldwide under copyright law, including all related and neighboring rights, to the extent allowed by law.

This is the raw data, we made several adjustments to facilitate analysis. During our analysis, we continuously identified imperfections in the data, prompting us to revisit and re-adjust the raw data. The adjustments we made are:

* Removed all winter games, focusing solely on summer games.

* Merged medals for team sports (e.g. basketball) so that each medal counts as one per country, rather than one per athlete.

* Excluded the 1906 Athens games, as they were not recognized by the International Olympic Committee (IOC).

* Addressed the 1956 Olympics, which were held in two cities, Melbourne and Stockholm. only equestrianism in Sweden. The dataset mistakenly duplicated the 1956 Olympics for two different host countries. We solved this by deleting the duplicates and attributing the host country of the equestrianism to Australia.

### Exploratory Data Analysis
In this section, a basic overview of the data is presented, so we can get a better understanding of It, and to summarize the data main characteristics.
![image](https://github.com/user-attachments/assets/4d25b777-1d06-4970-91f4-bdc7a8ae9c22)

Figure 1 - Number of athletes and medals per Olympic, notice the rise in numbers over the years.

It’s evident and logical that over the years, the Olympic games have grown significantly, leading to a hundredfold increase in the number of participating athletes and medals awarded.

![image](https://github.com/user-attachments/assets/796e86e9-7551-4589-b159-9ae0c5a1cca2)

Figure 2 - Athletes age distribution, in red is the age mean for all athletes.

Examining the age distribution of Olympic athletes reveals some unusual values, such as 10 and 97. A quick investigation revealed some intriguing stories. Dimitrios Loundras, a Greek gymnast, competed at the 1896 Athens Olympics at the age of 10. Winning a bronze medal and becoming the youngest medalist and competitor in Olympic history. John Quincy Adams Ward, though deceased in 1910, has his sculpture entered in the 1928 art competition, listing him at age 97.

![image](https://github.com/user-attachments/assets/3fdebdba-cf25-478d-a786-4986a0ca4a38)

Figure 3 - Number of medals won by each country including all Olympic games ever (top ten countries and Israel).

### Research Question
The goal of this research is to determine if hosting the Olympic Games, contributes to the country's medals count. We analyzed the data to observe the numbers and sought to identify any explanations for changes that are not related to hosting the games.
We focused on the United States for a several reasons, it has participated in every Olympic Games since 1896, except for the 1980 Games in Russia, which were boycotted by the USA. The USA has hosted the Olympics more times than any other country, 4 times, and have many athletes competing across a board spectrum of sports.

![image](https://github.com/user-attachments/assets/2b1ebb4a-a41e-4814-ab93-7f6c9aea2bc5)

Figure 4 - United States Medals Percentage won and the country hosted the games, the games that the USA hosted marked red, the average number of medals percentage USA won when it did not host is 8.09%.

Figure 4 highlights a key finding related to our research question, the USA won a significantly larger share of the total medals when it hosted the Olympics compared to when it did not. As shown in Table 1 below, the permutation test yielded a p-value of 0.0028 for the difference in the percentage of medals won between hosting and not hosting. This low p-value allows us to reject the null hypothesis, which suggests no difference in the percentage of medals based on hosting status.

![image](https://github.com/user-attachments/assets/4a9ca76f-9b25-4fe5-b8b7-75d5493bfb5e)

Figure 5 – Distribution of the percentage of medals won by the USA relative to all medals awarded in the current games and the percentage of athletes representing the USA relative to all participants in the current games.

Figure 5 sheds light on the anomalies observed in Figure 4. It shows that the USA had a significantly larger number of athletes and won more medals during the games it hosted compared to those hosted by other countries. For instance, in 1904, 80% of the total athletes were from the USA. This context helps explain why hosting countries often win a larger share of medals, they not only host the games but also have a significantly higher number of athletes competing. As shown in Table 1 below, the permutation test produced a p-value of 0.0 for the difference in the percentage of athletes representing while hosted versus not hosted. This extremely low p-value allows us to reject the null hypothesis, which suggests no difference in the percentage of athletes based on hosting status.

Table 1.1 – For each country that has hosted the Olympics at least once, this table presents the number of times it has hosted, the difference in the percentage of medals won and the percentage of athletes representing the country between hosting and not hosting and the p-values for each comparison.
![table 1_page-0001](https://github.com/user-attachments/assets/7201fee8-9540-40be-b98f-d43c3f11a923)

Table 2 – For each country that has hosted the Olympics at least once, this table presents the ratio between the percentage of athletes representing the country and the percentage of medals won during hosted versus non-hosted instances, as well as the difference in these ratios. This ratio indicates the change in the percentage of medals won for each additional percent of competitors. Additionally, the table includes the p-value for the difference in these ratios.
![table 2_page-0001](https://github.com/user-attachments/assets/ee3713a4-c4ab-47b1-8831-9dad024704a3)

Featuring the last column of Table 2, "Percentage Difference in Mean Athletes and Medals Ratio", we calculate the difference between the Percentage Ratio of Athletes and Medals When Hosted and When Not Hosted. A positive value indicates that for this country, each percent increase in athletes while hosting leads to a higher percentage of medals won compared to when not hosting. Conversely, a negative value suggests the opposite effect. As shown in Table 2, all differences are less than one and greater than -1, indicating that any observed difference is very small. The p-value of 0.986 supports this observation, suggesting that the differences are not statistically significant. Therefore, we fail to reject the null hypothesis, which posits that there is no significant difference in the ratio of athletes to medals won based on hosting status.

### Discussion and Conclusions
This analysis aimed to explore whether hosting the Olympic Games significantly impacts a country's medal count. Our findings suggest that hosting the Olympics is associated with an increase in the number of medals won by the host country. This effect is largely driven by the substantial growth in the number of athletes representing the host nation during the Games. For instance, the United States, which has hosted the Olympics four times, consistently saw an increase in both the number of athletes and the percentage of medals won when hosting.
The statistical significance of this observation is underscored by the extremely low p-value of 0.0 associated with the percentage growth of athletes representing the host country. This p-value indicates a strong correlation between hosting the Olympics and the growth in athlete representation, allowing us to confidently reject the null hypothesis that there is no difference in the percentage of athletes based on hosting status. The increased athlete participation directly contributes to the higher medal counts observed for host nations.
A particularly noteworthy example is the 1984 Los Angeles Olympics, where the Soviet Union's boycott resulted in a disproportionately large number of American athletes competing, which in turn significantly boosted the United States' medal count. This example illustrates how external factors, such as geopolitical events, can further amplify the impact of hosting the Games on medal counts.
Despite the clear increase in medals for host countries, it's important to note that when examining the ratio of athletes to medals, the differences between hosting and non-hosting years were minimal, as reflected in a p-value of 0.986. This suggests that while hosting countries benefit from increased athlete participation, the efficiency of converting athlete representation into medals does not significantly improve. The advantage of hosting appears to stem primarily from greater participation rather than enhanced athletic performance.
In conclusion, hosting the Olympic Games does provide a competitive edge in terms of increased medal counts, largely driven by the substantial growth in the number of athletes representing the host country. However, this advantage does not necessarily translate into a more efficient conversion of athlete participation into medals. The findings highlight the multifaceted benefits of hosting, which include increased national representation, international recognition, and potential economic gains. The case of the 1984 Olympics further underscores the role of external factors in shaping Olympic outcomes, suggesting avenues for future research into the long-term impacts of hosting on national sports programs and international athletic performance.
While this study has demonstrated that hosting the Olympic Games is associated with an increase in medal counts due to higher athlete participation, there are several avenues for future research that could provide deeper insights into the dynamics of Olympic success.
It is important to note that during our work with the dataset, we encountered several inaccuracies, such as those found in the 1956 Olympic data, which are detailed in the Jupyter notebook containing the analysis code. Although we made efforts to identify and correct all errors, we cannot guarantee that every issue has been detected. Consequently, some of the results may be inaccurate. For any future, more in-depth research, a thorough review of the data's accuracy is recommended.
A relevant follow-up study using the same dataset could examine the impact on the Winter Olympics, while another study using a different dataset could explore the effect on sports investment in host countries after the event.

![Olympics Breakdancing GIF](https://media.giphy.com/media/1tWa6agib0Vk9m7lDq/giphy.gif)

Disclaimer – This work was generated with the help of AI tools to support the analysis, writing, and organization of content.

All figures in this report are generated from the code provided in this repository.
