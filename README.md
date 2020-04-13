# FAIRView Corpus: Visual Explanations for Video Summaries

[![DOI](https://zenodo.org/badge/.svg)](https://zenodo.org/badge/latestdoi/)

This repository contains:
 * an annotated corpus of 200 videos with key concepts extracted from video subtitles and video frames;
 * an annotated corpus of 800 video summaries (four summaries per video) with concepts extracted from video subtitles and frames;
 * a corpus of 3200 visual explanations (four explanations per video summary, with different levels of *transparency*);
 * results from *two user studies* evaluating the utility of four types of visual explanations which are modeled based on *user preferences* and along *four dimensions of transparency* (*i.e.*, *semantic coverage*, *semantic prominence*, *quantity coverage* and *distance*) to understand the representativeness of video summaries;

referenced in the following paper:

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
 - [User Study 1](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/user_study1/user_study1_template.md): identify which type of visual explanation is preffered when assessing the representativeness of video summaries
 - [User Study 2](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/user_study2/user_study2_template.md): understand how one type of visual explanation is used by participants when asked to compare two summaries of the same video for their representativeness 
 
 
## Files structure



## Video Machine Enrichment

To regenerate the results of the machine enrichment tools, namely the video transcription, named entity extraction and video labeling, you need to register for the following Google Cloud APIs and follow their instructions. A schelethon notebook for running each of the APIs below is provided in the notebooks/machine_processing folder.
 * [Cloud Storage](https://cloud.google.com/storage) - Google Cloud Storage
 * [Speech-to-Text](https://cloud.google.com/video-intelligence/docs/transcription) - part of Google Cloud Video Intelligence API to transcribe the videos (extraction captions or subtitles)
 * [Label Detection](https://cloud.google.com/video-intelligence/docs/analyze-labels) - part of Google Cloud Video Intelligence API to detect and extract information about entities shown in video and video summaries
 * [Entity Extraction](https://cloud.google.com/natural-language/docs/analyzing-entities) - part of Google Cloud Natural Language to extract entities from the video subtitles
 
