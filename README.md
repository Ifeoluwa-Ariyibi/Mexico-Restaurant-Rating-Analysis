# Mexico Restaurant Rating Analysis

## Table of Contents
- [About Project](#About-Project)
- [Questions](#Questions)
- [Data Cleaning and Transformation](#Data-Cleaning-and-Transformation)
- [Full DashBoard](#Full-DashBoard)
- [Recommendation](#Recommendation)

## About Project
This dataset, known as the restaurant rating dataset, includes details about restaurants in Mexico. In 2012, a customer survey was conducted in the city to gather information on each restaurant, their cuisines, consumer details, and consumer preferences.

## Questions
This analysis aims to thoroughly analyze the restaurant rating dataset and provide answers to the questions listed below.
- Question 1. 
What can you learn from the highest rated restaurants? Do consumer preferences have an effect on ratings?
- Question 2. 
What are the consumer demographics? Does this indicate a bias in the data sample?
- Question 3. 
Are there any demand & supply gaps that you can exploit in the market?
- Question 4. 
If you were to invest in a restaurant, which characteristics would you be looking for?

## Data Cleaning and Transformation

 - Data Source

This restaurant rating dataset includes information about restaurants in Mexico. In 2012, a customer survey was conducted in the city to gather details about each restaurant, their cuisines, consumer information, and consumer preferences. The data is in Excel workbook .xlsx format with multiple tabs covering data and can be found here [Restaurants Rating Dataset.xlsx](https://github.com/user-attachments/files/16553812/Project.2.xlsx) It consists of columns such as Consumer_ID,	Preferred_Cuisine,	Consumer City,	Consume State,	Consume Country,	Smoker,	Drink_Level,	Transportation_Method,	Marital_Status,	Children,	Age,	Occupation,	Budget,	Overall_Rating,	Food_Rating,	Service_Rating,	Cuisine,	Restaurant, Name,	Restaurant, City,	State,	Country,	Alcohol_Service,	Smoking_Allowed,	Price,	Franchise,	Area, and Parking.

- Data Preparation

I started by removing the blank rows and columuns and I renamed the columns such city, state and country of consumer to Consumer City,	Consume State, and	Consume Country. This helped to diffreciate the city, state and country for both consumers and restaurants. After doing this, imported the data into PowerBi where I use DAX to create measures such as aggregating ratings (average Overall_Rating, average Food_Rating, average Service_Rating) as shown below:

Average Overall_Rating = AVERAGE('Consumer_Preferences'[Overall_Rating])
Average Food_Rating = AVERAGE('Consumer_Preferences'[Food_Rating])
Average Service_Rating = AVERAGE('Consumer_Preferences'[Service_Rating])

Custom Column was use to create Age Group column in the Custom Column dialog using the formula below:

Age group = if [Age] <= 18 then "Under 18"
else if [Age] <= 25 then "19-25"
else if [Age] <= 35 then "26-35"
else if [Age] <= 45 then "36-45"
else if [Age] <= 55 then "46-55"
else if [Age] <= 65 then "56-65"
else "Over 65"

## Full DashBoard

![Dashboard](https://github.com/user-attachments/assets/c906d552-0eca-4fc4-beeb-9be817224ff1)

This dashboard provides an analysis of the restaurant ratings and consumer preferences in Mexico. Key highlights include:

Overall Ratings by Restaurant and Cuisine: Displays the average overall ratings for various restaurants segmented by preferred cuisine types such as Afghan, American, Bagels, Bakery, Bar, and Barbecue.

- Consumer Demographics:
  - Majority are employed (85%), followed by students (13.2%) and unemployed (1.8%).
  - The Marital Status shows predominantly single consumers (93%), with a small portion married (7%).
  - The largest Age group is between 26-35 years old, followed by those 19-25 years old.
  - The Smoking Status shows that 77 consumers are non-smokers, while 21 are smokers.
  - Most consumers are casual drinkers (35), followed by abstainers (33) and social drinkers (30).

- Restaurant Locations: Displays the geographical distribution of restaurants in cities like San Luis Potosí, Ciudad Victoria, and Cuernavaca.
- Service, Food, and Overall Ratings by Alcohol Service: Shows average ratings based on different types of alcohol service (Full Bar, None, Wine & Beer).
- Preferred Cuisines: Mexican cuisine is the most preferred (31 consumers), followed by American (6) and Coffee (5).

Other Metrics:
- Total Restaurants Analyzed: 98
- Average Overall Rating: 1.23
- Service Rating: Average ratings for service, food, and overall.

## Data Visualisation and Interpretation
Question 1. 
What can you learn from the highest rated restaurants? Do consumer preferences have an effect on ratings?

![Question 1 visualization](https://github.com/user-attachments/assets/ecd6b9ea-e0e6-49ef-973d-c25b77755468)

From the provided chart, it was observe that the highest-rated restaurants uniformly score a 2.00, indicating generally positive but not outstanding satisfaction levels across various types of cuisines including Mexican, American, Pizzeria, and Coffee Shop. The prominence of Mexican cuisine among the highest-rated shows a strong consumer preference or cultural influence in the region. Despite this, the consistent ratings across diverse restaurant types imply that factors beyond cuisine preference, such as service quality, location, and overall dining experience, significantly influence consumer ratings.

Question 2. 
What are the consumer demographics? Does this indicate a bias in the data sample?

![consumer demographics](https://github.com/user-attachments/assets/29f7b62b-d2d7-4e23-85af-9e7b5448a8d8)

The demographics of consumers, as assessed through various charts, reveal that the majority are employed (85%), followed by students (13.2%) and unemployed individuals (1.8%), predominantly single (93%), primarily aged between 26-35 years old, and largely non-smokers (77). Most consumers are casual drinkers (35), followed by abstainers (33) and social drinkers (30). This charts indicate a potential bias towards single, employed, non-smoking individuals who are casual or abstinent drinkers, with a skew towards younger age groups (19-35 years).

Question 3. 
Are there any demand & supply gaps that you can exploit in the market?

To identify demand and supply gaps,  the "Consumer_ID and Restaurant Name by Preferred_Cuisine", "Consumer_ID by Smoker", and "Consumer_ID by Drink_Level" charts were used:

- Demand:
  ![image](https://github.com/user-attachments/assets/17d59ee9-67b1-4c5c-a88d-bf90231e34f2)
  
  - Mexican cuisine is the most preferred (31 consumers), followed by American (6) and Coffee (5). Certain cuisines like Japanese, Continental, Fast Food, and Bakery have lower representation despite potential consumer interest, indicating a market gap.

  - Smokers and Drinkers Market

![image](https://github.com/user-attachments/assets/edc8f4d5-4b70-4ca6-bfe0-52a3f6a51c1a)
The charts show significant portion of consumers are non-smokers (77 out of 98) and casual drinkers (35 out of 98). However, there is a notable presence of smokers (21) and social drinkers (30). This suggests potential gaps for restaurants that cater specifically to these groups:
  - For smokers: Restaurants that allow smoking or have dedicated smoking areas could attract this demographic.
  - For drinkers: Restaurants with a vibrant bar scene or a variety of alcoholic beverages might fill a demand gap.

- Exploitable Gaps:

Introducing more restaurants with underrepresented but preferred cuisines (e.g., Japanese, Continental) can address unmet consumer demand.
Targeting the smoker and social drinker market with specialized offerings, such as designated smoking areas or extensive alcohol service, presents new opportunities to attract these specific consumer groups.

Question 4. 
If you were to invest in a restaurant, which characteristics would you be looking for?

Characteristics to Consider:

Cuisine Preference: Focus on underrepresented but potentially high-demand cuisines like Japanese, Continental, Fast Food, and Bakery. These cuisines have fewer restaurants despite notable consumer interest, indicating a market gap.

Consumer Habits:
- Non-Smokers and Smokers: A significant portion of consumers are non-smokers (77 out of 98), but there is also a notable group of smokers (21). Restaurants with designated smoking areas or a smoker-friendly environment could attract this demographic.
- Drink Levels: Casual drinkers (35) and social drinkers (30) form a substantial part of the market. Restaurants with a vibrant bar scene or an extensive selection of alcoholic beverages can cater to these groups.
- Location and Accessibility: Ensure the restaurant is easily accessible and located in a high-traffic area to attract more customers. Key Cities such as Key cities like San Luis Potosí, Ciudad Victoria, and Cuernavaca will be considered.
- Service Quality: Invest in creating a welcoming ambiance and providing excellent service, as these factors significantly influence consumer satisfaction and repeat business.

## Recommendation

- The highest-rated restaurants score uniformly well across various cuisines, with Mexican cuisine being the most preferred. This indicates that while consumer preferences matter, factors like service quality and location also play significant roles in ratings.
- Consumers are mostly employed (85%), single (93%), aged 26-35, and non-smokers (77). This shows a bias towards young, employed, single, non-smoking individuals, suggesting a need to diversify offerings to attract a broader demographic.
- There are gaps in the market for underrepresented cuisines like Japanese, Continental, Fast Food, and Bakery. Additionally, there is potential to target smokers and social drinkers with specialized offerings like smoking areas and vibrant bars.
- Invest in restaurants offering underrepresented cuisines (e.g., Japanese, Continental), cater to non-smokers and smokers, have vibrant bar areas, and are located in high-traffic areas with excellent service and ambiance.
