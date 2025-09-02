# Precision Precipitation Forecasting 🌦️

## Overview

This project presents a hybrid deep learning framework to predict precipitation levels for 24, 48, and 72-hour windows, leveraging ConvLSTM for satellite imagery and LSTM (with attention mechanisms) for meteorological data. Designed to address challenges like severe class imbalance, the framework delivers improved predictions, especially for rare but critical precipitation categories such as "Heavy Rain."

---

## Objective

To develop a reliable and scalable precipitation forecasting system that predicts up to 72 hours into the future, while addressing significant class imbalances to improve accuracy for minority precipitation categories.

---

## Key Features

- **Hybrid Architecture**:
  - **ConvLSTM**: Extracts temporal and spatial patterns from satellite imagery.
  - **LSTM with Attention**: Captures long-term dependencies in meteorological data sequences.
- **Class Balancing**:
  - Mitigates severe class imbalance (93% "No Precipitation") by adjusting class weights during training. Assign higher weights for the minority classes.
  - Achieved 64% accuracy for the minority "Heavy Rain" class, up from 0% before balancing (the model couldn't learn anything from the data before class weights adjustment).
- **Sliding Window Approach**:
  - Facilitates time-series forecasting by creating sequential input data for training.
- **Multiple Forecasting Windows**:
  - Optimized for 24, 48, and 72-hour predictions with tailored models.

---

## Results

- **24-Hour Forecast**:
  - Validation accuracy: 47% overall
  - Improved precision for minority classes through class balancing.
- **48-Hour Forecast**:
  - Validation accuracy: 50% overall
  - Better and balanced predictions across all categories.
- **72-Hour Forecast**:
  - Validation accuracy: 52% overall
  - "Heavy Rain" class accuracy: 64%, addressing significant imbalance.

---

## Workflow

1. **Data Preparation**:
   - Processed meteorological data and GOES satellite imagery.
   - Sliding window approach to generate sequential training data.

2. **Exploratory Data Analysis (EDA)**:
   - Uncovered key data trends and imbalances to inform model design.

3. **Model Training**:
   - Trained hybrid models for 24, 48, and 72-hour windows.
   - Addressed class imbalance using weight adjustments.

4. **Model Evaluation**:
   - Classification reports and confusion matrices to assess performance.
   - Notable improvement in minority class predictions.

5. **Inference**:
   - Finalized models used for real-time precipitation forecasting.

---

## How to Use

### Clone the Repository
```bash
git clone https://github.com/Lokesh-Balamurugan/precision_precipitation_forecasting.git
cd precision_precipitation_forecasting
```
## How to Use

### Prepare the Dataset
- Use the `data_preparation_and_sliding_window_creation.ipynb` notebook to create the dataset and sliding windows.
- Ensure that the processed data is correctly formatted before proceeding.

### Train the Models
- Navigate to the model notebooks for the desired forecasting window (24, 48, or 72 hours).
- Run the corresponding training notebook to generate model weights.

### Evaluate and Inference
- Use the `inference_only_notebook.ipynb` notebook to load the trained weights and evaluate the models.
- Generate classification reports, confusion matrices, and predictions for new data.

---

## Challenges Addressed

### Severe Class Imbalance:
- Addressed the dominance of "No Precipitation" data (93% of total).
- Improved "Heavy Rain" class accuracy from 0% to 64%, as well as other minority classes ("Less Rain" & "Medium Rain") through weight adjustments.

### Scalability:
- Designed models to handle large meteorological datasets efficiently.

---

## Future Work

- Incorporate additional weather variables to enhance prediction accuracy.
- Experiment with advanced techniques like transformer-based architectures.
- Extend the forecasting window beyond 72 hours.

---

## License 📜

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
