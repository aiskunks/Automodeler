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

*_Input: data tabular ".csv" style file. 
Output: Stats and graphs about the data_*

This steps checks:  

a.  Data types  
b.  Descriptive statistics   
c.  Missing values   
d.  Data distributions  


We save as json process and ML related info and visualize it.

## Data_Scrubber  

*Data_Scrubber.py and Data_Scrubber.ipynb*   

This step asks for a target and confirms the data types from  Data_Preprocessor.py it the:  


*_Input: data & previous stats (Data_Preprocessor.json)
Output: Cleaned data and & stats related to the differences between the orginal and cleaned data.
determines and visualizes important features.   
_*      


a.  Imputes missing values using KNN and MICE   
b.  It calculates descriptive statistics, missing values & data distributions on the imputed data    
c.  It compares the difference bewteen the raw data and imputed data on descriptive statistics, missing values & data distributions    
d.  It determines and visualizes important features   

We compare the raw versus the orginal data for the differences.

We save as json process and ML related info and visualize it.

## Automodeler     

*Automodeler_H20.py and Automodeler_H20.ipynb*   

*_Input: cleaned data, important features & previous stats (Data_Preprocessor.json)
Output: Model files and & stats related to the performance of the best models._*      

This steps uses H2O.ai to create optimized models on the imputed data and outputs relevant statistics and visualization.

a.  Creates and saves models    
b.  Visualization and tables as .json   
  
Future versions will use other autoML libraries.      

We save as json process and ML related info and visualize it.

## Interpretability     

*Interpretability.py and Interpretability.ipynb*    


*_Input: validation data, important features, model files & previous stats (Automodeler_H20.json)
Output: Visualization and & stats related to the interpretability of the best models._*  

This steps checks loads a validation file and a model file and runs the following interpretability analysis: 

a. SHAP     
b. Feature importance  
c. PDP  

Future versions will add other interpretability libraries and algorithms.   

We save as json process and ML related info and visualize it.


