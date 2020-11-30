# Handling Concept Drift by Applying Explainability Frameworks in AI-Based Information Systems

This repository implements a two-step approach for concept drift handling with Explainability Frameworks and Active Learning.

Since minor adjustments had to be made in the backend depending on the type of data sets being processed, 
different directories SHAP_approach_synthetic_data, SHAP_approach_real_world and KSWIN_approach were created.

1 ) The directories „SHAP_approach_synthetic_data“ and „SHAP_approach_real_world“ have the same structure:
- The notebook "backend" contains the functionality to perform the stream processing and drift handling
- The notebook "execution" starts the drift handling approach and calls functionalities from the backend for this purpose. 
  Performed runs are stored in the form of a "detector object“. Also, a grid search is implemented in this notebook.
- The notebook "results" loads these "detector objects" and evaluates the results. Also, it creates plots.

2) The „KSWIN_approach“ directory contains functionality for drift detection with the KSWIN detector.
- The notebook „ks_backend" contains the same functionality as the other backend notebooks, with the exception that it 
  is determined in advance at which points in time new training will take place
- The notebook "ks_data" determines the drift points and performs the drift detection with these determined points. 
  For this purpose, the functionality of the notebook "ks_backend" is used
- The notebook "ks_result" loads the test runs and displays the results

3) The folder "create_data" contains functionality to create the synthetic data sets. 

4) The following notebooks are assigned under the root directory:
- The notebook "preparation" performs the preprocessing for real-world data sets
- The notebook „check_correlation“ compares the correlation between distance and accuracy before and after drift detection
- The notebook „feature_reduction“ performs the feature reduction based on the Shapley values

The folder "results/detector_objects" contains "detector objects", storing already performed test runs.
Not all configurations of the drift handling approach are stored here as an object. In order to evaluate further configurations with 
different data sets, new test runs can be performed by applying the notebook "execution" and afterwards loading the corresponding 
detector objects with the "results" notebook.
