
# containerized machine learning application deployed with kubernetes
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/lowryel/ml-microservice-kubernetes/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/lowryel/ml-microservice-kubernetes/tree/master)

* This project is based on predicting housing prices in Boston using a machine learning model. The model is containerized using docker and deployed with kubernetes.

- To run the web app, first pull the image from dockerhub 
    
- Open a terminal and run <docker run -p 5000:80 ml-kubernetes>

- Open another terminal and navigate to make_prediciton.sh file and run <./make_prediction.sh> to make a prediction.
    
- Or you can run <python app.py> in the terminal to start the app and in another terminal, you run <make_prediction.sh> to ,ake a prediction
    
- Another option is to use kubernetes. That is to run <kubectl port-forward ml-kubernetes 5000:80> after pushing the image to a kubernetes cluster

#### This repository contains a Dcokerfile. In it is a base image of python:3.7.3-stretch and the app.py copied to an app directory. Then a command to run the app.

*** Makefile -> A Makefile contains a virtual environment setup, to create a virtual env, an install to upgrade pip and run requirements.txt file to install the dependencies. Another step to lint and run tests on the Dockerfile and the app files

*** Requirements.txt file containing the project dependencies

*** .circleci folder containing a config.yml file for running further tests on the app

*** run_docker.sh contains the commands for containerizing the application and running it.

*** run_kubernetes.sh for running the image

*** make_prediction.sh is run upon container start to make prediction

*** upload_docker.sh file for uploading the image to dockerhub

*** output_txt_files where a sample prediction ouputs from running docker and kubernetes are saved

*** app.py contains flask application which is now containerized
