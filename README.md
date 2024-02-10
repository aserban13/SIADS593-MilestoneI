# SIADS593-MilestoneI

Team Project Proposal

College Football: How much talent do you need to recruit to win a national championship?

## 1. Team members 

Chris McAllister (chrismca)
Andreea Serban (aserban)

## 2. Project summary
Summarize your proposed project in a few sentences.
What is your proposed project and why are you proposing it? 
What are the question(s) you want to answer, or goal you want to achieve? 

There are hundreds of D1 college football teams, but only a handful of universities have won a championship in the past few years. What does it take to win it all, what edge do these teams have, and what constraints do other schools encounter? In this project, we're going to analyze the last 10 years of college football game outcomes and recruiting data to find out what type of players schools need to compete at the top of the sport.

We are proposing this project because we’re passionate about college football and love following the sport; however, there are many other reasons to pose this question. For instance, in the NIL (name, image, and likeness) era of college athletics, universities are trying to decide how much they need to spend in order to convince the most talented players to play for their team. Understanding the degree to which acquiring talented players impacts team success is central to the question. 


We hope to answer the following questions:
Do teams need to build talented rosters through recruiting in order to compete for championships? (Chris) (DONE!)
Is the college recruit rating a good indicator for their NFL draft. (Chris)  (DONE!)
What’s the minimum talent threshold required to compete at the top of the sport? (Andreea) 
Teams that were in the championship vs. the teams that weren’t in the championships, what % were drafted? (Andreea) 
Where do the best recruits come from and where do they go to school? (both) 


## 3. Datasets
Describe one primary dataset and at least one secondary dataset. If other secondary datasets will be used please describe them as well.
The proposed datasets should exhibit different features/columns and/or different access methods, e.g., *.csv file, *.json file, API retrieval, web scraping, etc. Different time periods, for example, with the same features/columns is not considered a different dataset. Remember, the focus of the project in this Milestone course is to give you the opportunity to practice your data manipulation skills, so feel free to challenge yourself.  
If you're unsure if your data sets are "different enough" describe the datasets and request a review via the #siads593_[semester]_001_project Slack channel.
Please note: all proposed datasets MUST be publicly available to all members of the class (students, instructors, course support personnel, etc.). Use of proprietary datasets for this project is not permitted.

### 3.1 Primary dataset description
Describe your primary dataset. How is the data collected and how will you access it? Please share what features in the dataset are relevant to your topic. At a minimum, include the following information:
Short description (i.e., 1-3 sentences) of its key features
Estimated size (in records and/or bytes)
Location (give the URL or other access method)
Format (CSV, JSON, etc.)
Access method (download, web scraping, API, etc.)

#### Description:

The primary dataset contains information on every college football game played from the 2013 - 2023 seasons. Each game will produce two records: one from each team’s perspective. 

It contains features such as where the game was played, point differential, what conference each team is in, and most importantly for us, what their ELO rating was after the game was played. See this wikipedia article for what the ELO rating means.

#### Size:

The final dataset will have roughly 150,000 rows and 23 columns. 

#### Location:

The dataset can be accessed via API call from this website:
https://api.collegefootballdata.com/api/docs/?url=/api-docs.json

#### Format:

CSV

#### Access Method:

API

### 3.2 Secondary dataset(s) description
Describe your secondary dataset(s). How is the data collected and how will you access it? Please share what features in the dataset(s) are relevant to your topic and describe the data types you’re expecting.  At a minimum, for each secondary dataset include the following information:
Short description (i.e., 1-3 sentences) of its key features
Estimated size (in records and/or bytes)
Location (give the URL or other access method)
Format (CSV, JSON, etc.)
Access method (download, web scraping, API, etc.)

#### Description:

The secondary dataset contains information on the NFL draft. 

From this dataset we extract the key features: (1) the draft round #, (2) the draft pick #, and (3) the player’s name. 

We will then join this dataset to a team roster dataset from the same API as the primary dataset by using the player’s name to better determine what proportion of championship teams end up getting drafted. 

#### Size:

The final dataset will have roughly 3,000 rows and 31 columns. 

#### Location:

It is sourced from the following website:

https://www.pro-football-reference.com/years/2022/draft.htm


#### Format:

CSV

#### Access Method:

Scraped from a website’s table


### 3.3 [ YES ] Affirm: datasets are public.
Please write YES in the above box to confirm that your primary and secondary datasets are accessible and available to your classmates and the instructional team.

## 4. Cleaning and manipulation
Describe how you will need to manipulate your datasets: how will you handle missing or anomalous data? How will you join your primary and secondary datasets? What cleaning and manipulation challenges, if any, do you anticipate?

[Please use this space for your response.  You may expand or contract this box as needed.]

### Joining datasets:

Join primary (game/team data) and secondary dataset (draft data) on school name and name of the player to get the number of college players for each school got drafted 

