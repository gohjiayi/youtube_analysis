# Going Big (Data) on YouTube

The main aim of this project is to test the hypothesis: “Having a positive sentiment title and humans in thumbnails are the 
most important factors in increasing YouTube engagement.” (TBD)

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
├── images
│   ├── thumbnail1.jpg
│   ├── thumbnail2.jpg
│   ├── ...
├── models
│   ├── model1.h5
├── extract_channel.ipnyb
├── aggregate_video.ipnyb
├── data_exploration.ipnyb
├── sentiment_analysis.ipnyb
├── parse_tree.ipnyb
├── object_detection.ipnyb
├── models.ipnyb
.   .
.   .
```

## Data Collection
To skip the data collection step, you may simply download all collected data from our Google Drive folder linked here (insert link).

In this section, we will be extracting information of YouTube channels of interest.

### YouTube Channels selected
The list of 160 channels the team have selected by hand is saved in `data/socialblade_df.csv` which includes 3 columns: channel's name, channel 
id and category.

### Channel Data
Run `extract_channel.ipnyb` to collect channel information for channels listed in `data/socialblade_df.csv`. The output is saved as 
`data/channel_df.csv`.

### Video Data
Run `XXXX.ipnyb` to extract all video information of channels listed in `data/socialblade_df.csv`. As YouTube API as a limit, we are only able to
retrieve the latest 20k videos from each channel. We have also chosen to retrieve videos published from 2015 onwards. The output is saved as 
`data/videos_df.csv`.

### Aggregated Video Data
Run `aggregate_video.ipnyb` to obtain aggregated metrics for all videos listed in `data/videos_df.csv`. The output is saved as `data/agg_videos_df.csv`.

## Data Exploration
Run `data_exploration.ipnyb` to see visualisations generated from the data collected.

## Data Collection using Machine Learning Algorithms 

### Sentiment Analysis
Run `sentiment_analysis.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/sentiment_analysis_df.csv`.

### Parse Tree
Run `parse_tree.ipnyb` for all videos listed in `data/videos_df.csv`. The output is saved as `data/parse_tree_df.csv`.

### Object Detection
Run `object_detection.ipnyb` to save all thumbnail images of videos in `data/videos_df.csv` into the `images/` folder (~2GB). Then, object
detection is executed for all thumbnail images downloaded. The output is saved as `data/object_detection_df.csv`.

## Feature Selection
(TBD)

## Model Building and Evaluation
Run `models.ipnyb` which will save our selected model to the `models/` folder. (TBD)