![image from https://www.nytimes.com/2015/12/13/movies/best-movies-2015.html](https://static01.nyt.com/images/2015/12/13/movies/13BESTMOVIES/13BESTMOVIES-superJumbo-v3.jpg)
# Exploratory Data Analysis for Microsoft Film Studios
Authors: 
Alexander Claudino Daffara
Utku Kale

## Introduction and Overview  
   Microsoft is planning to launch a new film studio and is looking to gain a deeper understanding of the film industry in order to maximize their profit, visibility and reception. In order to provide data-driven insights, we will be analyzing movie data from various sources such as IMDb, The Numbers, and Kaggle. We will focus on identifying the most profitable genres, analyzing the impact of movie runtime, and exploring the relationship between lead actor gender and box office success. This analysis will provide Microsoft with valuable information to inform their decision-making and strategy for their new film studio.

## Market and Business Understanding
   Microsoft is a well-established tech company that is now entering the film industry, with the goal of creating successful and profitable films. With that in mind, their initial film releases will attract significant attention, and they want to ensure that these films are of the highest quality. Microsoft is joining a competitive market where other originally tech-based companies such as Amazon, Netflix, and Hulu have already established successful film studios.

   We are currently in a modern era of film, where streaming services are booming. Due to this, we will be analyzing films only from 2013 to 2019. 2013 marks the beginning of this boom, as it was the year Netflix launched the show "House of Cards."

   Our project will address key questions such as: 
        How much should we spend on production to maximize profit? 
        What film genres and combinations of genres have been most profitable? 
        What is the distribution of movie runtimes in films with profitable genre choices? 
        Does the gender of the actor in a movie's lead role affect the movie's profitability? 
        Given a choice of gender, what genre is best? Given a choice of genre, what gender is best?

   Most film studios have had to learn these business insights through trial and error over time. However, with proper exploratory data analysis, Microsoft can learn from the mistakes of others and increase their chances of a successful launch. By analyzing existing data from sources such as IMDb, The Numbers, and Kaggle, we can provide Microsoft with data-driven actionable insights that will inform their decision-making and strategy for their new film studio.

## Data Understanding and Analysis
   The Datasets we used are from imdb, The Numbers and Kaggle
    - IMDb data contains information about the movie GENRES and RUNTIME in minutes
       - 146k movies before data-cleaning for our analysis
    - The Numbers contains information about PRODUCTION BUDGET and REVENUE for the films
       - ~5.5k movies before data-cleaning for our analysis
    - Kaggle's "The Movie Dataset" contains information about cast and ACTOR GENDER
       - ~45k movies before data-cleaning for our analysis

## Results:
### - Insight 1: Spend More to earn more. Risk of loss is especially above $50 million in production budget.
![budget_v_profit](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/budgetvProfit.png)

   We can see from this visualization that there is a positive correlation between production budget and profit. We can also see around $ 50 million in budget there is a greatly reduced probability of a movie resulting in loss.

### - Insight 2: Choose from one of the top 5 profitable genres.
![profit_by_genreCombination](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/profitByGenre.png)

   This visualization shows the average profit per genre and genre combination category. We made the decision to include only genre combinations with at least 40 samples as to not allow genres with few samples dominate the profit average. This makes the distribution more representative of our population. Each genre bin represents a sample of movies containing at least that genre or genre combination. 
   In example: "Adventure & Comedy", representing the highest average profit, contains all films that are both adventure and comedy, as well as films that are action, comedy and some other genre. A key insight to be taken from this chart is genre upscaling. For example, if Microsoft feels comfortable making a successful comedy movie, we would recommend you make an adventure & comedy movie to almost double your expected profit.
   Here is our original production budget vs. profit visualization, now showing the top genre:
![budget_v_profit](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/budgetvProfitWithGenre.png)

### - Insight 3: Choose an appropriate runtime length, given a choice of genre
![runtime_distribution_per_top_genreCombinations](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/runtime%20dist%20per%20genre%20(OG).png)

   This visualization shows the distribution of movie runtime lengths for each of our top 5 genres. From this we can choose a runtime length that is appropriate for each genre since the distributions (except for 'Adventure') are all heavily skewed towards one clear choice.
   Since we are choosing from proven profitable genres over the years, it is safe to assume that we want to emulate those common runtime choices.

### - Insight 4: Given a choice of actor in a movie's leading role, some genres are more profitable than others, depending on the actor's gender. Conversely, given a choice of genre, we can conclude a lead actor gender which is statistically more profitable.
![profit_distribution_for_Male_lead_actors_by_top_genreCombinations](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/MaleDistributionByProfitGenre.png)
![profit_distribution_for_Female_lead_actors_by_top_genreCombinations](https://raw.githubusercontent.com/alexanderdaffara/dsc-phase-1-project-Alex-Utku/main/visualizations/FemaleDistributionByProfitGenre.png)

   The Male distribution was sampled to have an equal sample population as the Female distribution, so we may compare them without the risk of mean inflation.

By analyzing the mean and bulge distribution of these probability density functions, we can make decisions such as:
  - If we have a specific female actress in mind, a Horror & Thriller is the most profitable choice
  - If we have a specific male actor in mind, the most profitable genre combination to go with is Action & Comedy   - If we are comfortable making a Horror & Thriller movie, a Female actress is the best choice
  
    Finally, the profit averages for males is very slightly higher than the profit averages for females. That being said, Microsoft is a highly influential company and have an opportunity to partake in building gender equality in the film industry for little net cost.

## Conclusion

TL;DR. These are the data driven suggestions we point out:
 - Spend more than 50 million to reduce the risk of loss, as the average high budget film will make more money than la ow budget film
 - Choose from one of these most profitable genre combinations, movie runtimes and lead actor gender (keeping in mind gender only slightly affects profit):
   Option 1:
       Genre -> Adventure & Comedy
       Runtime -> short (85 - 99 minutes)
       Leading Role Gender -> Male
   Option 2:
       Genre -> Action Adventure
       Runtime -> long (114 - 125 minutes)
       Leading Role Gender -> Male
   Option 3:
       Genre -> Adventure
       Runtime -> any (85 - 125 minutes)
       Leading Role Gender -> Male
   Option 4:
       Genre -> Sci-Fi
       Runtime -> medium (99 - 114 minutes)
       Leading Role Gender -> Male
   Option 5:
       Genre -> Horror Thriller
       Runtime -> short (85 - 99 minutes)
       Leading Role Gender -> Female
       
 With our data analysis we have suggested actionable insights to ensure success for Microsft Studio's launch.
 
## Future Improvements
 - Adjust profit values with inflation over the years
 - Work with streaming service dataset to incorporate valuable recent data
 - Require more data for analysis, so we may have sample sizes that better represent the population, especially for our gender analysis, which is a highly discussed topic and there is high demand for accurate data
