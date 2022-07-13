# DataExploration Project

This is a project for the data science course WWI20DSB at the DHBW Mannheim.
The project group consists of:

- Oliver Hinkel
- Antonino Piloro
- Karsten Kuczera

The goal of this project is to build a ML model that can predict stock prices. However, it is more like an exploration project in which we try to learn more about the ML topic rather than getting reliable results in the market predictions.

# Repository structure

This repository consists of 5 folders:

- api_tests
- data
- logs
- model_weights
- pretrained_models

### api_tests

Here you can find two notebooks that we use to determine the api which we use to get the data.

### data

In this folder we store the stock data which we use to train the model. In this state it is not yet scaled and split into train and test data.

### logs

Here we store the log files for a TensorBoard. It is also possible to view the live log data while training the model.
The log data consists of the loss and the mean-absolute-error per epoch.
To activate the TensorBoard enter the command below in the console:

```
tensorboard --logdir path/to/file
```

After it started you can access it under:

<http://localhost:6006>

### model_weights

We use the TensorFlow checkpoint system while training our model. This means that the model always saves the model's weights after it got an improvement that is determined by the loss function.

### pretrained_models

Since we use an LSTM which takes a lot of calculating power, we noticed that training the models just takes very long. This is why we decided to use Google Collaborate in order to gain access to the Google cloud GPUs.
We used this to pretrain some models to play around with them.
If you want to have a look into it you can access it via this link:

<https://colab.research.google.com/drive/1N4JKD_XUWReva8zyj69Uuy0RFmNdQbQi?usp=sharing>

Since this is a public repository, I disabled the ability to change stuff in the collab.

Inside this folder you can find two folders named after their stock.
For each stock we have prepared 6 models.
3 for predicting 1 day ahead and 3 for predicting 15 days ahead and for both we have 50, 500, 1000 epochs.

LS = Lookup_Step = how many days in the future we want to predict

E = Epochs = how often do we train our model

# How to use the code
### Import requirements
You may need to install some of the libaries/modules that are used in this project.
Please check if your python environment misses one of the following requirements:
- tensorflow
- sklearn
- numpy
- pandas
- matplotlib
- yahoo_fin
- seaborn

They can be installed via pip or conda.

### Training a new model

If you want to train a new model you have to open up the file: **Stock_prediction.ipynb**
Now, if you scroll down to the first cell after the function definitions you can see all the parameters that you are able to change.
After you have changed the parameters to your liking you can just hit "run all".
At the bottom of the notebook you can find the results and a plot.
In the "logs" folder you can find the logs of your training.
And in the "model_weights" folder you can find the model weights of your trained model.

### Getting results from a pretrained model

If you want to test a model, you have to open up the file: **Model_tester.ipynb**
In the cell that comes after the imports you can see the parameters.
In order to test a model the parameters have to be the same as in the model.
You can see the parameters in the name of the model file.
For the models in the "pretrained_models" folder you only need to change the "ticker" and the "Lookup_step".
After these changes were made, you can press "run all".
