# Docker

Docker is  just simply Linux containers which are a type of virtualization.

## Installation

[Ubutu](https://docs.docker.com/engine/install/ubuntu/)

## Images and Containers

Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

When we ran hello-world we used an official Docker image. We did not have to create the image ourself. But typically we will create custom images and we do so using a Dockerfile. We also will use docker-compose.yml files to run the containers.

## Summary

- Docker is a way to run Linux containers
- Containers are a lightweight alternative to Virtual Machines
- Dockerfile is a list of instructions for creating an image
- Images are made up of one or more layers
- Containers are a running instance of an image docker-compose.yml controls how to run the container
- Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes, but things become more complex with databases

# Library Website and API

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.

## Serializers

A serializer translates data into a format that is easy to consume over the internet, typically JSON, and is displayed at an API endpoint. We will also cover serializers and JSON in more depth in following chapters. For now I want to demonstrate how easy it is to create a serializer with Django REST Framework to convert Django models to JSON.

Make a serializers.py file within our api app.

    (library) $ touch api/serializers.py

Then update it as follows in a text editor.

    #api/serializers.py
    from rest_framework import serializers

    from books.models import Book


    class BookSerializer(serializers.ModelSerializer):
        class Meta:
            model = Book
            fields = ('title', 'subtitle', 'author', 'isbn')

On the top lines we import Django REST Framework’s serializers class and the Book model from our books app. We extend Django REST Framework’s ModelSerializer into a BookSerializer class that specifies our database model Book and the database fields we wish to expose: title, subtitle, author, and isbn.


## References

[Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)

[Django for APIs - Library Website](https://djangoforapis.com/library-website-and-api/)

## Bookmark/Skim

[Beginner’s Guide to Django REST Framework](https://learndjango.com/tutorials/official-django-rest-framework-tutorial-beginners)