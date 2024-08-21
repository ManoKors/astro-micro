---
title: How to check your pulled docker images
description: 
date: 
draft: false
tags:
  - docker
---
When you pull a Docker image using the `docker pull` command, the image isn't downloaded to your working directory, which is why you don’t see any new files or directories when you list the contents of your current directory.
## Where is the Docker Image Stored?

Docker images are stored in Docker’s storage, not in your home directory or any other directory you might be navigating in. On a typical Linux system (like your Raspberry Pi), Docker images are stored in:

**Docker's Storage Location:** `/var/lib/docker`
Within this directory, Docker organizes images, containers, volumes, and other data.

## Checking the Pulled Image

To see the Docker image you just pulled, you can use the following command:

```bash
docker images
```

This will list all Docker images that have been downloaded to your system, including `jupyterhub/singleuser`.

### Example Output:

```bash
REPOSITORY                 TAG       IMAGE ID       CREATED        SIZE
jupyterhub/singleuser      latest    <image-id>     <date>         <size>
```

### Managing Docker Images and Containers

If you want to run a container based on this image, you use the `docker run` command, as described earlier. The Docker engine will handle everything related to where the image is stored and how it is run.

So, even though you don’t see anything in your current directories after pulling the image, the image has indeed been stored in Docker's managed storage.