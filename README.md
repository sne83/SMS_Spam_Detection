**Steps performed:**

**1.Data Cleaning** = 
* Droped last 3 unknown columns 
* renaming columns (v1=Target, v2=Text)
* used labelencoder on Target column (ham = 0, spam = 1)
* check missing values
* check for duplicated values
* then removed duplicates.
  
**2.EDA** =  
* Check value_counts of target column and visualize that using pie chart.
* Data is imbalanced, consist 12% data is spam & 87% is ham.
* Calculated number of characters & number of words in each sentences. Checked Description of data.
* Plot histogram for both categories. Used pair plot to check relation between columns, Using Correlation matrix we got correlation between columns. We considered num_character column for analysis because it has more relation with target column than others.

**3.Data Preprocessing:**
* Formed one function which performed all the following preprocessing : Lowercasing, Tokenization, Removing special characters, Removing stop words and punctuation, Stemming
* Then formed Wordcloud to see most frequent ham & spam words. Then calculated total number of words in spam & ham messages and found most frequent top 30 words.

**4.Model Building** = 
* There is saying, naive bayes works best on textual data so first performed Naive Bayes model and then used other different models on data. First converted textual data into vectors as ML models only work on numerical data. For that I performed feature extraction using Bag-of-words(CountVectorizer) and TFIDF vectorizer. As I did not know which naive bayes among three will work better so I imported all three of them which were GaussianNB, MultinomialNB and BernoulliNB, then fit all three models, predict the X_test and found accuracy, confusion matrix and precision score for all three Naive bayes. I got good precision score (precision_score = 1) for MultinomialNB using TFIDF vectorizer, here FP = 0 perfect classification. Here data is imbalanced so precision score matters more than perfect accuracy score. So I kept MNB with TFIDF.
* Next considered some more ML models like SVC, KNC, DecisionTreeClassifier, LogisticRegression, RandomForestClassifier, AdaBoostClassifier, BaggingClassifier, ExtraTreesClassifier, GradientBoosting, XGB. Through one function I fit the models, calculated prediction, accuracy score, precision score. Stored all the records in a dataframe by sorting on the basis of precision score.
