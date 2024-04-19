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