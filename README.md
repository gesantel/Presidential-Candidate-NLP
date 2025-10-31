# Presidential-Candidate-NLP
Find the substack article here. 

I wanted to know if there was meaningful inisght to be gleaned from transcripts of party nominee and presidential nominee debates. To do so, I did feature analysis of the linguistics of the text. I also did a sentiment analysis of the text using the distilroberta-base-sst2-distilled classifier. Lastly, I used the distilroberta-base NLP classifier to predict the author of each input. Input was 

Tools used: BeuatifulSoup, Huggingface Transformers, matplotlib, sklearn (scikit-learn), pandas, numpy, PyTorch. 

# [Data Collection](https://github.com/gesantel/Presidential-Candidate-NLP/blob/main/TILIS_dataload.ipynb)
I used BeautfiulSoup to scrape www.presidency.ucsb.edu for presidential, vice presidential, and candidate debates from 2015-2024. I created a dataframe with debate title, debate date, speaker, and text. 

# [Feature Analysis](https://github.com/gesantel/Presidential-Candidate-NLP/blob/main/FeatureAnalysis.ipynb)
I used a small roberta base model to classify the sentiment of each row of text. I created histograms of negative/positive classified text per speaker. I normalized (per/1k words) and compared the ratios of positively versus negatively classified text by candidates/speakers. I also looked at most common words by speaker and counted use of pronouns "we," "i," and "he"to see if there were patterns there that could have deeper meaning.  

# [Data Preprocessing](https://github.com/gesantel/Presidential-Candidate-NLP/blob/main/NLPClassModel.ipynb)
I used sklearn Train_Test_Split to split one Presidential debate into a test and train set. I used a second Presidential debate as the evaluation set. 

# [Model and Fitting](https://github.com/gesantel/Presidential-Candidate-NLP/blob/main/NLPClassModel.ipynb)
For the speaker/candidate classification I applied weights that were neccessary for an imbalanced debate where one candidate spoke a lot more. 

#Conclusions
The speaker/candidate classification model confusion matrix and fine tuning -which included trying oversampling vs adding weights, and paramter tuning- process indicate our dataset did not capture enough linguistic difference for our classifier to perform well. Future direction could include diversifying the data set with possible reaction data from twitter.    
