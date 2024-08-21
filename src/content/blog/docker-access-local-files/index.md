---
title: 
description: 
date: 2023-12-12
draft: false
---

To access files from a folder in your `~/docker` directory inside a Docker container, you can use Docker's **volume mounting** feature. This allows you to map a directory on your host system (like `~/docker`) to a directory inside the Docker container. Here’s how you can do it:

### Step 1: Run the Docker Container with a Volume Mount

Assume you want to mount the `~/docker` directory to `/home/jovyan/work` inside the container (a typical working directory in Jupyter containers).

You can run the container with the following command:

bash

Code kopieren

`docker run -p 10000:8888 -v ~/docker:/home/jovyan/work jupyterhub/singleuser`

### Explanation:

- **`-p 10000:8888`**: Maps port `8888` inside the container to port `10000` on your host.
- **`-v ~/docker:/home/jovyan/work`**: Mounts the `~/docker` directory on your host to `/home/jovyan/work` inside the container.
- **`jupyterhub/singleuser`**: The image you are running.

### Step 2: Access the Files in Jupyter

1. **Start the Container**: The above command starts the container, exposing Jupyter on `http://localhost:10000`.
    
2. **Access Jupyter in Browser**: Open your web browser and go to `http://localhost:10000`.
    
3. **Navigate to the Mounted Directory**: Inside Jupyter, navigate to the `/home/jovyan/work` directory. You should see the contents of your `~/docker` directory here.
    

### Step 3: Work with Your Files

- You can now create, edit, and run notebooks or other files directly from your `~/docker` directory through the Jupyter interface.
- Any changes you make inside the `/home/jovyan/work` directory in the container will be reflected in the `~/docker` directory on your Raspberry Pi, and vice versa.

### Summary:

- **Host Directory**: `~/docker`
- **Container Directory**: `/home/jovyan/work`
- **Access URL**: `http://localhost:10000`

This setup allows seamless interaction with your files on your host system from within the Docker container.