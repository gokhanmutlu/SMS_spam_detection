# SMS Spam Detection | Preprocessing & Five Classifier Model

<img src="https://github.com/user-attachments/assets/49fbe5e5-afc8-4123-9f82-75471486a706" width="40%">


## Description

Dataset: [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)

The SMS Spam Collection is a set of SMS tagged messages that have been 
collected for SMS Spam research. It contains one set of SMS 
messages in English of 5,574 messages, tagged acording being ham (legitimate) or spam.

### Data Understanding

| Column Name                  | Description                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| **v1**                  | Spam or ham, label-target. |
| **v2**                  | Text of SMS. |

<br/>

## Analyze (EDA)

<img src="https://github.com/user-attachments/assets/9e84deb4-307a-4e16-812a-84e472294d79" width="60%">

- Contains imbalanced data.

### Text Adjustment Techniques

- **WordNetLemmatizer:** Reduces words to their base or dictionary form (lemma), preserving meaning (e.g., "running" → "run").

- **PorterStemmer**: Stems words by removing suffixes, often resulting in non-dictionary forms (e.g., "running" → "run").

- **CountVectorizer:** Converts text into a matrix of word counts, representing text as numerical data.

- **TfidfVectorizer:** Converts text into a matrix of TF-IDF scores, emphasizing important words while downweighting common ones.

### Example of What We Succeed

```
Sample of column text:
I want to show you the world, princess :) how about europe?

Sample of column clean_text: 
i want to show you the world princess how about europe

Sample of column without_stopwords: 
want show world princess europe

Sample of column lemmatization: 
want show world princess europe

Sample of column stemming_lemmatization: 
want show world princess europ
```

<br/>

## Construct

### Builded Models

1. LogisticRegression
2. SVC
3. MultinomialNB
4. BernoulliNB
6. XGBClassifier

### Result of Models

#### GridSearchCV Results

<img src="https://github.com/user-attachments/assets/35530a59-7a4b-4932-9af2-410ba16850ae" width="60%">

<br/>



#### Classification Results
<img src="https://github.com/user-attachments/assets/e3c6aa3e-4493-4765-b04f-ffd549b16d83" width="60%">

#### Confussion Matrixes
<p float="left">
    <img src="https://github.com/gokhanmutlu/SMS_spam_detection/blob/main/images/cm1.png" width="33%">
    <img src="https://github.com/gokhanmutlu/SMS_spam_detection/blob/main/images/cm2.png" width="33%">
    <img src="https://github.com/gokhanmutlu/SMS_spam_detection/blob/main/images/cm3.png" width="33%">
    
</p>

<br/>

<p float="left">
    <img src="https://github.com/gokhanmutlu/SMS_spam_detection/blob/main/images/cm4.png" width="33%">
    <img src="https://github.com/gokhanmutlu/SMS_spam_detection/blob/main/images/cm5.png" width="33%">
    
</p>

<br/>

## Summary

#### **Why Choose BernoulliNB?**

*Highest Recall (0.935):* Best at minimizing false negatives, making it ideal when missing positive cases is costly.

*Highest AUC (0.990):* Excellent at distinguishing between classes, especially useful for imbalanced datasets.

*Good F1-Score (0.913):* Balances precision and recall effectively.

*Lightweight and Fast:* Efficient for large datasets due to its simplicity.

#### **Why Choose SVC?**

*Highest Precision (0.989):* Best at minimizing false positives, ideal when false alarms are critical.

*Highest Accuracy (0.980):* Overall, it makes the most correct predictions.

*Strong F1-Score (0.913):* Balances precision and recall well.

*Robust Performance:* Handles complex decision boundaries effectively.

### **Summary:**

Choose BernoulliNB if recall and AUC are priorities (e.g., medical diagnosis, fraud detection).

Choose SVC if precision and accuracy are critical (e.g., spam detection, quality control).
