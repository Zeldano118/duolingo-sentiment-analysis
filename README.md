# duolingo-sentiment-analysis

Sentiment analysis of English Google Play reviews of Duolingo. The plan is to label the reviews by star rating, then compare Naive Bayes, Logistic Regression and SVM on them.

So far the repo has only the first step, collecting the data.

## What's here

`notebooks/01_scraping.ipynb` pulls the 1,000 newest English reviews of `com.duolingo` from the US Play Store with google-play-scraper. It keeps five columns (`reviewId`, `content`, `score`, `thumbsUpCount`, `at`), saves them to `data/raw/duolingo_raw.csv` and looks at how the ratings are spread.

In the run saved in the notebook, the reviews were posted on 11 and 12 May 2026. 72.4% gave 5 stars, 12.6% 4 stars, 4.7% 3 stars, 2.4% 2 stars and 7.9% 1 star, so the data leans heavily positive.

`data/` is in `.gitignore`, so the CSV isn't in the repo. Running the notebook again fetches whatever the newest reviews are at that moment.

## Running it

Open the notebook in Google Colab with the button at the top and run the cells in order. To run it locally instead:

```
pip install google-play-scraper pandas matplotlib
```

## Still to do

Preprocessing, labeling by star rating, and training and comparing the three models.
