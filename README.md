# ✈️ British Airways Reviews - Web Scraping & Sentiment Analysis

![Python](https://img.shields.io/badge/Python-3.9-blue.svg)
![BeautifulSoup](https://img.shields.io/badge/Library-BeautifulSoup-brightgreen.svg)
![TextBlob](https://img.shields.io/badge/NLP-TextBlob-yellow.svg)
![VADER](https://img.shields.io/badge/NLP-VADER-red.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

---

> 📊 **Dive deep into customer feedback for British Airways using web scraping, natural language processing, and data visualization!**

---

## 🔍 Overview

This project scrapes customer reviews from [airlinequality.com](https://www.airlinequality.com/airline-reviews/british-airways), processes the textual data, applies sentiment analysis using **TextBlob** and **VADER**, and visualizes the insights with **matplotlib**, **seaborn**, and **WordCloud**.

---

## 🚀 Features

* 🌐 Web scraping with `requests` & `BeautifulSoup`
* 🧹 Text cleaning & preprocessing
* 💬 Sentiment analysis with `TextBlob` and `VADER`
* 📊 Visualizations: bar plots, word clouds, topic modeling
* 🔍 LDA-based topic discovery from reviews

---

## 📦 Libraries Used

```bash
pandas, numpy, matplotlib, seaborn, BeautifulSoup, requests,
wordcloud, TextBlob, vaderSentiment, sklearn, re, tensorflow (for fun)
```

---

## 🧾 Data Collection

```python
base_url = "https://www.airlinequality.com/airline-reviews/british-airways"
pages = 20
page_size = 100
```

> ✅ Extracts over **2000+ reviews** with metadata like aircraft, seat type, route, and recommendation status.

---

## 🧹 Text Preprocessing

```python
def clean_text(text):
    text = text.lower()
    text = re.sub(r'[^a-zA-Z\s]', '', text)
    text = re.sub(r'\s+', ' ', text).strip()
    return text
```

---

## 🧠 Sentiment Analysis

### Using TextBlob

```python
def get_textblob_sentiment(text):
    score = TextBlob(text).sentiment.polarity
    return "Positive" if score > 0 else "Negative" if score < 0 else "Neutral"
```

### Using VADER

```python
def get_vader_sentiment(text):
    score = SentimentIntensityAnalyzer().polarity_scores(text)['compound']
    return "Positive" if score > 0.05 else "Negative" if score < -0.05 else "Neutral"
```

---

## 📈 Sentiment Comparison

### 🔷 TextBlob vs 🔶 VADER

![Sentiment Comparison]("C:\Users\hyash\Downloads\Comparison of Sentiment Analysis Models.png")

---

## ☁️ Word Clouds

### ✅ Positive Reviews

![Positive Word Cloud](path/to/your/wordcloud_positive.png)

---

## 📌 Most Common Words

```python
vectorizer = CountVectorizer(stop_words='english')
word_counts = vectorizer.fit_transform(df['Cleaned Review'])
```

![Barplot](path/to/your/common_words_barplot.png)

---

## 🔍 Topic Modeling (LDA)

LDA was applied using `sklearn.decomposition.LatentDirichletAllocation`:

* Extracts **7 topics** based on review content
* Visualizes key terms per topic

```python
lda_model = LatentDirichletAllocation(n_components=7)
```

> Each topic is visualized using a horizontal bar chart and word cloud.

---

## 🎨 SVG Animation (Just for Fun)

```svg
<svg width="100%" height="100" viewBox="0 0 1000 100" xmlns="http://www.w3.org/2000/svg">
  <text x="0" y="50" font-size="50" fill="#3f51b5">
    Web Scraping + Sentiment Magic! 🚀
  </text>
</svg>
```

---

## 📁 Project Structure

```
📦british-airways-sentiment
 ┣ 📄 Web_Scraping_of_British_Airways.ipynb
 ┣ 📊 output_visuals/
 ┣ 📈 wordclouds/
 ┗ 📘 README.md
```

---

## 📚 Learnings

* Scraped paginated content using Python
* Cleaned and preprocessed raw text data
* Applied two different sentiment models
* Visualized insights using plots and clouds
* Discovered themes using topic modeling

---

## 👨‍💻 Author

**Your Name** — [Yash Handa](https://github.com/Handa1810)

> If you liked this project, feel free to ⭐ the repo!

---

## 🤝 Let's Connect

* GitHub: [Handa1810](https://github.com/Handa1810)
* LinkedIn: [yashhanda18](https://linkedin.com/in/yashhanda18)

---

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&duration=2500&pause=1000&color=3F51B5&center=true&width=435&lines=Thanks+for+visiting!;Happy+Scraping+%26+Analyzing!"/>
</p>
