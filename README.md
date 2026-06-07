# ali-reddit-sentiment-analysis


# 📣 Reddit Sentiment Analysis for Mayoral Campaign

This project performs real-time sentiment analysis on Reddit posts and comments mentioning key terms like "mayor", "Mussab", or "Ali", especially in the context of Jersey City. It evaluates public perception towards the mayoral candidate using natural language processing and sends automated alerts to a campaign Slack channel.

---

## 🧠 What It Does

- 📥 **Scrapes Reddit Comments** 
 Collects up to 1,000 of the most recent comments from the `r/jerseycity` subreddit using the PRAW API.

- 🔍 **Keyword Filtering** 
 Filters comments based on key terms related to the campaign, including:
 - `mayor`
 - `mussab`
 - `ali`
 - `boe`

- 🧼 **Text Cleaning** 
 Removes:
 - Mentions (`@username`)
 - URLs
 - Hashtags
 - Newlines and punctuation

- 📊 **Sentiment Analysis** 
 Uses **TextBlob** to calculate:
 - **Polarity** (positive vs negative)
 - **Subjectivity** (factual vs opinionated)
 - Labels each comment as `Positive`, `Neutral`, or `Negative`

- 🚨 **Slack Alert Integration** 
 After sentiment analysis, the script pushes a summary (e.g., count of positive/negative mentions) to a designated Slack channel for real-time campaign monitoring.

---

## 📦 Tech Stack

| Component | Tool/Library |
|------------------|------------------------|
| Reddit Scraping | `praw` |
| Text Processing | `re`, `TextBlob` |
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib` |
| Alerts | `Slack Webhooks` (optional)

---

## 📈 Sample Output

| Sentiment | Count |
|-----------|-------|
| Positive | 43 |
| Neutral | 19 |
| Negative | 9 |

An example bar chart is generated to visualize sentiment distribution.

---

## 🛠️ Setup

```bash
pip install pandas numpy praw textblob matplotlib
```

Set up your `praw.Reddit(...)` object with proper credentials:
```python
reddit = praw.Reddit(
 client_id='YOUR_CLIENT_ID',
 client_secret='YOUR_SECRET',
 user_agent='YOUR_APP_NAME'
)
```

Add your Slack webhook URL in the alert script to enable real-time campaign alerts.

---

## 📌 Summary

This project automates public sentiment tracking around a local mayoral campaign using Reddit data and alerts your team via Slack when major sentiment changes occur. It's a lightweight but tool for campaign intelligence and voter pulse.

