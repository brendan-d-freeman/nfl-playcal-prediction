# nfl-playcall-prediction

## Abstract

#### Introduction

In the last 10 years, advanced analytics have taken off in sports. As one of the later adopters in the big 4 US sports, the NFL is just now starting to discover the power of analytics and data, but they have one of the most unique cases to work with in analytics. Unlike sports like basketball where gameplay is continuous and often relies on offensive and defensive play systems, football stops after every play allowing play callers the opportunity to consider the current situation before making a decision. Coaches consider time left in the game, the score, how many years until a first down or score, field position, and who they are playing before every play call. How would a coach’s decision change if he could predict what the other coach was going to call? Lots of time has been invested into determining which plays are most successful in which situations, but can the reverse be understood of what coaches tend to call in certain situations.

#### Solution

I believe that what play a coach is going to call in the NFL can be predicted with a high level of accuracy. Using the CRISP-DM methodology, I’ll be experimenting with several different approaches to find what’s the best option to predict the next play. I will look at traditional machine learning approaches like Random Forest and other classification methods.

#### Data Sources and Feature Engineering

The best data source available today is a detailed NFL play-by-play dataset posted on Kaggle that compiles all the game data from 2009-2018 into a CSV. The dataset is generated using the nflscrapR module in R to gather all of the data from publicly available data sources. My plan is to start with the Kaggle dataset and use the nflscrapR to get the data for the 2019 season as well. From there, I want to add data from outside sources to generate more data. For instance, the nflscrapR data does not consider who was calling the plays. My working hypothesis is that adding the head coach and offensive/defensive coordinator for each play will help increase the accuracy. This can be tested as NFL coaches and coordinators often move around teams. For instance, Bruce Arians is the former head coach of the Arizona Cardinals from 2013-2017. He has recently taken over as head coach of the Tampa Bay Buccaneers. It makes sense that Bruce’s play call tendencies as head coach in Arizona would be a better indicator for the Tampa Bay Bucaneers today than the Tampa Bay Bucaneers under a completely different coaching staff.

#### Background and Similar Research

Unsurprisingly, people have looked at predicting NFL play calls before. The two articles I was able to find documenting the results of training a model to predict plays were Jacob Davis’s article on Towards Data Science and Ahmed Cheema on the Spax. Of the two, Jacob had the higher performing model with a 77% accuracy across all teams. My goal is to set a new benchmark with a better accuracy than both of their models.

Related research was done by Blake Atkinson on Towards Data Science who looked at the impact of head coaches and quarterbacks on the play call (something I mentioned as a new feature above). His research found that the head coach and quarterback (most important skill position in football) do make a difference on what play is going to be called next.

#### Challenges

The biggest challenge is going to be how to create a model that can perform well for all coaches. As human beings, coach behaviors are all slightly different from each other, which will ultimately impact the decision they make. In order to get a higher level of accuracy, the model will have to take these differences into consideration when predicting the play. Furthermore, another difficulty with the individuality of coaches where real value can be added is how to accurately predict plays when a team hires a coach that has never coached in the NFL before. For instance, last year the Arizona Cardinals hired Kliff Kingsbury from Texas Tech instead of an experienced NFL coach. Without any historical NFL data, how can the model build an accurate profile of Kliff’s play calling tendencies? My hope is to explore possible abstractions when it comes to coaches to see if things like years of experience, record, and background can help the model perform well even for new coaches.

#### Future Work

In the future, I would like deep learning approaches like RNN and LSTM. I'm also hoping to use Dash and Flask in order to host my findings publicly, allow people to input their own scenarios into the model, and visualize the output and data. When the season is available, I would also like to post summaries of how my model compared to the real play calls.