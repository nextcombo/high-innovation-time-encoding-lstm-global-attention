# High Innovation | Time-Encoding + LSTM + Global Attention

Preface
This issue introduces an LSTM prediction model based on input information encoding and an improved global attention mechanism, providing a positional encoding + temporal encoding interface for time series data. This can be integrated into any previous models with this type of input information encoding!
Environment Framework: Python 3.9, PyTorch 1.8 or above are required to run.
Single-step prediction model score: Test set 0.97.
Usage: Paper requirements, graduation design requirements.
Code Guarantee: The code is detailed with comments, ready to run without modification.
1. Model Innovation Points Introduction
\t1.1 Time Encoding
\tInput information encoding is based on the Informer paper, we have optimized the source code and dataset compilation, making it convenient for any dataset with time-related columns to perform input information encoding.
\tInformer not only adds the necessary PositionEmbedding (positional encoding) from the Transformer architecture but also various encodings related to time:
\tDay cycle encoding: representing the time points in a day.
\tWeek cycle encoding: representing the time points in a week.
\tMonth cycle encoding: representing the time points in a month.
\tIn time series prediction tasks, different time points may contain important information, such as hierarchical timestamps (week, month, year) and unknown timestamps (holidays, events).
\tThe specific GlobalTimeStamp to add depends on the actual problem to be confirmed. For example, if calculating passenger flow at high-speed train stations, the time difference of "holiday" is very important. If calculating the passenger flow of public transportation like buses and subways, the "week" can reveal whether it's a working day.
\tYou can adjust according to your dataset's time resolution!
\t1.2 Based on GlobalAttention Optimized LSTM Network
Optimize the recurrent mechanism based on attention into a LSTM neural network based on global attention:
\t  
2. Overall Structure of the Model
The overall structure of the model is as follows, with multi-feature variable time series data first undergoing input information encoding:
\tToken Embedding - Time-series data encoding
\t  
The encoded data is extracted with global temporal features through a LSTM network based on GlobalAttention optimization. GlobalAttention is a mechanism used to enhance the model's focus on different parts of the input sequence. In the LSTM model, the global attention mechanism helps the model to better concentrate on the most relevant parts of the input sequence, thereby enhancing the model's performance and generalization capabilities. At each time step, the global attention mechanism calculates a weight vector that represents the model's focus on various parts of the input sequence. These weights are then applied to the feature representations output by the LSTM, allowing for weighted consideration of all positional features, which in turn enables the model to more specifically focus on important temporal features of the multi-feature sequences, improving its ability to perceive temporal features in multi-feature sequences.
We name the model:
\tGlobal Attention Temporal LSTM (GATLSTM)  
3. Data Preprocessing for Power Transformers Dataset
\tThe detailed introduction of the Electrical Transformers dataset can be found in the following text:
Introduction to the Power Transformer Dataset and Preprocessing
3.1 Import Data
\t  
3.2 Dataset Preparation and Preprocessing
\t  
For detailed information, please refer to the provided documents!
4 Prediction Model Based on GATLSTM
4.1 Definition of the GATLSTM prediction network model
4.2 Setting parameters and training the model
50 epochs, MSE is 0.0198, the GATLSTM prediction effect is significant, the model can fully extract the global context information of time series, converges quickly, has excellent performance, high prediction accuracy, appropriately adjusting the model parameters can further improve the model prediction performance.
5 Results Visualization and Model Evaluation
5.1 Prediction result visualization
5.2 Model evaluation
Click to download: Complete original data, Python code
Previously interesting content:
Time series prediction: Analysis and comparison of LSTM, ARIMA, Holt-Winters, SARIMA models
Wind speed prediction (I) Data introduction and preprocessing
Wind speed prediction (II) EMD-LSTM model based on Pytorch
Wind speed prediction (III) EMD-LSTM-Attention model
Wind speed prediction (IV) EMD-Transformer model based on Pytorch
Wind speed prediction (V) EMD-CNN-LSTM model based on Pytorch
Wind speed prediction (VI) EMD-CNN-GRU parallel model based on Pytorch
CEEMDAN + combined prediction model (BiLSTM-Attention + ARIMA)
CEEMDAN + combined prediction model (CNN-LSTM + ARIMA)
CEEMDAN + combined prediction model (Transformer - BiLSTM + ARIMA)
CEEMDAN + combined prediction model (CNN-Transformer + ARIMA)
Multi-feature variable sequence prediction (I) - CNN-LSTM wind speed prediction model
Multi-feature variable sequence prediction (II) - CNN-LSTM-Attention wind speed prediction model  
Multi-feature variable sequence prediction (III) - CNN-Transformer wind speed prediction model  
Multi-feature variable sequence prediction (IV) Transformer-BiLSTM wind speed prediction model  
Multi-feature variable sequence prediction (V) CEEMDAN+CNN-LSTM wind speed prediction model  
Multi-feature variable sequence prediction (VI) CEEMDAN+CNN-Transformer wind speed prediction model  
Prediction model based on the SSA of the Sparrow optimization algorithm: CEEMDAN-BiLSTM-Attention  
Prediction model based on the SSA of the Sparrow optimization algorithm: CEEMDAN-Transformer-BiGRU  
Superior predictive model: Secondary decomposition-combination prediction  
Multi-feature variable sequence prediction (VII) CEEMDAN+Transformer-BiLSTM prediction model  
Multi-feature variable sequence prediction (VIII) Prediction model based on the SSA of the CEEMDAN-SSA-BiLSTM based on the Sparrow optimization algorithm  
Multi-feature variable sequence prediction (11) Prediction model based on Pytorch's TCN-GRU  
VMD + CEEMDAN secondary decomposition, CNN-LSTM prediction model  
VMD + CEEMDAN secondary decomposition, CNN-Transformer prediction model  
VMD + CEEMDAN secondary decomposition, Transformer-BiGRU prediction model  
Prediction model based on the SSA of the Sparrow optimization algorithm - code family kit  
Introduction to the power transformer dataset and preprocessing  
 | Sci-Tech 1st Class High Innovation Predictive Model!
END

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
