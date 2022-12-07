## *Solution to exercises and problems:*<br /> **Hands-on Machine Learning ith Scikit-Learn, Keras and Tensorflow**
### by Aurélien Géron, 3rd Edition (2023)
<br />

# Chapter 1
## 1. How would you define machine learning?
Giving the machines the ability to learn without explicitly being programmed.

## 2. Can you name four types of applications where it shines?
Image processing, NLP, OCR, spam detection,autonomous cars,...

## 3. What is a labeled training set?
In this type of learning, types and classifications are being applied to the instances. These annotated sets are called labeled training sets.

## 4. What are the two most common supervised tasks?
1. classification (e.g. spam filters)
2. regression (e.g. predicting a value based on features, like )

## 5. Can you name four common unsupervised tasks?
1. clustering
2. dimensionality reduction
3. anomaly detection
4. association role learning

## 6. What type of algorithm would you use to allow a robot to walk in various unknown terrains?
Reinforcement learning

## 7. What type of algorithm would you use to segment your customers into multiple groups?
Clustering

## 8. Would you frame the problem of spam detection as a supervised learning problem or an unsupervised learning problem?
Supervised learning

## 9. What is an online learning system?
You train the system incrementally by feeding it data instances sequentially.

## 10. What is out-of-core learning?
When the problem is too bing to be solved using the available memory space and therefore need to be broken down before being solved.

## 11. What type of algorithm relies on a similarity measure to make predictions?
instance-based learning

## 12. What is the difference between a model parameter and a model hyperparameter?
**Model parameters** are estimated from data automatically and **model hyper-parameters** are set manually and are used in process to help estimate model parameters.

## 13. What do model-based algorithms search for? What is the most common strategy they use to succeed? How do they make predictions?
The best results for the new instances are sought after by model-based learning algorithms, which look for the model's optimal parameter values. To establish what the parameter value must be in order to minimize the function, we frequently utilize a cost function or something similar. The new instance's value and the function's arguments are used by the model to make predictions.

## 14. Can you name four of the main challenges in machine learning?
1. insufficient quantity of training data
2. non-representative training data
3. poor quality of the data
4. irrelevant features
5. overfitting the training data

## 15. If your model performs great on the training data but generalizes poorly to new instances, what is happening? Can you name three possible solutions?
In this situation overfitting takes place. solutions:
1. simplify the model by selecting one with fewer parameters.
2. Gather more training data
3. Reduce the noise in the training data

## 16. What is a test set, and why would you want to use it?
You split you data to training and test sets. The error rate on the test set is called generalization error and is being used for model optimization.

## 17. What is the purpose of a validation set?
you simply hold out part of the training set to evaluate several candidate
models and select the best one. The new held-out set is called the validation set
(or the development set, or dev set). More specifically, you train multiple models
with various hyper-parameters on the reduced training set (i.e., the full training
set minus the validation set), and you select the model that performs best on
the validation set. After this holdout validation process, you train the best
model on the full training set (including the validation set), and this gives you
the final model. Lastly, you evaluate this final model on the test set to get an
estimate of the generalization error.

## 18. What is the train-dev set, when do you need it, and how do you use it?
In some cases, it’s easy to get a large amount of data for training, but this data
probably won’t be perfectly representative of the data that will be used in
production.
In this case, the most important rule to remember is that both the validation
set and the test set must be as representative as possible of the data you expect
to use in production, so they should be composed exclusively of representative
pictures: you can shuffle them and put half in the validation set and half in the
test set (making sure that no duplicates or near-duplicates end up in both sets).
After training your model on the web pictures, if you observe that the
performance of the model on the validation set is disappointing, you will not
know whether this is because your model has overfit the training set, or
whether this is just due to the mismatch between the web pictures and the
mobile app pictures.
One solution is to hold out some of the training pictures (from the web) in yet
another set that Andrew Ng dubbed the train-dev set. After the
model is trained (on the training set, not on the train-dev set), you can
evaluate it on the train-dev set. If the model performs poorly, then it must
have overfit the training set, so you should try to simplify or regularize the
model, get more training data, and clean up the training data. But if it
performs well on the train-dev set, then you can evaluate the model on the dev
set. If it performs poorly, then the problem must be coming from the data
mismatch. You can try to tackle this problem by preprocessing the web images
to make them look more like the pictures that will be taken by the mobile app,
and then retraining the model. Once you have a model that performs well on
both the train-dev set and the dev set, you can evaluate it one last time on the
test set to know how well it is likely to perform in production.


## 19. What can go wrong if you tune hyper-parameters using the test set?
In this case you are measuring generalization error multiple times on this set and you are adapting the model and hyper-parameters to produce the best models for that set. This means the model is unlikely to perform as well on new data.