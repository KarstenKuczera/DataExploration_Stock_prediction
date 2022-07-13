# DataExploration Project

This is a Project for the Data Science Course WWI20DSB at the DHBW Mannheim.
The Projectgroup consists of:

- Oliver Hinkel
- Antonino Piloro
- Karsten Kuczera

The Goal of this Project is to build a ML Model that can predict Stock Prices. However, it is more like a Exploring Project in which we try to learn more about this Topic rather than getting good results.

# Repository Structure

This Repository consists of 5 Folders:

- api_tests
- data
- logs
- model_weights
- pretrained_models

### api_tests

Here you can find two Notebooks that we used to determin the api which we use to get the data.

### data

In this Folder we store the Stock data which we use to train the model. In this state it is not yet scaled and split into train and test data.

### logs

Here we store the log files for a Tensorboard. It is also posible to view the live log data while training the model.
The Log data consists of the loss and the mean-absolute-error per epoche.
To activate the Tensorboard enter the comand below in the console:

```
tensorboard --logdir path/to/file
```

After it is started you can acces it under:

<http://localhost:6006>

### model_weights

We use the Tensorflow chackpoint system while training our model. This means that the model always saves the model weights after it got an improvement determined by the loss function.

### pretrained_models

Since we use a LSTM which takes a lot of calculating power, we noticed that training the models just takes very long. This is why we decided to use Google Collaborate in order to gain acces to the Google cloud GPUs.
We used this to pretrain some models to play around with.
If you want to have a look into it you can acces it via this link:

<https://colab.research.google.com/drive/1N4JKD_XUWReva8zyj69Uuy0RFmNdQbQi?usp=sharing>

Since this is a public repository, I disabled the ability to change stuff in the collab.

Inside this Folder you can find two folders named after their Stock.
For each Stock we have prepared 6 Models.
3 for predicting 1 Day ahead and 3 for predicting 15 days ahead and for both we have 50, 500, 1000 Epochs.
LS = Lookup_Step = How many days in the future we want to predict
E = Epochs = How often do we train our Model

# How to use the Code

### Training a new model

If you want to train a new model, you have to open up the File: **Stock_prediction.ipynb**
Now if you scroll down to the first cell after the Function definitions, you can see all the Parameters that you can change.
After you´ve changed the params to your liking, you can just hit "run all".
At the bottom of the notebook you can find the results and a plot.
In the "logs" Folder you can find the logs of your training.
And in the "model_weights" Folder you can find the model weights of your trained model.

### Getting results from a pretrained Model

If you want to test model, you have to open up the File: **Model_tester.ipynb**
In the cell after the imports you can see the Parameters.
In order to test a Model the parameters have to be same like in the model.
You can see the Parameters in the Name of the Model File.
For the Models in the "pretrained_models" Folder you only need to change the "ticker" and the "Lookup_step".
After these changes were made, you can press "run all".
