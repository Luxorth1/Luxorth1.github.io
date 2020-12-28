---
layout: post
title:      "Working with the Riot API and Riotwatcher"
date:       2020-12-28 17:47:00 +0000
permalink:  working_with_the_riot_api_and_riotwatcher
---



Working through the curriculum at Flatiron School I came to the final capstone project, deciding what topic to complete my project was difficult overall. However, I decided to push for a project that I not only found interesting, but had previous knowledge on the data sets, which made it fairly natural to work on. The idea of the project was to grab data from the Riot API and utilize machine learning tools in order to create a production models that would provide recommendations on how you can win more games.

One large portion of this project was the data collection. I utilized the Riot API for obtaining match data, the point of this blog is to provide a brief tutorial of a Python library which makes using the Riot API incredibly simple. More information for Riotwatcher can be found [here](https://riot-watcher.readthedocs.io/en/latest/).



## Getting Started

First thing is first, you will need to install the package. This is as simple as the code snippit below:

`pip install riotwatcher`

## Using the Package

As outlined in the documentation for Riotwatcher, you will need to do some initial research on the Riot API documentation website, as this will tell you what functions from Riotwatcher that you need. For example, my project utilized data from all players within the Diamond I ranking. The below code snippit will retrieve all of the players that are currently in the Diamond I rank.


`diamond_data = watcher.league.entries(my_region, 'RANKED_SOLO_5x5', 'DIAMOND', 'I')`

Let's dig into this line of code, there are a few variables that may not quite make sense yet. The watcher portion is an instance of the LolWatcher class, this object has built in functions that will hit all of the proper endpoints for League of Legends data specifically. Since Riot has multiple games, having a separation allows us to not have any data bleed, or confusion by hitting the wrong games endpoint which could potentially have a similar name. The my_region variable is important as all of the API endpoints are further separated by region, the API documentation outlines what the valid strings are for this section. For establishing an instance of the LolWatcher class you will use the below code: 

`watcher = LolWatcher(api_key)`

In order to get an API key you will need to create an account and go [here](https://developer.riotgames.com). Once you have this API key it will most likely be a development key, this means you are limited to 20 API requests per second and 100 per 2 minutes. It is possible to get a production key which will vastly increase the request limits that you are allocated. Riotwatcher also takes data returned from the APIs in a dictionary form, or list form. This eliminates the requirement for additional processing of the returned data. 

## Conclusion

Now that we are relatively familiar with using the Riotwatcher package, understanding what endpoints to obtain specific data is the next step. This is where the Riot API documentation comes into play, it is inclusive documentation with well defined endpoints. Cross-referencing both sets of documentation from Riot API and Riotwatcher will allow you to obtain just about any data that is required for your needs. Since the Riot data can be spread out between multiple endpoints to obtain the proper data, it would be recommended to create a diagram to keep track of the many endpoints and what data they return and can recieve as arguements.
