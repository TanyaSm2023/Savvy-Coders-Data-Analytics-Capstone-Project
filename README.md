# U.S. Debt and Spending Trends Analysis

This is my Data Analytics Project from the Savvy Coders Data Analytics + Python bootcamp. The project aimed to explore changes in Americans' debt and spending habits over the past decade, identifying significant trends and patterns. The analysis delved into credit card usage, state finances, and overall spending patterns to uncover insights into how people manage their finances. This exploration is crucial for understanding individual financial behaviors, guiding personalized financial planning, and offering valuable information for businesses, policymakers, and the broader community.

The completed Tableau presentation for this project can be found on my Tableau Public profile by visiting the following link:
<https://public.tableau.com/app/profile/tatiana.smirnova7482/viz/ComparingStateFinancesin2022_PerCapitaIncomevs_PersonalSpending3/CapstonePresentation>

## Data Sources

The analysis in this project was conducted using three different datasets to get a complete understanding. Each dataset helps me look at specific things like total debt over time, trends in debt, credit card payments, state-wise income, and detailed spending categories.

1. [Federal Reserve Bank of Philadelphia:](<https://www.philadelphiafed.org/surveys-and-data/large-bank-credit-card-and-mortgage-data>)

23Q2-CreditCardBalances.csv - This data set is derived from credit card and mortgage data provided by the largest financial institutions in the United States.

2. [Bureau of Economic Analysis:](<https://www.bea.gov/>)

From this source, I acquired two datasets—one containing annual summary statistics on personal income and consumer spending, and the other featuring Per Capita Personal Consumption Expenditures (PCE) by major type of product.

SASUMMARY State annual summary statistics personal income, GDP, consumer spending.csv<br>
SAPCE2 Per capita personal consumption expenditures (PCE) by major type of product 1.csv

## Terms

1.	**Revolving credit** allows borrowing up to a certain limit with flexible repayment, like a credit card.

2.	**Installment credit** involves fixed payments over time, as seen in loans like car loans or mortgages.

3.	**Consumption expenditures** refer to the total amount of money spent by households and individuals on goods and services for personal use. These expenditures encompass a wide range of items, including but not limited to:

    -Goods: Physical items that individuals purchase for personal use, such as clothing, electronics, and furniture.

    -Services: Non-material items that people pay for, such as healthcare, education, transportation, and leisure activities.

4.	**Disposable income** refers to the total income that individuals or households have available for spending and saving after taxes have been deducted.

## Methodology

### Data Processing Steps

**Python**: I performed data cleaning on the first dataset, which contains credit card debt information. The initial analysis aimed to gain general insights into the data, including details such as the number of rows and columns, values, data types, and identification of any missing values. During this process, I removed unneeded rows containing common information and unnecessary columns using the DROP method. Additionally, I cleaned the data by eliminating symbols like '$', '%', and commas, and changed the data type from 'object' to 'float'.<br>
For categorizing credit balance debt, I created a new column named 'Installment Balances Only ($Billions)' by subtracting 'Revolving Balances Only ($Billions)' from 'Total Balances ($Billions)'. I utilized Matplotlib to generate the following graphs: 'Total Balances Over Time,' 'Percentage Change in Total Balances Over Time,' 'Revolving and Installment Balances,' and 'Average Share of Accounts Payment Distribution Over Years.'

**SQL**: I used the DB Browser for SQLite to import my second and third .csv files. After reviewing the files, I identified the need to transfer "Per capita personal income" and "Per capita disposable personal income" information to another file named "Per capita personal consumption expenditures (PCE) by major type of product 1.csv." <br> To achieve this, I performed updates on the LineCode values for the relevant rows in the "State annual summary statistics personal income, GDP, consumer spending.csv" file. Subsequently, I inserted this information into the second file. <br> Additionally, I made adjustments such as renaming specific column names and removing records in the "State" column that are not related to U.S. states.

**Tableau**: I used Tableau to visually represent and explore the comparison between Per Capita Income and Personal Spending by states. The visualizations include 'States Overspending,' which highlights cases where consumption expenditures surpass disposable income. Additionally, there are two breakdowns of Per Capita Consumer Spending Trends (2012-2022) – one focusing on Goods Categories and the other on Services Categories.

## Analysis and Findings

### Total Balances Over Time
The debt initially decreased from 700 billion to 550 billion during the pandemic, but from 2021 to 2022, there was an upturn, reaching 640 billion, and exceeding 750 billion by 2023.<br>

![Alt text](<Images\1 Total balance.jpg>)

![Alt text](<Images\2 Percentage Change in Total Balances (Q4 Only) Over Time.jpg>)

### Revolving and Installment Balances

A gradual increase in Installment Balances from 2012 to 2023, progressing smoothly over the years.<br>
In contrast, Revolving balances show a downward trend during the pandemic but have been consistently increasing since 2022. This pattern closely aligns with what we observed in the previous picture. 

![Alt text](<Images\3 Revolving and Installment Balances Over Time.jpg>)

### Average Share of Accounts Payment Distribution Over Years<br>

Noticed a regular pattern: People who pay the minimum on their credit cards haven't changed much over the years. But there's something interesting happening with those who pay more than the minimum. It looks like some folks who used to pay more have switched to paying the full amount since 2019, and this change keeps going up until 2023.
This got me curious about why this shift is happening – is it because of a change in people's habits or something else? To understand this better, I'm going to delve into 'Per Capita Income vs. Personal Spending by states.' I want to understand how money flows in different states and if there's a connection between how much people make and how much they spend. <br>

![Alt text](<Images\4 Average Share of Accounts Payment Distribution Over Years.jpg>)

### Per Capita Income vs. Personal Spending

In 2022, the District of Columbia spent significantly more than it earned. This prompted me to delve deeper and identify which states fall into the category of overspending, where expenses exceed income. <br>

![Alt text](<Images\5 Per Capita Income vs. Personal Spending.jpg>)

### States Overspending: When Expenses Exceed

States overspending, where expenses exceed income, was observed in seven states: Delaware, District of Columbia, Florida, Hawaii, Maine, Michigan, Vermont, while the majority demonstrated positive balances. 
This observation leads me to the next phase of exploration, where I will delve into the specifics of people's spending habits.<br>

![Alt text](<Images\6 States Overspending When Expenses Exceed.jpg>)

### Goods and Services Spending Per Capita
Both categories show sustained growth over the years. <br>

![Alt text](<Images\7 Goods and Services Spending Per Capita.jpg>)

### Per Capita Consumer Spending Trends (2012-2022): A Breakdown by Goods Categories

![Alt text](<Images\8 A Breakdown by Goods Categories.jpg>)

Examining the Goods categories, it's apparent that the pandemic had an impact on all subcategories, causing a temporary decrease. 
However, certain subcategories, such as "Food and beverages purchased for off-premises consumption," "Other nondurable goods," and "Recreational goods and vehicles," not only weathered the impact but display a consistent upward trend over the years, with a notable rise in the last three years.

For instance, "Food and beverages purchased for off-premises consumption" demonstrate an increased percentage in average spending per person—10% in 2020, 7.45% in 2021, and 7.81% in 2022. 

This indicates a significant rise in spending on takeout, delivery, and at-home dining experiences. More and more people seem to prefer the ease and flexibility of having meals at home or somewhere other than a restaurant. This change in how people choose to eat fits with today's lifestyle, where saving time and using technology for food delivery are top priorities.

Likewise, the category of "Other nondurable goods" saw a consistent rise, going up by 8.64% in 2020, 7.43% in 2021, and 7.31% in 2022. This indicates an ongoing increase in spending on different non-durable items, such as everyday goods and products. (food, clothing, personal care products).

"Recreational goods and vehicles" saw a remarkable increase too, reaching almost 18% in 2020, 19.48% in 2021, and 7.6% in 2022. This indicates a notable rise in spending on recreational items and vehicles during these years.

On the other hand, "Gasoline and other energy goods" showed a varying pattern, experiencing a notable decrease followed by an increase over the years, closely linked to changes in prices. Further investigation confirmed that from January to June 2022, the price of regular motor gasoline rose by 49%, while diesel fuel saw a slightly higher increase at 55%. You can check it here: <https://www.bts.gov/data-spotlight/record-breaking-increases-motor-fuel-prices-2022>

This highlights how changes in prices impact spending behaviors within this category.

### Per Capita Consumer Spending Trends (2012-2022): A Breakdown by Services Categories

![Alt text](<Images\9 A Breakdown by Services Categories.jpg>)

Looking at the spending in the "Food services and accommodations" category, there's something interesting to note. 

After a drop caused by the pandemic, spending went back to normal in 2021 and then shot up by 17% in 2022. This increase could mean that the economy is bouncing back, as people with more money to spend and a stronger belief in the economy are treating themselves to dining out, travel, and accommodations.

In the category of "Housing and utilities," there's been a change from the usual yearly increase of around 3%. In the last two years, it went up to 5.6% in 2021 and even more to 7.5% in 2022. 

Remarkably, U.S. home prices have been going up for 11 years straight, with a big jump of 18% in 2021. Although the market slowed a bit in 2022, it still went up by 4.77%. This tells us that various factors, like market trends and how people spend, are playing a role in this trend.

The "Recreation services" category observed a large rise of 14% from 2021 to 2022, reflecting a positive rebound from the impacts of the COVID-19 pandemic. This increase signals a potential recovery in the recreation and entertainment industry, with individuals showing a greater readiness to participate in events and recreational programs as pandemic-related concerns relieve.

Similarly, the "Transportation services" category observed a significant increase of almost 22% from 2021 to 2022. This rise could be affected by changes in fuel prices. 

Other interesting findings show that spending on "Financial services and insurance", "Health care," and "Other services" has bounced back to normal levels after a dip during the pandemic. These sectors are recovering and getting back to the spending patterns seen before the pandemic as economic conditions stabilize.

## OUTCOMES

### How has debt and spending in the U.S. changed over the past decade, and what does it reveal about how people handle their money? <br>

•	Total debt initially decreased during the pandemic but began to rise again from 2021 to 2023, exceeding 750 billion. This suggests a changed economic landscape. <br>

•	Revolving balances showed a downward trend during the pandemic but have consistently increased since 2022, indicating changes in credit card usage. <br>

•	Analysis of payment distribution showed a shift in behavior, with individuals moving from paying more than the minimum to paying the full amount from 2019 to 2023. However, it is noteworthy that a significant portion of people still adhered to paying only the minimum required for their debts.<br>

### By examining data related to credit card debt, state finances, and overall spending habits, what insights can be gleaned regarding shifts in financial behaviors? 

•	States overspending, where expenses exceed income, was observed in seven states: Delaware, District of Columbia, Florida, Hawaii, Maine, Michigan, Vermont, while the majority demonstrated positive balances. <br>

•	Goods and Services spending per capita showed a continuous upward trend, suggesting sustained growth. <br>

•	Specific subcategories like "Food and beverages purchased for off-premises consumption," "Other nondurable goods," and "Recreational goods and vehicles" showed consistent growth over the years. <br>

•	Notable shifts were observed in spending patterns within categories like "Food services and accommodations," "Housing and utilities," "Recreation services," and "Transportation services," indicating changing consumer behaviors and economic conditions.<br>
