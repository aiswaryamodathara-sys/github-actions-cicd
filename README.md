# CI/CD Pipeline for a Static Website

A static HTML website that is automatically tested, built into a Docker
image, and published to Docker Hub on every push to `main`.

## Tech Stack

- HTML
- Docker and Nginx
- GitHub Actions
- Docker Hub

## How It Works

1. Push code to the `main` branch
2. GitHub Actions starts automatically
3. The pipeline checks out the code, builds, and tests it
4. It logs in to Docker Hub
5. It builds the Docker image and pushes it to Docker Hub

If any step fails, the later steps do not run, so a broken version is never published.

## Project Structure

```
.github/workflows/ci-cd.yml   Pipeline definition
Dockerfile                    Nginx image for the site
index.html                    Website content
```

## Run Locally

```bash
docker pull aiswaryamodathara/my-website:latest
docker run -d -p 8080:80 --name mywebsite aiswaryamodathara/my-website:latest
```

Open http://localhost:8080 in your browser.

## Required GitHub Secrets

- `DOCKERHUB_USERNAME`: your Docker Hub username
- `DOCKERHUB_TOKEN`: a Docker Hub access token

## Docker Hub

https://hub.docker.com/r/aiswaryamodathara/my-website