### Missing Data:

Missing Data - not all teams have ELO ratings. Most of these are only for the smaller teams in the Group of 5 conferences (ie non-power 5 conferences).
Only include the Power 5 conferences for more complete data.
There is only 1 record where the final game of the season contains a missing ELO value. 

Missing Data - the individual / player grain recruiting data will occasionally have missing data when showing what school the player committed to.
We’ll avoid using the individual data in the team-talent level analysis by pulling in an additional dataset from the same API as the first dataset..
For analyzing individual recruits, we’ll just just exclude players that are uncommitted and/or have missing commitment data.
The missing data tends to only be a problem with less talented players and for older datasets (especially pre-2020).

### Data Cleaning / Manipulation:

Data cleaning team logo URL column - remove outer brackets to only get the image URL
Championship flag - We will have to create a championship flag to indicate whether a team has gone to the championship
Change grain of the game dataset. Initially, there was just one record for each game played. We need to change it such that there will be two records for a given so that the features will contain information about the outcome from each team’s perspective.

## 5. Analysis
Describe any analyses you plan to undertake. For each, please give the technique or approach and briefly explain what you expect to learn from it. 


### Do teams need to build talented rosters through recruiting in order to compete for championships? (Chris)

Explore the correlation between recruiting and Regular season ELO rating of championship winning teams.
What outlier exists? Were there any teams that found success even with less talented rosters?
Expect to Learn: What is the relationship between a team’s talent pipeline and their success?

### What’s the minimum talent threshold required to compete at the top of the sport? (Andreea)

Explore the correlation between a college team’s ELO rating and the recruiting ratings 
Expect to learn: The higher the recruiting rating for a player, the higher the ELO rating for that college team they are playing for

### Where do the best recruits come from and where do they go to school? (both)
Explore the geographical location of the most talented players and visualize their school of choice by using their college of choice’s color.
Expect to learn: Is there a geographic location of players that are known for great football players? 

### Teams that were in the championship vs. the teams that weren’t in the championships, what % were drafted? (Andreea)
Explore correlation between a college team’s ELO rating and the % of players that make it to the draft 
Expect to learn: The higher the ELO rating, more players in the team are more likely to be drafted into the NFL 

### How predictive is recruiting ranking in NFL draft stock? (Chris)
Explore the correlation between a player’s recruiting rating (on a scale from 0 -1) and their rank in the NFL draft.
Expect to Learn: How reliable are recruiting ranking in identifying talent at the end of their college career.

## 6. Visualizations
Describe in 1-3 sentences at least two data visualizations that you plan to create. Include the chart type (e.g. bar chart, scatterplot, SPLOM, etc.) as well as the variables (features) you intend to plot. 


- Explore ELO as a metrics visual - does it do a good job at identifying the best teams in the sport? (EDA) - 
add in some references to what ELO is.
- Add visuals about how ELO is constructed from outside sources.
- Heatmap showing talent volume by the recruits hometown, and the school they ended up choosing. (Where do the best recruits come from and where do they go to school?)
- ELO Rating and Average Recruit Ranking scatter plot (with a hue for the teams that competed in the national championships)  (What’s the minimum talent threshold required to compete at the top of the sport? & Do teams need to build talented rosters through recruiting in order to compete for championships?)
- ELO Rating and % drafted scatter plot ( with a hue for the teams that competed in the national championships) (Teams that were in the championship vs. the teams that weren’t in the championships, what % were drafted?) 
- High School recruit rating vs NFL draft round heat map.


## 7. Ethical considerations
Does your choice of data raise any ethical issues? If so, briefly describe the concern and how you plan to mitigate it. 


- ELO ratings/Recruitment ratings could have some biases. 
- Negative incentives that can happen if we just use the recruiters ratings. Could lead to players paying recruiting scouts to rate them more highly. 
- ELO ratings is less reliable early in a season when teams have only played a view games due to a small sample size of leads
- Mitigate: Leverage games ELO rating after 10 games 
- Mitigate: While doing this analysis, we will be always aware of this potential bias and check on the ratings online to make sure there aren’t any glaring biases. 

## 8. Contributions
Indicate the contribution that each team member will make to the project.

- Handling missing values and exploratory data analysis (both)
- Analysis / Visualizations:
- Do teams need to build talented rosters through recruiting in order to compete for championships? (Chris) 
- Where do the best recruits come from and where do they go to school? (both) 
- What’s the minimum talent threshold required to compete at the top of the sport? (Andreea) 
- Teams that were in the championship vs. the teams that weren’t in the championships, what % were drafted? 
- High School recruit rating vs NFL draft round heat map
- Final Report and project submission (both)
- Managing Git (both)


## Changelog
(2022.07.27.1.CT) Update for 593
(2021.07.24.1.AW) Adjust title, number sections, simplify section headings, edit text
(2023.02.07.1.AW) Add in description of the project

