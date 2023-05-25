# World-of-Pokemon

## What can we learn by looking at pokemon data?
#### An exploratory data analysis of dataset from Kaggle:
https://www.kaggle.com/datasets/rounakbanik/pokemon
<br />
#### Team project at Data Science bootcamp at InfoShare Academy 
https://github.com/infoshareacademy/jdszr12-databenders

## Introduction



## Dataset

#### The dataset has 1 table with 801 rows and 40 columns, from which 7 will be excluded from further analysis as irrelevant (Abilities, base eggs steps, base happieness, classification, japanese name, percentage male and pokedox number). The following 18 columns contain a multiplier used to calculate the damage given pokemon will take in a combat against certain type of attack, which will be most probably given by attacking pokemon of certain type. So for example water pokemon will be more resistant to fire type of attack than for example electric type of attack. Next group of columns is related to combat statistics such as attack, defense, special attack, special defense, speed (attack speed), hp (hit points) and base total which is the summary of basic combat statistics. Than we have capture rate which describes how hard or easy it is to catch certain pokemon and experience growth which describes how fast pokemon can gain experience. The remaining columns describe parameters such as height, weight, generation the pokemon was released and if it belongs or not to legendary pokemon. Two very important columns are type 1 and type 2, type one describes primary type of pokemon, and type 2 secondary type of pokemon. Some pokemon are only single typed and some double typed, and combination of types can help in lowering the risk of damage by certain combination of multipliers. Then ofcourse there is a name column with a name of each pokemon.

## Data cleaning, preparation and transformation

#### Description


## Questions

#### Through the analysis of this dataset we want to shed light on the following issues:

#### 1. Generations, types and combat statistics frequency distributions (histograms and barplots)
##### -   Are pokemon evenly distributed across generations?
##### -   Are pokemon evenly distributed across types?
##### -   What is the frequency distribution of all combat statistics and other relevant features?
#### 2. Best types at certain combat statistics (boxplots):
##### -   how much better are legendary pokemon from non legendary pokemon??
##### -   what are the best types at attack, defense, attack speed, hit points?
##### -   are the best types at combat statistics the same for both legendary and non legendary pokemon?
##### -   is between type variation bigger than within type variation for most combat statistics?
#### 3. Feature correlations (scatterplots, heatmaps and clusterplot):
##### -   are there strong or weak between feature correlations?
##### -   which features influence each other?
##### -   how do pokemon types cluster together based on median of combat statistics and other features?
#### 4. Balanced or specialised (stacked barplots and spiderplots with plotly):
##### -   are there different types of strategies among pokemon?
##### -   what is the distribution of those strategies among poluplation?
#### -   are some strategies more frequent in some types than others?
#### 4.  Examples of 4 strongest and 4 weakest pokemon  (spiderplots with plotly)
<br />  

## Insights from the analysys 
###
### 1. Generations, types and combat statistics frequency distributions:
### Map Charts made in Tableau showing:
1) primary forest coverage in each state in 2001
2) percent of deforested area till 2020
3) deforested area till 2020

![obraz](https://github.com/Joanna-Reszka/Amazon_Deforestation/assets/97312220/d0841d65-2132-48d0-b4f4-12c4c856bfd6)

    
