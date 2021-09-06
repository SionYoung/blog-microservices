# Posts

A simple web app to demonstrate event-driven microservice architecture

Users can create posts and comments. By doing so, events will be emitted to the event-bus microservice which will then forward the events to any microservices that are interested.

The app contains the following microservices:

    * posts service - for post creation

    * comments service - for comment creation

    * query service - for retrievval of posts and comments from the in-memory db/cache

    * event-bus - receives events from services, and emits them to the subscribers

    * moderation service - look into the content of the comments and check if the content contains any forbidden words. For demonstration purpose only, this app prohibites the word 'orange' in any comments.

# Technologies

- Docker - each microservice runs on Docker

- Kubernetes - orchestrates Docker containers

- Skaffold - automates the development workflow

# Sequence Diagram

## Creates a post

![alt post-creation-sequence-diagram](./post-flow.png "post-creation-sequence-diagram")

## Comments on a post

![alt post-creation-sequence-diagram](./comment-flow.png "post-creation-sequence-diagram")

# Software Architecture

![alt post-creation-sequence-diagram](./architecture.png "post-creation-sequence-diagram")

# How to run

1. To run the app, ensure you have the following tools installed locally

   - Dockers and Kubernetes - https://www.docker.com/products/docker-desktop
   - Skaffold - https://skaffold.dev/docs/install/

2. run `skaffold dev`
