# 🧴 Skincare Review Explorer & AI Sentiment Analyzer

This project is about analyzing skincare reviews and understanding what customers think about different aspects of a product. I built a machine learning model that looks at reviews and predicts whether customers have positive or negative opinions about things like texture, scent, breakouts, irritation, effectiveness, packaging, and value for money.

I also created a Streamlit web app where users can explore the results and try the sentiment analyzer themselves.

---

## 🚀 Live Demo

**Try the app here:** [Skincare Review Explorer](https://skin-review-explorer-avxvp6kng5tozxvacx3hrr.streamlit.app)

---

## 📊 Project Overview

The project was divided into four main phases, which are documented in the `notebooks/` directory.

### 1. Data Exploration and Preprocessing

- Started with a dataset containing around 944,000 skincare reviews.
- Explored the data, checked for missing values, and cleaned the review text.
- Prepared the data for annotation and model training.

### 2. Data Annotation

- Created a labeled sample of reviews to train the model.
- Added sentiment labels for seven skincare aspects: texture, scent, breakouts, irritation, efficacy, packaging, and value.

### 3. Model Training

- Used PyTorch and Hugging Face Transformers to fine-tune a DistilBERT model.
- Built a multi-head classifier with a separate prediction head for each skincare aspect.
- The model predicts one of three classes for each aspect:
  - `0` – Not mentioned
  - `1` – Positive
  - `2` – Negative

### 4. Predictions and Results

- Used the trained model to generate predictions for around 944,000 reviews.
- Saved the results in `skincare_reviews_with_predictions.csv`.
- 
---

## 🛠️ Technologies Used

- **Python, Pandas, NumPy** – Working with and preparing the data.
- **PyTorch** – Building and training the model.
- **Hugging Face Transformers** – Using and fine-tuning DistilBERT.
- **Streamlit** – Building the web application.
- **Plotly** – Creating interactive charts to explore sentiment results.

---

## 📂 Project Structure

- `app_final.py` – Main Streamlit application, including the dashboard and live AI analyzer.
- `requirements.txt` – Required Python packages.
- `notebooks/` – Jupyter notebooks covering the different project phases.

---

## 💻 How to Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/anesom1/skincare-review-explorer.git
cd skincare-review-explorer
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

On Windows, activate it with:

```bash
venv\Scripts\activate
```

### 3. Install the required packages

```bash
pip install -r requirements.txt
```

### 4. Start the application

```bash
python -m streamlit run app_final.py
```

The app should open in your browser. You can then explore the dashboard and test the sentiment analyzer.

