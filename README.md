# Overview
This repo sets up the most basic local infrasturcture possible to demonstrate sending and recieving Kafaka data streams between Jupyter Notebooks.


## This Demo Uses the Following:
- [Docker Compose](https://docs.docker.com/compose/) to create Kafka, Zookeeper, and Jupyter Lab services.  See `docker-compose.yml` for details.
- [jupyter/datascience-notebook](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-datascience-notebook) to mimic AWS SageMaker with notebook related data saved locally in "lab/notebooks".  Within this, we set up Jupyter's Notebooks to mimic Kafka Producers and Consumers. 


## Build and Start the Demo
- Clone this repo.
- Open a terminal and navigate to the *kafka-in-jupyter-lab* folder.
- Run `docker-compose up` to build and start the Kafka Broker (with Zookeeper) and Jupyter Lab.
    - Your terminal will now show Kafka is waiting for events.
- Open Jupyter Lab at http://localhost:8888/lab.


## Notebooks:
- When opening Jupyter Lab you will see 4 Notebooks total:
    - 2 Notebooks for "main_topic": 1 Producer, 1 Consumer
    - 2 Notebooks for "other_topic": 1 Producer, 1 Consumer 
- These Notebooks are intended to allow you to verify that publishing data to one topic does not interfere with another.


## Using the Demo
- Run all cells in the Consumer notebooks first.  The last cell will be listening for incomming data when you see "Topic unknown, creating main_topic topic".
- Run the all cells in the Producer notebooks.  You will see data being sent from the Producer and that same data being recieved by the Consumer.
- ...and now we can do stuff with the data!


## Shut Down and Clean-up
- Shut evertying down with *control + c*.
- Delete the *kafka-in-jupyter-lab* container in Docker.

