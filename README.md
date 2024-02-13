# HallofFameClassification

## Project Overview

### Project Goals
The goal of this project is to build a classification model to accurately predict if a MLB position player will be inducted into the Hall of Fame based on six inputs including `H` (career hits), `HR` (homeruns), `2B` (doubles), `batting_avg` (batting average), `SB` (stolen bases), and `career_all_star_games` (number of all star game appearances). This is a classification problem because the desired prediction ('Inducted into the Hall of Fame?') is a categorical output. The player is either inducted ('Y') or not inducted ('N').

### Project Success Criteria
The success of this project will be based on fitting and testing two different classification models (decision tree classifier and random forest classifier) and evaluating which is most accurate.
This project will be considered successful if success rates of each classification model meet a threshold of at least 95% accuracy.

## Data Understanding
This data comes from the [Lahman Database](http://seanlahman.com/download-baseball-database/) which provides baseball statistics from 1871-2021. Specifically, I used the 'Batting', 'People', 'HoF' (Hall of Fame), and 'AllStar' .csv files from the database which include batting statistics (at bats, hits, singles, etc.), biographical information (date of birth, first name, height, etc.), hall of fame status, and number of all star appearences respectively. 

## Data Preparation
The following are keys steps I took to prepare the data for analysis:
* Compile the career batting statistics for each player in the `batting` dataframe using `.groupby()` and `.sum()` and save this to a new dataframe named `career_batting`
* Create a function called `slash_line` that computes a player's career batting average and create a new column in `career_batting` which stores these values
* Calculate the number of career all-star games for each player using `.groupby()` and `.count()` and create a new column in `career_batting` which stores these values
* Use `.fillna()` to replace any NaN values in the `career_all_star_games` column with 0
* Create a new column with information on whether the player is in the Hall of Fame ('Y)' or not ('N')
* Remove rows for any players with less than 100 at-bats (since this model will only be predicting position players, not pitchers)

## Modeling
This project trained and fitted two different models, a decision tree classifier and a random forest classifier, on the following inputs: `H` (career hits), `HR` (homeruns), `2B` (doubles), `batting_avg` (batting average), `SB` (stolen bases), and `career_all_star_games` (number of all star game appearances). Prior to fitting the models, the data was split into training data and test data using a 75/25 percent split. 

## Evaluation
Both the decision tree and random forest models were able to predict to high accuracies (97.51% and 97.58%, respectively) the hall of fame players from the test data set.

## Conclusions

### Limitations
Within the last 10-20 years there has be an influx of new batting metrics used to evaluate a hitter's success, but this project used traditional batting statistics such at batting average, career hits, career homeruns, and career doubles. With time, these traditional metrics may be replaced with newer metrics when considering whether a player is Hall of Fame worthy.

### Recommendations
With the high success rate of both of the models I deployed in this project, I would recommend any Hall of Fame voters who are unsure whether to vote for a particular batter for the Hall of Fame use my models to help with their decision. 

### Next Steps
In future iterations of this project, I hope to explore the potential issue of overfitting. Additionally, I am interested to try other classification models such as K-Nearest Neighbors, along with using newer, up-to-date metrics that MLB organizations use to evaulate hitting performance. 
