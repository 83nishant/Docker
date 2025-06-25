# Docker Projects Collection

This repository contains a collection of Docker-based projects in various languages and frameworks. Each project is organized in its own folder with the necessary files to build and run using Docker.

## Repository Structure

```
/
├── distroless-python/
├── java-app/
├── portfolio/
└── README.md
```

## Project Folders

### 1. [`distroless-python`](https://github.com/83nishant/Docker/tree/main/distroless-python)

A Python application using distroless images for minimal containers.

**Contents:**
- [`Dockerfile`](https://github.com/83nishant/Docker/blob/main/distroless-python/Dockerfile)
- [`Dockerfile-multi`](https://github.com/83nishant/Docker/blob/main/distroless-python/Dockerfile-multi)
- [`README.md`](https://github.com/83nishant/Docker/blob/main/distroless-python/README.md)
- [`app.py`](https://github.com/83nishant/Docker/blob/main/distroless-python/app.py)
- [`requirements.txt`](https://github.com/83nishant/Docker/blob/main/distroless-python/requirements.txt)
- [`run.py`](https://github.com/83nishant/Docker/blob/main/distroless-python/run.py)

### 2. [`java-app`](https://github.com/83nishant/Docker/tree/main/java-app)

A Java application packaged for Docker.

**Contents:**
- [`Dockerfile`](https://github.com/83nishant/Docker/blob/main/java-app/Dockerfile)
- [`README.md`](https://github.com/83nishant/Docker/blob/main/java-app/README.md)
- [`quotes.txt`](https://github.com/83nishant/Docker/blob/main/java-app/quotes.txt)
- [`src/`](https://github.com/83nishant/Docker/tree/main/java-app/src) (Java source files)

### 3. [`portfolio`](https://github.com/83nishant/Docker/tree/main/portfolio)

A portfolio web application, primarily in TypeScript (likely using Next.js or a similar framework).

**Contents (first 10 items):**
- [`Dockerfile`](https://github.com/83nishant/Docker/blob/main/portfolio/Dockerfile)
- [`LICENSE`](https://github.com/83nishant/Docker/blob/main/portfolio/LICENSE)
- [`README.md`](https://github.com/83nishant/Docker/blob/main/portfolio/README.md)
- [`app/`](https://github.com/83nishant/Docker/tree/main/portfolio/app)
- [`community_project_demo_1.png`](https://github.com/83nishant/Docker/blob/main/portfolio/community_project_demo_1.png)
- [`community_project_demo_2.png`](https://github.com/83nishant/Docker/blob/main/portfolio/community_project_demo_2.png)
- [`contexts/`](https://github.com/83nishant/Docker/tree/main/portfolio/contexts)
- [`next.config.mjs`](https://github.com/83nishant/Docker/blob/main/portfolio/next.config.mjs)
- [`package-lock.json`](https://github.com/83nishant/Docker/blob/main/portfolio/package-lock.json)
- [`package.json`](https://github.com/83nishant/Docker/blob/main/portfolio/package.json)
- ...and more (see the full list [here](https://github.com/83nishant/Docker/contents/portfolio?ref=main))

## How to Use

Each project directory contains its own README with details on how to build and run the application using Docker. Generally, you can:

```sh
cd <project-folder>
docker build -t <image-name> .
docker run <image-name>
```
You can also check out my Docker Hub profile: https://hub.docker.com/repositories/nishantdocker83

Refer to each project's README for specific instructions.

---
