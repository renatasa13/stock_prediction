# Stock Prediction Using Wavelet-GRU

## Description
Stock price prediction is a challenging task due to market volatility, external economic influences, and noisy data, which make it difficult for traditional models to provide accurate forecasts. The unpredictability of stock movements often leads to misleading signals, causing potential losses for investors. To address these issues, this project implements a Wavelet-GRU model that combines Wavelet Transform for noise reduction and trend extraction with Gated Recurrent Unit (GRU) for capturing long-term dependencies in stock prices. This hybrid approach aims to enhance prediction accuracy, stability, and computational efficiency, enabling better decision-making in stock investments.

## Objectives
The primary objective of this project is to develop an accurate and reliable stock price forecasting model by integrating Wavelet Transform and GRU. Specifically, it aims to reduce the impact of noise and short-term fluctuations, improve trend identification by decomposing stock data into different frequency components, and enhance prediction stability by leveraging GRU’s capability to process sequential financial data. Ultimately, this model seeks to assist investors, financial analysts, and traders in making more data-driven and informed investment decisions.

## Methods
* **Wavelet Transform** is a signal analysis technique used to break down data into different frequency components and time scales. In the context of stock price prediction, Wavelet helps decompose stock price data into multiple scales or frequency components, effectively reducing noise in stock prices and capturing seasonal patterns.
* **Gated Recurrent Unit (GRU)** is a type of Recurrent Neural Network (RNN) designed to address the vanishing gradient problem and improve efficiency in processing sequential data. GRU consists of two main gates that control the flow of information: the Update Gate and the Reset Gate, allowing it to capture long-term patterns in price trends.

## Approach
1. **Data Collection and Preprocessing** : The data used comes from PT Bursa Efek Indonesia, where historical stock price data (date and closing price) is cleaned and normalized.
2. **Stock Data Decompose** : Next, Wavelet Transform is applied to decompose the stock data into multiple frequency components, eliminating noise and improving pattern recognition.
3. **Predicition by GRU** : The transformed data is then fed into a GRU model, which learns historical price dependencies and forecasts future trends.
4. **Evaluation** : Finally, the model’s performance is evaluated using metrics such as Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) to ensure prediction accuracy before being used for real-world stock forecasting applications.
5. **Investment Risk Analysis** : Investment risk analysis is conducted by calculating Value at Risk (VaR) and Expected Shortfall (ES)

## Result
The result of this prediction is the Wavelet-GRU prediction model and the forecast of the stock closing price for the upcoming period.
### For example, in the following case study of Bank BRI (BBRI)
This is the result of comparing the actual BBRI stock price with the predicted stock price. Through this comparison, the model achieved a **MAE (Mean Absolute Error) of 52.8274**, **MSE (Mean Squared Error) of 4860.1744**, **RMSE (Root Mean Squared Error) of 69.7150**, and **MAPE (Mean Absolute Percentage Error) of 1.1480%**. This indicates that the **Wavelet-GRU model has a fairly high level of accuracy in predicting BBRI stock prices, with a relatively small prediction error compared to the actual price**.
![image](https://github.com/user-attachments/assets/6e2d24c6-2b57-4d66-86e7-b9afb6854c52)

## Investment Risk Analysis
Value at Risk (VaR) estimates the potential maximum loss of an investment over a given period at a specified confidence level. It provides a statistical measure of downside risk, helping investors understand the worst-case loss under normal market conditions. Expected Shortfall (ES), also known as Conditional VaR (CVaR), goes a step further by measuring the expected loss beyond the VaR threshold. It provides a more comprehensive risk assessment by considering extreme market movements and tail risks. By combining VaR and ES, investors can better quantify and manage financial risks, ensuring more informed decision-making in portfolio management. <br>

### For example, in the following case study of Bank BRI (BBRI)
![image](https://github.com/user-attachments/assets/60aa9a12-cc86-4a47-bb03-a345b9cf31f4)
The image shows the closing stock price of BBRI for the next 200 days. Assuming an initial investment of $1,000,000, the predicted investment risk is as follows:
1. VaR (95% Confidence): -0.0231 <br>
   With a 95% confidence level, the maximum expected loss in a single period is 2.31% of the investment value under normal market conditions.
2. ES (95% Confidence): -0.0337 <br>
   Expected Shortfall (ES) measures the average loss beyond the VaR threshold. Here, the expected loss in extreme conditions is 3.37% of the investment value.
3. VaR Absolute: 23,138.26 <br>
   In absolute terms, the maximum expected loss (VaR) translates to $23,138.26, assuming an initial investment of $1,000,000.
4. ES Absolute: 33,693.67 <br>
   If market conditions worsen beyond the VaR threshold, the average loss (ES) is projected to be $33,693.67.<br>

The conclusion is that the model predicts that under normal conditions, the worst-case daily loss is around 2.31% of the investment. If extreme market conditions occur, the potential loss could be higher, averaging 3.37%. Therefore, this analysis helps investors understand and prepare for possible financial risks before making investment decisions.
