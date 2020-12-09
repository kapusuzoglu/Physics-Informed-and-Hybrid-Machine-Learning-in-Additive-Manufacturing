# Physics-Informed-Machine-Learning
Physics-based models are used to inform the deep learning models to better predict the quantity of interests.

## notebooks
DataGeneration: Generates and saves data.
	1. Loop over measured data (bond length and porosity)
	2. Loop over temperature evolution results from simulations and predict neck growth and porosity for synthetic data (physics-based).

PorosityPredictions: Predict porosity & bond length using Physics-based models (Temperature data is obtained using the analytical solution for transient heat conductions for 25 sets of parts stored in \data\ModelData)


## data
labeled_data -> results
unlabeled_data -> results (1519 samples)


1. supervised
	- temperature (simulations)
	- experiment
2. unsupervised
	- temperature (simulations for 1519 synthetic data)
		-- "temperature/syntheticdata/" (temperature evolution for 25 synthetic data with similar inputs as used in expeirments)
	- simulation (process parameters for synthetic data)
		-- SyntheticData: 25 parts representing 25 experiments
		-- Parts: 1519 parts representing random synthetic data
		
## Results
1. results
	- Sintering model developed by BK

