# Physics-Informed-Machine-Learning
Physics-based models are used to inform the deep learning models to better predict the quantity of interests.

## notebooks
DataGeneration: Generates and saves data.
	1. Loop over measured data (bond length and porosity)
	2. Loop over temperature evolution results from simulations and predict neck growth and porosity for synthetic data (physics-based).

MCdropout_PorosityPredictions: Utilize *PorosityPredictions* to predict porosity and bond length and use these predictions as training samples for the (Bayesian) Neural Network.

PorosityPredictions: Predict porosity & bond length using Physics-based models (Temperature data is obtained using the analytical solution for transient heat conductions for 25 sets of parts stored in \data\ModelData)

predict_BL: Predict bond length using Physics-based models (Temperature data is obtained using Abaqus for different 25 sets of parts)

Physics-Informed NN_bond: Physics-Informed neural network model with bond length used as physics law. 
Dimensionless bond length should be less than 1.

Physics-Informed NN_bond-poro: Physics-Informed neural network model with bond length and porosity used as physics law.
Dimensionless bond length should be less than 1.
Final porosity predictions should be less than inital porosity.

## data
labeled_data -> results
labeled_data_BK_constw -> results_BK
labeled_data_BK_constw_unique -> results_unique
labeled_data_BK_constw_v2 -> results_BK_v2

unlabeled_data -> results (1519 samples)
unlabeled_data_25part -> results (25 samples)
unlabeled_data_BK_constw -> results_BK
unlabeled_data_BK_constw_unique -> results_unique
unlabeled_data_BK_constw_v2 -> results_BK_v2


1. supervised
	- temperature (simulations)
	- experiment
2. unsupervised
	- temperature (simulations for 1519 synthetic data)
		-- "temperature/syntheticdata/" (temperature evolution for 25 synthetic data with similar inputs as used in expeirments)
	- simulation (process parameters for synthetic data)
		-- SyntheticData: 25 parts representing 25 experiments
		-- Parts: 1519 parts representing random synthetic data

labeled_data_BK	& unlabeled_data_BK: experimental results and predictions of these 25 parts using physics model is included in labeled_data_BK & 25 synthetic data physics model predictions are included in unlabeled_data_BK.


## Results]
1. results
	- Hernandez' Sintering model
2. results_unique
	- Results based on unique samples (i.e., not more than one sample with the same process parameters)
3. results_BK
	- Sintering model developed by me (BK)
4. results_BK_v2
	- Sintering model developed by me (BK), correct version, in which the width of the filament does not change, and height changes.

