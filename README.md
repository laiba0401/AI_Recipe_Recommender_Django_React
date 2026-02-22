# AI-Powered Recipe Recommender (Django + React)

A sophisticated full-stack web application that leverages **Natural Language Processing (NLP)** and **Machine Learning** to suggest recipes based on user-inputted ingredients. The platform is integrated with the **YouTube Data API** to provide real-time video tutorials for every recommendation.

## 🧠 The AI Engine
The recommendation system is built on **Content-Based Filtering** principles:
* **Vectorization:** Raw ingredient strings are transformed into numerical feature vectors using `TfidfVectorizer`.
* **Similarity Logic:** A **Nearest Neighbors** model calculates the Cosine Similarity between the user's ingredients and a dataset of over 200,000 recipes.
* **Smart Ranking:** Results can be dynamically prioritized based on "Preparation Time" or "Average User Rating."

## 🛠 Tech Stack
* **Frontend:** React.js, Axios, Modern CSS
* **Backend:** Django REST Framework (DRF)
* **Machine Learning:** Scikit-learn, Pandas, NumPy, Pickle
* **API Integration:** YouTube Data API v3
* **Database:** SQLite (User accounts, favorites, and comments)

## 📦 Machine Learning Models
**Note:** Due to GitHub's file size limitations (>100MB), the serialized `.pkl` files are not stored in this repository.

**To run this project locally:**
1. Download the model files from: [INSERT YOUR GOOGLE DRIVE LINK HERE]
2. Place these files inside the `/core` folder:
   - `vectorizer (1).pkl`
   - `tfidf_matrix (1).pkl`
   - `nn_model (1).pkl`
   - `recipes_df (1).pkl`

## 🚀 Installation & Setup

### 1. API Configuration
1. Obtain a key from the [Google Cloud Console](https://console.cloud.google.com/).
2. Open `core/recommendation.py` and replace `"YOUR_API_KEY_HERE"` with your key.

### 2. Backend Setup (Django)
```bash
# From the main project root
python -m venv venv
.\venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

# Run migrations and start server
python manage.py migrate
python manage.py runserver
