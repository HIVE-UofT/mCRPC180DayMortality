# mCRPC 180-Day Mortality Early Warning Model
This repository contains the code, and model architectures for the development and external validation of a visit-level early warning system for metastatic castration-resistant prostate cancer (mCRPC) mortality (https://doi.org/10.48550/arXiv.2601.20046).

The project focuses on predicting 180-day survival using longitudinal clinical trial data, providing clinicians with a predictive tool to identify patients at high risk of mortality during routine visits.

### At a glance
We developed and compared five candidate architectures to identify the most robust model for clinical decision support:

High-Performance Architecture: A Gated Recurrent Unit (GRU) was selected as the final model due to its superior temporal handling and calibration.

Comparison Models: The pipeline also includes implementations for LSTM, Random Survival Forest (RSF), Cox Proportional Hazards, and Logistic Regression.

Performance: The final GRU model achieved an AUC-ROC of 0.89.

Calibration & Lead Time: The model demonstrated strong calibration (slope: 0.93) and provides a median lead time of 151 days for true positive alerts.

Data Source: Developed using longitudinal clinical trial data from Open Data Sphere, using the CC-5013-PC-002 for model development and EFC6546 for external validation.

Code Strucutre: The code contains two sections, the first shows the initial candidate models on the first trial and further down, the second shows the external validation on the GRU and the RSF models. All of the figures are generated in the code and readily available.

### Tutorial


1. Set up the environment (see below).

2. Open 180DaySurvivalModel.ipynb.

3. Navigate to the "Evaluation" and "External Validation" sections.

4. Run the cells to generate the performance of all the candidate models and all the corresponding plots.

Environment setup
Python venv
Bash
git clone https://github.com/HIVE-UofT/mCRPC180DayMortality.git
cd mCRPC180DayMortality

python -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install -r requirements.txt
Key Dependencies
PyTorch/TensorFlow: For GRU and LSTM implementations.

Scikit-Survival: For Random Survival Forest and Cox models.

Pandas/NumPy: For longitudinal data manipulation.
