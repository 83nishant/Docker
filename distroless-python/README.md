# Distroless Python

This directory contains resources and files for building and using a **Distroless Python** container image. Distroless images contain only the minimal runtime dependencies required to run an application, without package managers, shells, or any unnecessary files. This makes them smaller, more secure, and production-ready.

---

## Table of Contents

- [What is Distroless Python?](#what-is-distroless-python)
- [Directory Structure](#directory-structure)
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Building the Image](#building-the-image)
- [Running a Python Application](#running-a-python-application)
- [Best Practices](#best-practices)
- [References](#references)

---

## What is Distroless Python?

Distroless Python images are container images that include only the Python runtime and the application dependencies, omitting unnecessary OS components such as package managers, shells, and compilers. This results in:

- **Reduced image size:** Faster downloads and deployments
- **Improved security:** Smaller attack surface due to fewer packages
- **Better performance:** Less bloat for containerized Python apps

---

## Directory Structure

```
distroless-python/
├── Dockerfile
├── requirements.txt
├── app/ (optional)
│   └── your_python_app.py
└── README.md
```

- **Dockerfile:** Instructions to build the distroless Python image.
- **requirements.txt:** Python dependencies for your application.
- **app/**: (Optional) Directory containing your Python application code.
- **README.md:** Project documentation (this file).

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/83nishant/Docker.git
cd Docker/distroless-python
```

### 2. Prepare your application

Place your Python application in the `app/` directory and ensure all dependencies are listed in `requirements.txt`.

### 3. Review the Dockerfile

The Dockerfile typically uses a multi-stage build:

- The **builder stage** installs dependencies.
- The **final stage** copies only the minimal set of files and uses a distroless Python base image.

---

## How It Works

A typical `Dockerfile` for a distroless Python image looks like this:

```dockerfile
# Stage 1: Build dependencies
FROM python:3.12-slim AS builder
WORKDIR /app
COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install --prefix=/install -r requirements.txt

# Stage 2: Distroless
FROM gcr.io/distroless/python3-debian12
WORKDIR /app
COPY --from=builder /install /usr/local
COPY app/ .
CMD ["your_python_app.py"]
```

- The first stage installs Python packages into a temporary location.
- The second stage uses the distroless base image and copies only the installed packages and application code.

---

## Building the Image

Run the following command from the `distroless-python` directory:

```bash
docker build -t my-distroless-python-app .
```

---

## Running a Python Application

To run your application using the distroless image:

```bash
docker run --rm my-distroless-python-app
```

If your app needs environment variables or ports exposed, adjust your `Dockerfile` and run commands accordingly.

---

## Best Practices

- **Pin dependencies** in `requirements.txt` for reproducible builds.
- **Minimize COPY scope** in the Dockerfile to avoid including unnecessary files.
- **Use multi-stage builds** to keep the final image small and clean.
- **Avoid non-essential OS tools** in your image for security and size.

---

## References

- [Distroless Images Documentation](https://github.com/GoogleContainerTools/distroless)
- [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
- [Python Official Docker Images](https://hub.docker.com/_/python)

---

*Feel free to customize this README to match your project’s specifics or add more usage details as needed!*
