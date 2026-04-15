# Docker-Assignment
# Part 1: Application Setup 
<br>Run the  flask app https://github.com/mohanDevOps-arch/flask_Practice.git
<br>Run it locally first 

# Part 2: Dockerfile Creation 
<br>Write a Dockerfile to containerize the application.
<br>Requirements:
<br>Use an official Python base image.
<br>Copy application code into the container.
<br>Install required dependencies (requirements.txt).
<br>Expose the correct port.
<br>Define the correct CMD or ENTRYPOINT.

# Part 3: Docker Image & Container
<br>Build the Docker image.
<br>Run the container and verify:
<br>Application is accessible in browser 
<br>Use appropriate naming conventions.

# Part 4: Docker Compose 
<br>Create a docker-compose.yml file.
<br>Use it to run the application.

# Part 5: Best Practices & Optimization 
<br>Use .dockerignore.
<br>Minimize image size.
<br>Use proper tagging.
<br>Follow a clean and readable structure.

=============================================================================
=============================================================================
# Push Docker Image to Docker Hub

This guide explains how to push a Docker image to Docker Hub step by step.

---

## Prerequisites

- Docker installed
- Docker Hub account
- Image already built locally

---

## Step 1: Login to Docker Hub

```bash
docker login
```

Enter:
- Username
- Password or Access Token

---

## Step 2: Check Local Images

```bash
docker images
```

Example output:

```
REPOSITORY                      TAG       IMAGE ID
flask_practice-flask-app        latest    abc123
```

---

## Step 3: Tag the Image

Format:
```
<docker-username>/<repository>:tag
```

Example:

```bash
docker tag flask_practice-flask-app avinashsain65/flask-app:latest
```

---

## Step 4: Create Repository on Docker Hub

1. Go to: https://hub.docker.com  
2. Click **Create Repository**
3. Name: `flask-app`
4. Visibility: Public or Private
5. Click **Create**

---

## 🔹 Step 5: Push Image

```bash
docker push avinashsain65/flask-app:latest
```

---

## Success

Your image is now available at:

https://hub.docker.com/r/avinashsain65/flask-app

---

## Verify

```bash
docker pull avinashsain65/flask-app:latest
```

---

## Common Errors

### access denied
```bash
docker login
```

---

### tag does not exist
```bash
docker images
```
Make sure image name is correct.

---

## Run Image Anywhere

```bash
docker run -d -p 2050:2050 avinashsain65/flask-app:latest
```

---

## Best Practice (Versioning)

```bash
docker tag flask_practice-flask-app avinashsain65/flask-app:v1
docker push avinashsain65/flask-app:v1
```

---

## Summary

```bash
docker login
docker images
docker tag <image> <username>/<repo>:latest
docker push <username>/<repo>:latest
```

---

Done! Your Docker image is now live on Docker Hub.

