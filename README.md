<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>


# Audio Analysis

*[Alberto Ranz]*

*[DA FT RT May 2021]*


## Content

- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Organization](#organization)
- [Links](#links)


## Project Description

This project is about a multiclass classification of audio events through machine learning methods. This project is a milestone in the process of learning how to perform data analysis with ML methods.


## Hypotheses / Questions

* Is it possible to classificate different audios based on their acoustic features?
* Which kind of model would work better for this?
* Which kind of audio features are more relevant for the classification?
* Possible applications would be implementation in recording or audio recognition software, .


## Dataset

* The dataset used was extracted from the ESC-50 audio set: https://github.com/karolpiczak/ESC-50 
* This is a collection of 2000 audio events with a 5 second duration, in wav format. The sample rate and bit depth are: 44,1 kHz - 16 bit.
* There is class balance (400 events per class).
* A better accuracy score could be achieved with a bigger amount of audio events.


## Cleaning

The data was extracted from each audio event using the Librosa library for python.
For each audio event, a calculation of the mean, median, standard deviation and sum of the extracted arrays was calculated.
The extracted features are: chroma stft, mfcc, rms, spectral centroid, spectral bandwidth, spectral contrast, spectral flatness, spectral roll off, poly features, tonal centroid features, zero crossing rate and autocorrelation.
https://librosa.org/doc/latest/feature.html


## Analysis

* The classification was tested through several methods including Gradient Boosting, Random Forest Classification, Search Grid and Neural Networks.
* The best performing model was a Random Forest Classification with Search Grid to find the best parameters. 
* The features were selected by observing the correlation matrix. As expected, there was big correlation between mean, median and sum values. Therefore, the median and sum values were dropped.


## Model Training and Evaluation

* The model was trained testing several sets of features, and finally selecting the best ones with Grid Search. The accuracy achieved is 0.68 and the Kappa score is 0.60. 
* The class that was worstly predicted is "human".


## Conclusion

* The results are acceptable, and would be better by either using a high level Neural Network, or by using a broader dataset.
* The classification works fine. There is a low level of error, but considering the resources available, this is completely normal.


## Future Work

Address any questions you were unable to answer, or any next steps or future extensions to your project.


## Organization

A trello board was used to organize the work
The repo has two directories, one for the code and one for the data. The code directory includes two files, one for the feature extraction, and another for the ML models.


## Links

[Dataset](https://github.com/karolpiczak/ESC-50)
[Repository](https://github.com/albertoranz/Final-Project-DA)  
[Slides](https://docs.google.com/presentation/d/1P6HnTDtupBFhwozzsj4MYkXXZscxdlsit7H2P51l1wc)  
[Trello](https://trello.com/b/5HfNwHnB/final-proyect)  
