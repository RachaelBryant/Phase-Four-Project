# Phase-Four-Project

# Classifying Positive and Negative Tweets
<img src="twitter-new-edit-tweet-.jpg" width=400 height=200 />

### Summary of Project:
Classifying tweets as positive or negative according to their context in order to improve Twitter's marketing is the business problem addressed in this project. The data chosen is from CrowdFlower via data.world and contains written tweets, the device to which these tweets were written about, and the emotion attributed to that tweet. There were not enough tweets classified as 'I can't tell' or 'No emotion toward brand or product' so that data was discarded, as well as the information regarding the device the emotion was directed towards. Due to the class imbalance found between the number of positive and negative tweets (84% positive and 16% negative) SMOTE (Synthetic Minority Oversampling Technique) was utilized before modeling the data in order to overcome the problem of overfitting. While exploring the data, it was discovered that word count and review length were about the same for positive and negative tweets. While preparing the data for modeling, NLK (Natural Language Toolkit) was utilized in tokenizing, lemmatization, and navigating stop words in the text. After conducting a train-test split on the data in order to properly validate the models, the data was standardized using StandardScaler and then vectorized using CountVectorizer. FreqDist from the NLK package aided in displaying the most frequent words that appear throughout the tweets (sxsw, mention, ipad, link). Basic Logistic Regression, Support Vector Machines, Stochastic Gradient Descent, Random Forest, Naive Nayes, and K-nearest Neighbors models were tested first. Logistic Regression (.96 Recall), Stochastic Gradient Descent (.96 Recall) and Random Forest (.99 Recall) were chosen for hypertuning. Stochastic Gradient Descent in a GridsearchCV resulted in a best recall score of .97 recall and false negatives occuring at 2.5%. Logistic Regression utilized GridSearchCV of estimators totalling 4800 fits resulting in a nest recall score of .93 and false negatives occuring at 5.6%. The best performing model was the Random Forest model which utilized RandomizedSearchCV totalling in 300 fits resulting in a best recall score of .99 and false negatives occuring .78%.

## Overview
![image](https://user-images.githubusercontent.com/65221687/217709194-b63b9387-ae7a-4844-ac41-b88cb2796475.png)

This project analyses the text of tweets in order to understand whether people tweet more negative or positive information in order to further Twitter's marketing campaign towards the appropriate demographic. This project primarily uses NLTK and base python with models of the data.

## Business Problem
<img src="positiveneutralnegativepic.png" width=500 height=200 />


Twitter is inquiring whether the majority of their tweets are positive or negative and requires a method in which to keep up with the wade and rise of their popularity. With this information they will be able to divert their traffic to different marketing areas to improve their reputation if it's low. We will train the data with labeled positive and negative tweets in order to choose the best model to decipher positive and negative data.



## Data Understanding
The tweet data is from CrowdFlower via data.world and consists of 9,000 documents including columns of emotion expressed in the tweet, the tweet itself and the device that the emotion is directed towards.

The most frequent words across the tweets in general are expressed in the visualization below: 

![image](https://user-images.githubusercontent.com/65221687/217976622-e72599a8-69be-4eb4-8fa3-167f4a4898f9.png)


In exploring the data it was found that 15% of people who expressed a negative emotion and 82% of people who expressed a positive emotion. 

![image](https://user-images.githubusercontent.com/65221687/217976513-108d2963-e758-48b8-8f11-c7b1983971c5.png)


With SMOTE applied to address the imbalance within the data.

![image](https://user-images.githubusercontent.com/65221687/217976482-9eed101d-bc47-4b41-be68-18d5d575d6b9.png)


There are about the same number of words used for negative and positive tweets (N=19, P=18), however the distribution slightly differed.

![image](https://user-images.githubusercontent.com/65221687/217976546-a3074277-17a8-44ff-8708-f7a26b31110d.png)

The distribution of word count for all the tweets was a normal distribution.

![image](https://user-images.githubusercontent.com/65221687/218289601-8817b501-4cff-4e83-8ea1-1032caad24c1.png)


There are about the same number of review length for negative and positive tweets (N= 108, P= 105), distribution is also slightly different. 

![image](https://user-images.githubusercontent.com/65221687/218289577-c667b893-f09d-482e-9d85-8076e3f4adb0.png)



## Modeling
The basic models with their recall scores are: Logistic regression (.96),  Support Vector Machines (.92), Stochastic Gradient Descent (.96), Random Forest (.99), Naive Bayes(.77), K-Nearest Neighbors (92), and the highest recall was recorded with Random Forest (.99). 

![image](https://user-images.githubusercontent.com/65221687/218289691-9ec72aeb-9d4a-4af1-8a80-559bf7aecda2.png)

## Hypertuning

The highest recall scores amongst the basic models were used for hypertuning: Stochastic Gradient Descent, Logistic Regression, and Random Forest. The Random Forest was still the highest model after hypertuning as it was before hypertuning as depicted in the model comparison figure below. 

![image](https://user-images.githubusercontent.com/65221687/218289712-980ad0d9-7206-42da-8326-ffb5b16c55fd.png)

The confusion matrix displays the lowest amount of false positives at .75%

![image](https://user-images.githubusercontent.com/65221687/218289730-8cac2a76-0041-46b8-9583-8573db611970.png)


The Hypertuned Random Forest model also displayed the best ROC curve in comparison to the other models as shown below. 

![image](https://user-images.githubusercontent.com/65221687/218289750-322f4054-90bc-4cb2-a988-4ee0415eb389.png)


## Conclusion
The best model for understanding positive and negative tweets for Twitter is the Random Forest model as it has the highest Recall score, highest scores on both the train and test sets and the least false positives. I would recommend that the company can use this model in sorting through the massive amounts of tweets sent everyday in order to make their workflow easier, the marketing more targeted depending on the times in which they recieve more negative tweets than others, and this will lead to a better understanding of the emotions of people when they are tweeting about different devices and products.

## Next Steps
-Utilizing multi class classification for a ‘neutral’ emotion
-Attempt to code correctly sarcastic or ironic tweets
-Utilizing other vectorizers other than countvectorizer such as tfidfvectorizer.
-Hypertuning other models 


# For More Information
See the full analysis in the [Jupyter Notebook](https://github.com/rabrya0072/Phase-Four-Project/blob/main/Phase%20Four%20Project.ipynb) or [presentation](https://github.com/rabrya0072/Phase-Four-Project/blob/main/Phase%204%20presentation.pdf) in this repository.

For additional info, contact Rachael Bryant at Rachaelbryant94@gmail.com
# Repository Structure
├── data
├── gitignore
├── presentation.pdf
├── Phase_3_project.ipynb
├── README.md
├── ROC.png
├── positiveneutralnegativepic.png
├── twitter-new-edit-tweet-.jpg


