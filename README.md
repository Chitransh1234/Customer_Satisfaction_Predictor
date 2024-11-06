This project aims to predict customer satisfaction for future orders using historical purchase data. Leveraging the Brazilian E-Commerce Public Dataset by Olist, which includes data on 100,000 orders across various marketplaces in Brazil from 2016 to 2018, we can analyze customer behavior through multiple dimensions—order status, payment methods, product attributes, and customer reviews. By accurately predicting customer review scores for future orders, businesses can enhance customer experience and proactively address potential issues.

Project Overview
Objective
The goal is to predict the customer satisfaction score for the next order based on historical data. By understanding which features, such as order status, price, and location, influence customer satisfaction, this model provides valuable insights to improve customer experience.

Tools and Frameworks
To achieve a production-ready model, this project uses ZenML, an open-source MLOps framework, to build, manage, and deploy machine learning pipelines efficiently. ZenML integrates seamlessly with MLflow to track and deploy models, enabling continuous monitoring and iteration.

Pipeline Structure
The ZenML framework provides structure and automation, creating two core pipelines:

Training Pipeline: This pipeline ingests and processes data, trains the model, and tracks results with MLflow.

Steps:
ingest_data: Imports and organizes the dataset into a DataFrame.
clean_data: Cleans data and removes irrelevant columns.
train_model: Trains the model with autologging to MLflow for tracking.
evaluation: Evaluates model performance, logging metrics to MLflow.
Deployment Pipeline: Extends the training pipeline for continuous deployment. It redeploys models if they meet specified performance criteria.

Additional Steps:
deployment_trigger: Validates if the model meets criteria (e.g., MSE threshold) for deployment.
model_deployer: Deploys the model as a service using MLflow if criteria are met.
ZenML and MLflow Integration
The integration with MLflow allows for tracking of all model metrics, parameters, and artifacts. The model is deployed through an MLflow deployment server, automatically updated when a newly trained model meets the set accuracy threshold. This setup ensures that the latest, most accurate model is always available for predictions.

Real-Time Demo with Streamlit
A Streamlit application demonstrates real-time model predictions. This interactive web app accepts product details and predicts customer satisfaction, showcasing the model’s practical application in a business context. You can run the app locally or access a hosted version for quick testing.

Setup and Requirements
Python Environment
To set up, clone the project repository and install the required packages:

bash
Copy code
git clone https://github.com/zenml-io/zenml-projects.git
cd zenml-projects/customer-satisfaction
pip install -r requirements.txt
Running the Pipelines
Training Pipeline: Run with python run_pipeline.py
Deployment Pipeline: Run with python run_deployment.py
Launching the Streamlit App
To run the Streamlit app locally:

bash
Copy code
streamlit run streamlit_app.py
Solution Benefits
This project demonstrates how ZenML enables streamlined MLOps workflows, allowing businesses to efficiently build, deploy, and maintain machine learning models in production. By predicting customer satisfaction scores before an order is placed, businesses can make informed decisions to improve customer experiences and drive loyalty.
