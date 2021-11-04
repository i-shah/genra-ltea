GenRA-LTEA
==============================

Generalised Read Across (GenRA) in Python: Proof-of-Concept (LTEA)

Read-Across is extensively used to fill data gaps for compounds that have not been evaluated. We created Genralised Read-Across (GenRA) as a computational toxicology tool to simulate the manual reasoning of a human expert using similarity-weighted activity.

This repository provides a case example using genra-py, a Python 3 implementation of GenRA based on the scikit-learn estimator.  We show how to utilize genra-py to create a proof-of-concept utilizing published chemical structure, LTEA biological hit-call data, and toxicity data.

![image](https://user-images.githubusercontent.com/20391049/140403097-680c4db8-d26e-4c95-993d-6fe2b47cc33f.png)



Getting Started
==============================
The entire analysis is implemented using open source tools and the genra-py package. 

To get started:

`pip install genra`

Alternatively, either clone or download this repository:

Running the notebooks in this repository requires Python 3, Anaconda, Jupyter and some additional configuration.

1. Install Python 3, anaconda/conda and Jupyter Lab
Clone this repo:

`git clone https://github.com/i-shah/genra-ltea.git`

2. Go into genra-py directory and create genra-py conda environment:

`conda create -f condaenv.yml`

3. Activate conda environment:

`conda activate genra-ltea`

4. Add this conda environment as a kernel to jupyter-lab:

`ipython kernel install --user --name=genra-ltea`

5. Copy the notebooks/dotenv file to notebooks/.env and edit the environemnt variables (replace path_to_top with the correct directory name):

`TOP=path_to_top/genra-ltea SRC=path_to_top/genra-ltea/src DAT=path_to_top/genra-ltea/data FIG=path_to_top/genra-ltea/figs`

Further details are provided in the genra-py user manual 

`notebooks/manual/001-genra-py-user-manual.ipynb`





Project Organization
------------
No spaces in filenames!

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data               <- Data from public domain sources.
    │   └─ shah-2016       <- https://doi.org/10.1016/j.yrtph.2016.05.008
    |
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── notebooks          <- Jupyter notebooks (XXX-UU-DDDDDD.ipynb). Convention:- 
    |   |                     XXX = numeric sequence 
    |   |                     UU  = user initials
    |   |                     DDDDDDD = descriptive string 
    |   ├─is               <- Imran Shah
    |   ├─gp               <- Grace Patlewicz
    |   ├─tt               <- Tia Tate
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    ├── condaenv.yaml      <- The spec for creating a conda environment. Generated using:
    |                          conda env export > condaenv.yml
    │                         Can create environment using:
    |                          conda env create -f condaenv.yml
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    |
    ├── tools              <- GenRA command-line tools (installed in /usr/local/bin) that depend on src 
    └── src                <- Source code for use in this project.
        │
        └─genra          
            ├─db           <- Database access and etl
            ├─data         <- Data preparation / manipulation
            |  └─chm       <- chemical structure and physchem data processing 
            |  └─bio       <- bioactivity data processing             
            |  └─tox       <- toxicity data processing             
            ├─rax          <- Read Across prediction
            |  └─skl       <- Standalone based on scikit-learn
            |  └─srv       <- Server based on mongodb 
            ├─viz          <- Visualization 
            ├─utl          <- Utilities
            
           
Built using cookiecutter 
