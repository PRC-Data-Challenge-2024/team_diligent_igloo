# Repo for team_diligent_igloo for the PRC Data Challenge

Team members: Antonio Pereira Barata, Bernard Bronmans, Victor Ciulei (teamlead), members of the Innovation and Datalab, Human Environment and Transportation Inspectorate, Ministry of Infrastructure and Water Management, Dutch Government.  

## Introduction
Welcome to the Gitlab Repo of our team. Please read this file carefully to understand the approach we took on predicting the estimate Take-Off Mass as part of the competition organized by the Performance Review Comission of EUROCONTROL. We include here detailed information about the feature engineering process, extra data we used, libraries, models, hardware used and runtime.

## The Why behind the Why

- Why is the challenge focusing on ATOW?
ATOW is an important input for models estimating fuel burnt and derived gaseous emissions.
The current lack of openly available ATOW is typically compensated by assuming it to be equal to a certain percentage of the Maximum TakeOff Weight (MTOW) for the relevant aircraft model.
With this challenge we aim at making available a better way to estimate ATOW, i.e. an Estimated TakeOff Weight (ETOW).

- Why an Open model?
The PRC (and many other Organizations, industrial actors and academia by the way) is interested in studies assessing the impact of Aviation to Climate Change. To this extent the availability of an open model allows for reproducibility, transparency of the results presented and in the end to trust in the performed analyses.

## Prerequisites on running the notebooks

We have worked with Python in Jupyter Notebooks. Consider running `conda env create -f conda_install.txt` using the file provided to install all the libraries. The notebooks were ran on the GPU machine locally, hence the use of torch and CUDA. Additionally we have worked with our own datafolder paths, those would also need to be properly selected. Antonio please check.

## Usage

If all libraries and data folders are in order, the notebooks should be ran in the order of the notebook names (except downloading the data, if the user already has it.)

## Our approach

We decided to use an XGBoost model and performed a random search for the hyperparameter optimisation. We train the model  using a Stratified 5-Fold approach to ensure that the resulting best hyperparameters are robust for the final_submission file. The feature engineering is core to our approach and is described in the next paragraph.

## Feature Engineering

## What we didn't do

We thought that it was not in the spirit of the competition to reverse engineer the flights and uncover airlines and the aircraft registration number, even though this was possible. Such information would have led to finding out the precise engine and engine type, its age and modifications, which would potentially improve the prediction power of our model. Something we also didn't manage to test in time was whether adding engine noise information would have helped the prediction.

## Contributing
People who want to contribute are free to do so, by reusing the available code. Fork from this github and mention the authors and github whenever you make a publication. 

## License
This project and its accompanying files is licensed under the GNU GPLv3 license and is free to use or modify without any restrictions. Please see the accompanying GNU General Public License V3 Terms and Conditions in the file called COPYING.txt



