# Forecasting Pharmacy Medication Sales

**Karin Huegele**

## Executive summary
This project explores several models to find the best model to forecast pharmacy medication sales.

## Rationale
Accurate forecasting of drug sales will enable pharmacies to manage their inventory more efficiently. If pharmacies can rely on the forecast's accuracy, they can maintain smaller inventories, reduce operating costs, and reduce waste due to medication expiration.

## Research Question
In the pharmacy industry, it is essential to ensure patient safety and that the pharmacy dispenses only high-quality medications. As the pharmacy mail order utilization increases, it becomes crucial that the pharmacy can deliver medications efficiently and on time.  

However, predicting medication dispensing can be tricky. Some of the main factors that affect a prescription order are:
* Doctor's approval
* Pharmacy benefit manager's (PBM) approval
* Product availability
* Product unbreakable unit of packaging
* Risk of medication stockpiling

Due to PHI restrictions, patient personal health data is not publicly available. Using only the pharmacy sales data available in the public domain, how might we devise an accurate forecast of medication demand in the future?

## Data Sources
For this project, I use a dataset from [Kaggle](https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data) consisting of weekly pharmacy sale data collected in 6 years, from 2014 to 2019, for eight drug categories.

## Methodology
For this project, I explored time series for three drug categories:
* M01AB - Anti-inflammatory and antirheumatic products, non-steroids, Acetic acid derivatives, and related substances
* R03 - Drugs for obstructive airway diseases
* R06 - Antihistamines for systemic use.

I performed a manual seasonal decomposition as my baseline for this project. From there, I explored possible performance improvement using ARMA, SARIMAX, and RNN models using Dense, Simple RNN, LSTM with one layer, and LSTM with three layers.

## Results
The neural network models have the lowest RMSE, with LSTM, stacked LSTM, and Conv1D performing the best. However, neural networks require a high level of training. Also, setting up the train/test data was confusing and prone to mistakes. The SARIMAX and the stats model seasonal decomposition are the easiest to use and interpret. 

![Alt text](/notebooks/R06/R06-prediction-performance.png)

![Alt text](/notebooks/R03/R03-prediction-performance.png)

![Alt text](/notebooks/M01AB/M01AB-prediction-performance.png)

## Next steps
Additional work that will enhance my understanding of the models:
* **Troubleshoot animation for the neural network models.**  Unfortunately, I encountered errors while trying to do my animation. Getting it running will improve my understanding of the train/test window generation.
* **Get the XGBoost model to work.**  I tried to do XGBoost. However, I encountered errors with my train/test window setup.
* **Improve the grid search mechanism for the Sarimax model.**  I want to enhance my grid search mechanism to make it easier to find the best Sarimax model parameters.
* **Improve finetuning of my LSTM models.** I would like to better understand how to use the LSTM model effectively for time series analysis.

This project produced a valuable framework for evaluating time series models. With further enhancements, we will be able to utilize this tool to perform real-world analysis and build a performant prediction model for production deployment.

## Outline of project

- [R06 - Antihistamines for systemic use](https://github.com/kg5hqx/Capstone2/blob/master/notebooks/R06/Module-24-v3-R06.ipynb)
- [R03 - Drugs for obstructive airway diseases](https://github.com/kg5hqx/Capstone2/blob/master/notebooks/R03/Module-24-v3-R03.ipynb)
- [M01AB - Anti-inflammatory and antirheumatic products, non-steroids, Acetic acid derivatives, and related substances](https://github.com/kg5hqx/Capstone2/blob/master/notebooks/M01AB/Module-24-v3-M01AB.ipynb)

## Contact and Further Information
For more information about this project, please contact Karin Huegele, kg5hqx@hugelheim.us
