# California Housing Price Prediction Project

A machine learning regression project that predicts house prices in California using the California Housing dataset.

## Project Overview

This project implements a regression model to predict house prices based on various features such as location, population, median income, and other housing characteristics. The model is deployed as a Flask web application with an interactive UI for real-time price predictions.

## Features

- **Machine Learning Model**: Trained regression model using the California Housing dataset
- **Web Application**: Flask-based web interface for predictions
- **Data Preprocessing**: Includes data scaling and normalization
- **Visualization**: Box plots for data analysis and exploration
- **Interactive UI**: User-friendly HTML form for inputting house features

## Project Structure

```
california-housing-project/
├── app.py                      # Flask web application
├── Predicting_House_Prices.ipynb  # Jupyter notebook with model training
├── model.pkl                   # Trained ML model
├── scaling_new.pkl             # Data scaler for preprocessing
├── Income Dataset.csv          # Housing dataset
├── templates/                  # HTML templates folder
│   └── home.html              # Web interface
├── boxPlot.jpg                # Box plot visualization
├── boxPlotTestData.jpg        # Test data box plot
├── boxPlotTrainData.jpg       # Training data box plot
├── README.md                  # Project documentation
└── LICENSE                    # Apache-2.0 License
```

## Installation

### Prerequisites
- Python 3.7+
- pip (Python package manager)
- Git

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/priya6971/california-housing-project.git
   cd california-housing-project
   ```

2. **Create a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install flask numpy scikit-learn pandas jupyter
   ```

## Usage

### Running the Flask Web Application

1. Navigate to the project directory:
   ```bash
   cd california-housing-project
   ```

2. Start the Flask app:
   ```bash
   python app.py
   ```

3. Open your browser and go to:
   ```
   http://127.0.0.1:5000/
   ```

4. Enter house features in the form and click "Predict" to get price predictions

### Using the Jupyter Notebook

To explore the model training process and data analysis:

```bash
jupyter notebook Predicting_House_Prices.ipynb
```

## Dataset

**California Housing Dataset**
- **File**: Income Dataset.csv
- **Features**: 
  - Longitude
  - Latitude
  - Housing Median Age
  - Total Rooms
  - Total Bedrooms
  - Population
  - Households
  - Median Income
  - Median House Value (Target variable)

- **Samples**: 20,640 records
- **Time Period**: 1990 Census data

## Model Information

- **Algorithm**: Linear Regression / Ridge Regression (trained on California Housing dataset)
- **Input Features**: 8 numerical features
- **Output**: Predicted house price (in hundreds of thousands of dollars)
- **Performance**: Model evaluated using test data (see visualizations in boxPlot images)

## Key Files Explained

| File | Description |
|------|-------------|
| `app.py` | Flask application with routes for home page and prediction API |
| `model.pkl` | Serialized trained regression model |
| `scaling_new.pkl` | Serialized MinMaxScaler or StandardScaler for feature normalization |
| `Predicting_House_Prices.ipynb` | Complete ML pipeline: data loading, EDA, model training, evaluation |
| `home.html` | Web form interface for user input |

## API Endpoints

### GET `/`
Returns the home page with the prediction form.

### POST `/predict_api`
**Parameters** (form data):
- Takes 8 numerical input features corresponding to housing attributes

**Returns**:
- JSON response with predicted house price

**Example**:
```
POST /predict_api
Form data: Feature1=value1, Feature2=value2, ...
Response: {"prediction": 350000}
```

## Data Flow

```
User Input (HTML Form)
    ↓
Flask /predict_api endpoint
    ↓
Data Scaling (scaling_new.pkl)
    ↓
ML Model Prediction (model.pkl)
    ↓
JSON Response (Predicted Price)
```

## Dependencies

- **flask**: Web framework
- **numpy**: Numerical computations
- **scikit-learn**: Machine learning library
- **pandas**: Data manipulation
- **pickle**: Model serialization
- **jupyter**: Interactive notebook environment

## Results & Visualizations

The project includes visualization plots for data analysis:
- `boxPlot.jpg` - Overall box plot
- `boxPlotTrainData.jpg` - Training set distribution
- `boxPlotTestData.jpg` - Test set distribution

## Future Improvements

- Add more feature engineering techniques
- Implement cross-validation
- Experiment with ensemble methods (Random Forest, Gradient Boosting)
- Add error handling and input validation
- Deploy to cloud platform (AWS, Heroku, etc.)
- Add more visualization and analytics dashboards

## Contributing

Feel free to fork this project and submit pull requests for improvements.

## License

This project is licensed under the **Apache License 2.0** - see the LICENSE file for details.



## Acknowledgments

- California Housing Dataset from scikit-learn
- Inspired by regression prediction projects
- Community contributions and feedback

---

**Last Updated**: May 2026
