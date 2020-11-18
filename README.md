# Going Big (Data) on YouTube

The main aim of this project is to test the hypothesis: “Having a positive sentiment title and humans in thumbnails are the 
most important factors in increasing YouTube engagement.”

## Project Directory Structure
```
├── data
│   ├── socialblade_df.csv
│   ├── channel_df.csv
│   ├── videos_df.csv
│   ├── agg_videos_df.csv
│   ├── sentiment_analysis_df.csv
│   ├── parse_tree_df.csv
│   ├── object_detection_df.csv
│   ├── features_df.csv
├── images
│   ├── thumbnail1.jpg
│   ├── thumbnail2.jpg
│   ├── ...
├── models
│   └── object_detection
│       ├── coco.names
│       ├── yolov3.cfg
│       └── yolov3.weights
├── extract_channel.ipnyb
├── aggregate_video.ipnyb
├── sentiment_analysis.ipnyb
├── parse_tree.ipnyb
├── object_detection.ipnyb
├── data_exploration.ipnyb
├── feature_selection.ipnyb
├── model_polynomial_regression.ipnyb
├── model_random_forest.ipnyb
├── model_gradient_boosting.ipnyb
└── model_neural_network.ipnyb
.   .
.   .
```

## Data Collection
To skip the data collection step, you may simply download all collected data from our Google Drive folder linked [here](https://drive.google.com/drive/folders/1BGLeZOULr42pAgc6zqhshybP3YxXhFLA?usp=sharing).

In this section, we will be extracting information of YouTube channels of interest.

### YouTube Channels selected
The list of 160 channels the team have selected by hand is saved in `data/socialblade_df.csv` which includes 3 columns: channel's name, channel 
id and category.

### Channel Data
Run `extract_channel.ipnyb` to collect channel information for channels listed in `data/socialblade_df.csv`. The output is saved as 
`data/channel_df.csv`.

### Video Data
Run `???.ipnyb` to extract all video information of channels listed in `data/socialblade_df.csv`. As YouTube API as a limit, we are only able to
retrieve the latest 20k videos from each channel. We have also chosen to retrieve videos published from 2015 onwards. The output is saved as 
`data/videos_df.csv`.

### Aggregated Video Data
Run `aggregate_video.ipnyb` to obtain aggregated metrics for all videos listed in `data/videos_df.csv`. The output is saved as `data/agg_videos_df.csv`.

## Feature Extraction 

### Sentiment Analysis
Run `sentiment_analysis.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/sentiment_analysis_df.csv`.

### Parse Tree
Run `parse_tree.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/parse_tree_df.csv`.

### Object Detection
Run `object_detection.ipnyb` to save all thumbnail images of videos in `data/videos_df.csv` into the `images/` folder (~2GB). Then, object detection is executed for all thumbnail images downloaded. The output is saved as `data/object_detection_df.csv`. Alternatively, code for performing this step on Amazon Web Service (AWS) S3 and SageMaker has been provided to facilitate efficiency.

## Data Exploration
Run `data_exploration.ipnyb` to see visualisations generated from the data collected.
Visualisations includes:
- Video Views Distribution by Category
- Video Count Distribution by Category
- Subscriber Count Distribution by Category
- Correlation Matrix of Comment Count, Like Count, Dislike Count, View Count, Days Published and Title Length
- Distribution of Videos Published by Hour
- Distribution of Videos by Day of Week
- Top 10 Most Watched Videos
- Top 10 Most Liked Videos
- Top 10 Most Disliked Videos
- Top 10 Most Commented Videos
- Distribution of Most Popular Words in Truncated Titles

## Feature Selection
Run `feature_selection.ipnyb` to select features used for model building in the next stage, the finalised files are saved as `data/features_df.csv`.

## Model Building and Evaluation
For all 4 models built, they were split into different files as `model_[model name].ipnyb`. Run the respective files to build the models and the results can be seen in the table below.

Model | RMSE | MAE | 
--- | --- | --- 
Polynomial Regression | 0.00 | 0.00
Random Forest | 0.00 | 0.00
Gradient Boosting | 0.00 | 0.00 
Artificial Neural Network | 0.00 | 0.00 