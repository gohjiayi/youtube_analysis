# Going Big (Data) on YouTube

The main aim of this project is to test the following hypotheses. <br>
A. “A positive sentiment title in a YouTube video will affect views” <br>
B. “Having humans in the thumbnail of a YouTube video will affect views”

## Links
1. [Report](https://drive.google.com/file/d/1-WZgLGmtj8yZLXgQRGSgHIJ0QZjTMqzD/view?usp=sharing)
2. [Presentation Slides](https://drive.google.com/file/d/1Ek9DPWIk8zs0lSnMeWrSBAP6BIHOHfuT/view?usp=sharing)
3. [Files Used](https://drive.google.com/drive/folders/1BGLeZOULr42pAgc6zqhshybP3YxXhFLA?usp=sharing)

## Project Directory Structure
```
├── data
│   ├── socialblade_df.csv
│   ├── channel_df.csv
│   ├── videos_df.csv
│   ├── sentiment_analysis_df.csv
│   ├── pos_tagging_df.csv
│   ├── object_detection_df.csv
│   └── features_df.csv
├── images
│   └── ...
├── models
│   └── object_detection
│       ├── coco.names
│       ├── yolov3.cfg
│       └── yolov3.weights
├── extract_channel.ipnyb
├── sentiment_analysis.ipnyb
├── pos_tagging.ipnyb
├── object_detection.ipnyb
├── data_exploration.ipnyb
├── feature_selection.ipnyb
├── model_polynomial_regression.ipnyb
├── model_random_forest.ipnyb
├── model_gradient_boosting.ipnyb
└── model_neural_networks.ipnyb
```

## Data Collection
In this section, we will be extracting information of YouTube channels of interest. All data used in this project can be downloaded from Link (3) under the Links section above.

### YouTube Channels selected
The list of 160 channels the team have selected by hand is saved in `data/socialblade_df.csv` which includes 3 columns: channel's name, channel id and category.

### Channel and Video Data
Run `extract_channel.ipnyb` to collect channel and video information for channels listed in `data/socialblade_df.csv`. The output is saved as `data/channel_df.csv` and `data/videos_df.csv`.

As YouTube API as a limit, we are only able to retrieve the latest 20,000 videos from each channel. We have also chosen to retrieve videos published from 2015 onwards.

### Aggregated Video Data
Run `aggregate_video.ipnyb` to obtain aggregated metrics for all videos listed in `data/videos_df.csv`. The output is saved as `data/agg_videos_df.csv`.

## Feature Extraction 

### Sentiment Analysis
Run `sentiment_analysis.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/sentiment_analysis_df.csv`.

### Part-of-Speech (PoS) Tagging
Run `pos_tagging.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/pos_tagging_df.csv`.

### Object Detection
Run `object_detection.ipnyb` to save all thumbnail images of videos in `data/videos_df.csv` into the `images/` folder. Then, object detection is executed for all thumbnail images downloaded. The output is saved as `data/object_detection_df.csv`. Alternatively, code for performing this step on Amazon Web Service (AWS) S3 and SageMaker has been provided to facilitate efficiency.

## Data Exploration
Run `data_exploration.ipnyb` to see visualisations generated from the data collected.

## Feature Selection
Run `feature_selection.ipnyb` to select features used for model building in the next stage, the finalised files are saved as `data/features_df.csv`.

## Model Building and Evaluation
For all 4 models built, they were split into different files as `model_[model name].ipnyb`. Run the respective files to build the models and the results can be seen in the table below.

Model | RMSE | MSE | MAE
--- | --- | --- | ---
Polynomial Regression | 24,486,700 | 599,598,500,178,391 | 2,410,707
Random Forest | 29,491,373 | 869,741,069,564,456 | 2,369,201
Gradient Boosting | 29,839,713 | 890,408,446,899,621 | 2,363,009
**Artificial Neural Network** | **20,330,611** | **413,333,730,000,000** | **2,338,276**
