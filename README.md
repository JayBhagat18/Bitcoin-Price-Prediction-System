Dataset link - 

This notebook focuses on forecasting Bitcoin prices using two popular architectures in Recurrent Neural Networks (RNNs): Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU). The process involves several key steps, from data preparation and exploration to model building, training, and evaluation. Here's a breakdown:

1. Data Loading and Preparation
The dataset includes historical Bitcoin prices with columns like Timestamp, Open, High, Low, Close, Volume, and Weighted Price.
Data is loaded, and initial checks for null values and data types are performed.
The data is transformed to group by daily average prices, providing a more manageable dataset for time series analysis.
2. Data Splitting
The dataset is split into a training set (from January 1, 2016, to October 15, 2017) and a test set (from October 15, 2017, to October 20, 2017).
This split is crucial for evaluating the model's performance on unseen data.
3. Exploratory Data Analysis
The dataset is analyzed for trends and seasonality using Seasonal Decomposition.
Autocorrelation and Partial Autocorrelation plots help identify repeating patterns and dependencies within the time series.
4. Data Preparation for Modeling
Data is scaled using MinMaxScaler due to the scale-sensitive nature of LSTM and GRU models.
The data is reshaped to fit the input requirements of the models.
A lookback mechanism is created to structure the dataset for sequential forecasting, where each prediction is based on previous time steps.
5. Model Training and Comparison
Different models are compared, including ARIMA, 1-layer LSTM, Bidirectional 1-layer LSTM, GRU, and 2-layers LSTM.
The 2-layer LSTM model performs the best in terms of Root Mean Squared Error (RMSE) but takes more time to train.
GRU is a close competitor with faster training times but slightly higher RMSE.
6. Building and Training the 2-Layer LSTM Model
A sequential model with two stacked LSTM layers (256 units each) is built.
The model is trained using the Adam optimizer and Mean Squared Error (MSE) loss function.
Early stopping is applied to prevent overfitting.
7. Model Evaluation
The model's performance is evaluated by comparing predicted prices to actual prices on the test set.
The RMSE is calculated to measure the accuracy of the predictions, with a lower RMSE indicating better performance.
Visualizations show the comparison of true prices and predicted prices, demonstrating the model's effectiveness.
8. Conclusion
The LSTM model shows promising results in predicting Bitcoin prices, making it a valuable tool for investors and policymakers.
The trade-off between model complexity (LSTM vs. GRU) and training time is highlighted, with GRU offering a faster alternative with slightly less accuracy.
This notebook demonstrates the practical application of LSTM and GRU for time series forecasting, particularly in the volatile and unpredictable cryptocurrency market.
