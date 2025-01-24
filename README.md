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

## Experiments and Results: (Different counties for train, val, and test)
![table1](https://github.com/user-attachments/assets/f9ed9cfc-1a3d-4636-825e-bfc63d50c8e6)

## Experiments and Results: (Training and testing on all counties)
![table2](https://github.com/user-attachments/assets/b98b1c13-ced0-42cc-87fd-aa8f7135e0c8)

## Model architecture:
![architecture](https://github.com/user-attachments/assets/16010d8b-3596-434f-8750-d1b638c06078)

## Test result visualization:
![test_data_Cheyenne_visualization](https://github.com/user-attachments/assets/f35cae10-decd-4385-bfd5-e563e453f89f)
![test_data_Decatur_visualization](https://github.com/user-attachments/assets/c7bdee5b-3ea8-4c44-973f-726ece0bb6f6)
![test_data_Greeley_visualization](https://github.com/user-attachments/assets/bfba2c7a-c741-44d8-ab14-6e23bfd0c5b1)
![test_data_Norton_visualization](https://github.com/user-attachments/assets/c71f78f7-d20e-4b83-b662-999911249836)
![test_data_Phillips_visualization](https://github.com/user-attachments/assets/3af80fef-f022-4df7-8ea3-9814c3ca50ed)
![test_data_Rawlins_visualization](https://github.com/user-attachments/assets/4bfe0e1b-eb05-4120-a25b-82132db6f47b)
![test_data_Sheridan_visualization](https://github.com/user-attachments/assets/9a3dd25b-ea87-4482-ae3c-705594b8979a)
![test_data_Sherman_visualization](https://github.com/user-attachments/assets/9bd53464-3ca2-47d9-b065-3cb6e0a37a85)
![test_data_Thomas_visualization](https://github.com/user-attachments/assets/df5bfc09-e8a9-4db6-8f6f-305d1faf6c5e)
![test_data_Wallace_visualization](https://github.com/user-attachments/assets/4f1196e8-0faa-4fc8-95e7-3a55cb83d535)









