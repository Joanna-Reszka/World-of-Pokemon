# World-of-Pokemon

## What can we learn by looking at pokemon data?
#### An exploratory data analysis of dataset from Kaggle:
https://www.kaggle.com/datasets/rounakbanik/pokemon
<br />
#### Team project at Data Science bootcamp at InfoShare Academy 
https://github.com/infoshareacademy/jdszr12-databenders

## Introduction



## Dataset

#### The dataset consistsof 1 table with 801 records and 40 columns. 7 were excluded from further analysis as irrelevant ('abilities', 'base eggs steps', 'base happieness', 'classification', 'japanese name', 'percentage male' and 'pokedox number'). The 'name' column with a name of each pokemon was used as an index.The following 18 columns contain a multiplier used to calculate the damage given pokemon will take in a combat against certain type of attack, which will be most probably given by attacking pokemon of certain type. So for example water pokemon will be more resistant to fire type of attack than for example electric type of attack. Next group of columns is related to combat statistics such as 'attack', 'defense', 'special attack', 'special defense', 'speed' (attack speed), 'hp' (hit points) and 'base total' (the summary of basic combat statistics). Column 'capture rate' describes how hard or easy it is to catch certain pokemon and 'experience growth' describes how fast pokemon can gain experience. The remaining columns describe parameters such as 'height', 'weight', 'generation' the pokemon was released and if it belongs or not to 'legendary' pokemon. Two very important columns are 'type 1' and 'type 2', type one describes primary type of pokemon, and type 2 secondary type of pokemon. There are 18 types of pokemon. Some pokemon are only single typed and some double typed, and combination of types can help in lowering the risk of damage by certain combination of multipliers. 

## Data cleaning, preparation and transformation

#### Most missing values (384) were present at "type2" column, because many pokemon are only of single type, the missing valueswere replaced with "None". Remaining two columns with missing values were "Height_m" and "Weight_kg", and 20 missing values are for the same pokemon for both columns. They were replaced with median weight and height for given type. 
#### In order to obtain one column with each type for each pokemon dataframe was transformeed by duplicating each row and replacing duplicated "type1" value with "type2" value. This allowed for grouping values of combat statistics such as "base_total", "attack", "defence", "speed", "hit_points", "capture_rate", "Weight", "height" by type.

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
frequency distribution of pokemon by primary and secondary type with distinction between 7 generations 

![obraz](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/758cf2f9-76b2-446c-b395-0406967d4f4d)

    
