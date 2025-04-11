# Video Streaming Microservice – Cloud Deployment with Docker

This project demonstrates how to build, push, and run a Dockerized Node.js microservice using **Google Cloud Artifact Registry**.

---

## 📦 1. Requirements

- Docker
- Node.js
- Google Cloud SDK (`gcloud`)
- A Google Cloud project with **Artifact Registry** enabled

## 🚀 2. Build and Push the Docker Image

### Step 1: Authenticate Docker with Artifact Registry

```bash
gcloud auth configure-docker australia-southeast1-docker.pkg.dev
```

### Step 2: Build the Docker Image Locally

```bash
docker build -t video-streaming ./video-streaming
```

### Step 3: Tag the Image for Google Artifact Registry

```bash
docker tag video-streaming australia-southeast1-docker.pkg.dev/sit737-25t1-behbahani-2aa0d06/my-repo/video-streaming:latest
```

### Step 4: Push the Image

```bash
docker push australia-southeast1-docker.pkg.dev/sit737-25t1-behbahani-2aa0d06/my-repo/video-streaming:latest
```

---

## 🧪 3. Run the Container (Test from Cloud Image)

Use this to test the image directly from the Artifact Registry:

```bash
docker run -p 8080:80 -e PORT=80 australia-southeast1-docker.pkg.dev/sit737-25t1-behbahani-2aa0d06/my-repo/video-streaming:latest
```

---

## ⚙️ 4. Using Docker Compose

Local development:

```bash
docker-compose -f docker-compose.yml up
```

---

## 🧹 5. Cleanup

To stop and remove containers:

```bash
docker-compose down
```
