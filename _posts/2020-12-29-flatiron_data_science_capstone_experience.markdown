---
layout: post
title:      "Flatiron Data Science Capstone Experience"
date:       2020-12-29 15:50:32 +0000
permalink:  flatiron_data_science_capstone_experience
---


## Introduction

Starting in March of 2020, just before the world became a crazy, uncertain place I decided to embark on my data science journey. Little did I know that this course would turn a slight interest of code and data into an almost obsession with learning new insights from data. Eight months of learning, projects, stress, and dealing with COVID-19 finally led to the culmination event, the Capstone Project. The idea of this project was to take a topic you are interested in and apply some level of Supervised Machine Learning to data in order to better understand the topic. I took it a step further and ended up creating an app that utilized my machine learning algorithm to provide insights, but we will get into those details later. I will go through the main milestones in my Capstone experience and outline some challenges that I ran into, and how I eventually overcame them.

## Week One

This was potentially the largest challenge of the entire 2 months of working on the project. I had to finally decide what my topic would be, I wanted to to be focused on the competitive gaming industry. However, this would prove to be a bit difficult due to the amount of video games that do not necessarily have an API to work with for data gathering. The original idea was to take a demo from Counter Strike: Global Offensive and parse this into raw data. This proved to be more difficult, and did not fit within the time constraints of the project. At this point it was the second or third week after doing research on the Counter Strike idea, I had to get moving. That is where I found the Riot API and decided to work with the data provided here.

## Data Collection

The data collection portion of this project was another challenge I ran into, I am a bit newer working with REST APIs so there was a ton of research to do while working with them. However, I managed to find a Python Library called Riotwatcher, which was a massive help. Limitations with the development API key means that I had to optimize my data collection process carefully to not exceed the limit on requests. I managed to eventually collect over 100,000 records which was eventually cleaned and reduced to roughly 30,000 records. This data collection portion took longer than anticipated since I was learning how to use APIs more at the time as well as trying to make sure I stay under the rate limits. It was a huge relief once I was able to successfully complete the data collection, which I then quickly saved it to a .csv file so I did not have to worry about additional collection.

## Modeling

This stage was not necessarily a challenge, but a pivot point for my project. Typically, students tend to use machine learning to predict or recommend a product to some degree. I decided to take a different approach to this project. Rather than what is described above, I decided to use my predictions to help improve a player gameplay instead of telling them who would win. Having this approach meant that I didn't necessarily want my model to predict the actual supervised outcome every time, the goal was to have the model take the wheel and determine who 'should' have won the game based on the data provided. From this data and the prediction provided from the model if the player 'should' have won the game, but in reality did not, our model goes through and provides custom recommendations based on important features determined by the model. This portion was a tad tricky to get right, I went through numerous iterations of recommendations and additional subject-matter research in order to provide proper advice that is meaningful and useful to the player.

## Productionizing

This portion was the most straightforward, but difficult, challenge throughout the project. I utilized Streamlit, a Python Library for creating web apps for Data Science. Using Streamlit was quite simple, however properly setting up the environment when I went to publish the app using Streamlit Share was a challenge. They provide this service which hosts your application, however you need to provide a requirements.txt, I used a python command to export this, however it did not match what I was using in my code so I spent a few days diagnosing why the app would work locally, but not online. Once this was resolved it was smooth sailing and then we had a nice productionized app using machine learning to help players improve gameplay.

## Conclusion

I have learned an massive amount during this project, from simple problem solving to using APIs to gather data and productionizing a machine learning app. This project has taken me leaps and bounds in my Data Science career from where I started, I am very excited to get into the weeds and explore other opportunites to grow as a Data Scientist.
