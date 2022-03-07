# Automodeler
Automodeler - A simple AutoML lite pipeline

A simple but practical AutoML lite pipeline that can be used in production or for teaching.

Each script is intended for use in a pipeline. Each notebook is intended for understanding each step of the pipeline and to allow web/UX developers to see the visualizations and tables.

The pipeline consists of four steps:

1. Data_Preprocessor   
2. Data_Scrubber  
3. Automodeler  
4. Interpretability   

## Data_Preprocessor  
*Data_Preprocessor.py and Data_Preprocessor.ipynb*

This steps checks:  

a.  Data types  
b.  Descriptive statistics   
c.  Missing values   
d.  Data distributions  

## Data_Scrubber  

*Data_Scrubber.py and Data_Scrubber.ipynb*   

This step asks for a target and confirms the data types from  Data_Preprocessor.py it the:  

a.  Imputes missing values using KNN and MICE   
b.  It calculates descriptive statistics, missing values & data distributions on the imputed data    
c.  It compares the difference bewteen the raw data and imputed data on descriptive statistics, missing values & data distributions    
d.  It determines and visualizes important features   

## Automodeler     

*Automodeler_H20.py and Automodeler_H20.ipynb*   

This steps uses H2O.ai to create optimized models on the imputed data and outputs relevant statistics and visualization.

a.  Creates and saves models    
b.  Visualization and tables as .json   
  
Future versions will use other autoML libraries.      

## Interpretability     

*Interpretability.py and Interpretability.ipynb*    

This steps checks loads a validation file and a model file and runs the following interpretability analysis: 

a.  SHAP     

Future versions will add other interpretability libraries and algorithms.   



