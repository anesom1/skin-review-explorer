# 🧴 Skincare Review Explorer & AI Sentiment Analyzer

An interactive web application and aspect-based sentiment analysis tool built for skincare reviews. This project explores customer feedback across specific product attributes—**texture, scent, breakouts, irritation, efficacy, packaging, and value**—using a fine-tuned Multi-Head DistilBERT model.

---

## 🚀 Live Demo
- **App URL:** [Check out the live app here](https://skin-review-explorer-avxvp6kng5tozxvacx3hrr.streamlit.app)

---

## 📊 Project Overview & Pipeline

The project follows a rigorous end-to-end Data Science & Machine Learning lifecycle across four distinct phases (available in the `notebooks/` directory):

1. **Phase 1: Data Exploration & Preprocessing**[cite: 2]
   - **Raw Data:** Utilized a massive corpus of skincare product reviews (~944k rows) containing text, product details, ratings, and skin-type metadata[cite: 2].
   - Handled missing values, cleaned text data, and filtered records for downstream tasks.

2. **Phase 2 & 3: Annotation & Model Training (PyTorch & Transformers)**[cite: 2]
   - Created a labeled sample dataset to supervise aspect-level sentiment classification.
   - Built a **Multi-Head Classifier** on top of `distilbert-base-uncased` utilizing the `[CLS]` token representation followed by independent linear heads for each of the 7 skincare aspects[cite: 2].
   - Trained the model to predict 3 classes per aspect: `0` (*Not mentioned*), `1` (*Positive*), and `2` (*Negative*)[cite: 2].

3. **Phase 4: Full-Dataset Inference & Aggregation**[cite: 2]
   - Executed batched inference over the entire clean dataset (~944k reviews) using the trained checkpoint (`aspect_sentiment_model_final.pt`)[cite: 2].
   - Attached predictions back to the dataset (`skincare_reviews_with_predictions.csv`) and aggregated metrics at the product × skin-type level for rapid querying in the web app[cite: 2].

---

## 🛠️ Tech Stack
- **Python, Pandas, NumPy:** Data manipulation and transformation.
- **PyTorch & Hugging Face Transformers:** Deep learning model architecture, custom dataset loaders, and tokenization (`AutoTokenizer`).
- **Streamlit:** Interactive web application framework and multi-tab user interface.
- **Plotly:** Dynamic, stack-barmode visualizations of sentiment distributions.

---

## 📂 Repository Structure
- `app_final.py`: Main Streamlit multi-tab application (Dashboard + Live AI Analyzer).
- `requirements.txt`: Python package dependencies.
- `notebooks/`: Jupyter notebooks detailing phases 1 through 4 of the data science lifecycle.

---

## 💻 How to Run Locally

If you want to run this application on your local machine, follow these steps:

### 1. Clone the repository
```bash
git clone [https://github.com/anesom1/skin-review-explorer](https://github.com/anesom1/skincare-review-explorer.git)
cd skincare-review-explorer 
```

### 2. Create and activate a virtual enviroment
```bash 
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install dependencies
```bash 
pip install -r requirements.txt
```

### 4. Run the Streamlit application
```bash 
python -m streamlit run app.py
```