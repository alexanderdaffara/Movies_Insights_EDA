# Exploratory Data Analysis for Microsoft Film Studios
Authors: 
Alexander Claudino Daffara
Utku Kale

## Introduction and Overview
 - Microsoft want to launch a new film studio, but they know very little about films, so we want to explore existing data to provide Microsoft with data-driven actionable insights to maximize profit, visibility and reception
 - We will be analyzing movie data from imdb, The Numbers and Kaggle for most profitable genres, movie runtime and choice of lead actor gender

## Market and Business Understanding
 - Microsoft understands its huge Tech company, so we know they will garner much attention with their initial film releases, so let's make them good!
 - Microsoft is joining a competitive field where other originally-tech-based companies (such as Amazon, Netflix, Hulu) are launching film studios and having great success
 - We understand Microsoft stakeholders are making this decision to expand their business, and will measure the success of that expansion by how much profit they make
 - We are in the modern era of film, where streaming services are booming. Due to that we will be analyzing films only from 2013 to 2019. 2013 marks the beginning of this boom, as it was the year Netflix launched the show "House of Cards"
 - These are the key Questions we'll be addressing:
    - How much should we spend on production maximize profit?
    - What film genres and combinations of genres have been most profitable?
    - What is the distribution of movie runtimes in films with profitable genre choices?
    - Does the gender of the actor in a movie's lead role affect the movie's profitability?
    - Given a choice of gender, what genre is best?
    - Given a choice of genre, what gender is best?
 - Most Film studios throughout history have had to learn these business insights through trial and error over time. With proper exploratory data analysis, Microsoft can learn from others mistakes and increase their chances of a successful launch.

## Data Understanding and Analysis
 - The Datasets we used are from imdb, The Numbers and Kaggle
    - imdb data contains information about the movie genres and runtime in minutes
       - 146k movies before data-cleaning for our analysis
    - The Numbers contains information about production budget and revenue for the films
       - ~5.5k movies before data-cleaning for our analysis
    - Kaggle's "The Movie Dataset" contains information about cast and actor gender
       - ~45k movies before data-cleaning for our analysis

## Results:
### - Insight 1: Spend More to earn more. Risk of loss is especially above $50 million in production budget.
![budget_v_profit](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/budgetvProfit.png)
    - We can see from this visualization that there is a positive correlation between production budget and profit. 
    - We can also see around $ 50 million in budget there is a greatly reduced probability of a movie resulting in loss

### - Insight 2: Choose from one of the top 5 profitable genres.
   - This visualization shows the average profit per genre and genre combination category.
   - We made the decision to include only genre combinations with at least 40 samples as to not allow genres with few samples dominate the profit average. This makes the distribution more representative of our population. 
   - Each genre bin represents a sample of movies containing at least that genre or genre combination. 
    - In example: "Adventure & Comedy", representing the highest average profit, contains all films that are both adventure and comedy, as well as films that are action, comedy and some other genre.
   - A key insight to be taken from this chart is genre upscaling. For example, if Microsoft feels comfortable making a successful comedy movie, we would recommend you make an adventure & comedy movie to almost double your expected profit

### - Insight 3: Choose an appropriate runtime length, given a choice of genre
   - This visualization shows the distribution of movie runtime lengths for each of our top 5 genres
   - From this we can choose a runtime length that is appropriate for each genre since the distributions (except for 'Adventure') are all heavily skewed towards one clear choice.
   - Since we are choosing from proven profitable genres over the years, it is safe to assume that we want to emulate those common runtime choices.

### - Insight 4: Given a choice of actor in a movie's leading role, some genres are more profitable than others, depending on the actor's gender. Conversely, given a choice of genre, we can conclude a lead actor gender which is statistically more profitable.
 - The Male distribution was sampled to have an equal sample population as the Female distribution, so we may compare them without the risk of mean inflation.
 - By analyzing the mean and bulge distribution of these probability density functions, we can make decisions such as:
    - If we have a specific female actress in mind, a Horror & Thriller is the most profitable choice
    - If we have a specific male actor in mind, the most profitable genre combination to go with is Action & Comedy
    - If we are comfortable making a Horror & Thriller movie, a Female actress is the best choice
    - Finally the profit averages for males is very slightly higher than the profit averages for females. That being said, Microsoft is a highly influential company and have an opportunity to partake in building gender equality in the film industry for little net cost.

## Conclusion
 - Spend more than $50 million to reduce the risk of loss, as the average high budget film will make more money than la ow budget film
 - Choose from one of these most profitable genre combinations, movie runtimes and lead actor gender (keeping in mind gender only slightly affects profit):
    - Adventure & Comedy, short, Male
    - Action Adventure, long, Male
    - Adventure, any, Male
    - Sci-Fi,  medium, Male
    - Horror Thriller, short, Female
 - choice of lead actor gender 
## Future Improvements
 - Adjust profit values with inflation over the years
 - Work with streaming service dataset to incorporate valuable recent data
 - Require more data for analysis, so we may have sample sizes that better represent the population, especially for our gender analysis, which is a highly discussed topic and there is high demand for accurate data
