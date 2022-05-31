# Capstone: Book Image Classification

## Problem Statement

Can an image classifier classify a book's genre by its cover?

## Overview

Data source: https://github.com/uchidalab/book-dataset

My approach is to build a NN model to classify these images into their respecitve genres. There are more than 1000 images for each class, and there are 30 total classes in the train and test set. I haven't narrowed down the types of models in totality quite yet, but I am planning on trying NN and CNN variations.

My success metric will be accuracy, and the goal is to beat the baseline score. My assumption is that the model will be able to distinguish genre based on images on the cover (or perhaps the text), but I'm not sure yet. The risks are that the model doesn't pick up on anything distinct and can't determine the genre.