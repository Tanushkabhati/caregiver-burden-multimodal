# Caregiver Burden Analysis - Multimodal Dataset

## 📌 Project Overview

This project analyzes **caregiver burden** using multimodal data sources including **text, images, and metadata** from social media platforms and publicly available datasets. The goal is to understand the emotional, physical, and psychological challenges faced by caregivers through sentiment analysis, emotion detection, and topic modeling.

---

## 🎯 Objectives

1. **Collect Data** from multiple sources:
   - 🐦 **Twitter/X**: Caregiver discussions and experiences
   - 📊 **Kaggle**: Public health and caregiver datasets
   - 📸 **Images**: Visual content related to caregiving

2. **Analyze Caregiver Burden** through:
   - Sentiment Analysis (Positive/Negative/Neutral)
   - Emotion Detection (Joy, Sadness, Anger, Fear, etc.)
   - Topic Modeling (Common themes in caregiver discussions)
   - Named Entity Recognition (Diseases, medications, relationships)

3. **Build ML Models** to:
   - Classify caregiver sentiment
   - Predict burden levels
   - Identify at-risk caregiver populations

---

## 📁 Project Structure

```
caregiver-burden-multimodal/
├── README.md                           # Project documentation
├── requirements.txt                    # Python dependencies
├── .gitignore                          # Ignore sensitive files
│
├── data/
│   ├── raw/                            # Raw data from APIs
│   │   ├── twitter_raw/
│   │   ├── kaggle_raw/
│   │   └── metadata/
│   ├── processed/                      # Cleaned & processed data
│   ├── external/                       # External datasets
│   └── README.md                       # Data documentation
│
├── notebooks/
│   ├── 01_twitter_data_collection.ipynb
│   ├── 02_kaggle_data_collection.ipynb
│   ├── 03_data_exploration.ipynb
│   ├── 04_preprocessing.ipynb
│   ├── 05_feature_engineering.ipynb
│   ├── 06_model_training.ipynb
│   └── 07_visualization.ipynb
│
├── src/
│   ├── __init__.py
│   ├── data_collection.py              # API data collection functions
│   ├── preprocessing.py                # Data cleaning & preprocessing
│   ├── feature_engineering.py          # Feature extraction
│   ├── models.py                       # ML models
│   └── utils.py                        # Utility functions
│
├── models/                             # Trained models & checkpoints
│   └── .gitkeep
│
├── reports/                            # Analysis reports & results
│   ├── figures/                        # Charts & visualizations
│   └── analysis.md
│
└── config/
    └── config.yaml                     # Configuration file
```

---

## 🔧 Technologies Used

| Technology | Purpose |
|-----------|---------|
| **Python 3.9+** | Programming language |
| **Tweepy** | Twitter API interaction |
| **Kaggle API** | Dataset download |
| **Pandas** | Data manipulation |
| **NumPy** | Numerical computing |
| **NLTK** | Natural language processing |
| **TextBlob** | Sentiment analysis |
| **Transformers** | Transformer-based models (BERT, etc.) |
| **Scikit-learn** | Machine learning models |
| **Matplotlib & Seaborn** | Data visualization |
| **Jupyter** | Interactive notebooks |

---

## 📊 Data Sources

### 1. **Twitter/X API** 🐦
- **Keywords**: #caregiver, #caregiverburden, #familycaregiver
- **Data collected**: Tweets, likes, retweets, user profiles
- **Language**: English
- **Time period**: Recent tweets (last 6-12 months)

### 2. **Kaggle Datasets** 📊
- Mental health datasets
- Healthcare burden studies
- Social media sentiment datasets
- Public health data

### 3. **Images** 📸
- Infographics about caregiving
- Visual content from social media
- Healthcare-related images

---

## 📋 Setup & Installation

### **Step 1: Clone the Repository**
```bash
git clone https://github.com/Tanushkabhati/caregiver-burden-multimodal.git
cd caregiver-burden-multimodal
```

### **Step 2: Create Virtual Environment (Optional but Recommended)**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### **Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **Step 4: Set Up API Credentials**
Create a `.env` file in the root directory:
```
TWITTER_BEARER_TOKEN=your_twitter_bearer_token
KAGGLE_USERNAME=your_kaggle_username
KAGGLE_KEY=your_kaggle_api_key
```

