# Project Title : **Make your song Bilboard Top 100**  
<hr>

### Authors : Boseong Kang, Geonho Lee

## Description of Question and Research Topic<br>
This project aims to comprehensively analyze lyric embeddings and the characteristics of commonly used instruments for Billboard's Top 100 songs, revealing trends over time. <br>
For example, if an artist is tryting to compose a song, our model can predict which instruments with lyrics would be used to enter a Billboard Top 100. <br>
We analyze trends by clustering lyrics and examining word similarity. <br>
Then analyze the instrument usage ratios by spectralizing the songs. <br>
Finally, we combine these two analyses to build a machine learning model that predicts chart entry probability. <br>

## Project Outline/Plan <br>
Data Collection Plan (two parts, one for each author)<br>
- Part 1: Boseong Kang <br>
Use billboard.py Python library to get Billboard top 100 song's title, rank, and artist. <br>
Using lyrics from websites have copyright issue so use lyrics data from kaggle. <br>
~https://www.kaggle.com/datasets/bwandowando/spotify-songs-with-attributes-and-lyrics <br>~
~This data set has License CC BY-NC-SA 4.0 which means we can free to share, adapt if we use as NonCommercial and give appropriate credit. <br>~
https://www.kaggle.com/datasets/suparnabiswas/billboard-hot-1002000-2023-data-with-features <br> (new dataset)
New dataset License CC0: Public Domain, -> You can copy, modify, distribute and perform the work, even for commercial purposes, all without asking permission

- Part 2: Geonho Lee <br>
Use the songs collected in Part 1 to analyze their audio characteristics. <br>
Convert each song’s WAV data into a frequency spectrum using NumPy and SciPy, and extract features such as band energy ratios (bass, vocal, cymbal). <br>
Estimate the instrument approximation energy ratios to identify which sound ranges are dominant in each song. <br>
Visualize the results using Matplotlib to compare how different tracks emphasize different sound bands. <br>
Compare audio patterns with lyrical patterns to analyze overall music trends. <br>

## Model Plans (two parts, one for each author) <br>
- Part 1: Boseong Kang <br>
Logistic Regression: Similar to the MNIST Dataset, after preprocessing the data, use one-hot encoding or TF-IDF from scikit-learn to classify from the top 10 songs and others. <br>
MLP: With preprocessed words, we can classify the top 10 songs vs other songs using ReLu and the sigmoid activation function

- Part 2: Geonho Lee <br>
Visualization: Use Matplotlib to visualize each song’s frequency spectrum and energy distribution. <br> 
Model: Apply Logistic Regression from scikit-learn to analyze relationships between extracted audio features (band energy ratios) and data from Part 1. Additionally, since non-linear relationships can’t be properly captured by Logistic Regression, we will use MLP implemented with PyTorch to explore non-linear sound patterns across frequency bands.<br>

## Project Timeline
<img width="1713" height="264" alt="Image" src="https://github.com/user-attachments/assets/a10e609a-4738-4381-80b8-b7c915fb93d7" />

## Our Project Roadmap link 
It may take time to load our Roadmap.<br>
[Open the Roadmap on GitHub](https://github.com/users/boseongkang/projects/2/views/1?layout=roadmap)

