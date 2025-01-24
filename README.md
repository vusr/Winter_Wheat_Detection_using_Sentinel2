## Goal
The goal of this project is to make a machine-learning model to detect winter wheat fields in Armenia using the datasets available in the USA.

## Description
This repository consists of source code for the winter wheat detection model using sentinel2 images of the year 2023 in the following 10 counties in Kansas
* Cheyenne
* Decatur
* Greeley
* Norton
* Phillips
* Rawlins
* Sheridan
* Sherman
* Thomas
* Wallace
We have selected the above 10 counties from Kansas because their weather is most similar to Armenia's. Weather similarity is calculated based on Cosine similarity and Euclidean similarity between the daily weather of these regions throughout 2023. Various experiments have been conducted to select the appropriate data and model.

## Data Preparation
* Input data: sentinel2, weather
* Target or GT data: Winter Wheat from USDA's CDL layer
* Shape matching: Sentinel2 and Winter Wheat data downloaded from the Google Earth engine have slight differences. Sentinel2 width and height are not exactly the same as thrice the widths and heights of the CDL layer. We have matched the shapes by center cropping.
* Normalization: We have clipped the sentinel2 pixel values to \[0, 10000\] and min-max normalized all bands with min as 0 and max as 10000
* Numpy files: After determining the data split, we have prepared npy files for inputs and labels so they can be loaded directly into a Dataloader during training, validation, and testing
* Code: All data preparation code for each of the experiments can be found in the data_preparation_scripts
* Data preparation required a high amount of RAM and disk space. We have used a computer with 64GB of RAM.

## Experiments and Results
