[![abdelino17](https://circleci.com/gh/abdelino17/devopsnano-microservices.svg?style=svg)](https://circleci.com/gh/abdelino17/devopsnano-microservices)

## Operationalize a Machine Learning Microservice API

In this project, I have applied the skills I have acquired in the course (Microservices at Scale using AWS & Kubernetes) operationalize a Machine Learning Microservice API. 

Given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests my abilities to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

My project goal was to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project I had to:
* Test the project code using linting
* Complete a Dockerfile to containerize this application
* Deploy the containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**All the tasks were succesfully done**

---

## Setup the Environment

* Create a virtualenv and activate it:
```
$ make setup
```
* Install the necessary dependencies:
```
$ make install
```

### Running `app.py`

There are three ways for running `app.py`: standalone, with docker and with kubernetes.

#### Standalone
* Run `app.py`
```
$ python app.py
```

#### Running in docker
* Run the `run_docker.sh` which will build the image and will run directly the container
```
$ ./run_docker.sh
```

#### Running in kubernetes
* Run the `run_kubernetes.sh` which will run a pod containing the docker image and will expose it
```
$ minikube start
$ ./run_kubernetes.sh
```

### Files in the directory

* `Dockerfile`: contains the instructions for building the docker image
* `app.py`: contains the Web application code (Flask framework)
* `upload_docker.sh`: upload the image to Docker Hub
* `Makefile`: instructions to group some commands