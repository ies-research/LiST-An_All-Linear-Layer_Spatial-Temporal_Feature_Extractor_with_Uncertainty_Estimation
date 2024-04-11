# LiST-An_All-Linear-Layer_Spatial-Temporal_Feature_Extractor_with_Uncertainty_Estimation
This code is related to the paper "LiST: An All-Linear-Layer Spatial-Temporal Feature Extractor with Uncertainty Estimation for RUL Prediction".

## Methodology
ThiIn the context of Remaining Useful Life (RUL) prediction for industrial systems, the pursuit of prediction accuracy must be balanced against the hardware costs of model operation and the reliability of prediction results. 
To resolve these challenges, we introduce LiST, an all-linear-layer spatial-temporal feature extractor integrated with uncertainty estimation, specifically designed for processing multivariate sensor time series (MTS) data. 
Unlike traditional linear models that flatten MTS and thus neglect their spatial-temporal dependencies, LiST's linear layers act on both the sensor and time dimensions of MTS that can extract spatial and temporal features like GNN and RNN models.
Through performance comparisons on four RUL prediction datasets, LiST uses only 66.1% of the parameters, achieves comparable accuracy to state-of-the-art GNN and RNN models, obtains the best results on two datasets with up to a 6.3% improvement in RMSE, and enhances training efficiency by 3.2 times. 
Additionally, LiST can predict RUL with uncertainty estimation and precisely disentangle epistemic and aleatoric uncertainties,  thus enhancing the model's practicality and reliability in real-world industrial applications.

## Dataset
The experiment is based on the public data set [Turbofan Engines Degradation Simulation Data Set](https://data.nasa.gov/Aerospace/CMAPSS-Jet-Engine-Simulated-Data/ff5v-kuh6/about_data)
provided by NASA is being used in this paper for Remaining Useful Life prediction.

## File Structure
```
├───checkpoints          //To save the best fine tunned model 
├───CMAPSSData           //Dataset location 
├───images               //To save the visualization result 
├───requirements.txt     //Requirements for python envoriment 
├───utils.py             //Utilities for dataset loading 
├───LiST.ipynb           //Core code of LiST  
└───results              //It stores the running results of LiST step by step on  each dataset 
```

## Setup
Environment setup:

```
python -m venv ./venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
python -m ipykernel install --user --name=venv
```

Download the dataset:

```
download CMAPSSData.zip 
unzip -d CMAPSSData/ CMAPSSData.zip
```

Run Code:
```
Run LiST.ipynb in jupyter server

All the experimental configurations have been set in the code for four datasets FD001, FD002, FD003, FD004. Only change the dataset index, the correspond config will be load automatically. 
IN_IDX = {0,1,2,3}
```
