# Football-Prediction
Spanish Football league La Liga prediction using Python using the machine learning method random forest
# La Liga Match Outcome Prediction

This project predicts football match results for Spain's La Liga using machine learning.  
It consists of two main stages:
1. **Data scraping & preprocessing** – Gathering historical match stats from public sources and engineering useful features.
2. **Model training & prediction** – Using a Random Forest classifier to predict upcoming match outcomes and estimate the league winner.

---

## 📂 Project Structure
```
.
├── scraptest-2.ipynb                # Data scraping, cleaning, feature engineering
├── Copy_of_Random_forest-3.ipynb    # Model training, predictions
├── README.md                        # Project documentation
```

---

## ⚙️ Requirements
Install dependencies before running the notebooks:
```bash
pip install soccerdata pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```

---

## 📊 Stage 1 – Data Scraping & Preprocessing (`scraptest-2.ipynb`)
- Uses [`soccerdata`](https://pypi.org/project/soccerdata/) to fetch match data from Understat and ESPN.
- Cleans and standardizes team names.
- Engineers additional features:
  - `Xg_diff` (expected goals difference)
  - `elo_diff` (Elo rating difference)
  - `Xpoint_diff` (expected points difference)
  - `ppda_ratio` (pressing intensity ratio)
  - `deep_comp_ratio` (deep completions ratio)
- Handles missing values and balances target classes using oversampling.
- Saves processed datasets:
  - `team_Match_dataB.csv`
  - `resampled_team_Match_dataB.csv`

---

## 🤖 Stage 2 – Model Training & Prediction (`Copy_of_Random_forest-3.ipynb`)
- Loads processed datasets.
- Trains a **Random Forest Classifier** to predict:
  - `1` → Home win  
  - `2` → Draw  
  - `0` → Away win
- Prepares upcoming fixture data using the same feature set.
- Generates predictions with probabilities.
- Aggregates results to simulate the full season and estimate potential league standings.

---

## 🚀 Usage
1. Run `scraptest-2.ipynb` to scrape and preprocess match data.
2. Run `Copy_of_Random_forest-3.ipynb` to:
   - Train the model.
   - Predict results for upcoming matches.
   - Estimate the league winner.

---

## 📈 Example Outputs
- **Match prediction**:
  ```
  Home: Barcelona | Away: Real Madrid
  Predicted: Home Win | Confidence: 78%
  ```
- **Season simulation**:
  ```
  1. Barcelona – 85 points
  2. Real Madrid – 83 points
  ...
  ```

---

## 📝 Notes
- The model is trained on past La Liga seasons; performance depends on the quantity & quality of scraped data.
- Elo ratings must be available or computed separately before training.
- You can adapt the code to other leagues supported by `soccerdata`.

---
## 📚 References & Documentation

- [soccerdata Documentation](https://soccerdata.readthedocs.io/) – Python library for accessing football data from multiple sources.
- [Understat API Info](https://understat.com/) – Public football stats website (used via `soccerdata`).
- [scikit-learn Documentation](https://scikit-learn.org/stable/) – Machine learning library for model training and prediction.
- [imbalanced-learn Documentation](https://imbalanced-learn.org/stable/) – Tools for handling imbalanced datasets.
- [pandas Documentation](https://pandas.pydata.org/docs/) – Data manipulation and analysis.
- [matplotlib Documentation](https://matplotlib.org/stable/contents.html) – Data visualization.
- [seaborn Documentation](https://seaborn.pydata.org/) – Statistical data visualization.
---
## 📜 License
This project is open-source and available under the MIT License.
