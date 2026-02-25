# EO-Africa R&D SWAM
**SWAM**, stands for "*Sentinel 2 user-relevant water quality monitoring in small southern African water bodies*", is an European Space Agency (ESA) EO-Africa (https://www.eoafrica-rd.org) funded research project. 

SWAM aimed to use the Sentinel-2 Multi-Spectral Instrument (MSI) high spatial resolution imagery to monitor water quality variables including chlorophyll-a (Chla) and total suspended matter (TSM) concentrations in small inland water bodies in the Western Cape Province, South Africa. As a starting poitnt, the project focused on six lakes and reservoirs that are key for drinking water, irrigation and recreations, including:
* Clanwilliam Dam (CW)
* Misverstand Dam (MV)
* Voëlvlei Dam (VV)
* Theewaterskloof Dam (TW)
* Lake Zeekoevlei (ZV)
* Lake Rietvlei (RV)

This repository includes the Python code that developed and used during the SWAM project for Chl-a and TSM monitoring from Sentinel-2 MSI imagery.

<img width="978" height="768" alt="image" src="https://github.com/user-attachments/assets/493bb2b5-d6df-42e8-8c45-f60123bd3f61" />


## 1. Chl-a
### (i) Algorithm
Chl-a concentration products were produced using the ACOLITE-RAdCor atmospherically corrected ([Vanhellemont & Ruddick 2016](https://articles.adsabs.harvard.edu/full/2016ESASP.740E..55V); [Castagna & Vanhellemont, 2025](https://doi.org/10.1364/ao.546766)) remote sensing reflectance product, and then deriving Chl-a using the Mixture Density Network (MDN) from [Pahlevan et al (2020)](https://doi.org/10.1016/j.rse.2019.111604). 
### (ii) Requirements
Make sure that you have installed the [ESA SNAP](https://step.esa.int/main/download/snap-download/) (Version 12 is used here), and the IdePix S2-MSI plugin in SNAP. You also need to either cloned or copied an ACOLITE installation (we used acolite20250402) into your working directory, following the installation instructions from the [acolite github repository](https://github.com/acolite) 

<img width="1208" height="182" alt="image" src="https://github.com/user-attachments/assets/fe8fb8bd-c7b4-4b5f-b221-721afc7506e2" />


## 2. TSM
### (i) Algorithm
TSM concentration products were produced using the remote sensing reflectance that derived from the Case 2 Regional CoastColour (C2RCC) atmopsheric correction processor ([Brockmann et al., 2016](https://articles.adsabs.harvard.edu/full/2016ESASP.740E..54B)) with the C2X-Complex neural network, and then deriving TSM using the [Jiang et al (2023)](https://doi.org/10.1016/j.isprsjprs.2023.09.020) algorithm with re-calibrated coefficients.  
### (ii) Requirements
Make sure you have installed [ESA SNAP](https://step.esa.int/main/download/snap-download/) (Version 12 is used here), and the plugins of C2RCC and IdePix S2-MSI in SNAP.

<img width="1182" height="271" alt="image" src="https://github.com/user-attachments/assets/9e481f58-9eba-4d0f-8e7f-dbefe7fcef33" />


## 3. How to use the code
Code in this repository were developed for Sentinel-2 MSI imagery only, satellite images were accessed through the EO Africa [Innovation Lab](https://www.eoafrica-rd.org/innovation-lab/).

For both Chl-a and TSM estimations, a multi-step Jupyter Notebook Python code are provided, and these should be run sequentially:
* Step 1: Search for available satellite images (*Jupyter Notebook: xx_Step1_Search_for_images.ipynb*)
* Step 2: Run atmospheric correction (ACOLITE for Chl-a, C2X-Complex for TSM) (*Jupyter Notebook: xx_Step2_xxx.ipynb*)
* Step 3: Retrieve water quality variables, i.e., Chl-a, TSM (*Jupyter Notebook: xx_Step3_xx.ipynb*)
* Step 4: Create data cube, which compiles Chl-a and TSM timeseries (*Jupyter Notebook: xx_Step4_xx.ipynb*)

In addition, a separate Jupyter Notebook can be used to estimate Chl-a and TSM for one Sentinel-2 MSI image (*Jupyter Notebook: xx_working_example.ipynb*).

## 4. Data availability
SWAM Chl-a and TSM data during 2015 and 2025 with a spatial resolution of 20 m for the six water bodies will be freely available upon publishing.

## 5. License


## 6. Project PI
* Marie Smith, CSIR, South Africa (MSmith2@csir.co.za)
* Dalin Jiang, University of Stirling, UK (dalin.jiang@stir.ac.uk)

## 7. References
* Vanhellemont, Q., & Ruddick, K. (2016, May). Acolite for Sentinel-2: Aquatic applications of MSI imagery. In Proceedings of the 2016 ESA living planet symposium, Prague, Czech Republic (Vol. 9).
* Castagna, A., & Vanhellemont, Q. (2025). A generalized physics-based correction<? TeX\break?> for adjacency effects. Applied Optics, 64(10), 2719-2743.
* Pahlevan, N., Smith, B., Schalles, J., Binding, C., Cao, Z., Ma, R., ... & Stumpf, R. (2020). Seamless retrievals of chlorophyll-a from Sentinel-2 (MSI) and Sentinel-3 (OLCI) in inland and coastal waters: A machine-learning approach. Remote Sensing of Environment, 240, 111604.
* Brockmann, C., Doerffer, R., Peters, M., Kerstin, S., Embacher, S., & Ruescas, A. (2016, August). Evolution of the C2RCC neural network for Sentinel 2 and 3 for the retrieval of ocean colour products in normal and extreme optically complex waters. In Living planet symposium (Vol. 740, p. 54).
* Jiang, D., Matsushita, B., Pahlevan, N., Gurlin, D., Fichot, C. G., Harringmeyer, J., ... & Spyrakos, E. (2023). Estimating the concentration of total suspended solids in inland and coastal waters from Sentinel-2 MSI: A semi-analytical approach. ISPRS Journal of Photogrammetry and Remote Sensing, 204, 362-377.
