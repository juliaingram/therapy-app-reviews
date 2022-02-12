# Scraping Teletherapy App Data from the Apple App Store

This notebook uses the itunes_app_scraper and app_store_scraper packages to scrape the Apple app store for the reviews of 10 digital therapy apps to examine the benefits and shortfalls of mental health apps like these.

The apps were selected based on search results for "therapy" and "CBT" on the app store, as well as online reviews of mental health apps. The dataframe containing their names and ids is manually created here. Then, the packages are used to extract app information and app ratings.

Due to the biased nature of ratings, I will use these reviews to isolate potential problems or solutions unique to these apps, rather than trying to use them as a metric for efficacy. I will use regular expressions to do explore the following questions:

Do users experience quicker or slower response times than they might with in-person therapy or more traditional, appointment-based telehealth?
Do users experience issues navigating insurance claims with these apps? Do they report feeling unfairly charged?
If users feel the apps helped them, how?
