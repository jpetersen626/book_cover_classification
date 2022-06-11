# Capstone: Book Cover Image Classification

## Problem Statement

Can an image classifier classify a book's genre or the decade it was published by its cover?

The primary metric I will be using to score the models is accuracy, and I will also be examining the confusion matrices to see the misclassifications. This will allow me to see which models are having less misclassifications and could be performing better than the accuracy score tells us.

## The Data

Data source: https://github.com/uchidalab/book-dataset

This dataset came from the above repo. The data was all pulled from Amazon. For more information on the data, refer to the above link.

|Feature|Type|Dataset|Description|
|---|---|---|---|


## Table of Contents

|#|Folder|Notebook|Description|
|---|---|---|---|
|1|code|0.5_Downloading_Images|This is where the download_images.py script was run from in order to download full sizes of the images in the dataset.|
|2|code|01_Cleaning_EDA|Data cleaning and EDA of the book, train, and test datasets.|
|3|code|02_Cleaning_EDA_2|More data cleaning and EDA of the datasets. Also, getting more information on the books using the isbntools library.|
|4|code|03_Modeling_Genre|Various types of modeling to classify genre based on the book cover with all original 30 classes (genres) and again with the cleaned up version of 7 classes.|
|5|code|04_Modeling_Decade|Various types of modeling to classify the decade the book was published based on the cover. 5 total classes (decades) were used.|
|6|code|05_Modeling_Decade_Binary|More modeling with the decades, but this time as binary classification. The decades were split between pre-2010 and 2010 and beyond.|
|7|code|06_Modeling_Genre_2|More modeling with genres, but this time with only 5 total classes (genres).|

## Software Requirements



## Summary of Analysis



## Conclusions



## Next Steps
