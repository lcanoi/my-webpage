---
title: NLP Prediction Neural Network (MLP) - Machine Learning model for Cemex
subtitle: ""
date: 2021-09-01T03:57:45.024Z
summary: Created a Tensorflow - Python - Keras Neural Network (Multilayer Perceptron) for Cemex, used for predicting an arbitrary value based on Natural Language Processing. 
draft: false
featured: false
tags:
  - 1
  - 3
  - 5
  - 6
  - 7
  - Python
  - React
  - API
  - Neural Network
external_link: ""
# 
image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
---

## Overview
Based in JIRA stories and tasks used for CEMEX Go, I was tasked to develop a Neural Network model to predict the effort for a given story or task (predict how much time would it take CEMEX employees to solve said task)

## Tools
For the creation of this project, the tools that were mainly used were:
+ Python: tensorflow.python.keras for the development of the Multilayer Perceptron Neural Network
+ React.js: for the development of the web app
+ Microsoft SQL Server: for the database
+ Nest: for the API
+ Redux: for state managment
+ Django: Server

## Final Product:
The Final Product is a React.js website with an interface to upload single task or a bulk of tasks (.csv file). When a task is uploaded, the website makes a request with a Nest.js API for our trained Neural Network models hosted in a Django Server. The Keras Neural Network is a Multilayer Perceptron which does Natural Language Processing (NLP) tokenizing the input text, and then runs the values through the model, predicting an output. This output is then returned by the API request and the user gets the resulting prediction of effort for every inputted task. 

# Natural Language Processing - Tokenizer
For NLP I had to tokenize the text from every input. For this I used Pandas for reading .csv files, Tensorflow Keras for the Tokenizer() function, and nltk for a list of stopwords.
With pandas I read specific columns from the .csv files, being the Priority, Severity, Summary and Description of each JIRA task. All of these columns are strings.
With the Keras Tokenizer I transform each of the text into a sequence of integers, using fit_on_texts() and texts_to_sequences() functions.
Additionally, for the Summary and Description columns I apply a formula to remove every stopword from the text, increasing the quality of the Machine Learning training.
Lastly, I join all the tokens and as I use a Multilayer Perceptron which needs an input of an exact shape (size), I run the Keras pad_sequences function with post padding and post truncating of 0s to set every array of input tokens to the same size (=50).
The whole list of input tokens and outputs obtained from the .csv file are then returned to the Neural Network.

# Neural Network - Machine Learning
For the Neural Network I used tensorflow.python.keras to create a Multilayer Perceptron model with regression.
![Game Main Screen](img1.png "Main Screen")
### The Model
+ The model has one initial Masking layer with a mask value of 0 so that it can ignore any 0s that could have been generated in the pad_sequences function at the tokenizer. This initial layer takes an input shape of (50,).
+ The following N layers of the model are multiple Dense layers with relu activation (rectified linear unit). The amount of these layers and neurons in each is modified along the training of different saved models.
+ The last one is Dense layer with a single neuron and linear activation, which is used for regression in the model.
+ I did not use Dropout layers as they are not needed for this solution.
+ The model uses the Adam optimizer from tensorflow keras, and uses the loss function of Mean Squared Error (MSE) as we seek to minimize the difference between our predictions and the actual results.
### Training
+ For the training we first split the input (X) and output (Y) tokens into training and testing data, which is randomly splited as 70% training and 30% testing data.
+ We then create a new model and run model.fit with the training values, for a varying amount of epochs and a batch size of 32. We use the test values for validation.
+ Then we evaluate the model and we get the MSE, the Root MSE and the Mean Absolute Error (MSA), this with the train data and then with the test data to see the accuracy of the trained model and determine if we would work with it or not.
These steps are ran multiple times by a main python training function, saving only the models with the lowest errors in a serialized manner. On completition, the saved models are stored and the variables of the Neural Network are modified, such as number of layers, number of neurons, amount of epochs, train-test data split %, and amount of inputs (in the tokenizer and MLP model). Then the main python training function is ran again with this new configuration.



With this game we ultimately looked for a balance between player skill and Trivia knowledge, keeping the game fun and relevant to the objective Ternium is trying to achieve.

# Web App - React
We created a web app using React.js. We also used Bootstrap for some of the web components. 
![Web App Admin Dashboard](img2.png "Admin Dashboard")
### Functions and Characteristics
+ This web app works with different user roles (admin, master admin, employee), and has different layouts and functions correspondingly (website changes depending on who logs in).
+ Every user has a dashboard, with graphs and data that corresponds to them or to their role.
+ An admin can create a user group of employees to manage them and receive data of their performance with the training game app.
+ An admin can create a new trivia topic for the game, and create a list of questions for it. At any moment an admin can delete or add new ones.
+ There is a leaderboard where users can see the top scorers of the TerniumRUN game.

# Database & API - MySQL & Python
We created a database which contained information about the users and the games. To have the react.js web app connected to everything else we used Redux, which worked with the Python API to connect to the database, doing actions such as storing data in the database and retriving data from it to update the dashboards and other modules in the web app.
![Database Structure](img3.png "Database Structure")
### Uses of the Database and API
+ User creation and authentication. In the web app, a master admin could create a new admin user or employee user with email and password. This information is then saved in the database with an encrypted password, and an authentication token is created there. Then the new user can log in with his new credentials and access his own account in the web app. The user could later change his password which would call a function telling the database to make the change.
+ Game creation. In the web app, an admin could create a game with a set list of questions. This game is then saved in the database with a set game_id, and all of its questions are also saved in their own table keeping that id as a secondary key.
+ Playing a game with specific set of random trivia questions. When selecting a game from the web app, the user would be redirected to the TerniumRUN game with a set game_id. Then the unity game can pull random questions from the database with said game_id (also keeping track of the question_id to not get repeated ones).


