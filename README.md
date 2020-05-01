# FAIRView Corpus: Visual Explanations for Video Summaries


This repository contains:
 * 200 [videos](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/data/video_dataset_content.csv) machine annotated with key concepts extracted from video subtitles and video frames;
 * 800 [video summaries](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/data/video_summaries)  (four summaries per video) machine annotated with concepts extracted from video subtitles and frames;
 * 3200 [visual explanations](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/data/visual_explanations) (four explanations per video summary with different levels of *transparency*):
   * semantic coverage,
   * semantic prominence
   * quantity coverage
   * distance
 * human validated **utility** of each visual explanation type ([mTurk crowdsourcing study_1](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study1/user_study1_template.md) with 20 videos and single summary)
 * human validated **representativeness** of video summaries with regard to their original videos ([mTurk crowdsourcing study_2](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study2/user_study2_template.md) with 18 videos with 2 summaries per video). In total 36 video-summary pairs


All results are published in the following paper:

> Oana Inel, Nava Tintarev and Lora Aroyo: **[Eliciting User Preferences for Personalized Explanations for Video Summaries](https:...)**. [UMAP 2020](https://um.org/umap2020/).


If you find the paper and the data useful in your research, please consider citing:

```
@inproceedings{inel2020eliciting,
  title={Eliciting User Preferences for Personalized Explanations for Video Summaries},
  author={Inel, Oana and Tintarev, Nava and Aroyo, Lora},
  booktitle={To Appear in the Proceedings of the 28th Conference on User Modeling, Adaptation and Personalization (UMAP)},
  year={2020},
  organization={ACM}
}
```

## User Studies

The following online user studies have been conducted in order to evaluate the utility of four types of visual explanations:
 - [User Study 1](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study1/user_study1_template.md): identify which type of visual explanation is preferred when assessing the representativeness of video summaries
 - [User Study 2](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study2/user_study2_template.md): understand how one type of visual explanation is used by participants when asked to compare two summaries of the same video for their representativeness 
 
 
## Files structure

    .
    ├── data                                  # Folder storing all experimental data
    |   ├── video_dataset_metadata.csv        # CSV containing the experimental videos and their metadata
    |   ├── video_dataset_content.csv         # CSV containing the experimental videos and links to relevant processed files
    |   ├── video_summaries                   # Folder containing all video summaries (split into smaller archives due to 
    |   |                                       space limitation); For each video four video summaries are created, following 
    |   |                                       the notation: summary_{videoId}___{no_seconds}___{summary_type}.mp4, where  
    |   |                                       {no_seconds} = {10s, 20s} and {summary_type} = {aq, nq}
    |   ├── video_subtiles                    # Folder containing all video subtitles (one file per video); extracted through   
    |   |                                       video transcription (see notebook below)
    |   ├── named_entities_subtitles          # Folder containing all named entities extracted from video subtitles (one file 
    |   |                                       per video); extracted through named entity extraction (see notebook below)
    |   ├── labels_video_frames               # Folder containing all labels extracted from video frames (one file per video); 
    |   |                                       extracted through named entity extraction (see notebook below)
    |   ├── key_concepts_videos
    |   |   └── video_concepts_overview.csv   # CSV containing the key concepts extracted from videos (see notebook below); 
    |   |                                       each line contains the key concepts of an experimental video
    |   ├── concepts_video_summaries          # Folder containing two files for each video summary: one storing the named 
    |   |                                       entities of the video summary, 
    |   |                                       entities_{videoId}___{no_seconds}___{summary_type}.csv
    |   |                                       and one storing the labels of the video summary, 
    |   |                                       labels_{videoId}___{no_seconds}___{summary_type}.csv, 
    |   |                                       where {no_seconds} = {10s, 20s} and {summary_type} = {aq, nq}
    |   └── visual_explanations               # Folder containing all visual explanations (split into smaller archives due to 
    |                                           space limitation); Four visual explanations are available for each video 
    |                                           summary, following the notation: 
    |                                           {videoId}___{no_seconds}___{summary_type}_{explanation_type}.png, where 
    |                                           {no_seconds} = {10s, 20s} {summary_type} = {aq, nq} and {explanation_type} = 
    |                                           {summary_wordcloud, overlap_fraction, overlap_wordcloud, 
    |                                           combined_wordcloud_and_fraction}
    ├── notebooks                             # Jupyter Notebooks used for data processing
    │   ├── ...Speech to Text.ipynb           # Jupyter Notebook for video subtitles extraction
    │   ├── ...Label Detection.ipynb          # Jupyter Notebook for label extraction from video frames
    │   ├── ...Natural Language....ipynb      # Jupyter Notebook for entity extraction from video subtitles
    │   └── ...Explanations Generation.ipynb  # Jupyter Notebook for identifying the key concepts in videos and generating     
    |                                           the four types of visual explanations
    ├── user_study1                           # Template, data and analysis of user study 1
    │   ├── user_study1_template.html         # User study 1 template (to be run on mTurk)
    │   ├── user_study1_template.md           # Visual interface of user study 1 template
    |   ├── img                               # Folder containing parts of the visual interface of user study 1
    │   ├── input_user_study1.csv             # Input file for user study 1
    │   ├── crowd_results_userstudy1.csv      # Crowdsourcing results of user study 1
    |   └── Analyze ... Study1.ipynb          # Jupyter Notebook used for processing the results of user study 1
    ├── user_study2                           # Template, data and analysis of user study 2
    │   ├── user_study2_template.html         # User study 2 template (to be run on mTurk)
    │   ├── user_study2_template.md           # Visual interface of user study 2 template
    |   ├── img                               # Folder containing parts of the visual interface of user study 2
    │   ├── input_user_study2.csv             # Input file for user study 2
    │   ├── crowd_results_userstudy2.csv      # Crowdsourcing results of user study 2
    |   └── Analyze ... Study2.ipynb          # Jupyter Notebook used for processing the results of user study 2
    └──.



