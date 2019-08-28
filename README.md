# Tweet Analysis

### Problem Statement:
We have dataset consists of large no. of tweets(text) along with sentiments(0=negative, 2=neutral, 4=positive).
### Solution:
We need a Classifier that can predict sentiments using data in training set.
### Column names:
1. polarity (sentiments) </br>
2. tweet id </br>
3. tweet date </br>
4. query </br>
5. user </br>
6. tweet (text) </br>

### Dataset dimension:
train_df.shape = (1600000, 6) </br>
test_df.shape = (498, 6)

***we have only two classes present in our output that is 0 --> negative & 4 --> positive. </br>
So, predicting 2 --> neutral sentiment in test data is not possible***

![center](./images/shape.png)

### Data Preprocessing:
Data Preprocessing steps are as follows :-
1. Removing html tags and other links available in tweets </br>
2. Removing numbers. </br>
3. changing letters from capitals to lowers </br>
4. Removing of Stopwords </br>
5. Making every tweet in to a meaningful tweet which computer can understand well (by tokenizing each word </br>

![center](./images/libs.png)

***Due to large training dataset Data Preprocessing is very time consumption as well as memory constraint for my Machine. This seems to be very challenging part for me. Well i decided to not for go data preprocessing, instead i will use one of the pretraining word embedding file called Glove. In this file each word is pretrained and has its coefficients. But, Glove don't have embedding matrix. So i will create it manually.***

![center](./images/embed_matrix.png)

### Model:
In this project i'm using Bi-directional LSTM model to get best prediction with out any data cleaning.
![center](./images/model.png)

### Model Summary:
Choosed batch_size 5000 in oder to make by fitting process faster. considered only 2 ephocs bcoz from 3rd ephoc model is overfitting.
![center](./images/model_run.png)

### Accuracy:
Model with bit tuning can manage to hit an accuracy of 60 % without any data cleaning.
***Performing all Data Preprocessing steps can definitely give best results***
![center](./images/accuracy.png)
