# NBA MVP Award Forecasting Using Machine Learning

### 📌 Overview
This project builds a machine learning model that forecasts NBA MVP vote share for the upcoming season using historical player performance data. The objective is to estimate each candidate’s likelihood of winning the award and to rank players accordingly.

The project is fully reproducible and uses publicly available data from Basketball Reference.
Machine learning models including Linear Regression, Ridge Regression, Random Forest, XGBoost, and LightGBM are evaluated to determine the best predictive performance.

# 🧠 Approach

### 1. Data Acquisition
	Data was scraped using the Basketball Reference Scraper package and custom scraping logic. The following datasets were gathered for seasons 2000–2024:
	- Player advanced statistics
	- Total statistics
	- Team standings and win percentage
	- MVP vote share (target variable)

### 2. Feature Engineering

	The model uses a combination of:
	
	Player Performance Features
	- Points
	- Usage rate
	- Win Shares/48 minutes
	- Box Plus/Minus (BPM)
	- Value Over Replacement Player (VORP)
	- PER
	
	Team Context Features
	- Team wins
	- Total Wins
	- Conference seed
	
	Target Variable
	- MVP vote share

### 3. Modeling
	A variety of regression models were trained to predict continuous MVP vote share:
	- Linear Regression
	- Ridge Regression
	- Random Forest Regressor
	- XGBoost Regressor
	- LightGBM Regressor
	
	Models were trained using seasons 2000–2023, validated on the 2024 season, and then tested on the current 2025-26 NBA season statistics.
	
	The best model was selected using:
	- Mean Squared Error (MSE)
	- Ranking accuracy on the validation season


# 📘 Notes & Limitations
- Basketball Reference rate-limits requests (HTTP 429). A delay was added between scraping calls.
- Team names and advanced stats change formatting between seasons; additional cleaning was required.

# 📚 Sources & Citations
- https://www.basketball-reference.com
- https://github.com/basketball-reference-scraper
- NBA Advanced Stats Glossary
