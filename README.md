# Predicting Crude Spreads using Fundamental Data

## Introduction
The project involves building a Deep learning model using Long Short Term Memory (LSTM) and Gated Recurrent Unit (GRU) models on time series data, to predict future Oil prices, primarily the front month Brent spread or the difference in prices between the Front Month Brent Futures contract and the second month futures contract. 
This will give my organization an edge over others and to extract alpha in an inefficient market. This is also useful as we live in a world where huge amounts of data exist and not enough tools have been developed to harness the usefulness and efficiencies from these data sources.

## Data Sources and Types of Fields
The data has been kindly provided by my company's analytics team where these data are collected from various sources, cleaned, and stored. I access this data using and an API provided by the team. The type of data includes
1.	Crude Oil Monthly Production volumes by Country
2.	Crude Flows from Country to Country for major exporters and importers
3.	Refinery Runs for major refiners
4.	Lost Production capacity due to Refinery Turnarounds (Crude Distillation Unit maintenance)
5.	Crude Oil Inventories
6. Prices for Crude, Naphtha, Gasoil, Gasoline, RBOB and JET (products)

## Expected Outcomes
The outright Crude prices are difficult to predict. The front month spread, which is the difference between the front month Brent Crude futures contract and the second month Brent futures contract react to the short and medium term supply demand fundamentals in the market.
Hence the column in the data set ‘Brent_Diff’ is chosen as the target variable.
The model is being developed to see if changes in any of the above inputs such as Crude Production, refinery runs, product prices etc can be used to predict this Front month spread.

## Models Used
The following deep learning models are used to train and predict Brent Differential between the first and second months.

1. LSTM (Long Short Term Model)
2. GRU (Gated Recurrent units)

Both of the above are part of the wider Recurrent Neural Networks (RNNs) that can be used for processing sequential data

## Preview of the Target Variable (Brent_Diff)
The below graph shows the bar plot of the target variable Brent_Diff. The front month spread reacts to the short to mid term fundamentals unlike the outright Brent price. The differential dropped during the COVID in early 2020 reflecting lower demand and spiked after the start of the Ukraine war in Feb 2022 indicating huge demand for oil.

![image](https://user-images.githubusercontent.com/39402428/189820113-5fceaa86-29bd-457e-9abb-f699055bddf4.png)

As can be seen from the below graph of the 6 month rolling standard deviation of the Brent Differential, the volatlity of the spread spiked during both periods mentioned above and especially after the start of the  Unkraine war in Feb 2022, it went through the roof.

![image](https://user-images.githubusercontent.com/39402428/189819618-f82f51ac-c3ad-42d5-a1e9-26e115beb35d.png)
## Results Obtained

### LSTM model 
The LSTM model showed better performace relatively with the below errors on the training and test sets
![image](https://user-images.githubusercontent.com/39402428/189821640-1b0d09ed-8cf5-4eed-a369-b89a721625c8.png)

The below shows how much fitting happened in the Learning stage of the LSTM model
![image](https://user-images.githubusercontent.com/39402428/189821806-9f388fcd-ee3b-403c-a197-e49e2a0077ba.png)

and the below shows the prediction of the LSTM model on the test set
![image](https://user-images.githubusercontent.com/39402428/189821942-a3e25e98-60f6-418c-b26c-a803dbaf7860.png)

### GRU Model
The GRU model gave the below errors on the training and test sets
![image](https://user-images.githubusercontent.com/39402428/189822247-212f300d-fb43-486b-b399-b9ed8a519f4f.png)
The training was not as impressive as the LSTM on the training data
![image](https://user-images.githubusercontent.com/39402428/189822372-7b078f62-17e6-462d-9e1a-7f24bfc48193.png)
But the GRU model results were comparable to the LSTM model on the test data
![image](https://user-images.githubusercontent.com/39402428/189822448-6b5272f5-14ec-4214-ac59-818b41b64b66.png)

## Conclusions
The data is monthly and is only from 2017 to 2022. Hence there were only 69 monthly data points and hence the training was very limited to the kind of learning the model is expected to do.

The test set includes the period when the Ukraine war started. This may be an outlier event causing the models to underperform on test data

Further improvements can be done with daily granularity, so the model has longer periods to learn and generalize.
