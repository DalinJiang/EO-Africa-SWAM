# EO-Africa-SWAM
This repository includes the Python code that developed and used during the European Space Agency (ESA) EO-Africa (https://www.eoafrica-rd.org) funded SWAM Project. SWAM stands for "Sentinel 2 user-relevant water quality monitoring in small southern African water bodies". 

SWAM aimed to use the Sentinel-2 Multi-Spectral Instrument (MSI) high spatial resolution imagery to monitor water quality variables including chlorophyll-a (Chla) and total suspended matter (TSM) concentrations in the small inland water bodies in the Western Cape Province, South Africa. As a starting poitnt, the project focused on six lakes and reservoirs that are key for drinking water, irrigation and recreation, including:
* Clanwilliam Dam (CW)
* Misverstand Dam (MV)
* Voëlvlei Dam (VV)
* Theewaterskloof Dam (TW)
* Lake Zeekoevlei (ZV)
* Lake Rietvlei (RV)
<img width="449" height="361" alt="image" src="https://github.com/user-attachments/assets/ad45a78f-88de-480a-b737-e862432ee4d4" />


## 1. Chl-a
### (i) Algorithm
Chl-a concentration products were produced using the ACOLITE-RAdCor atmospheric correction ([Vanhellemont & Ruddick 2016](https://articles.adsabs.harvard.edu/full/2016ESASP.740E..55V); [Castagna & Vanhellemont, 2025](https://doi.org/10.1364/ao.546766)) to produce the remote sensing reflectance product, and then deriving Chl-a using the Mixture Density Network (MDN) from [Pahlevan et al (2020)](https://doi.org/10.1016/j.rse.2019.111604). 
### (ii) Requirements
Make sure that you have installed the [ESA SNAP](https://step.esa.int/main/download/snap-download/) (Version 12 is used here), the IdePix S2-MSI plugin. You also need to either cloned or copied an ACOLITE installation (we used acolite20250402) into your working directory. Follow the installation instructions from the [acolite github repository](https://github.com/acolite) 

## 2. TSM
### (i) Algorithm
TSM concentration products were produced using the Case 2 Regional CoastColour (C2RCC) atmopsheric correction processor ([Brockmann et al., 2016](https://articles.adsabs.harvard.edu/full/2016ESASP.740E..54B)) with the C2X-Complex neural network to produce the remote sensing reflectance product, and then deriving TSM using the [Jiang et al (2023)](https://doi.org/10.1016/j.isprsjprs.2023.09.020) algorithm with re-calibrated coefficients.  
### (ii) Requirements
Make sure you have installed [ESA SNAP](https://step.esa.int/main/download/snap-download/) (Version 12 is used here), and the plugins of C2RCC and IdePix S2-MSI in SNAP.

## 3. How to use the code
For both Chl-a and TSM estimations, a multi-step Jupyter Notebook Python code are provided, and these should be run sequentially:
* Step 1: Search for available satellite images
* Step 2: Run atmospheric correction (ACOLITE for Chl-a, C2X-Complex for TSM)
* Step 3: Retrieve water quality variables, i.e., Chl-a, TSM
* Step 4: Create data cube, which compiles Chl-a and TSM timeseries

In addition, a separate Jupyter Notebook can be used to estimate Chl-a and TSM for one image.

## 4. Data availability
SWAM Chl-a and TSM data during 2015 and 2025 with a spatial resolution of 20 m for the six water bodies are freely available at Zenodo ().

## 5. License


## 6. Project PI
* Marie Smith, CSIR, South Africa (MSmith2@csir.co.za)
* Dalin Jiang, University of Stirling, UK (dalin.jiang@stir.ac.uk)
