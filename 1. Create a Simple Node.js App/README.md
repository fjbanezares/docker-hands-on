## **Docker Intro Lab**

Docker is a platform for developing, shipping, and running applications in containers. Containers are lightweight, portable, and provide a consistent environment for applications from development to production. In this lab, you'll get a brief introduction to Docker and learn how to containerize a simple Node.js application.

### **Table of Contents**

1. What is Docker?
2. Why Use Docker?
3. Docker Architecture
4. Lab Steps
5. Further Reading

---

### **1. What is Docker?**

Docker is a platform that uses OS-level virtualization to deliver software in packages called containers. These containers are isolated from each other and the host system, but they share the same OS kernel. This makes them lightweight and fast compared to traditional virtual machines.

### **2. Why Use Docker?**

- **Consistency**: Docker ensures that your application runs the same regardless of where the container is run.
- **Isolation**: Containers encapsulate all dependencies, ensuring that there are no conflicts.
- **Portability**: You can build a container on your local machine and run it anywhere Docker runs.
- **Microservices**: Docker is ideal for microservices architecture, allowing each service to run in its own container.

### **3. Docker Architecture**

- **Docker Engine**: The runtime that runs and manages containers on a system.
- **Docker Image**: A lightweight, stand-alone, executable software package that includes everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings.
- **Docker Container**: A runtime instance of a Docker image.

---

### **4. Lab Steps**

#### **Step 1**: Create a Simple Node.js App

You've already seen the code for this in the previous section. This will be your application that you'll containerize.

#### **Step 2**: Write a Dockerfile

The Dockerfile is a set of instructions for building a Docker image. It will specify the base image, application code, and dependencies.

#### **Step 3**: Build the Docker Image

Run the following command to build your Docker image:

```bash
docker build -t simple-node-app .
```

#### **Step 4**: Run the Docker Container

```bash
docker run -p 8080:8080 simple-node-app
```

Visit http://localhost:8080 in your browser, and you should see the greeting from the app.

#### **Step 5**: Inspecting Running Containers

To see a list of all running containers:

```bash
docker ps
```
This will display container IDs, image names, port mappings, and other details.

#### **Step 6**: Interacting with the Container

If you wish to execute commands inside a running container:

```bash
docker exec -it [CONTAINER_ID] /bin/sh
```

#### **Step 7**: Stopping and Removing a Container

To stop a running container:

```bash
docker stop [CONTAINER_ID]
```

If you wish to remove a stopped container:

```bash
docker rm [CONTAINER_ID]
```
#### **Step 8**: Removing Docker Images

Over time, as you build and experiment, you may accumulate Docker images. To list all images:

```bash
docker images
```

To remove an image:

```bash
docker rmi [IMAGE_ID]
```

#### **Step 9**: Volume Mapping (Optional)

Docker allows you to map directories from your host machine to the container. This is especially useful during development to reflect code changes without rebuilding the image.

```bash
docker run -p 8080:8080 -v /path/on/host:/path/in/container simple-node-app
```

Any changes you make to the specified directory on your host will reflect in the container in real-time.







