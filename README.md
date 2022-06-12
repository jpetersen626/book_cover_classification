# Capstone: Book Cover Image Classification 📚

## Problem Statement

Can an image classifier classify a book's genre or the decade it was published by its cover?

The primary metric I will be using to score the models is accuracy, and I will also be examining the confusion matrices to see the misclassifications. This will allow me to see which models are having less misclassifications and could be performing better than the accuracy score tells us.

## The Data

Data source: https://github.com/uchidalab/book-dataset

This dataset came from the above repo, where they gathered all the data from Amazon. For more information on the data, refer to the above link.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**filename**|*object*|train_2_cleaned, test_2_cleaned, train_genre_cleaned, test_genre_cleaned|Filename of the image.|
|**image_url**|*object*|train_genre_cleaned, test_genre_cleaned|URL for the images.
|**title**|*object*|train_2_cleaned, test_2_cleaned, train_genre_cleaned, test_genre_cleaned|The title of the book.|
|**author**|*object*|train_2_cleaned, test_2_cleaned, train_genre_cleaned, test_genre_cleaned|The author of the book.|
|**category**|*object*|train_2_cleaned, test_2_cleaned, train_genre_cleaned, test_genre_cleaned|The genre classification of the book.|
|**meta**|*object*|train_2_cleaned, test_2_cleaned|The metadata for the book.|
|**year**|*int64*|train_2_cleaned, test_2_cleaned|The year the book was published.|
|**meta_author**|*object*|train_2_cleaned, test_2_cleaned|The author that was included when the metadata was obtained. Used to compare to the author that was in the original dataset.|
|**decade**|*object*|train_2_cleaned, test_2_cleaned|The decade in which the book was published. Converted from the year column.|
|**post_2010**|*object*|train_2_cleaned, test_2_cleaned|Whether the book was published pre-2010 or 2010 and beyond.|

## Table of Contents

|#|Folder|Notebook|Description|
|---|---|---|---|
|**1**|*code*|download_images.py|Python script to download full size images. This was taken from the repo where the data came from.|
|**2**|*code*|0.5_Downloading_Images|This is where the download_images.py script was run from in order to download full sizes of the images in the dataset.|
|**3**|*code*|01_Cleaning_EDA|Data cleaning and EDA of the book, train, and test datasets.|
|**4**|*code*|02_Cleaning_EDA_2|More data cleaning and EDA of the datasets. Also, getting more information on the books using the isbntools library.|
|**5**|*code*|03_Modeling_Genre|Various types of modeling to classify genre based on the book cover with all original 30 classes (genres) and again with the cleaned up version of 7 classes.|
|**6**|*code*|04_Modeling_Decade|Various types of modeling to classify the decade the book was published based on the cover. 5 total classes (decades) were used.|
|**7**|*code*|05_Modeling_Decade_Binary|More modeling with the decades, but this time as binary classification. The decades were split between pre-2010 and 2010 and beyond.|
|**8**|*code*|06_Modeling_Genre_2|More modeling with genres, but this time with only 5 total classes (genres).|

## Software Requirements



## Summary of Analysis

My initial idea for this project was to see if I could build a model to classify the book genre based on the cover image. I used the train and test CSV files that were in the repo for the modeling, which originally included 30 total genres. I started modeling and attempted various CNN model iterations, transfer learning with EfficientNetB0, and Data Augmentation. I then decided to reduce the genres in the hopes the models would have an easier time. I reduced the 30 genres to 7, but the models didn't seem to do any better. 

After this, I wondered if maybe building a model to predict the decade the book was published based on the cover would be more successful. However, the dataset didn't come with that information. I utilized the isbntools library to get the metadata, which included the ISBN number, title, author, publisher, year, and language. From there I converted the year published to the decade and modeled with that. I attempted the same models as above and was still having a hard time getting an accuracy score above baseline, and the confusion matrices didn't look great.

I went back to modeling with genres, but reduced it further to 5 genres. Still, I wasn't able to get an accuracy above baseline, but one model seemed to have okay predictions. However, there are still many misclassifications. It was a CNN model with 5 layers and a dropout layer.

![_](./images/Screenshot%202022-06-11%20165655%20-%20resized.png)

## Conclusions

Throughout the process, I came to the conclusion that it's very difficult for a neural net to distinguish between the various book covers. Some are more easily discernible than others, and the models tended to guess some genres better than others. However, I did discover that some of the books were misclassified from the source. Either the books were completely in the wrong genre, or because Amazon has genres and sub-genres, some books more closely resembled their sub-genre but the dataset only included the main genre. This would definitely explain some of the hardships the model went through while trying to classify the covers. Also, for the decades, some of the covers were very similar to other decades for the human eye to distinguish. This is another thing I'm sure the model had a hard time picking up on.

## Next Steps

First things first, the data either needs to be cleaned up or a whole new set acquired. I would probably prioritize trying to gather my own data from scratch and trying the modeling again. I would also consider trying different transfer learning models to see if any of those work better for this project. I'm hopeful that there's a way to get this to work better in the future!