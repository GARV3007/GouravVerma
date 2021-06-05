---
title: "Speech Emotion Recognition"
header:
  teaser: "assets/images/SER.png"
categories:
  - Machine Learning
  - Classification
tags:
  - Speech Analysis
  - CNN
  - Librosa
  - MFCC

author_profile: true
---

{% capture fig_img %}
![Foo]({{ '/assets/images/SER.png' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }}

### Abstract
  In this project, Speech Emotion Recognition (SER) is performed. To achieve this Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS) data from ZENODO was used. Directly or indirectly, people show their feelings through their speech, facial expressions, gestures, or writings. Many different sources of information, such as speech, text, and visuals can be used to analyze emotions. The RAVDESS database contains 24 professional actors (12 female, 12 male), vocalizing two lexically matched statements in a neutral North American accent. Speeches include neutral, calm, happy, sad, angry, fearful, surprise, and disgusted expressions. My focus for the research is only on acoustic expressions with the assumption that audio speech signal contains sufficient human emotion information to extract and identify. Several two-dimensional features such as Mel-frequency cepstral coefficients (MFCC), Short-Time Fourier Transform (STFT), Zero-Crossing Rate, Log-Mel Spectrogram, and Spectral Centroid are used to represent features of speech emotions. A 1D-Convolutional Neural network (CNN) was used to classify human emotions from audio recordings. I achieve a recognition rate of approximately 60% when testing eight emotions for both males and females.
 <br />

### Problem Statement
  As emotions are subjective, emotion recognition is easy for humans but very difficult for machines. Due to the increase, in the interaction with voice assistants such as Alexa, Siri, and Google Assistant, challenges have been created to correctly understand human instructions in different tones and emotions. Hence, continuous development is ongoing to create a more efficient human emotion recognition system that will be able to enhance the performance of these voice assistants. Once we started the communication via text messages and emails, we started feeling the importance of emotion recognition.
  The call center uses SER (Speech Emotion Recognition) to classify the calls according to emotions, and it can be used as a performance parameter for customer segmentation, thus identifying the customers by their emotional responses. It will help companies improving their services. SER system is also used in the Cars to provide information about the mental state of the driver. Accidents can be prevented, by providing an SER outcome to the car system to initiate driver’s safety prevention. With the help of SER, better decisions can be made by computers to help users. Emotion recognition will help boost the popularity of robotic research, by making human–robot interaction more natural.
 <br />

### Data
  For this project, I will be using a portion of data available from ZENODO. The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS) contains 7356 files (total size: 24.8 GB). The database contains 24 professional actors (12 female, 12 male), vocalizing two lexically matched statements in a neutral North American accent. Speech includes calm, happy, sad, angry, fearful, surprise, and disgust expressions, and the song contains calm, happy, sad, angry, and fearful emotions. Each expression is produced at two levels of emotional intensity (normal, strong), with an additional neutral expression. All conditions are available in three modality formats: Audio-only (16bit, 48kHz .wav), Audio-Video (720p H.264, AAC 48kHz, .mp4), and Video-only (no sound). A portion of the RAVDESS from Kaggle which contains 1440 files: 60 trials per actor x 24 actors = 1440, was used for this research.

  Each of the 1440 audio files has a unique filename. The filename consists of a 7-part numerical identifier (e.g., 03-01-06-01-02-01-12.wav). These identifiers define the stimulus characteristics:
*Filename identifiers*
•	Modality (01 = full-AV, 02 = video-only, 03 = audio-only).
•	Vocal channel (01 = speech, 02 = song).
•	Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).
•	Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the 'neutral' emotion.
•	Statement (01 = "Kids are talking by the door", 02 = "Dogs are sitting by the door").
•	Repetition (01 = 1st repetition, 02 = 2nd repetition).
•	Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).

  *Filename example: 03-01-06-01-02-01-12.wav*
1.	Audio-only (03)
2.	Speech (01)
3.	Fearful (06)
4.	Normal intensity (01)
5.	Statement "dogs" (02)
6.	1st Repetition (01)
7.	12th Actor (12)
  Female, as the actor ID number is even. 
 <br />

### Feature Selection
  Audio features are broadly classified into two domains: Time-domain and frequency domain . Time-domain features are Amplitude envelope, Root-mean-square energy, and Zero crossing rate. These are very easy to extract and provide an easier way to analyze audio signals. The frequency-domain features are Band energy ratio, spectral centroid, and spectral flux. Mostly sound is defined for its frequency. In time-based features, we will not have any frequency information. Similarly, with the frequency-domain representation, we will not be able to see changes in sound for the time. To overcome this issue, we have time-frequency features such as spectrogram, Mel-spectrogram, MFCC, and Constant-Q transform. During EDA and extensive analysis, each feature was analyzed. However, for the model creation, MFCC was used.
 <br />
 
### Methodology
  Emotion recognition is a division of speech recognition, and it is gaining enormous popularity these days. Although there are methods to recognize emotion using machine learning techniques, this project attempts to use deep learning to recognize the emotions from data. There are several algorithms and methods used for SER in prior research. Each of these models is focused on specific audio features that had their benefits and limitations. The most effective method is to use neural networks which seem to provide higher accuracy than others. As I mentioned earlier in this paper, the audio signal can have many defining features and among those MFCC is highly capable of representing an audio signal completely. In this paper, I have created 1D CNN model with multiple layers using the MFCC feature. 
   Librosa is a Python library for analyzing audio and music. It has a flatter package layout, standardizes interfaces and names, backwards compatibility, modular functions, and readable code.
<br />

### Results
  I conducted a feature-focused analysis with only MFCC and 1D CNN. Achieved good results with widely used engineered feature MFCC for speech emotion recognition. High performance was seen with gender-specific emotion classification. This is due to the difference in the pitch and energy in the average male and average female voice. This was seen in different plots. I tested the model on RAVDESS audio dataset and achieved 60% accuracy. Future studies can explore other audio features such as Log-Mel spectrogram. Also, other neural networks like 2D CNN, 3D CNN, and HMM could be used to test-train and choose between best-performing models. 
  <br />

### [Github Repository](https://github.com/GARV3007/Speech-Emotion-Recognition){: .btn .btn--primary .btn--small}
