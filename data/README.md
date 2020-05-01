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
    |   |                                       video transcription (see notebook in the notebooks folder)
    |   ├── named_entities_subtitles          # Folder containing all named entities extracted from video subtitles (one file 
    |   |                                       per video); extracted through named entity extraction (see notebook below)
    |   ├── labels_video_frames               # Folder containing all labels extracted from video frames (one file per video); 
    |   |                                       extracted through named entity extraction (see notebook in the notebooks 
    |   |                                       folder)
    |   ├── key_concepts_videos
    |   |   └── video_concepts_overview.csv   # CSV containing the key concepts extracted from videos (see notebook in the 
    |   |                                       notebooks folder); 
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
    └──.

### Note

Due to upload size constraints, the visual explanations have been scaled down. In case you would like to have access to higher quality visual explanations, please contact the owner of this repository.
