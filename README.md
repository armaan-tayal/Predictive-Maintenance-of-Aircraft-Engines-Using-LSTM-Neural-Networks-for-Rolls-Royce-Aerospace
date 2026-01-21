Predictive Maintenance of Aircraft Engines Using LSTM Neural Networks


✈️ Deep Learning Approach for Remaining Useful Life (RUL) Prediction


📖 Project Overview
This repository contains a deep learning solution for Predictive Maintenance in the aerospace industry, specifically targeting Rolls-Royce aircraft engines. By leveraging Long Short-Term Memory (LSTM) neural networks, this project predicts the Remaining Useful Life (RUL) of engines based on time-series sensor data.

Predictive maintenance is critical in aviation to prevent failures, optimize maintenance schedules, and reduce operational costs. This project demonstrates how time-series forecasting can proactively identify when an engine unit is approaching failure.

📊 Dataset
The model utilizes multivariate time-series data from aircraft gas turbine engines. The dataset includes:

Operational Settings: 3 distinct operational settings that influence engine performance.

Sensor Measurements: 21 sensor readings (e.g., Temperature, Pressure, Fan Speed) recording the state of the engine during each flight cycle.

Time Cycles: The progression of engine life measured in cycles.

🧠 Methodology
The core of this project is a Sequential Deep Learning Model built using Keras/TensorFlow. The architecture is designed to capture temporal dependencies in sensor data:

Input Layer: Accepts sequences of sensor data (sliding window approach).

LSTM Layers: Two stacked LSTM layers (64 units and 32 units) to learn long-term dependencies and degradation patterns over time.

Dropout Regularization: Applied after LSTM layers to prevent overfitting.

Dense Output Layer: A single neuron regression output to predict the exact RUL value.

🛠️ Model Architecture
Python
Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 lstm (LSTM)                 (None, 30, 64)            22,784    
 dropout (Dropout)           (None, 30, 64)            0         
 lstm_1 (LSTM)               (None, 32)                12,416    
 dropout_1 (Dropout)         (None, 32)                0         
 dense (Dense)               (None, 1)                 33        
=================================================================
Total params: 35,233
Trainable params: 35,233
📈 Results & Performance
The model was trained over 30 epochs, achieving strong convergence on the validation set.

Final Evaluation Metrics:

RMSE (Root Mean Squared Error): 19.88

MAE (Mean Absolute Error): 13.83

These metrics indicate the model's average prediction error in terms of engine cycles, demonstrating a high degree of accuracy for maintenance planning.

📉 Visualizations
The notebook includes detailed visualizations to interpret model performance:

RUL Prediction vs. True RUL: Line plots comparing predicted degradation paths against actual values.

Prediction Accuracy Scatter Plot: A direct correlation plot showing how closely predictions align with ground truth (Perfect Prediction line).

Error Distribution: Histogram of prediction errors to analyze model bias and variance.

💻 Technologies Used
Python 3.x

TensorFlow / Keras: For building and training the LSTM model.

Pandas & NumPy: For data manipulation and sequence generation.

Matplotlib / Seaborn: For plotting training history and prediction results.
