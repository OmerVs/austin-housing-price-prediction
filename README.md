# Austin Housing Price Prediction

A machine learning project predicting housing prices in Austin, Texas using advanced feature engineering and gradient boosting algorithms.

## 🎯 Project Overview

This project tackles housing price prediction for 6,700+ residential properties in Austin using comprehensive feature engineering and model comparison. Our CatBoost model achieved **$160 RMSE** using 5-fold cross-validation.

## 📊 Dataset

- **Size**: 6,784 properties (2019-2020)
- **Original Features**: 35
- **Engineered Features**: 97 (total: 132)
- **Target**: House price (latestPrice)
- **Range**: $5.8K - $6.25M (mean: $486K)

## 🔧 Feature Engineering

Expanded from 35 to 132 features across multiple categories:

### 1. Ratio Features
- `sqft_per_bedroom` - Layout efficiency
- `bath_bed_ratio` - Quality indicator
- `lot_to_living_ratio` - Land utilization
- `room_density` - Space optimization

### 2. Location Features
- Distance to downtown, UT campus, airport
- Proximity scores (normalized distances)
- Cardinal directions from downtown
- Geographic density analysis

### 3. Temporal Features
- House age and age categories
- Condition flags (new/old, extreme sizes)
- Recent construction indicators

### 4. Text Mining Features (75 total)
- Luxury keywords (granite, marble, custom)
- Condition indicators (move-in ready)
- TF-IDF with dimensionality reduction
- Sentiment analysis ratios

### 5. School & Quality Features
- School rating tiers (Excellent, Above Average)
- Teacher-student ratios
- Property condition indicators
- Size categories and luxury scores

## 🤖 Model Performance

| Rank | Model | CV RMSE | ±Std |
|------|-------|---------|------|
| **1** | **CatBoost** | **$160** | **±$29** |
| 2 | HistGradientBoosting | $163 | ±$26 |
| 3 | LightGBM Optimized | $163 | ±$27 |
| 4 | Random Forest Optimized | $163 | ±$28 |
| 5 | Gradient Boosting Tuned | $166 | ±$25 |
| 6 | Extra Trees Optimized | $167 | ±$28 |
| 7 | XGBoost Optimized | $172 | ±$25 |

### Why CatBoost?
- **Ordered Boosting**: Reduces overfitting vs traditional gradient boosting
- **Categorical Handling**: Built-in target encoding prevents data leakage
- **Feature Selection**: Automatic best feature selection at each split
- **Robust Defaults**: Minimal tuning required

## 📈 Key Findings

### Feature Importance
1. **Living Area** (11.6) - Strongest predictor
2. **Location Features** - Distance to downtown/UT campus crucial
3. **Engineered Features** - Combined metrics (lotSize_bathrooms: 3.4)
4. **School Ratings** - Significant impact on valuations
5. **Text Mining** - Description features contributed value

### Austin-Specific Insights
- Downtown proximity commands premium
- UT campus proximity drives demand
- Luxury keywords (granite, marble, custom) significantly impact valuations
- Geography-driven housing market confirmed

## 🛠️ Technologies Used

- **Python 3.x**
- **Machine Learning**: CatBoost, LightGBM, XGBoost, scikit-learn
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn, folium
- **Text Processing**: TF-IDF, sentiment analysis
- **Validation**: 5-fold cross-validation

## 📁 Repository Structure
```
austin-housing-prediction/
│
├── RunCode.ipynb          # Main Jupyter notebook with all code
├── Report.pdf             # Detailed project report
├── README.md              # This file
└── requirements.txt       # Python dependencies
```

## 🚀 Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Running the Analysis
1. Clone the repository
2. Install dependencies
3. Open `RunCode.ipynb` in Jupyter
4. Run all cells to reproduce results

## 👥 Team

- Ishrak Wasif Udoy
- Nikhil Kumar
- Mohar Chaudhuri
- Pavithran Murugan

## 📝 Project Context

Completed as part of MS Business Analytics coursework at UT Austin McCombs School of Business.

## 📄 License

This project is available for educational and reference purposes.

## 🙏 Acknowledgments

- UT Austin McCombs School of Business
- Austin housing market data providers
- Open-source ML community

---

**Note**: This project demonstrates practical application of feature engineering, model selection, and validation strategies for real estate price prediction.
