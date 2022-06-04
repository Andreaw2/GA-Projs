# Project 3: Capstone: Signature Forgery 
---


## Problem Statement 

### Signature Forgery Detection

Despite widespread digitalisation in with many financial or mortgage transactions being done online, there are still certain transactions that require the use of signatures as a primary way of authenticating a transaction. Signing cheques, authorising documents and contracts, approving purchases are some business activities that usually require signatures. Furthermore, laws in singapore requires some documents to be signed physically. This would include documents that determine how individuals' assets would be divided at death, negotiable instruments, power of attorney and real estate transactions. 


How are we able to navigate the risks involved with signature forgery? Especially if the signatures are use as authentication for these documents of high importance. Manual signature verification methods are also generally dependent on human factors and may be prone to errors including expertise or mood. 


In this capstone, I will be exploring the use of neural networks in classifying whether a signature is genuine or forged. The focus of this project would be on offline handwritten signatures. The goal of the project is to limit both type I and Type II errors. Type I error refer to mistakenly identifying a genuine signature wrongly, leading to a negative impact on customer satisfaction. Type II error refers to wrongly identifying a forged signature, leading to financial loss and a negative impact on reputation as well. 

---

## Approach 

#### 1) Data Gathering 

Kaggle Signature Verification Dataset

Data from dutch users was extracted from ICDAR 2011 Signature Dataset 

https://www.kaggle.com/datasets/robinreni/signature-verification-dataset


#### 2) EDA, Image Preprocessing

#### EDA Findings 
1) There are 1649 images in the 128 subfolders within the train directory

2) There are 500 images in the 42 subfolders within the test directory

The csv files was mapped in a way in which each signature from each individual was match against other signatures from the same individual (genuine + forgery). For example if individual 001 has 10 signatures in the training file, 5 genuine, 5 forgery. each genuine signature will be mapped 9 times with the other 9 signatures.

2) The number of genuine signatures and forgery signatures per individual are not identical in both the train and test directory

3) Both the test and train images are similar as test images are a subset of the train images. 

#### Image Preprocessing 

Here are the following steps taken to pre process the images before feeding it into the model. 

1) Color Space Conversion

2) Resize Image 

3) Normalize pixel values (Scales values of the pixels in 0-1 range instead of 0–255) 

#### 3) Modelling process 

Siamese network can be used to predict the similarity between two image pairs and, more specifically, whether the two input images belong to the same or different classes. Siamese networks use only a few images to get better predictions, which was why I have chosen siamese model.  The ability to learn from very little data has made siamese networks was useful for me to explore. 


Here are the results from the modelling below:


| Model   | Network architecture and parameters                                                                               | Accuracy  |
|---------|-------------------------------------------------------------------------------------------------------------------|-----------|
| Model 1 | 2 convolution layers, Relu activation, Max Cooling layer, categorical crossentropy                                | 0.7262    |
| Model 2 | 2 convolution layers, Relu activation, Max Cooling layer, categorical crossentropy, Batch Normalization, Drop Out | 0.9499    |


 The 2nd model included batch normalization and drop ou which also led to the highest accuracy as compared to the fisrt model at 95%. A common observation over the two models were that the data is overfitting it is an area that require more attention as we are trying to prioritize for accuracy for this project. 
 
 
 Dropout forces a neural network to learn more robust features that are useful in conjunction with many different random subsets of the other neurons. 
Batch normalization is added between the layers of the neural network and it continuously takes the output from the previous layer and normalizes it before sending it to the next layer. This has the effect of stabilizing the neural network. Batch normalization is also used to maintain the distribution of the data.


#### Evaluation 

Overfitting is a huge issue with my model, I have to address this problem. One way in which I can work with this is to develop a GAN Model to generate more data, using generative adversarial networks to study handwritten signature identification.

Alternatively, more time will be required to explore and try out methods in which to address overfitting. E.g. Data Augmentation or GAN to improve my model. Furthermore, I can source out places in which to obtain datasets with more data on signatures.


Use cases for in identifying forged signatures will be very useful in further applications in online signatures as well. How are we able to apply the knowledge from identifying handwritten signatures to online signatures. This would help address the validity of e-signatures, which is one of the considerations of why handwritten signatures are still preferred for transactions of great importance like a will.



#### References 

https://builtin.com/machine-learning/siamese-network
https://pyimagesearch.com/2020/11/30/siamese-networks-with-keras-tensorflow-and-deep-learning/
https://medium.com/@amarbudhiraja/https-medium-com-amarbudhiraja-learning-less-to-learn-better-dropout-in-deep-machine-learning-74334da4bfc5
https://analyticsindiamag.com/hands-on-guide-to-implement-batch-normalization-in-deep-learning-models/
