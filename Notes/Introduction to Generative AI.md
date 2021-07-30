# Introduction to Generative AI

Generative AI and Its Applications
Generative AI is one of the biggest recent advancements in artificial intelligence because of its ability to create new things.

Until recently, the majority of machine learning applications were powered by discriminative models. A discriminative model aims to answer the question, "If I'm looking at some data, how can I best classify this data or predict a value?" For example, we could use discriminative models to detect if a camera was pointed at a cat.

As we train this model over a collection of images (some of which contain cats and others which do not), we expect the model to find patterns in images which help make this prediction.

A generative model aims to answer the question,"Have I seen data like this before?" In our image classification example, we might still use a generative model by framing the problem in terms of whether an image with the label "cat" is more similar to data you’ve seen before than an image with the label "no cat."

However, generative models can be used to support a second use case. The patterns learned in generative models can be used to create brand new examples of data which look similar to the data it seen before.

![image](https://user-images.githubusercontent.com/70132200/127690532-85740c82-15b1-4f8e-958c-4c6a9c37ac4e.png)
Discriminative versus Generative algorithms


# Generative AI Models

In this lesson, you will learn how to create three popular types of generative models: generative adversarial networks (GANs), general autoregressive models, and transformer-based models. Each of these is accessible through AWS DeepComposer to give you hands-on experience with using these techniques to generate new examples of music

# Autoregressive models

Autoregressive convolutional neural networks (AR-CNNs) are used to study systems that evolve over time and assume that the likelihood of some data depends only on what has happened in the past. It’s a useful way of looking at many systems, from weather prediction to stock prediction.

# Generative adversarial networks (GANs)

Generative adversarial networks (GANs), are a machine learning model format that involves pitting two networks against each other to generate new content. The training algorithm swaps back and forth between training a generator network (responsible for producing new data) and a discriminator network (responsible for measuring how closely the generator network’s data represents the training dataset).

# Transformer-based models

Transformer-based models are most often used to study data with some sequential structure (such as the sequence of words in a sentence). Transformer-based methods are now a common modern tool for modeling natural language.

# Generative AI with AWS DeepComposer

What is AWS DeepComposer?

AWS DeepComposer gives you a creative and easy way to get started with machine learning (ML), specifically generative AI. It consists of a USB keyboard that connects to your computer to input melody and the AWS DeepComposer console, which includes AWS DeepComposer Music studio to generate music, learning capsules to dive deep into generative AI models, and AWS DeepComposer Chartbusters challenges to showcase your ML skills

Summary
-------


# AWS DeepComposer keyboard
You don't need an AWS DeepComposer keyboard to finish this course. You can import your own MIDI file, use one of the provided sample melodies, or use the virtual keyboard in the AWS DeepComposer Music studio.

# AWS DeepComposer music studio
To generate, create, and edit compositions with AWS DeepComposer, you use the AWS DeepComposer Music studio. To get started, you need an input track and a trained model.

For the input track, you can use a sample track, record a custom track, or import a track.
![image](https://user-images.githubusercontent.com/70132200/127690993-1963f404-bed8-4df4-8cd7-a7064faf00ce.png)


For the ML technique, you can use either a sample model or a custom model.

Each AWS DeepComposer Music studio experience supports three different generative AI techniques: generative adversarial networks (GANs), autoregressive convolutional neural network (AR-CNNs), and transformers.

>   Use the GAN technique to create accompaniment tracks.
>   Use the AR-CNN technique to modify notes in your input track.
>   Use the transformers technique to extend your input track by up to 30 seconds.

# GANs with AWS DeepCompose

We’ll begin our journey of popular generative models in AWS DeepComposer with generative adversarial networks or GANs. Within an AWS DeepComposer GAN, models are used to solve a creative task: adding accompaniments that match the style of an input track you provide. Listen to the input melody and the output composition created by the AWS DeepComposer GAN model:

Input melody
Output melody

# Q) What are GANs?

A GAN is a type of generative machine learning model which pits two neural networks against each other to generate new content: a generator and a discriminator.

A generator is a neural network that learns to create new data resembling the source data on which it was trained.
A discriminator is another neural network trained to differentiate between real and synthetic data.
The generator and the discriminator are trained in alternating cycles. The generator learns to produce more and more realistic data while the discriminator iteratively gets better at learning to differentiate real data from the newly created data.

Collaboration between an orchestra and its conductor
A simple metaphor of an orchestra and its conductor can be used to understand a GAN. The orchestra trains, practices, and tries to generate polished music, and then the conductor works with them, as both judge and coach. The conductor judges the quality of the output and at the same time provides feedback to achieve a specific style. The more they work together, the better the orchestra can perform.

The GAN models that AWS DeepComposer uses work in a similar fashion. There are two competing networks working together to learn how to generate musical compositions in distinctive styles.


## Training Methodology
Let’s dig one level deeper by looking at how GANs are trained and used within AWS DeepComposer. During training, the generator and discriminator work in a tight loop as depicted in the following image.

![image](https://user-images.githubusercontent.com/70132200/127691529-0463869c-909d-4b19-8487-ae07bb34a281.png)
Note: While this figure shows the generator taking input on the left, GANs in general can also generate new data without any input.

# Generator

The generator takes in a batch of single-track piano rolls (melody) as the input and generates a batch of multi-track piano rolls as the output by adding accompaniments to each of the input music tracks.
The discriminator then takes these generated music tracks and predicts how far they deviate from the real data present in the training dataset. This deviation is called the generator loss. This feedback from the discriminator is used by the generator to incrementally get better at creating realistic output.

# Discriminator

As the generator gets better at creating music accompaniments, it begins fooling the discriminator. So, the discriminator needs to be retrained as well. The discriminator measures the discriminator loss to evaluate how well it is differentiating between real and fake data.

Beginning with the discriminator on the first iteration, we alternate training these two networks until we reach some stop condition; for example, the algorithm has seen the entire dataset a certain number of times or the generator and discriminator loss reach some plateau (as shown in the following image).

![image](https://user-images.githubusercontent.com/70132200/127691625-83b5b506-cff0-4a5a-a936-f963f8580f91.png)


# New Terms

Generator: A neural network that learns to create new data resembling the source data on which it was trained.

Discriminator: A neural network trained to differentiate between real and synthetic data.

Generator loss: Measures how far the output data deviates from the real data present in the training dataset.

Discriminator loss: Evaluates how well the discriminator differentiates between real and fake data.

# AR-CNN with AWS DeepComposer

Summary
-------

Our next popular generative model is the autoregressive convolutional neural network (AR-CNN). Autoregressive convolutional neural networks make iterative changes over time to create new data.

To better understand how the AR-CNN model works, let’s first discuss how music is represented so it is machine-readabl

# Image-based representation


Nearly all machine learning algorithms operate on data as numbers or sequences of numbers. In AWS DeepComposer, the input tracks are represented as a piano roll**. *In each two-dimensional piano roll, time is on the horizontal axis and pitch* is on the vertical axis. You might notice this representation looks similar to an image.

The AR-CNN model uses a piano roll image to represent the audio files from the dataset. You can see an example in the following image where on top is a musical score and below is a piano roll image of that same score.

How the AR-CNN Model Works
--------------------------
When a note is either added or removed from your input track during inference, we call it an edit event. To train the AR-CNN model to predict when notes need to be added or removed from your input track (edit event), the model iteratively updates the input track to sounds more like the training dataset. During training, the model is also challenged to detect differences between an original piano roll and a newly modified piano roll.



In this lesson, we learned many advanced machine learning techniques. Specifically, we learned:
-----------------------------------------------------------------------------------------------

Computer vision and its application
How to train a computer vision project with AWS DeepLens
Reinforcement learning and its application
How to train a reinforcement learning model with AWS DeepRacer
Generative AI
How to train a GAN and AR-CNN model with AWS DeepComposer
Now, you should be able to:

Identify AWS machine learning offerings and how different services are used for different applications
Explain the fundamentals of computer vision and a couple of popular tasks
Describe how reinforcement learning works in the context of AWS DeepRacer
Explain the fundamentals of Generative AI, its applications, and three famous generative AI model in the context of music and AWS DeepComposer
