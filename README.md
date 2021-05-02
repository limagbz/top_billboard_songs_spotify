# A study of billboard's most popular songs from 1950 to 2015
This repository is a complement of the visualization done in Tableau and available on [Tableau Public: BillboardSpotify](https://public.tableau.com/views/BillboardSpotify/Storytelling?:language=en&:display_count=y&:origin=viz_share_link). 

## Preparing the Environment
This section explains how to use/reproduce this project. Note that this tutorial is made to work on a linux machine.

### 1. Installing Python
#### PyEnv
This projects used Python 3.8.5. For management of multiple python versions we recommend the installation of [Pyenv](https://github.com/pyenv/pyenv). For installation of the tool visit [Pyenv Installation](https://github.com/pyenv/pyenv#installation). After the installation you are ready to install the python version by using the command:

```shell
pyenv install 3.8.5
```
To make this version the default for this project you can use the command below (make sure you are on this folder): 

```shell
pyenv local 3.8.5
```

#### Without PyEnv
If you don't want to use pyenv, make sure you are using the correct version of python. You can see instruction on how to install python on [Python Downloads](https://www.python.org/downloads/).

### 2. Python Libraries and Virtual Environments (Dependency Manager)
#### Poetry
For dependency management we use the [Poetry Project](https://python-poetry.org/). For installation see [Poetry Installation](https://python-poetry.org/docs/#installation). After the installation, all the packages used by this project can be installed via:
```shell
poetry install
```
To use the packages, you also need to activate the environment by using the command:
```shell
poetry shell
```
For other commands, see [Poetry Commands](https://python-poetry.org/docs/cli/).

#### Other Dependency Management or No Virtual Environments
If you don't want to use Poetry or any virtual environments, we provide a "requirements.txt" file. To install this on your version of python:

```shell
python -m pip install -r requirements.txt
```

## Data
All the data used on this project and their transformations can be found in the data folder of this repository. The raw data was acquired on the [Billboard](https://github.com/kevinschaich/billboard) repository. To download the data using the code (*1-Data Acquisition*) you first need to create a .env file in the root folder of the project containing the following information: (1) SPOTIPY_CLIENT_ID, (2) SPOTIPY_CLIENT_SECRET, (3) SPOTIFY_OAUTH_TOKEN. For (1) and (2) the credentials can be obtained by creating an application on spotify, this can be done by following ["Web API Tutorial"](https://developer.spotify.com/documentation/web-api/quick-start/). For (3) you can use the [Developer's console](https://developer.spotify.com/console/get-search-item/), click on the button "Get Token", Login into your account and copy the value generated in the field. 

## Project Structure
The project's structure is based on the [Cookiecutter Data Science Project Template](https://drivendata.github.io/cookiecutter-data-science/) by Driven Data. We recommend reading the documentation for a deep understanding on how it works and the benefits of this approach. For this project the organization occurs as folows:

    ├── LICENSE               <- Project's License of Use
    ├── README.md             <- This document
    ├── data
    │   ├── external          <- Data from third party sources.
    │   ├── interim           <- Intermediate data that has been transformed.
    │   ├── processed         <- The final, canonical data sets for study
    │   └── raw               <- The original, immutable data dump.
    ├── BillboardSpotify.twbx <- Tableau Workbook
    ├── poetry.lock           <- Poetry file that configures the virtual environment
    ├── pyproject.toml        <- Build System file configuration (PEP 518)
    └── requirements.txt      <- The requirements file for reproducing the analysis environment