## Machine Annotation of Videos and Video summaries

We used three enrichment tools for machine the annotations:
* [video transcription](https://cloud.google.com/video-intelligence/docs/transcription)
* [named entity extraction](https://cloud.google.com/natural-language/docs/analyzing-entities)
* [video labeling](https://cloud.google.com/video-intelligence/docs/analyze-labels)

If you want to regenerate the results of the machine enrichment tools used for the machine annotation of both original videos and video summaries, which can be found in the [data folder](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/data) of this repository, you need to register for the following Google Cloud APIs and follow their instructions. A schelethon notebook for running each of the APIs below is provided in the [notebooks folder](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/notebooks) of this repository.
 * [Cloud Storage](https://cloud.google.com/storage) - Google Cloud Storage
 * [Speech-to-Text](https://cloud.google.com/video-intelligence/docs/transcription) - part of Google Cloud Video Intelligence API to transcribe the videos (extraction captions or subtitles): [schelethon notebook](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/notebooks/Google%20Video%20Intelligence%20API%20-%20Speech%20to%20Text.ipynb)
 * [Label Detection](https://cloud.google.com/video-intelligence/docs/analyze-labels) - part of Google Cloud Video Intelligence API to detect and extract information about entities shown in video and video summaries: [schelethon notebook](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/notebooks/Google%20Video%20Intelligence%20API%20-%20Label%20Detection.ipynb)
 * [Entity Extraction](https://cloud.google.com/natural-language/docs/analyzing-entities) - part of Google Cloud Natural Language to extract entities from the video subtitles: [schelethon notebook](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/notebooks/Google%20Cloud%20Natural%20Language%20API.ipynb)
 
 
### Note

Due to upload size constraints, the visual explanations have been scaled down. In case you would like to have access to higher quality visual explanations, please contact the owner of this repository.
