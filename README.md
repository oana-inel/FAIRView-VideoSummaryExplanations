# FAIRView Corpus: Visual Explanations for Video Summaries

[![DOI](https://zenodo.org/badge/.svg)](https://zenodo.org/badge/latestdoi/)

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
 - [User Study 1](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study1/user_study1_template.md): identify which type of visual explanation is preffered when assessing the representativeness of video summaries
 - [User Study 2](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study2/user_study2_template.md): understand how one type of visual explanation is used by participants when asked to compare two summaries of the same video for their representativeness 
 
 
## Files structure



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
 
