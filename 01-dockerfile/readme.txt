What is Dockerfile?
- Dockerfile is like a blueprint is a simple text file with instruction to build a image

Why we need Docker?
-  Docker is to improve the portability and scalability of our applications. By using Docker containers, 
   developers can ensure that their applications work consistently across different machines, regardless of the software and hardware configurations.
   
  Example Senario
   - Imagine a team of developers working on a web application that runs on a specific version of a programming language, database, and other dependencies. 
     Without Docker, each developer would need to set up their own development environment, which can be time-consuming and error-prone. 
     Additionally, when the application needs to be deployed to a production server, there is always a risk of differences between the development and production environments leading to deployment issues.
  



Here are the most common instructions used in a Dockerfile: 

1. FROM - specifies the base image for the container
2. RUN - executes commands in the container
3. COPY - copies files from the host machine to the container
4. WORKDIR - sets the working directory for the container
5. EXPOSE - exposes a port from the container to the host machine
6. ENV - sets environment variables in the container
7. CMD - specifies the default command to run when the container starts
8. VOLUME - creates a mount point for volumes in the container
9. MAINTAINER - specifies the maintainer of the Dockerfile
10. LABEL - adds metadata to the image

11. ADD - use to add files to the container being built.

Here is an example of a Dockerfile using these instructions:

```
FROM ubuntu:latest
RUN apt-get update && apt-get install -y python3
WORKDIR /app
COPY . /app
ENV PORT=5000
EXPOSE 5000
CMD ["python3", "app.py"]
VOLUME /data
MAINTAINER John Doe
LABEL version="1.0" description="My Dockerfile"
```

This Dockerfile installs Python 3, copies the current directory into the container, sets an environment variable, exposes a port, sets a default command, creates a volume mount, specifies 
a maintainer, and adds a label.