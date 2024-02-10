# Data 

This folder contains the data that we will be using in the analysis. 

### Primary dataset description

#### Description:

The primary dataset contains information on every college football game played from the 2013 - 2023 seasons. Each game will produce two records: one from each team’s perspective. 

It contains features such as where the game was played, point differential, what conference each team is in, and most importantly for us, what their ELO rating was after the game was played. See this wikipedia article for what the ELO rating means.

#### Size:

The final dataset will have roughly 150,000 rows and 23 columns. 

#### Location:

The dataset can be accessed via API call from this website:

[https://api.collegefootballdata.com/api/docs/?url=/api-docs.json](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json)

#### Format:

CSV

#### Access Method:

API

#### Files 

- games.csv 
    - games_manipulated.csv 
- recruits.csv
- roster.csv
- team_talent.csv
- teams.csv 

### Secondary dataset(s) description 

#### Description:

The secondary dataset contains information on the NFL draft. 

From this dataset we extract the key features: (1) the draft round #, (2) the draft pick #, and (3) the player’s name. 

We will then join this dataset to a team roster dataset from the same API as the primary dataset by using the player’s name to better determine what proportion of championship teams end up getting drafted. 

#### Size:

The final dataset will have roughly 3,000 rows and 31 columns. 

#### Location:

It is sourced from the following website:

[https://www.pro-football-reference.com/years/2022/draft.htm](https://www.pro-football-reference.com/years/2022/draft.htm)


#### Format:

CSV

#### Access Method:

Scraped from a website’s table

#### Files 

- draft.csv




