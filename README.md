
# Generic Benign IDS Model using Clustering

This project was done as part of my coursework in CMPE 789 ML for Cyber Analytics.

## Problem Statement

To understand the behavior of benign(normal traffic) data in Intrusion Detection Systems(IDS) and classify them into different clusters based on their common properties. Also, to analyze and compare how the benign traffic is different across datasets. Finally, use this information to build a generic benign classifier using a distance threshold.

## Datasets

This project uses primarily the open-source IDS datasets provided by the University of New Brunswick(UNB).
- CIC-IDS 2017 - https://www.unb.ca/cic/datasets/ids-2017.html
- CIC-IDS 2018 - https://www.unb.ca/cic/datasets/ids-2018.html

In addition to these two datasets, I have also used the IDS dataset created by the University of Sannio, Benevento. This dataset was created using the [CICFlowMeter](https://github.com/ahlashkari/CICFlowMeter) tool provided by UNB
- USB-IDS - http://idsdata.ding.unisannio.it/

## Methodology
In this project, clustering is used to understand the patterns in benign data. Initially, the benign cluster centroids of the CIC-IDS 2017 dataset are taken as base and new classes of malicious data are added to the dataframe. The Euclidean distance between the benign cluster centroids and the new cluster centroids formed by the new data is calculated. The binary classifier is trained on the CIC-IDS 2017 and a mean distance between the benign clusters and the malicious clusters is obtained as the threshold. This threshold is then used to test on the CIC-IDS 2018 dataset to classify different classes as either benign or malicious.

## Execution

I have used Jupyter notebooks to implement this project. It can be either run locally on your machine or you can upload and run using Google Colab.

**Note:** The datasets are pretty huge and sometimes the Google Colab can throw out of memory errors or the imported pandas dataframe might be corrupted with objects instead of the actual datatypes. This issue can be either solved by running it locally on a machine with a good amount of RAM(min. 8GB) or the code can be modified to load the data one file at a time, or in chunks as discussed [here](https://www.geeksforgeeks.org/how-to-load-a-massive-file-as-small-chunks-in-pandas/) and then concatenate it to get a single dataframe for processing.
