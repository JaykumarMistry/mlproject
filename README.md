# Machine Learning Model Deployment with AWS for Student Performance Prediction

## Overview
This project involves the end-to-end implementation of a machine learning pipeline for predicting student performance based on various features such as gender, race/ethnicity, parental education level, and test scores. The pipeline includes data preprocessing, model training, evaluation, and deployment on AWS Elastic Beanstalk using a CI/CD pipeline. The project is designed to be scalable, modular, and production-ready.

## Features
- **Data Preprocessing**: Cleaning and transforming input data using a custom preprocessing pipeline.
- **Model Training**: Training multiple machine learning models with hyperparameter tuning and selecting the best-performing model.
- **Prediction Pipeline**: Enabling real-time predictions using the trained model.
- **Web Application**: A Flask-based web application to interact with the pipeline.
- **Deployment**: Automating deployment using AWS Elastic Beanstalk and CI/CD pipelines.

## Project Structure
```
├── src
│   ├── components
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   ├── model_trainer.py
│   ├── exception.py
│   ├── logger.py
│   ├── pipeline
│   │   ├── predict_pipeline.py
│   ├── utils.py
├── templates
│   ├── index.html
│   ├── home.html
├── application.py
├── README.md
├── requirements.txt
├── setup.py
├── artifacts
│   ├── model.pkl
│   ├── preprocessor.pkl
```

## Key Components

### 1. `src/components`
- **`data_ingestion.py`**: Handles the ingestion of raw data into the pipeline.
- **`data_transformation.py`**: Applies preprocessing steps, including scaling and encoding.
- **`model_trainer.py`**: Implements the training of multiple machine learning models and selects the best one based on evaluation metrics.

### 2. `src/pipeline`
- **`predict_pipeline.py`**: Provides a streamlined process for real-time predictions using the trained model and preprocessor.
  - `PredictPipeline`: Loads the trained model and preprocessor for making predictions.
  - `CustomData`: Converts input data into a format compatible with the preprocessor.

### 3. `app.py`
- Flask application to interact with the prediction pipeline. Includes:
  - Home page to display information.
  - Form-based user input to make predictions.

### 4. `src/utils.py`
- Contains utility functions for:
  - Saving and loading serialized objects.
  - Evaluating models with metrics like R-squared.

## Deployment
The application is deployed on AWS Elastic Beanstalk with the following steps:

### CI/CD Pipeline
1. **Code Repository**:
   - Host the code on GitHub.
2. **CI/CD Workflow**:
   - Automate builds and tests using tools like GitHub Actions.
3. **AWS Elastic Beanstalk**:
   - Create an Elastic Beanstalk application.
   - Deploy the Flask application along with the trained model and preprocessor.
4. **Environment Setup**:
   - Use `requirements.txt` to configure dependencies.

### Running the Application Locally
1. Clone the repository:
   ```bash
   git clone https://github.com/JaykumarMistry/mlproject.git
   cd mlproject
   ```
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the Flask application:
   ```bash
   python application.py
   ```
5. Open your browser and navigate to `http://127.0.0.1:5000`.

## Results
- **Model Selection**: The pipeline selects the best model based on evaluation metrics.
- **Real-Time Prediction**: Users can make predictions via a user-friendly web interface.
- **Scalable Deployment**: The application is deployed on AWS Elastic Beanstalk for robust and scalable access.

## Technologies Used
- **Programming Language**: Python
- **Machine Learning Libraries**: scikit-learn, XGBoost, CatBoost
- **Web Framework**: Flask
- **Deployment**: AWS Elastic Beanstalk
- **Version Control**: Git

## Future Enhancements
- Incorporate real-time data ingestion.

## Conclusion
This project demonstrates a comprehensive workflow for developing and deploying a machine learning application. It is modular, scalable, and ready for production. Contributions and suggestions are welcome!

## Acknowledgments
I would like to express my gratitude to @krishnaik06, whose YouTube tutorials on data science and machine learning were instrumental in shaping the foundation of this project.

## Author
**Jaykumar Mistry**
