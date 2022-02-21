# Scraping Teletherapy App Reviews from the Apple App Store

[Read the story on my portfolio site](http://juliaingram.github.io/therapy-apps)

## Goal
This project aims to investigate issues that teletherapy apps may present users by examining app store reviews. /why this is important, teletherapy growing/. In light of this, I scraped reviews from the Apple App Store and built a classifier to predict which 1- and 2- star reviews included reports of unfair charges, unresponsive therapists, or unsatisfactory care. 

## Findings
Reviews of the apps Talkspace and Cerebral since January 2020 stood out: while their reviews include success stories of people who were helped by the apps, they sit alongside a combined estimated 500 users who reported being charged unfairly and 375 who never heard from or experienced long wait times for therapists. 

## Data Collection
[My Jupyter notebook](/App%20Scraper.ipynb) contains the code behind my data collection and analysis.

Using the [app-store-scraper](https://pypi.org/project/app-store-scraper/) package, I scraped up to about 1,500 reviews from 10 teletherapy apps from the Apple App Store. (The 10 apps were Talkspace, Betterhelp, Wysa, Bloom, 7 Cups, Sanvella, WoeBot, Larkr, Youper and Cerebral). 

I first built a dataframe with the app names and ids from their URLs on the app store before running a loop to scrape the reviews for each one and save it to a dataframe. I then concatenated the dataframes together so all 9,175 reviews were in one place. 

## Analysis
To analyze the reviews, I built a classifier using the sklearn and pystemmer packages to predict whether they fell into one or more of three categories: an unfair charge, unresponsive therapist or an unsatisfactory one. 

Because some of the apps had so few reviews, for this part of the process, I only examined the six with the most reviews. I also built and ran the classifer only on 1- and 2- star reviews to filter for negative experiences. This made the total number of reviews examined 1,835. 

I pulled a random sample of 180 reviews (roughly 10%) from the total and manually tagged them with true/false values for whether they fit into one or more of the three categories. I then trained the model on the manually labeled data before running it on the other 90% of reviews to add predictions on each of the three categories.

I also analyzed the reviews using regular expressions to investigate reviews that mentioned insurance and reviews that mentioned keywords that might indicate suicidal ideation. 

## Skills & Growth
For this project, I learned multiple approaches and techniques for text analysis. Previously, I had only applied regular expressions to short bits of text, such as poems, and I had never built a classifer before. 

## Further Developments

To publish the most accuate information, I would use the model's predictions and its confifence in them to independently verify each of the reviews tagged in any of the three categories. Due to time constraints, I trusted the model for my reporting and specified in the story that these classifications were estimated by the algorithm.

A similar analysis could be performed on 4- and 5-star reviews to examine the benefits users experience. I could also dive into the less-often reviewed apps, which experienced different issues that were less noticeable due to the smaller number of reviews. 
