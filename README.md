# Going Big (Data) on YouTube

The main aim of this project is to test the hypothesis: “Having a positive sentiment title and humans in thumbnails are the 
most important factors in increasing YouTube engagement.” 

## Data Collection
By the end of this section, you should have obtained 3 different files containing information of the YouTube channels of interest.

### YouTube Channels selected
The list of channel selected is saved as `socialblade_df.csv`. This list can be edited to suit your objectives.

### Channel Data
For all channels listed in `socialblade_df`, we have then collected their channel information by executing `extract_channel.ipnyb`
and the output is saved under `data/channel_df.csv`.

### Video Data
For all channels listed in `socialblade_df`, we have also collected all their video information by running the `?` file. As the
file size is rather big, we'll be hosting it in a google drive link for download.

### Aggregated Video Data
For all videos listed in `videos_df`, `aggregate_video.ipnyb` is executed to obtain aggregated values which are then stored
in `data/agg_videos_df.csv`.

## Sentiment Analysis

## Object Detection
To save all thumbnail images under the `thumbnail` folder by executing the `?` script.
