# Wet-Waste-Biomass-Opt
code for Advancing Sustainable Development Goals with Machine Learning and Optimization for Wet Waste Biomass to Renewable Energy Conversion paper submitted to the journal of cleaner produciton

## Running the code

To run the code, use the jupyter notebook sz_master_071323.ipynb.  

### Code versions

The code was developed on Python 3.9.7 using optuna version 3.0.2, xgboost 1.6.1, and sklearn 1.1.1.  Performance may differ if the most updated versions of those packages are used.

Use ```pip install optuna==3.0.2``` and similar commands to install packages with specific versions.

### Scenario modification

To adjust which dataset, pyrolysis or HTC, is being used, set the variable ```p``` in the Technology Type section to true for pyrolysis and false for HTC.

To adjust which optimal solution, CSI or REI, is being used to generate uncertainty analysis points, set the variable ```c``` in the Technology Type section to true for CSI and false for REI.

Because Optuna trials are time-consuming, running the block "Running Optuna Trials - S3-S4", users may wish to only run specific trials.  This can be done by uncommenting any of the following lines of code to run that specific scenario.

```
#HTC
XGB_opt(h_X_train, h_y_train, h_X_test, h_y_test)
#RF_opt(h_X_train, h_y_train, h_X_test, h_y_test)
#DNN_opt(h_X_train, h_y_train, h_X_test, h_y_test)

# pyrolysis
#XGB_opt(p_X_train, p_y_train, p_X_test, p_y_test)
#RF_opt(p_X_train, p_y_train, p_X_test, p_y_test)
#DNN_opt(p_X_train, p_y_train, p_X_test, p_y_test)
```

### Non-deterministic results
Optuna is non-deterministic, so optimal hyperparameters are subject to change.

Likewise, DNN optimization is non-deterministic, and so R2 and RSME values for the optimal hyperparameters are subject to change.

Likewise, generating the lognormal distributions is non-deterministic, so the outputs for CSI and REI values are subject to change.  

## Additional data (not in the jupyter notebook)

Data for Table S1 and Table S2 can be found in the .xlsx versions of the dataset at the bottom of the file.

The data for Figure 2 and Figure 5 will be provided upon request.  TODO fix.

