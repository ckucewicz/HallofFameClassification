# HallofFameClassification

## Project Goal
This project builds a classification model to accurately predict if a MLB position player will be inducted into the Hall of Fame based on six inputs including `H` (career hits), `HR` (homeruns), `2B` (doubles), `batting_avg` (batting average), `SB` (stolen bases), and `career_all_star_games` (number of all star game appearances).

This is a classification problem because the desired prediction ('Inducted into the Hall of Fame?') is a categorical output. The player is either inducted ('Y') or not inducted ('N'). In this project, I fit and test two different classification models (decision tree classifier and random forest classifier) and evaluate which is most accurate.

## Data Source and Data Exploration
This data comes from the [Lahman Database](http://seanlahman.com/download-baseball-database/) which provides baseball statistics from 1871-2021. Specifically, I used the 'Batting', 'People', 'HoF' (Hall of Fame), and 'AllStar' .csv files from the database which include batting statistics (at bats, hits, singles, etc.), biographical information (date of birth, first name, height, etc.), hall of fame status, and number of all star appearences respectively. 

## Machine Learning Model Implementation and Evaluation
This project trained and fitted two different models, a decision tree classifier and a random forest classifier, on the following inputs: `H` (career hits), `HR` (homeruns), `2B` (doubles), `batting_avg` (batting average), `SB` (stolen bases), and `career_all_star_games` (number of all star game appearances). Prior to fitting the models, the data was split into training data and test data using a 75/25 percent split. Each model predicted the hall of fame status of players in the test data set with 97% accuracy. 
