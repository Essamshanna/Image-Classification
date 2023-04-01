# Image-Classification
Image Classification in 10 Minutes with MNIST Dataset


Neural networks
Although neural networks have gained enormous popularity over the last few years, for many data scientists and statisticians the whole family of models has (at least) one major flaw: the results are hard to interpret. One of the reasons that people treat neural networks as a black box is that the structure of any given neural network is hard to think about.

Neural networks frequently have anywhere from hundreds of thousands to millions of weights that are individually tuned during training to minimize error. With so many variables interacting in complex ways, it is difficult to describe exactly why one particular neural network outperforms some other neural network. This complexity also makes it hard to design top-tier neural network architectures.

Some machine learning terminology appears here, in case you haven’t seen it before:

The name x refers to input data, while the name y refers to the labels. ŷ (pronounced y-hat) refers to the predictions made by a model.
Training data is the data our model learns from.
Test data is kept secret from the model until after it has been trained. Test data is used to evaluate our model.
A loss function is a function to quantify how accurate a model’s predictions were.
An optimization algorithm controls exactly how the weights of the computational graph are adjusted during training
For a refresher about splitting up test and training data, or if this is new information, consider reading this article.

MNIST handwritten digits dataset
In this article, we’re going to work through a series of simple neural network architectures and compare their performance on the MNIST handwritten digits dataset. The goal for all the networks we examine is the same: take an input image (28x28 pixels) of a handwritten single digit (0–9) and classify the image as the appropriate digit.

State of the art neural network approaches have achieved near-perfect performance, classifying 99.8% of digits correctly from a left-out test set of digits. This impressive performance has real world benefits as well. The US Postal Service processes 493.4 million pieces of mail per day, and 1% of that workload is 4.9 million pieces of mail. Accurate automation can prevent postal workers from individually handling and examining millions of parcels each day. Of course, automatically reading complete addresses isn’t as simple as processing individual digits, but let’s learn to crawl before we try to jog.

It’s always a good idea to familiarize yourself with a dataset before diving into any machine learning task. Here are some examples of the images in the dataset:


A random selection of MNIST digits. In the Jupyter Notebook you can view more random selections from the dataset.
The MNIST dataset is a classic problem for getting started with neural networks. I’ve heard a few people joke that it’s the deep learning version of “hello world”— a lot of simple networks do a surprisingly good job with the dataset, even though some of the digits are pretty tricky:


This image is from the wonderful book Neural Networks and Deep Learning, available online for free.
Preparing the data
The first and most important step in any machine learning task is to prepare the data. For many scientists and industry practitioners, the process of gathering, cleaning, labeling, and storing the data into a usable digital format represents the lion’s share of the work. Additionally, any errors introduced during this step will cause the learning algorithm to learn incorrect patterns. As they say: garbage in, garbage out.

Thanks to the Keras library and the hard work of the National Institute of Standards and Technology (the NIST of MNIST) the hardest parts have been done for us. The data’s been collected and is already well-formatted for processing. Therefore, it is with deep gratitude for NIST and the Keras maintainers that our Python code for getting the data is simple:

