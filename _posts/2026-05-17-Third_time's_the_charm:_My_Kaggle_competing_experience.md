---
layout: post
title: "What I learned from doing kaggle competition the third time"
exerpt: "I realize it's important to have confident in things you are doing."
---

# Third time's the charm: My Kaggle competing experience 

I started my college specialization path in Data Science 2 years ago. In that time, there were 2 times I had to participate in Kaggle competition for courses' project, in which I did not do well, because I didn't have a framework to think about machine learning modeling. 

## What do you do when you don't know what to do?

The framework we learned in class on building Machine Learning model was simple:  

<p align='center'>
(1) Do EDA -> (2) Do modeling.  
</p>

*(though I don't remember if it's officially introduced in a lecture or just from the material.)*

What I do remember is that we were very confused about what to do (because we were new). We have questions that I will write down bellow, but back in those days we didn't have the words to talk about it. 
- What is the goal of doing EDA? (Let's just display basics stats about the data set like length and class distribution and plot it, but, is that it?)
- How to choose features (for feature engineering) really? How do I know if the features I added help?
- What model to chose? (omg so many/so little to choose. Also I don't know how any of these work)
- What's the point of doing any of this if we use deep learning and it trumps all?

I know more now compare to those time ago. I know now we do EDA to **understand** the data and **communicate** and yes - even though deep learning can learn better than most models out there, GPU is expensive and we still need to be able to answer people when they ask: *'What classes are we using for training and why? Why is model so bad at predicting label 5?'* etc.

Coming back to the past, do you wonder what we did facing this problem back then? Simple. We go to the `Code` tab, pick a solution and study it. It's simple, and effective if published competition notebook were good. But it was also messy and confusing.

## Navigation with only what's ahead 

There are 2 type of compeition notebooks: EDA and submission. 
- EDA notebooks are usually full of graphs stats for the dataset - and mostly are bad. When I say 'bad', I don't mean they are of no quality. Most are done very properly and well organized. They are 'bad' in the sense that they don't have a narrative, meaning all that they usually accomplish is visualize data without telling a story. If you are reading this and are new to data science, please check out Kaggle Grandmaster [Chris Deotte](https://www.kaggle.com/cdeotte) and [Jeremy Howard](https://www.kaggle.com/jhoward/code). Their works are exceptional and if you're starting your Kaggle journey I highly recommend reading their work (It'll save a lot of time, trust me.)
- Submission notebooks are solution notebooks that can be submitted straight to the competition. There are many reasons to duplicate and use one. If you are new it's help lower your anxiety level if you don't know pandas/polars/etc operations very well and your notebook version just crashed again or submission raised an error, or when you don't know to start modeling. But there are several problems with this approach (and I only come to aware of these during my third time participating): 
1. They are usually messy: The codes in these notebook are usually not clean, imports got introduced again and again in cells, no comments are narratives to follow. It makes people mistaken that this is the **norm** (unconciously), and subsequencely people overlook notebook organization.
2. They limits your imagination: All of my teams Kaggle submission was based on other notebooks, and what happen is that we only dare to move along the base notebook. Add a feature here, change a model there, but never we got down and say to build our own solution. We didn't build our own baseline so we never had a sense of progression and control in our modeling process.

## What had change this time?

5 months after graduation, I decided to try Kaggle competition again. What had change is now I have more confidence in myself, because (1) I have done more than my younger self and (2) I have seen what great work look like. 

### The competition

[SPR 2026 Mammography Report Classification](https://www.kaggle.com/competitions/spr-2026-mammography-report-classification) is a competition about predicting BI-RADS score (how likely it is that you have breast cancer) from doctor's note in Portugese. 

### My solution 

I start with a simple baseline: TFIDF word embedding + LinearSVC -> LB score of 0.79. 

From there, I build up my solution based on this chain of thoughts: 
1. Is other models better? -> Let's try deep learning and Light GBM and Logistic regression. 
2. I should add engineered features -> I checked the pattern in the samples and do some research in BIRADS. 
3. What are some rules I can set for the edge classes? -> Words that only specific to 1 class! (like carcinoma for class 6 )
4. What is stacking and assembling? Can I use those? -> Stacking: combine predictions from many models -> input for final model. Assembling: get votes from predictions from many models -> final prediction.

And after this, I was stuck. It was fun testing things out but at this point I encounter another problem is that my evaluation score don't help me predict my leaderboard score (I come to understand more about validation score but at this point in the story I didn't), so I spent my time trying to see if I did the validation loop wrong and anything I could improve upon. 

> Nhi from the future here. So I realize I need to add a footnote about the validation here. There are 2 problems I identified for why my local score doesn't represent private leaderboard score. (1) There are too few samples in class 5 (~20) -> when doing kfold the validation varies quite a bit and (2) the data distribution of the validation set and private leaderboard is probably different. In the end, I find I should trusting the kfold validation.


And the competition deadline was drawing close...

**Submission setups**: 
1. Data processing: word TFIDF 
2. Word feature engineering: check if sample has certain word. 
3. Concept negation engineering: check if certain concept is negated. 
4. Training: all data is used to train a LightGBM model. Prediction from LighGBM is then combine back to the dataset and used to train a LinearSVC model. There are certain force rule for samples that has certain word -> certain class.

You can check my submission notebook [here](https://www.kaggle.com/code/phamletunhi/mammography-model-test-submission). Please leave a comment if you find things I can improve upon. Thank you. 

#### The results 

And the results are... suprising. I ranked ~70 in the private leaderboard but dropped to 263th place. There are a lot of shake up in the public leaderboard too with many up/down few 100/200 place. 

It seems that there are some real different between the public and private test set. In any case... I felt quite sad because my solution didn't do well, but also curious of the winners solution. 

### What the winners did

The first to forth solution writeup is open and you can check them in the [competiton leaderboard](https://www.kaggle.com/competitions/spr-2026-mammography-report-classification/leaderboard). The first place is a deep learning approach while the other 3 are not.  

I don't have a lot of things to say about their solutions because I don't think I can judge it very well. Overall, compared to my solution they have a more clearly defined strategy and understanding of what their work was doing.

### Lessons and questions 
For me, the biggest lession for this project is that **it's important to be confident in things you are doing**. I didn't realize till now that ML and kaggle feel a bit like gambling (up to chance) for me, so I can't never could put my finger in and say what I did right or wrong. Though still not perfect, this time was an attempt for me to regain a sense of control in the process, as well as where my knowledge are shaky. 

Specific technical lession: Definition of macro-f1, stacking and emsembling, embedding and finetuning, kfold validation loop.

There are questions I haven't been able to answer as well:
- How do you have a strategy?
- Why my deep learning attempts suck so much? (only 0.1 something macro f1) This has a partial answer as my friend who also compete told me the quality of prediction is different if you are using generic `Trainer` vs write your own training loop.