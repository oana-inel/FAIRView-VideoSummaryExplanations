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

## User Study 2

This online user study, [user study 2](https://github.com/oana-inel/FAIRView-VideoSummaryExplanations/blob/master/user_study2/user_study2_template.md) has been conducted in order to understand how one type of visual explanation is used by participants when asked to compare two summaries of the same video for their representativeness. 

## Files structure

    .
    ├── user_study2                           # Template, data and analysis of user study 2
    │   ├── user_study2_template.html         # User study 2 template (to be run on mTurk)
    │   ├── user_study2_template.md           # Visual interface of user study 2 template
    |   ├── img                               # Folder containing parts of the visual interface of user study 2
    │   ├── input_user_study2.csv             # Input file for user study 2
    │   ├── crowd_results_userstudy2.csv      # Crowdsourcing results of user study 2
    |   └── Analyze ... Study2.ipynb          # Jupyter Notebook used for processing the results of user study 2
    └──.
