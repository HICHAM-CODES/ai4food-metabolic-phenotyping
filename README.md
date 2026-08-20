# AI4Food (Metabolic Phenotyping Using Multimodal Health Data)

## Overview
This repository contains the code and analysis pipeline developed during 
a 6-month research internship at IMDEA Nutrition (Madrid, Spain) as part 
of the AI4Food project. The project integrates multimodal longitudinal 
health data to characterize metabolic phenotypes in overweight and obese 
adults using machine learning and explainable AI approaches.

## Research Question
Can we identify distinct metabolic profiles in individuals with obesity 
by integrating wearable signals, continuous glucose monitoring, sleep 
data, nutritional intake, and microbiome diversity; And can sleep-derived 
features predict metabolic outcomes such as glucose regulation and 
thermoregulation?

## Study Design
- 93 participants with overweight or obesity (BMI 27–35 kg/m²)
- 30-day crossover intervention combining:
  - Traditional phase: questionnaires and food diaries
  - Digital phase: Fitbit Sense Smartwatch + FreeStyle Libre 2 CGM
- Data collected across three clinical visits (V1, V2, V3)

## Data Modalities
- Wearable physiological signals (HRV, SpO2, respiratory rate, 
  skin temperature, sleep stages)
- Continuous glucose monitoring (CGM) every 15 minutes
- Sleep recordings and subjective sleep quality (OSQ questionnaire)
- Nutritional intake records (analyzed with DIAL software)
- Gut microbiome diversity (shotgun metagenomic sequencing)

## Data Access
The AI4FoodDB dataset is publicly available for research purposes:

- **Full dataset:** https://bidalab.eps.uam.es/static/AI4FoodDB/AI4FoodDB.zip
- **Nutrition dataset (DS3):** https://bidalab.eps.uam.es/static/AI4FoodDB/FoodNExtDB.zip
- **Gut Microbiome (DS5):** https://www.ebi.ac.uk/ena/browser/view/PRJEB87701

> The database is intended for research purposes only and may not be 
> used in commercial applications.

## Citation
If you use this data, please cite the original publication:

Romero-Tapiador S., et al. — *AI4FoodDB: A Database for Personalized 
e-Health Nutrition and Lifestyle through Wearable Devices and 
Artificial Intelligence* — Database: The Journal of Biological 
Databases and Curation, 2023. 
DOI: 10.1093/database/baad049

## Methods
- Multimodal data preprocessing and temporal alignment in Python
- K-means clustering with elbow method for metabolic phenotyping
- PCA for nutritional data dimensionality reduction
- Supervised ML models: Random Forest and Neural Network (MLP)
- Explainable AI (SHAP) for feature importance analysis
- Statistical testing: t-tests, Wilcoxon, Chi-square, Spearman correlations

## Key Results
- Digital monitoring produced significantly greater weight loss than 
  manual phase (-1.55 kg vs -0.75 kg, p = 0.0004)
- Three distinct weight-response clusters identified:
  - Marked responders: -4.2 kg average
  - Moderate responders: -1.8 kg average  
  - Non-responders: +0.7 kg average (p < 0.0001)
- Nocturnal respiratory rate significantly associated with weight 
  variation (p = 0.0014)
- Skin temperature clusters significantly associated with weight 
  variation (p = 0.0116)
- Neural Network achieved 87% accuracy (AUC = 0.95) predicting 
  glucose profiles from sleep variables
- Random Forest achieved 84% accuracy (AUC = 0.93) predicting 
  thermoregulation profiles
- SHAP analysis identified restlessness, HRV (RMSSD), respiratory 
  rate, and REM sleep duration as key predictors of metabolic outcomes
- Gut microbiome composition remained stable across the 30-day 
  intervention, consistent with short-term dietary study limitations

## Repository Structure
> Notebooks and source files are being uploaded progressively.
├── notebooks/
│   ├── 01_preprocessing.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   ├── 03_clustering.ipynb
│   ├── 04_ml_models.ipynb
│   └── 05_shap_interpretability.ipynb
├── src/
│   ├── preprocessing.py
│   └── features.py
├── figures/
├── requirements.txt
└── README.md

## Tools and Technologies
Python 3.11 | scikit-learn | TensorFlow/Keras | PyTorch | SHAP | 
Pandas | NumPy | Matplotlib | Seaborn | JupyterLab

## License
This project is licensed under the MIT License.
