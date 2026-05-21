# integrative-industry-synthesis-project
This my seventh project in the capstone course of Udacity's Master's Degree in AI (https://www.udacity.com/masters-artificial-intelligence). 

## Overview
The aim of this project is to develop data-driven models and workflows for the German energy market. We start by loading and cleaning several datasets:
- From the regulator for the German energy market, we obtained time series for the total load (i.e. the total energy demand on a given day) and the residual load (i.e. the fraction of the energy supply coming from conventional sources on that day), as well as a time series for daily wholesale energy prices.
- From the German Meteorological Service, we obtained time series for variables driving the supply of renewable energies, namely wind speed, sunshine hours, and temperatures.
- From Yahoo Finance, we obtained time series for daily prices of the commodities natural gas and European carbon allowances, which drive the marginal cost of natural gas power plants.

We use these datasets in order to develop three building block models:
- Our first model is intended to predict the daily wholesale energy price, given the total load, the residual load, and the commodity prices on each day.
- Our second model is intended to predict the daily residual load, given the total load and the meteorological variables on each day.
- Our third model is intended to forecast the total load for a given day, given the timeseries of total loads and temperatures up to that day.

The building block models are then integrated into a system of several work flows and potential use cases in the German energy market.
We also list some limitations and potential improvements of our system, and conclude with a short summary.

## How to run the project
The main component of the project is the Jupyter notebook 'integrative_industry_synthesis.ipynb'.
When checking out this repository, the following dataset files are already included:
	
	commodity_prices.csv
	Gro_handelspreise_201501010000_202412310000_Tag.csv
	produkt_klima_tag_18580101_20241231_01691.txt
	Realisierter_Stromverbrauch_201501010000_202412310000_Tag.csv

In addition, the repository contains a 'requirements.txt' file with all required dependencies, which was generated via the command
	
	pip freeze > requirements.txt
	
It can be used e.g. in a virtual Anaconda environement by opening an Anaconda prompt window in the project directory and running the following commands:

	conda create -n env_msai_cap_7 python
	conda activate env_msai_cap_7
	pip install -r requirements.txt
	python -m ipykernel install --user --name=env_msai_cap_7
	jupyter notebook
	
The last command opens a Jupyter GUI, where one needs to click on the notebook 'integrative_industry_synthesis.ipynb' and then click on Run... -> Run All Cells