⚠️ **IMPORTANT**: Never commit `.env` file to GitHub! It's in `.gitignore` for security.

### **Step 5: Configure Kaggle API**
Place `kaggle.json` in `~/.kaggle/` directory (see requirements.txt notes)

---

## 📚 Notebooks Overview

| Notebook | Description |
|----------|-----------|
| **01_twitter_data_collection** | Collect tweets using Twitter API v2 |
| **02_kaggle_data_collection** | Download datasets from Kaggle |
| **03_data_exploration** | Exploratory Data Analysis (EDA) |
| **04_preprocessing** | Clean, normalize, and prepare data |
| **05_feature_engineering** | Extract relevant features |
| **06_model_training** | Train ML/DL models |
| **07_visualization** | Create visualizations & insights |

---

## 🚀 Quick Start

### Run Data Collection:
```python
# In Jupyter Notebook
from src.data_collection import TwitterDataCollector, KaggleDataCollector

# Collect Twitter data
twitter_collector = TwitterDataCollector()
tweets = twitter_collector.collect_tweets(keywords=['#caregiver'], limit=1000)

# Collect Kaggle data
kaggle_collector = KaggleDataCollector()
kaggle_collector.download_dataset('dataset-name')
```

### Run Analysis:
```python
# In Jupyter Notebook
from src.preprocessing import DataPreprocessor
from src.feature_engineering import FeatureExtractor

# Preprocess data
preprocessor = DataPreprocessor()
clean_data = preprocessor.clean_text(tweets)

# Extract features
extractor = FeatureExtractor()
features = extractor.extract_sentiment(clean_data)
```

---

## 📈 Expected Analysis Output

✅ **Sentiment Distribution**
- Percentage of positive, negative, neutral sentiments
- Trend analysis over time

✅ **Emotion Analysis**
- Common emotions in caregiver discussions
- Emotion intensity scores

✅ **Topic Modeling**
- Top 10-15 themes in caregiver discussions
- Keywords for each topic
- Topic prevalence

✅ **Burden Indicators**
- Stress-related keywords and phrases
- Health concerns mentioned
- Support needs identified

✅ **Visualizations**
- Word clouds
- Sentiment timelines
- Topic distribution charts
- Emotion heatmaps
- Geographic distribution (if available)

---

## 📝 Data Ethics & Privacy

✅ **Twitter Data**: Public tweets only, respecting Twitter's ToS  
✅ **User Privacy**: No personal identification data stored  
✅ **Consent**: Using publicly available, consented data  
✅ **Responsible AI**: Results used to help caregivers, not discriminate  

---

## 🔐 Security Notes

⚠️ **API Keys & Tokens**:
- Store in `.env` file (added to `.gitignore`)
- Never commit credentials to GitHub
- Regenerate keys if accidentally exposed

⚠️ **Data Storage**:
- Raw data stored locally, not on GitHub
- Large files in `/data/raw/` folder
- Use `.gitignore` for data files

---

## 📖 References & Resources

### APIs:
- [Twitter API v2 Documentation](https://developer.twitter.com/en/docs/twitter-api)
- [Kaggle API Documentation](https://github.com/Kaggle/kaggle-api)

### Libraries:
- [Tweepy Documentation](https://docs.tweepy.org/)
- [NLTK Book](https://www.nltk.org/book/)
- [Scikit-learn](https://scikit-learn.org/)
- [Transformers (HuggingFace)](https://huggingface.co/docs/transformers/)

### NLP & Sentiment Analysis:
- [TextBlob](https://textblob.readthedocs.io/)
- [VADER Sentiment Analysis](https://github.com/cjhutto/vaderSentiment)
- [HuggingFace Models](https://huggingface.co/models)

---

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👨‍💻 Author

**Tanushka Bhati**  
GitHub: [@Tanushkabhati](https://github.com/Tanushkabhati)

---

## 📧 Contact & Support

For questions or issues:
- Open an issue on GitHub
- Check existing documentation in `/docs`
- Review notebook comments for detailed explanations

---

## 🙏 Acknowledgments

- Twitter/X for API access
- Kaggle for datasets
- NLP community for open-source tools
- Caregiver organizations for inspiring this research

---

## 📅 Last Updated

June 2026

---

**Happy researching! 🎉 Together, let's understand and support caregivers better.**
