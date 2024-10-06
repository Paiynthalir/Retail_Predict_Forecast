## Table of Contents
- [Retail_Predict_Forecast](#retail_predict_forecast)
- [Project Organization](#project-organization)
- [Order of Running the Data Preparation Notebooks](#order-of-running-the-data-preparation-notebooks)
- [Project Setup](#project-setup)
- [Custom Functions](#custom-functions)
- [Quick Commands to Push Changes to Git](#quick-commands-to-push-changes-to-git)

# Retail_Predict_Forecast

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

This project is to build two different models that will be deployed into production as API:
1. A predictive model using a Machine Learning algorithm to accurately predict the sales revenue for a given item in a specific store at a given date.
2. A forecasting model using a time-series analysis algorithm that will forecast the total sales revenue across all stores and items for the next 7 days

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         Retail_Predict_Forecast and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── Retail_Predict_Forecast   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes Retail_Predict_Forecast a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------
## Order of running the data preperation notebooks:
1. SamyappanNallamuthu_Paiynthalir-24715435-DataPreparation.ipynb - under notebooks folder
   This notebook is to be run first since this is to merge the raw data and come up with the interim files, which can later be used for further data processing needed

2. Predictive and Forecasting folders contains model experiments 

3. SamyappanNallamuthu_Paiynthalir-24715435-datasplitForPredictiveModels - under Predictive folder
   This notebook has to be run first before running any other model specific experiment notebooks under Predictive folder. Because this notebook produces the final train, validation and test datasets that can be directly used for prediction modelling

4. Notebooks under Forecasting models can be run in any order since each notebook uses the interim data saved and performs more data transformation based on the algorithm chosen. 

----------
## Project setup
1. Go to the projects folder (Retail_Predict_Forecast)
2. pip install cookiecutter-data-science (give the 'Retail_Predict_Forecast as project and repo names)
3. ccds
4. cd Retail_Predict_Forecast 
5. initialise git repo 
	- git init
6. login to git repo in a browser and create a repository with same <folder name>
7. In your local repo, link it with Github (replace the url with your username) -------> follow the steps given in git website
	- git remote add origin git@github.com:<username>/<repo name>.git
8. Install Python version with Pyenv and set the local version
	- pyenv install 3.11.4 and
	- pyenv local 3.11.4
9. poetry init
	- poetry add pandas==1.5.3 numpy==1.23.2 prophet==1.1.5
	- poetry add jupyterlab==4.2.3 scikit-learn==1.5.1
	- poetry export --output requirements.txt (generate the requirements file)
10. poetry shell 
11. poetry run jupyter lab - This command is to run the jupyter lab to run experiments with notebooks

--------

## Custom Functions 

The Python package of custom module on TestPypi that is used in this project is https://test.pypi.org/simple/my_krml_pine==2024.0.1.19

Tried to install this package through poetry, but was throwing error even after multiple tries. So in consideration of the timelines of the project delivery, as of now used pip command in the notebook to install this custom package. In future, it is recommended to clean the code.

--------

## Quick commands to push the changes to git

git add .
git commit -m "message"
git push 

--------




